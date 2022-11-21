Analysis
========

STOmics Analysis data must be submitted in `the STOmics submission portal <https://db.cngb.org/stportal/submissions/>`_.

Two popular spatial technologies are supported to submit Spatial Transcriptomic data.

In the template, the purple fields are mandatory, the blue fields are conditional, and the orange fields are optional.

The template is mainly to fill in the name of the relevant data file, the restrictions are as follows.

Stereo-seq
----------

**Spatial positions**: A binary file that records positions of Coordinate identity (CID) on the Stereo chip. ``Stereo chip mask``, suffixed with ``.h5``, ``.bin``.

**Matrices**：``.gem``, ``.gef``, ``.gem.gz``, ``.tsv``, ``.tsv.gz``, ``.txt``, ``.txt.gz`` are accepted for matrix (``raw feature-spot matrix``, ``filtered feature-spot matrix``) submission. The ``filtered feature-spot matrix`` should be provided and its bin size (``bin size (matrix)``) is also needs to be provided.

**Annotation**: Define each cell population according to the marker gene, cell morphology, etc. ``.csv``, ``.txt``, ``.tsv``, ``.csv.gz``, ``.txt.gz``, ``.tsv.gz`` are accepted.

  - There are two types of annotation files.
     - Bin. It is mandatory, and bin size also needs to be provided. (``cell annotation``, ``bin size (annotation)``)
     - Cell bin. It is conditional. It can be left blank or fill in "not applicable". (``cell annotation: cell bin``)

**Images**: images taken by microscope (``microscope slide image``) and its corrected images (``registered image``). ``.jpg``, ``.jpeg``, ``.png``, ``.tiff``, ``.tif``, ``.tiff.gz``, ``.tif.gz`` are accepted. They are optional. Both are required if provided. And "not applicable" is accepted for no information.

**Report**: It is optional. The file name needs to be suffixed with ``.html``.

**MD5 list**: It should be provided and must be named with your submission ID, for example, ``sts*******.md5.list``. MD5 values of all files listed in the template should be provided in this file. The file has two columns, **file name** and **MD5 value** in order, separated by spaces or tabs.

Visium Spatial Gene Expression
------------------------------

**Spatial positions**: ``.csv``, ``.csv.gz`` are accepted, for example, ``tissue_positions_list.csv``.

**Matrices**：``.tar.gz``,``.tar.bz2``, ``.h5`` are accepted for matrix (``raw feature-barcode matrices``, ``filtered feature-barcode matrices``) submission. The ``filtered feature-barcode matrices`` should be provided.

**Annotation**: Define each cell population according to the marker gene, cell morphology, etc. ``.csv``, ``.txt``, ``.tsv``, ``.csv.gz``, ``.txt.gz``, ``.tsv.gz`` are accepted.

**scale factors**: It supported json file, for example, ``scalefactors_json.json``.

**Images**: There are two types of images: ``high resolution tissue image`` and ``low resolution tissue image``. The latter is mandatory.

**Report**: It is optional. The file name needs to be suffixed with ``.html`` or ``.csv``.

**MD5 list**: It should be provided and must be named with your submission ID, for example, ``sts*******.md5.list``. MD5 values of all files listed in the template should be provided in this file. The file has two columns, **file name** and **MD5 value** in order, separated by spaces or tabs.

Relevant instructions
---------------------

For more detailed explanation for the fields, please refer to the standard below:

.. toctree::
   :maxdepth: 1

   ../../Standard/Analysis

.. important::

   - The number of rows in the template cannot be greater than 100, and the template file cannot be greater than 10MB.
   - All file names ​​cannot be repeated in the **Stereo-seq** template, expect ``Stereo chip mask``, ``summary report`` and ``MD5.list``.
   - All file names ​​cannot be repeated in the **Visium spatial** template, expect ``summary report`` and ``MD5.list``.
   - In the MD5 list, MD5 values ​​must be unique, and file name should not be repeated.
   - The data files that have been submitted cannot be submitted again, judged according to the MD5 value.
   - Each row in the **Stereo-seq** template represents a dataset with a unique combination of *tissue section alias + Stereo chip mask + filtered feature-spot matrix + bin size (matrix)*.
   - Each row in the **Visium spatial** template represents a dataset with a unique combination of *tissue section alias + tissue position + filtered feature-barcode matrices*.
