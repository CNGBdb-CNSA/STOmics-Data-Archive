STOmics Sample
==============

Description of biological source material; each physically unique specimen should be registered as a single sample with a unique set of attributes.

\*sample name :

* Definition: An arbitrary and unique identifier for each sample.
* Note: The sample name is used to associate Sample with other objects.

\*sample title :

* Definition: The sample title for public display is a short, preferably a single sentence, description of the sample.
* Note: The sample title is for public display of Sample.

\*taxonomy ID :

* Definition: The Taxonomy ID indicates the taxonomic classification of the sample (e.g. 9606 for human).

\*organism :

* Definition: The most descriptive organism name for this sample (to the species, if relevant).

\*isolate :

* Definition: Identification or description of the specific individual from which this sample was obtained.

\*tissue ：

* Definition: Type of tissue the sample was taken from.

\*sex :

* Definition: Physical sex of sampled organism.
* Field Format: text choice
* Expected value: enumeration
* Value syntax: ['male', 'female', 'pooled male and female', 'neuter', 'hermaphrodite', 'intersex', 'not determined', 'not applicable', 'not collected', 'not provided', 'restricted access', 'missing']

\*age :

* Field Format: restricted text
* Expected value: measurement value
* Value syntax: {float} {unit}
* Preferred unit: centuries,days,decades,hours,minutes,months,seconds,weeks,years

\*development stage :

* Definition: Developmental stage at the time of sampling.

\*biomaterial provider :

* Definition: Name and address of the lab or PI, or a culture collection identifier.
* Field Format: free text

\*geographic location :

* Definition: Geographical origin of the sample; use the appropriate name from this list http://www.insdc.org/documents/country-qualifier-vocabulary. Use a colon to separate the country or ocean from more detailed information about the location, eg "China:Shenzhen" or "China:Hebei:Baoding".
* Field Format: restricted text
* Expected value: country or sea name (INSDC or GAZ):region(GAZ):specific location name
* Value syntax: {term}:{term}:{text}
* Example: Germany:Sylt:Hausstrand

\*collection date :

* Definition: The time of sampling, either as an instance (single point in time) or interval. date/time ranges are supported by providing two dates from among the supported value formats, delimited by a forward-slash character,e.g., 2017/2019; In case no exact time is available, the date/time can be right truncated i.e. all of these are valid times: 2008-01-23T19:23:10+00:00; 2008-01-23T19:23:10; 2008-01-23; 2008-01; 2008; Except: 2008-01; 2008 all are ISO8601 compliant.
* Field Format: restricted text
* Expected value: date and time
* Value syntax: {timestamp}
* Example: 2017/2019, 2008-01-23T19:23:10+00:00, 2008-01-23T19:23:10, 2008-01-23, 2008-01, 2008

collected by :

* Definition: Name of persons or institute who collected the sample.
* Field Format: free text

latitude and longitude :

* Definition: The geographical coordinates of the location where the sample was collected. Specify as degrees latitude and longitude in format "d[d.dddd] N|S d[dd.dddd] W|E", eg, 38.98 N 77.11 W
* Field Format: restricted text
* Expected value: decimal degrees
* Value syntax: {float} {float}
* Example: 38.98 N 77.11 W

strain :

* Definition: Microbial or eukaryotic strain name.

breed :

* Definition: breed name - chiefly used in domesticated animals or plants.

cultivar :

* Definition: cultivar name - cultivated variety of plant.

ecotype :

* Definition: A population within a given species displaying genetically based, phenotypic traits that reflect adaptation to a local habitat, e.g., Columbia

isolation source :

* Definition: Describes the physical, environmental and/or local geographical source of the biological sample from which the sample was derived.

disease :

* Definition: List of diseases diagnosed; can include multiple diagnoses. the value of the field depends on host; for humans the terms should be chosen from DO (Disease Ontology), free text for non-human. For DO terms, please see https://www.ebi.ac.uk/ols/ontologies/symp
* Field Format: free text
* Expected value: disease name or DO
* Value syntax: {term}

disease stage :

* Definition: Stage of disease at the time of sampling.

cell line :

* Definition: Name of the cell line.

cell type :

* Definition: Type of cell of the sample or from which the sample was obtained.

treatment :

description :

* Definition: Description of the sample.
