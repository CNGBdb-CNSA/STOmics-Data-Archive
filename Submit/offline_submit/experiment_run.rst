Experiment and Run
==================

The sequencing reads can be submitted in `the STOmics submission portal <https://db.cngb.org/stportal/submissions/>`_.

The template consists of four parts:

1. **Metadata**, describing associated tissue section, spatial slides, library and sequencing information.

   |  Metadata is required and cannot be left blank.
   |  ``tissue section alias``: multiple values ​​are supported, separated by commas.
   |  ``spatial slide``: multiple values ​​are supported, separated by commas.
   |  ``library name`` is unique for each library.
   |  Fixed value or drop-down options have been given for some fields.

2. **Fastq data files**

 ``.fastq.gz``, ``.fastq.bz2``, ``.fq.gz``, ``.fq.bz2`` are accept for fastq format data files.

 MD5 values for these files should be filled in the template.

 The fastq format is the most commonly submitted.

3. **Aligned data files**

 The file name needs to be suffixed with ``.bam``. The md5 value is also required.

4. **Referenece data files**

 They are not mandatory. Sequence and annotation are supported if available.

 There are two ways to submit them.

 - The reference accession in the public repository. For example, GRCh38.p14, NCBI Homo sapiens Annotation Release 108, GENCODE 40.
 - Custom data file and its md5 value.

 ``.fa``, ``.fasta``, ``.fna``, ``.fna.gz``, ``.fa.gz``, ``.fasta.gz``, ``.fna.bz2``, ``.fa.bz2``, ``.fasta.bz2`` are accept for sequence submission. ``.gff.gz``, ``.gff3.gz``, ``.gtf.gz`` are accept for annotation data submission.

For more detailed explanation for the fields, please refer to the standard below:

.. toctree::
   :maxdepth: 1

   ../../Standard/Experiment&Run

.. important::

   - The number of rows in the template cannot be greater than 800, and the template file cannot be greater than 10MB.
   - All file names and MD5 values ​​cannot be repeated in the template, expect reference data.
   - The data files that have been submitted cannot be submitted again, judged according to the MD5 value.
   - Both fastq data and aligned data must be submitted at least one.
   - If need to modify, the assigned accession numbers can not be modified.
