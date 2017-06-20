IGSN Description Metadata is intended to describe the core elements of a specimen. The set of attributes is seen as the "birth certificate" of a specimens and should not contain stateful attributes, where possible. The base document for the development are the notes from the [IGSN Metadata Kernel Workshop](http://igsn.github.io/2015/09/15/IGSN-Metadata-Kernel-Working-Meeting/) held in Los Angeles in September 2015.

# IGSN Descriptive Metadata Elements #


ID    | Element        | A/C          | Occ    | Definition  | Description and instructions
----- | -------------- | ------------ | ------ | ----------- | ----------------------------
&nbsp;| resource       | Root element |        |             | IGSN "birth certificate" for a physical sample, associated feature, or collection 
1     | identifier     | C            | 1      | string      | The  Identifier is a unique string that identifies a resource. IGSN (International GeoSample Number) registered by an IGSN member. Format should be: "10273/foo" 
1.1   | identifierType | A   | 1      |include/identifierType.xsd | currently only type=IGSN is supported |
2     | name           |     |  1...1, not nillable| string | Text string for people to understand what is identified. What would typically be presented in a user interface. Collector's or contributor's local/field name used to name the specimen; not globally unique but typically unique within a set of specimens. |
3     | alternateIdentifiers |  | 0...1 |  | Other formal identifiers for this resource, in addition to the IGSN. |
3.1   | alternateIdentifier | C | 0...n | string |   |
3.1.1 | identifierType | A | 0...1 | include/identifierType.xsd  | Controlled list of identifiers in include/identifierType.xsd |
4     | relatedIdentifiers |  | 0...1 |  | Formal identifiers of resources related to this resource, including the scheme and relationType for each. Link to parent sample, paper, other resource; here we link to a field expedition, journal article, etc. |
4.1   | relatedIdentifier| C | 0...n | string |  |
4.1.1 | identifierType | A | 1 | include/identifierType.xsd | Controlled list of identifiers in include/identifierType.xsd  |
4.1.2 | relationType   | A | 1 | include/relationType.xsd | Controlled list of relation types in include/relationType.xsd |
5     | description    |   | 0...1 | string | Descriptive text about the sample. Free text, anything else that might be useful to know about the sample at its 'birth' |
6     | registrant     |   | 1 | string | registrant (cf. datacite:publisher) - agent (person or organization) that registered the IGSN for this resource |
6.1   | identifier     | C | 0...1 |  | Identification of the registrant |
6.1.1 | identifierType | A | 1 | include/identifierType.xsd | Controlled list of identifiers in include/identifierType.xsd |
6.2   | name           | C | 0...1 |        | Name of the registrant. |
6.3   | affiliation    | C | 0...1 |        | Information about the affiliation of the registrant. |
6.3.1 | identifier     | C | 0...1 |        | Identification of the institutional affiliation of the registrant.  |
6.3.1.1 | identifierType| A | 1    | include/identifierType.xsd | Controlled list of identifiers in include/identifierType.xsd |
6.3.2 | name           | C | 0...1 | string | Name of the institution to which the registrant is affiliated |
7     | collector      |   | 0...1 |        | Collector of the resource. Who collected the sample. Must be nillable. Ideally want an URI for agent; also need name string. Role: Person who gets credit for picking location, getting funding, selecting and extracting the actual object. (1..N, nilable). ODP chief scientist, field geologist. Synthetic sample--experimentalist is collector. 
7.1   | identifier     | C | 0...1 |        | Identification of the sample collector. |
7.1.1 | identifierType | A | 1     | include/identifierType.xsd | Controlled list of identifiers in include/identifierType.xsd |
7.2   | name           | C | 1     | string | Name of the sample collector. |
7.3   | affiliation    | C | 0...1 | string | Name of the institution to which the collector is affiliated |
7.3.1 | identifier     | C | 0...1 | string | Identification of the institutional affiliation of the collector. |
7.3.1.1 | identifierType| A | 1    | include/identifierType.xsd | Controlled list of identifiers in include/identifierType.xsd |
7.3.2 | name           | C | 1     | string | Name of the institution to which the collector is affiliated |
8    | contributors   |   | 0...1 |        | Agents (persons or organizations) that contributed to this resource; investigator, funder, technician, etc. |
8.1  |contributor     | C | 1...n |        |   |
8.1.1 | contributorType | A | 1 | include/contributorType.xsd | Controlled list of identifiers in include/contributorType.xsd |
8.1.1 | identifier    | C | 0...1 | string | Identification of the contributor |
8.1.1.1 | identifierType| A | 1   | include/identifierType.xsd | Controlled list of identifiers in include/identifierType.xsd |
8.1.1.2 | name        | C | 0...1 | string | Name of the contributor |
9    | geoLocations   |   | 0...1 |        | geoLocations (geometry cf. odm2:samplingfeaturegeotype|toponym) - location of the resource, expressed as 2-D geometry and/or place name(s)|
9.1  | geoLocation    | C | 1...1 |        | Where was the sample acquired relative to the Earth (or another celestial body...). Some samples might  be 'non-geographic': mineral specimen, synthetic material.
9.1.1 | geometry      |   | 1     |        | Geospatial geometry element. |
9.1.1.1 | geometryType| A |  1    | include/geometryType.xsd | Controlled list of identifiers in include/geometryType.xsd |
9.1.1.2 | sridType    | A | 0...1 | include/sridType.xsd | Controlled list of identifiers in include/sridType.xsd |
9.1.2 | toponym       |   | 1     | string | Named location
9.1.2.1 | identifier  | C | 0...1 | string | Identification of the geographical location. |
9.1.2.1.1 | identifierType | A | 1 | include/identifierType.xsd | Controlled list of identifiers in include/identifierType.xsd |
9.1.2.2 | name        | C | 0...1 | string | Name of the location. |
10     | resourceTypes |   | 0...1 |        | Describe the basic form of the object that is registered. e.g. polished section; core; pulp; solution, dredge haul in a box, lot, piece of material. Different profiles might have different vocabularies. (1..N, not nillable). Implementation should be a 'scoped' name (vocabulary URI, concept/term URI, label for display). |
10.1   | resourceType  | C | 1     | include/resourceType.xsd | Controlled list of identifiers from include/resourceType.xsd |
10.2   | alternateResourceTypes | C | 0...1 |   |   |
10.2.1 | alternateResourceType| C | 0...n |  string or URI |   |
11     | materials     |   | 0...1 |        | Categorize the material that composes to the sample, e.g. water, granite, tissue. Idea is to create a high-level cross-domain vocabulary. (1..N, nillable). 'lot' type samples (dredge haul, drill core) may have multiple materials included. Material may be categorized under different schemes. Implementation should be a 'scoped' name (vocabulary URI, concept/term URI, label for display). 
11.1   | material      | C | 1...n | include/materialType.xsd | Controlled list of identifiers from include/materialType.xsd |
11.2   | alternateMaterials | C | 0...1 |   | Alternate description of the material in addition to controlled vocabulary |
11.2.1 | alternateMaterial  | C | 1...n | string or URI |  |
12     | collectionMethods |  | 0...1 |   | term to categorize the process through which the sample was acquired as an independent object.
12.1   | collectionMethod | C | 1 | include/methodType | 1...1, nillable, broad classification of instrument/technique used to create or extract this resource - must provide 1 term from SESAR (collectionMethod) vocabulary plus 0-N additional terms from any vocabulary; typically only used for samples |
12.2   | alternatecollectionMethods | C | 0...1 |  | Alternate description of the collection method in addition to controlled vocabulary |
12.2.1 | alternatecollectionMethod | C | 0...1 | string or URI |   |
13     | collectionTime |  | 1...1 | Datetime | Time when  the sample was collected. 1...1, nillable[reason]. May be instant or interval. Has to determine encoding scheme for interchange, e.g. (ISO 19156). Example encodings: YYYY, YYYY-MM, YYYY-MM-DD, YYYY-MM-DDZhh:mm
14     | sampleAccess  |   | 1...1 | accessible, restricted, private  | Indicates whether this resource is available for reuse beyond the original contributor. Typically only used for samples, not sampling features. | 
15     | supplementalMetadata |   | 0...1 |	 | Location (URI) of a supplemental metadata records. These records may be more detailed or in other formats and are provided by the repository. This element was introduced to the high-level descriptive metadata kernel to point to richer and more detailed descriptions without bloating the kernel with many optional elements that mostly go unused.
15.1   | record        | C | 1...n | URI | Any URI pointing to supplemental metadata of the resource |

A = Attribute, C = Child
