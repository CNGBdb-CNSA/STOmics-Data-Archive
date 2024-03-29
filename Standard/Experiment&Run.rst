Experiment & Run
=================

A description of tissue-sample-specific sequencing library, instrument and sequencing methods. Runs describe the files that belong to the previously created experiments.

Metadata
--------

\*spatial slide:

* Definition: slide serial number.

\*experiment title:

* Definition: Short description that will identify the dataset on public pages. A clear and concise formula for the title would be like: {methodology} of {organism}: {sample info} e.g. RNA-Seq of mus musculus: adult female spleen

\*library name:

* Definition: Short unique identifier for the sequencing library. Each library name MUST be unique!

\*library strategy:

* Definition: Sequencing technique intended for the library.
* Value syntax: ['STOmics_RNA']

\*library source:

* Definition: The library source specifies the type of source material that is being sequenced.
* Value syntax: ['TRANSCRIPTOMIC SPATIAL']

\*library selection:

* Definition: Method used to enrich the target in the sequence library preparation.
* Value syntax: ['cDNA barcoded with spatial and molecular identifier(FF)', 'ligated probes extended with spatial and molecular identifier(FFPE)']

\*sequencer:

* Value syntax: ['DNBSEQ-G50(MGISEQ-200)','DNBSEQ-G400(MGISEQ-2000)','DNBSEQ-G400 FAST','DNBSEQ-T1','DNBSEQ-T5','DNBSEQ-T7','DNBSEQ-T10','DNBSEQ-T10×4','DNBSEQ-T20','DNBSEQ-T20×2','Illumina NovaSeq 6000','Illumina HiSeq 4000','Illumina HiSeq 3000','Illumina HiSeq 2500','Illumina NextSeq 500','Illumina NextSeq 550','Illumina NextSeq 2000','Illumina MiSeq','Illumina iSeq 100']

\*library layout:

* Definition: The library layout specifies whether to expect single, paired, or other configuration of reads. In the case of paired reads, information about the relative distance and orientation is specified.
* Value syntax: ['paired']

\*nominal size:

* Definition: The average insert size for paired reads.
* Value syntax: {integer}

\*spot layout:

* Definition: a spot descriptor that describes the position of the technical reads (e.g. Spatial barcode/CID, UMI/MID).
* Example: Spatial barcode: read1 1-25; UMI: read1 41-50

Data file
---------

FASTQ files
~~~~~~~~~~~

FASTQ format is a text-based format for storing both a biological sequence (usually nucleotide sequence) and its corresponding quality scores. This is the most widely used format in sequence analysis as well as what is generally delivered from a sequencer.

Each sequence requires at least 4 lines:

  | @<identifier and expected information>
  | <sequence>
  | +<identifier and other information OR empty string>
  | <quality>

