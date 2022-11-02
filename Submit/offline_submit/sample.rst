Sample Registration
===================

In the **STOmics sample** template, the green fields are mandatory, and the yellow fields are optional.

- ``sample name``

 | User-defined name for the sample. It is unique for each sample. It cannot be modified if submitted, because it only used for objects association in the database.

- ``sample title``

 | The sample title is for public display as you want.

- ``taxonomy ID`` and ``organism``

 | Species information for your research subjects. The ``taxonomy ID`` and ``organism`` should be consistent with each other. For example, the ``taxonomy ID`` is ``10090``, and the ``organism`` is ``Mus musculus`` for the house mouse, which can be retrived `here <https://db.cngb.org/search/organism/10090/>`_.

- ``sex``

 | It need to choose from the following list:
 | ['male', 'female', 'pooled male and female', 'neuter', 'hermaphrodite', 'intersex', 'not determined', 'not applicable', 'not collected', 'not provided', 'restricted access', 'missing']

- ``age``

 | It is restricted text. The value syntax is '{float} {unit}'.

- ``geographic location``

 | It is restricted text. It expected to fill in country or sea name (INSDC or GAZ):region(GAZ):specific location name. The value syntax is '{term}:{term}:{text}', eg. "China:Shenzhen" or "China:Hebei:Baoding".

- ``collection date``

 | It is restricted text. It expected to fill in date and time, for example, 2008-01-23T19:23:10+00:00; 2008-01-23T19:23:10; 2008-01-23; 2008-01; 2008; 2017/2019.
 | The value can not be a future time.

- ``latitude and longitude``

 | It is restricted text. Specify as degrees latitude and longitude in format "d[d.dddd] N\|S d[dd.dddd] W\|E", eg, 38.98 N 77.11 W.

For more detailed explanation for the fields, please refer to the standard below:

.. toctree::
   :maxdepth: 1

   ../../Standard/Sample

.. important::

   - The number of the Sample filled in the template cannot be larger than 100, and the template file cannot be larger than 10MB.
   - ``sample name`` cannot be modified. ``sample title`` can be modified because it is for publication.
   - Each of your samples must have differentiating information (excluding ``sample name``, ``sample title``, and ``description``). This check was implemented to encourage submitters to include distinguishing information in their samples. If it is necessary to represent true biological replicates as separate Samples, you might add an 'aliquot' or 'replicate' attribute, e.g., 'replicate = biological replicate 1', as appropriate.
   - The ``taxonomy ID`` and ``organism`` should be consistent with each other.
   - ``geographic location`` and ``latitude and longitude`` (if filled in) should be consistent with each other.
   - If need to modify sample, the assigned sample accession number can not be modified.
