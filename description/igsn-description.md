# IGSN core metadata
Markdown documentation created by [pyLODE](http://github.com/rdflib/pyLODE)


## Metadata
* **IRI**
  * `http://schema.igsn.org/description`
* **Creators(s)**
  * <a href='https://orcid.org/0000-0002-3884-3420'>Simon J D Cox, CSIRO</a>
* **Created**
  * 2020-02-18
* **Imports**
  * <a href="http://www.w3.org/ns/dcat">http://www.w3.org/ns/dcat</a>
  * <a href="http://www.w3.org/ns/ssn/ext">http://www.w3.org/ns/ssn/ext</a>
  * <a href="http://purl.org/dc/terms/">dcterms:</a>
  * <a href="http://www.opengis.net/ont/geosparql">http://www.opengis.net/ont/geosparql</a>
  * <a href="http://www.w3.org/ns/ssn/">http://www.w3.org/ns/ssn/</a>
* **Ontology Source**
  * <a href="igsn-description.ttl">RDF (turtle)</a>
### Description
<p>An RDF-based implementation of the IGSN core metadata model, utilizing elements from commonly-used RDF vocabularies in preference to creating new elements</p>

## Table of Contents
1. [Classes](#classes)
1. [Object Properties](#objectproperties)
1. [Datatype Properties](#datatypeproperties)
1. [Namespaces](#namespaces)  


## Overview
![IGSN Resource overview](./images/IGSN-resource-description.png)
**Figure 1:** Ontology overview  
## Classes
[Collection](#Collection),
[Feature](#Feature),
[Resource](#Resource),
[Sample](#Sample),
### Collection <sup>c</sup>
Property | Value
--- | ---
IRI | `http://schema.igsn.org/description#Collection`
Super-classes |<a href="#Resource">igsn:Resource</a><sup class="sup-c" title="class">c</sup><br />
### Feature <sup>c</sup>
Property | Value
--- | ---
IRI | `http://schema.igsn.org/description#Feature`
Super-classes |<a href="#Resource">igsn:Resource</a><sup class="sup-c" title="class">c</sup><br />
### Resource <sup>c</sup>
Property | Value
--- | ---
IRI | `http://schema.igsn.org/description#Resource`
Description | IGSN "birth certificate" for a physical sample, associated feature, or collection
Super-classes |<a href="http://www.w3.org/ns/sosa/FeatureOfInterest">http://www.w3.org/ns/sosa/FeatureOfInterest</a><sup class="sup-c" title="class">c</sup><br />
Restrictions |<a href="#ismetadatapublic?">igsn:isMetadataPublic</a><sup class="sup-dp" title="datatype property">dp</sup> <span class="cardinality">exactly</span> 1<br /><a href="http://purl.org/dc/terms/type">dcterms:type</a> <span class="cardinality">min</span> 0<br /><a href="http://purl.org/dc/terms/identifier">dcterms:identifier</a> <span class="cardinality">exactly</span> 1 <a href="http://schema.igsn.org/description#IGSN">igsn:IGSN</a><sup class="sup-c" title="class">c</sup><br /><a href="#Registrant">igsn:registrant</a><sup class="sup-op" title="object property">op</sup> <span class="cardinality">min</span> 0<br /><a href="http://www.w3.org/ns/sosa/isResultOf">http://www.w3.org/ns/sosa/isResultOf</a> <span class="cardinality">only</span> <a href="http://www.w3.org/ns/sosa/Sampling">http://www.w3.org/ns/sosa/Sampling</a><sup class="sup-c" title="class">c</sup><br /><a href="#material">igsn:material</a><sup class="sup-op" title="object property">op</sup> <span class="cardinality">min</span> 0 <a href="http://vocabulary.odm2.org/medium">odm2:medium</a><sup class="sup-c" title="class">c</sup><br /><a href="http://purl.org/dc/terms/creator">dcterms:creator</a> <span class="cardinality">min</span> 0<br /><a href="http://purl.org/dc/terms/spatial">dcterms:spatial</a> <span class="cardinality">min</span> 0<br /><a href="http://www.w3.org/ns/sosa/isSampleOf">http://www.w3.org/ns/sosa/isSampleOf</a> <span class="cardinality">min</span> 0<br /><a href="http://purl.org/dc/terms/description">dcterms:description</a> <span class="cardinality">min</span> 0<br /><a href="http://purl.org/dc/terms/created">dcterms:created</a> <span class="cardinality">some</span> <a href="http://www.w3.org/2006/time#TemporalEntity">http://www.w3.org/2006/time#TemporalEntity</a><sup class="sup-c" title="class">c</sup><br /><a href="http://www.w3.org/ns/dcat#qualifiedRelation">http://www.w3.org/ns/dcat#qualifiedRelation</a> <span class="cardinality">min</span> 0<br /><a href="http://purl.org/dc/terms/contributor">dcterms:contributor</a> <span class="cardinality">min</span> 0<br /><a href="http://www.w3.org/ns/sosa/usedProcedure">http://www.w3.org/ns/sosa/usedProcedure</a> <span class="cardinality">min</span> 0<br />
Sub-classes |<a href="#Sample">igsn:Sample</a><sup class="sup-c" title="class">c</sup><br /><a href="#Feature">igsn:Feature</a><sup class="sup-c" title="class">c</sup><br /><a href="#Collection">igsn:Collection</a><sup class="sup-c" title="class">c</sup><br />
### Sample <sup>c</sup>
Property | Value
--- | ---
IRI | `http://schema.igsn.org/description#Sample`
Super-classes |<a href="#Resource">igsn:Resource</a><sup class="sup-c" title="class">c</sup><br /><a href="http://www.w3.org/ns/sosa/Sample">http://www.w3.org/ns/sosa/Sample</a><sup class="sup-c" title="class">c</sup><br />

## Object Properties
[material](material),
[Registrant](Registrant),
[](material)
### material <sup>op</sup>
Property | Value
--- | ---
IRI | `http://schema.igsn.org/description#material`
Description | (13.) materials - physical medium of this resource; must provide 1 term from ODM2 vocabulary (medium) plus 0-N additional terms from any vocabulary; typically only used for samples
[](Registrant)
### Registrant <sup>op</sup>
Property | Value
--- | ---
IRI | `http://schema.igsn.org/description#registrant`
Description | (8.) registrant (cf. datacite:publisher) - agent (person or organization) that registered the IGSN for this resource
Super-properties |<a href="http://purl.org/dc/terms/contributor">dcterms:contributor</a><br />

## Datatype Properties
[is metadata public?](ismetadatapublic?),
[](ismetadatapublic?)
### is metadata public? <sup>dp</sup>
Property | Value
--- | ---
IRI | `http://schema.igsn.org/description#isMetadataPublic`
Range(s) |<a href="http://www.w3.org/2001/XMLSchema#boolean">xsd:boolean</a><sup class="sup-c" title="class">c</sup><br />

## Namespaces
* **default (:)**
  * `http://schema.igsn.org/description#`
* **dcterms**
  * `http://purl.org/dc/terms/`
* **igsn**
  * `http://schema.igsn.org/description#`
* **odm2**
  * `http://vocabulary.odm2.org/`
* **owl**
  * `http://www.w3.org/2002/07/owl#`
* **rdf**
  * `http://www.w3.org/1999/02/22-rdf-syntax-ns#`
* **rdfs**
  * `http://www.w3.org/2000/01/rdf-schema#`
* **xml**
  * `http://www.w3.org/XML/1998/namespace`
* **xsd**
  * `http://www.w3.org/2001/XMLSchema#`

## Legend
* Classes: c
* Object Properties :op
* Functional Properties: fp
* Data Properties: dp
* Annotation Properties: dp
* Properties: p
* Named Individuals: ni