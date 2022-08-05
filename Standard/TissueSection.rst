Tissue Section
==============

Description of fresh frozen or formalin fixed & paraffin embedded (FFPE) tissue that has undergone a series of treatments. Cryosectioning,  section placement,  staining and visualization, then the tissue is permeabilized for reactions to generate a sequencing-ready library.

\*tissue section alias:

* Definition: An arbitrary and unique identifier for each tissue section.
* Note: The tissue section alias is used to associate Tissue Section with other data objects.

\*tissue section ID:

* Definition: A phrase or short sentence for public display.
* Note: The tissue section ID is for public display of Tissue Section.

\*tissue type:

* Definition: It can be fresh frozen or formalin fixed paraffin embedded (FFPE)  tissues.
* Field Format: text choice
* Expected value: enumeration
* Value syntax: ['fresh frozen (FF)', 'formalin fixed paraffin embedded (FFPE)']

tissue freezing and embedding:

* Definition: Freezing and embedding may be performed simultaneously, or as separate steps. If fresh tissue is available, simultaneous freezing and embedding may be preferred. Thin tissues that are prone to curling may benefit from simultaneous freezing and embedding.
* Field Format: text choice
* Expected value: enumeration
* Value syntax: ['','simultaneously', 'separately']

\*section resource:

* Definition: Describe the section from an anatomical point of view. For human, it may be "sagittal posterior section", "sagittal anterior section", etc. For plant, it may be "transverse section", "tangential longitudinal section", "radial longitudinal section", etc.

slice position:

* Definition: Slice position can be described as the relative position between tissue sections. For example, 355/1000 means that 1000 slices have been cut from the sample, and this tissue section is the 355th slice.
* Example: 355/1000

\*cryosectioning temperature:

* Definition: Cryosectioning temperatures impact tissue section integrity. A temperature setting of –20°C for blade and –10°C for the specimen head is recommended. The temperature settings depend upon the local conditions, tissue types, and the cryostat used and should be optimized based on the quality of resulting tissue sections.
* Field Format: restricted text
* Expected value: measurement value
* Value syntax: {float} {unit} [deg C]
* Preferred unit: degree Celsius, ºC

\*tissue section size:

* Definition: A tissue section of ≤6.5 mm\*6.5 mm is compatible with Visium Spatial slides. A tissue section of ≤130 mm\*130 mm is compatible with Stereo-seq Spatial slides.
* Field Format: restricted text
* Expected value: measurement value
* Value syntax: {float} {unit}\*{float} {unit}
* Preferred unit: millimeter\*millimeter, mm\*mm

\*section thickness:

* Definition: Recommended section thickness for most tissue types is 10 µm. Tissues with higher fat content (e.g., breast tissue) may require thicker sections. Visit the 10x Genomics support website for guidance on section thickness for compatible tissue types (https://support.10xgenomics.com/spatial-gene-expression/sample-prep/doc/specifications-visium-spatial-gene-expression-optimized-tissues).
* Field Format: restricted text
* Expected value: measurement value
* Value syntax: {integer} {unit}
* Preferred unit: micrometer, µm

RIN:

* Definition: RNA Integrity Number (RIN) should be ≥7 and RNA quality assessment should be done before placing the tissue sections on the Spatial slides. Various factors could lead to low RIN scores, such as specific tissue types, diseased or necrotic tissues, sample preparation and handling.
* Field Format: restricted text
* Expected value: measurement value
* Value syntax: {integer}

tissue score:

* Definition: Large tissue samples can be scored during sectioning to generate smaller samples to fit the Capture Areas. Scoring can be done by making a shallow incision (~1 mm deep) on the cutting surface of the tissue with a pre-cooled razor blade.
* Field Format: restricted text
* Expected value: measurement value
* Value syntax: {float}

DV200:

* Definition: DV200 represents the percentage of RNA fragments that are >200 nucleotides in size. Using DV200 to assess FFPE RNA quality and it should be ≥50%.
* Field Format: restricted text
* Expected value: measurement value
* Value syntax: {integer} {unit}
* Preferred unit: percentage, %

\*staining protocol:

* Definition: It can be immunofluorescent staining, DNA fluorescent staining, or histological staining, etc., which is used to obtain spatial information such as RNA fragments distribution, specific molecules distribution via the Spatial slides.
* Field Format: text choice
* Expected value: enumeration
* Value syntax: ['ssDNA staining', 'H&E Staining', 'IF Staining','not determined', 'not applicable', 'not collected', 'not provided', 'restricted access', 'missing']

optimal permeabilization time:

* Definition: For fresh frozen sample, ensure that permeabilization times are optimized for each tissue type. Sub-optimal permeabilization will diminish sensitivity and spatial resolution.
* Field Format: restricted text
* Expected value: measurement value
* Value syntax: {integer} {unit}
* Preferred unit: hours, minutes
