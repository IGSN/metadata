# IGSN Description Metadata #

IGSN Description Metadata is intended to describe the core elements of a specimen. The set of attributes is seen as the "birth certificate" of a specimens and should not contain stateful attributes, where possible. The base document for the development are the notes from the [IGSN Metadata Kernel Workshop](http://igsn.github.io/2015/09/15/IGSN-Metadata-Kernel-Working-Meeting/) held in Los Angeles in September 2015.

# IGSN Descriptive Metadata Elements #

The descriptive metadata schema captures basic characteristics of physical samples and collections.

ID  | Element  | A/C  | Occ  | Definition  | Description and instructions
--- | -------- | ---- | ---- | ----------- | ----------------------------
  | resource| Root element | 1  |  The Identifier is a unique string that identifies a resource. |IGSN (International GeoSample Number) registered by an IGSN member. Format should be: "10273/foo"|
1 | identifier|C |
1.1 | identifierType|A |
2 | name| |  1...1, not nillable|Text string for people to understand what is identified. What would typically be presented in a user interface. Free Text. | 
3 | alternateIdentifiers| |
3.1 | alternateIdentifiers|C|
3.1.1 | identifierType|A|
4 | parentIdentifier| |
4.1 | identifierType| A|
~~5~~ | ~~CollectionIdentifier~~| | |~~the IGSN of a set of related resources to which this resource belongs~~ |
~~5.1~~ | ~~identifierType~~| ~~A~~|
6 | relatedIdentifiers| |
6.1 | relatedIdentifier|C | 0...n|Link to parent sample, paper, other resource. 
6.1.1 | identifierType| A|
6.1.2 | relationType| A|
7 | description|0...1 ||Free text, anything else that might be useful to know about the sample at its 'birth'
8 | registrant| |
8.1 | identifier| C|
8.1.1 | identifierType| A|
8.2 | name| C|
8.3 | affiliation|C|
8.3.1 | identifier| C|
8.3.1.1 | identifierType| A|
8.3.2 | name| C|
9 | collector| | 1...n, nillable|Who collected the sample. Must be nillable. Ideally want an URI for agent; also need name string. Role: Person who gets credit for picking location, getting funding, selecting and extracting the actual object. (1..N, nilable). ODP chief scientist, field geologist. Synthetic sample--experimentalist is collector. 
9.1 | identifier| C|
9.1.1 | identifierType| A|
9.2 | name| C|
9.3 | affiliation|C|
9.3.1 | identifier| C|
9.3.1.1 | identifierType| A|
9.3.2 | name| C|
10 |contributors | |
10.1 |contributor | C|
10.1.1 | contributorType|A |
10.1.1 | identifier| C|
10.1.1.1 | identifierType| A|
10.1.1.2 | name| C|
11 | geoLocations| |  1...1, nillable[reason]| Where was the sample acquired relative to the Earth (or another celestial body...). Some samples might  be ‘non-geographic’: mineral specimen, synthetic material.
11.1 |geoLocation | |
11.1.1 | geometry| |
11.1.1.1 | geometryType|A |
11.1.1.2 | sridType| A|
11.1.2 | toponym| |
11.1.2.1 | identifier| C|
11.1.2.1.1 | identifierType| A|
11.1.2.2 | name| c|
12 | resourceTypes| |1...n, not nillable|Describe the basic form of the object that is registered. e.g. polished section; core; pulp; solution, dredge haul in a box, lot, piece of material. Different profiles might have different vocabularies. (1..N, not nillable). Implementation should be a ‘scoped’ name (vocabulary URI, concept/term URI, label for display).
12.1 | resourceType|C |
12.2 | alternateResourceTypes| C|
12.2.1 | alternateResourceType|C |
13 | materials| |1...n, nillable|Categorize the material that composes to the sample, e.g. water, granite, tissue. Idea is to create a high-level cross-domain vocabulary. (1..N, nillable). ‘lot’ type samples (dredge haul, drill core) may have multiple materials included. Material may be categorized under different schemes. Implementation should be a ‘scoped’ name (vocabulary URI, concept/term URI, label for display). 
13.1 | material|C |
13.2 | alternateMaterials| C|
13.2.1 | alternateMaterial| C|
14 | collectionMethods| |1...1, nillable|term to categorize the process through which the sample was acquired as an independent object.
14.1 | collectionMethod|C |
14.2 | alternatecollectionMethods| C|
14.2.1 | alternatecollectionMethod|C |
15 | collectionTime| |  1...1, nillable[reason]|When was the sample collected. instant or interval. have to determine encoding scheme for interchange, eg.(ISO 19156) (1...1, nillable[reason]). (need specifiction of sample dateTime encoding). YYYY, YYYY-MM, YYYY-MM-DD, YYYY-MM-DDZhh:mm
16 | sampleAccess| |
17 | supplementalMetadata| |0...n, nillable|	Location (URL) of a supplemental metadata records. These records may be more detailed or in other formats and are provided by the repository. This element was introduced to the high-level descriptive metadata kernel to point to richer and more detailed descriptions without bloating the kernel with many optional elements that mostly go unused.
17.1 | record|C |

A = Attribute, C = Child
