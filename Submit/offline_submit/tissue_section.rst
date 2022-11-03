Tissue Section registration
===========================

There are two ways/templates to register Tissue Section. You can choose one to submit your tissue sections.

- One is registered with **sample name**,

  | You can register tissue sections with ``sample name``, which associated a tissue section to a sample.

- The other one is registered with **sample accession**.

  | You can also register tissue sections with ``sample accession`` if you get the sample accession number, which is start with 'STSA'.

In the **Tissue section** template, the green fields are mandatory, and the yellow fields are optional.

- ``tissue section alias``

  | User-defined name for the tissue section. It is unique for each tissue section. It cannot be modified if submitted, because it only used for objects association in the database.

- ``tissue section ID``

  | The tissue section ID is for public display as you want.

- ``tissue type``

  | It need to choose from the following list:
  | ['fresh frozen (FF)', 'formalin fixed paraffin embedded (FFPE)']

- ``tissue freezing and embedding``

  | It need to choose from the following list:
  | ['','simultaneously', 'separately']

- ``section thickness``

  | It is restricted text. The value syntax is '{integer} {unit}'. The unit is usually 'μm'.

- ``RIN``

  | Numbers are allowed. Supporting up to 1 digits after the decimal point.

- ``tissue score``

  | Numbers are allowed. Supporting up to 2 digits after the decimal point.

- ``DV200``

  | It is restricted text. The value syntax is '{integer} {unit}'. The unit is usually '%'.

- ``staining protocol``

  | It need to choose from the following list:
  | ['ssDNA staining', 'H&E Staining', 'IF Staining','not determined', 'not applicable', 'not collected', 'not provided', 'restricted access', 'missing']

  For more detailed explanation for the fields, please refer to the standard below:

  .. toctree::
     :maxdepth: 1

     ../../Standard/TissueSection

.. important::

   - The number of the Tissue Section filled in the template cannot be larger than 100, and the template file cannot be larger than 10MB.
   - ``tissue section alias`` cannot be modified. ``tissue section ID`` can be modified because it is for publication.
   - If need to modify tissue section, the assigned tissue section accession number can not be modified.