* Identifier and expected information: text string terminated by white space.
* fastq sequence should contain standard base calls (ACTGactg) or unknown bases (Nn) and can vary in length.
* Qualities options:

  +-----------------------------------+-------------------------------------------------+
  | Decimal-encoding, space-delimited | [0-9]+ | <quality>\s[0-9]+                      |
  +-----------------------------------+-------------------------------------------------+
  | Phred-33 ASCII                    | [\!\"\#\$\%\&\'\(\)\*\+,\-\.\/0-9:;<=>\?\@A-I]+ |
  +-----------------------------------+-------------------------------------------------+
  | Phred-64 ASCII                    | [\@A-Z\[\\\]\^_`a-h]+                           |
  +-----------------------------------+-------------------------------------------------+

  Quality string length should be equal to sequence length.

Paired-end FASTQ
^^^^^^^^^^^^^^^^

Paired-end data submitted in FASTQ format should be submitted as separate files for forward and reverse reads, in which the reads are in the same order.

BAM files
~~~~~~~~~

BAM is a compressed binary version of the Sequence Alignment/Map (SAM) format (see `SAMv1 <https://samtools.github.io/hts-specs/SAMv1.pdf>`_) that is used to represent aligned sequences.

The BAM format file generated by STOmics Analysis Workflow (`SAW <https://github.com/BGIResearch/SAW>`_ can be downloaded at https://hub.docker.com/r/stomics/saw) is more suitable for reading, writing and storage of spatial transcriptome big data.

SAW **mapping** BAM adds custom tags in the BAM optional field to record reads coordinates, CID and MID information. **count** BAM adds annotation information in the tag field. Custom tags are described in the table below.

+--------+------------------------------------------------------------------------------------------+
| Tag    | Description                                                                              |
+========+==========================================================================================+
| Cx:i   | The x coordinate of CID.                                                                 |
+--------+------------------------------------------------------------------------------------------+
| Cy:i   | The y coordinate of CID.                                                                 |
+--------+------------------------------------------------------------------------------------------+
| UR:Z   | The hexadecimal representation of uncorrected binary-encoded MID.                        |
+--------+------------------------------------------------------------------------------------------+
| XF:Z   | Mapping region on the reference genome. Valid value: 0=EXONIC, 1=INTRONIC, 2=INTERGENIC. |
+--------+------------------------------------------------------------------------------------------+
| GE:Z   | Annotated gene name.                                                                     |
+--------+------------------------------------------------------------------------------------------+
| GS:Z   | ‘+’ or ‘-’, indicating forward/reverse strand respectively.                              |
+--------+------------------------------------------------------------------------------------------+
| UB:Z   | The hexadecimal representation of count corrected binary-encoded MID.                    |
+--------+------------------------------------------------------------------------------------------+

Example of **mapping** BAM:

 | E100026571L1C009R00301275185 16 1 3000095 255 26M121066N74M * 0 0 GGCTTTTTTTTTTTTTTTTTTTTTTTTTTTCTAAATATTGGGTTTTATTAGCACCATGATAACTGTAT
 | ATTAATTTGCACTGACTGTCATAACAAAATACG+:GFFGGFGFFGFFGFGGFFGFFFFFCFGFCFG
 | GGFGGFGFFFFGGFGGFGFFFGGFFGFFFGFGFGFFGFFGFGFFFFGFFFFFFFFGGFFGGFFGEF
 | NH:i:1 HI:i:1 AS:i:88 nM:i:0 Cx:i:4826 Cy:i:11598 UR:Z:6FA29

Example of **count** BAM:

 | E100026571L1C002R00703943265 1040 1 3082766 255 11M132671N89M * 0 0 CTGCTGCAGCTTTTTTTTCTTTGAGATTTATTTTTATGCTATGTGTATGGGTATTTTGCCTGCATAT
 | ATGTCTATGCACCATGTGTGTGCAGTGCTTGAGFFFFFECGFDCFGDGDFEE\@EEGIBFGGCGFFGA
 | CGFCGFFDGDGFFFFFFEGCDFCGFFGG\@FFF=EFFDGGGGGFDGFFFGGGFGFFGGGFFGGGDFG
 | NH:i:1 HI:i:1 AS:i:88 nM:i:0 Cx:i:7767 Cy:i:18052 UR:Z:7AE49 XF:i:0 GE:Z:Xkr4 GS:Z:- UB:Z:79E49

Reference files
~~~~~~~~~~~~~~~

Reference fasta
^^^^^^^^^^^^^^^

FASTA format is the most basic format for reporting a sequence. A sequence in FASTA format begins with a single-line description, followed by lines of sequence data. The definition line (defline) is distinguished from the sequence data by a greater-than (>) symbol at the beginning. The word following the ">" symbol is the identifier of the sequence, and the rest of the line is the description (optional).

**Example**:

  | >gi|129295|sp|P01013|OVAX_CHICK GENE X PROTEIN (OVALBUMIN-RELATED)
  | QIKDLLVSSSTDLDTTLVLVNAIYFKGMWKTAFNAEDTREMPFHVTKQESKPVQMMCMNNSFNVAT
  | LPAEKMKILELPFASGDLSMLVLLPDEVSDLERIEKTINFEKLTEWTNPNTMEKRRVKVYLPQMKIEEKY
  | NLTSVLMALGMTDLFIPSANLTGISSAESLKISQAVHGAFMELSEDGIEMAGSTGVIEDIKHSPESEQFR
  | ADHPFLFLIKHNPTNTIVYFGRYWSP

Reference annotation
^^^^^^^^^^^^^^^^^^^^

A 9-column annotation file conforming to the GFF, GFF3 or GTF specifications can be used for reference annotation submission.

General Feature Format (GFF) is a tab-delimited text file that holds information any and every feature. Everything from CDS, microRNAs, binding domains, ORFs, and more can be handled by this format. It consists of one line per feature, each containing 9 columns of data, plus optional track definition lines.

There have been many variations of the original GFF format and many have since become incompatible with each other. The latest accepted format (GFF3) has 9 required fields, though not all are utilized (either blank or a default value of ‘.’).

The Gene transfer format (GTF) is a file format used to hold information about gene structure. It is a tab-delimited text format based on the general feature format (GFF), but contains some additional conventions specific to gene information.

The basic characteristics of the file formats are described at:

* **GFF**: https://github.com/The-Sequence-Ontology/Specifications/blob/master/gff3.md
* **GTF**: http://mblab.wustl.edu/GTF22.html
