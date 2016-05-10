# Mappings defined in DCAT-AP+Schema.org

## Status of this document

This document presents a proposal for mapping the relevant terms from the [DCAT Application Profile for European Data Portals](https://joinup.ec.europa.eu/asset/dcat_application_profile/) (DCAT-AP) to the [Schema.org vocabulary](http://schema.org/).

This document is a draft meant to report work in progress. As such, it can be updated any time and it must be considered as unstable.

## Abstract

This documents illustrates the mappings defined in DCAT-AP+Schema.org.

The background and methodology for the design of DCAT-AP+Schema.org are illustrated in a separate document:

[<cite>DCAT-AP+Schema.org: Background & methodology</cite>](./Background.md)

## Table of contents

*   [Introduction](#introduction)
*   [Used namespaces](#used-namespaces)
*   [Reference code lists for metadata elements](#ref-code-lists)
*   [Mapping summary](#mapping-summary)
    *   [Classes](#mapping-classes)
    *   [Properties for mandatory classes](#mapping-properties-mandatory)
    *   [Properties for recommended classes](#mapping-properties-recommended)
    *   [Properties for optional classes](#mapping-properties-optional)
*   [Formal definition](#mapping-formal)
    *   [Mandatory classes](#mapping-formal-mandatory)
    *   [Recommended classes](#mapping-formal-recommended)
    *   [Optional classes](#mapping-formal-optional)

## <a name="introduction">Introduction</a>

The mappings illustrated in this document cover the metadata elements defined in the following specifications:

*   [DCAT-AP v1.1](https://joinup.ec.europa.eu/asset/dcat_application_profile/asset_release/dcat-ap-v11) (<time datetime="2015-10-23">23 October 2015</time>)
*   [GeoDCAT-AP v1.0](https://joinup.ec.europa.eu/asset/dcat_application_profile/asset_release/geodcat-ap-v10) (<time datetime="2015-12-23">23 December 2015</time>)
*   [DCAT-AP Implementation Guidelines](https://joinup.ec.europa.eu/asset/dcat-ap_implementation_guidelines/) (DCAT-AP IG)

For each of the mapped elements and the reference controlled vocabularies, the relevant specification is referred to in the tables included in the following sections.

For Schema.org, the reference specification is [Schema.org 2.2](http://schema.org/version/2.2/) (<time datetime="2015-11-05">5 November 2015</time>).

This document includes, in a separate section, also a tentative formal definition of the mappings, in form of SPARQL queries.

**NB**: In the current version, this document does not include mappings concerning the GeoDCAT-AP representation of agent roles and conformance results based on the W3C PROV Ontology [[PROV-O](https://www.w3.org/TR/prov-o/)].

## <a name="used-namespaces">Used namespaces</a>

<table>

<thead>

<tr>

<th>Prefix</th>

<th>Namespace URI</th>

<th>Schema & documentation</th>

</tr>

</thead>

<tbody>

<tr>

<td>`adms`</td>

<td>`[http://www.w3.org/ns/adms#](http://www.w3.org/ns/adms#)`</td>

<td>[Asset Description Metadata Schema](http://www.w3.org/TR/2013/NOTE-vocab-adms-20130801/ "ADMS")</td>

</tr>

<tr>

<td>`cnt`</td>

<td>`[http://www.w3.org/2011/content#](http://www.w3.org/2011/content#)`</td>

<td>[Representing Content in RDF 1.0](http://www.w3.org/TR/2011/WD-Content-in-RDF10-20110510/)</td>

</tr>

<tr>

<td>`dc`</td>

<td>`[http://purl.org/dc/elements/1.1/](http://purl.org/dc/elements/1.1/)`</td>

<td>[Dublin Core Metadata Element Set, Version 1.1](http://dublincore.org/documents/2012/06/14/dces/)</td>

</tr>

<tr>

<td>`dcat`</td>

<td>`[http://www.w3.org/ns/dcat#](http://www.w3.org/ns/dcat#)`</td>

<td>[Data Catalog Vocabulary](http://www.w3.org/TR/2014/REC-vocab-dcat-20140116/ "DCAT")</td>

</tr>

<tr>

<td>`dct`</td>

<td>`[http://purl.org/dc/terms/](http://purl.org/dc/terms/)`</td>

<td>[DCMI Metadata Terms](http://dublincore.org/documents/2012/06/14/dcmi-terms/)</td>

</tr>

<tr>

<td>`dctype`</td>

<td>`[http://purl.org/dc/dcmitype/](http://purl.org/dc/dcmitype/)`</td>

<td>[DCMI Type Vocabulary](http://dublincore.org/documents/2012/06/14/dcmi-terms/#H7)</td>

</tr>

<tr>

<td>`foaf`</td>

<td>`[http://xmlns.com/foaf/0.1/](http://xmlns.com/foaf/0.1/)`</td>

<td>[FOAF Vocabulary](http://xmlns.com/foaf/spec/20140114.html)</td>

</tr>

<tr>

<td>`gsp`</td>

<td>`[http://www.opengis.net/ont/geosparql#](http://www.opengis.net/ont/geosparql#)`</td>

<td>[GeoSPARQL - A Geographic Query Language for RDF Data](http://www.opengeospatial.org/standards/geosparql)</td>

</tr>

<tr>

<td>`locn`</td>

<td>`[http://www.w3.org/ns/locn#](http://www.w3.org/ns/locn#)`</td>

<td>[ISA Programme Core Location Vocabulary](http://www.w3.org/ns/locn)</td>

</tr>

<tr>

<td>`owl`</td>

<td>`[http://www.w3.org/2002/07/owl#](http://www.w3.org/2002/07/owl#)`</td>

<td>[OWL Web Ontology Language Reference](http://www.w3.org/TR/2004/REC-owl-ref-20040210/)</td>

</tr>

<tr>

<td>`prov`</td>

<td>`[http://www.w3.org/ns/prov#](http://www.w3.org/ns/prov#)`</td>

<td>[PROV-O: The PROV Ontology](http://www.w3.org/TR/2013/REC-prov-o-20130430/)</td>

</tr>

<tr>

<td>`rdf`</td>

<td>`[http://www.w3.org/1999/02/22-rdf-syntax-ns#](http://www.w3.org/1999/02/22-rdf-syntax-ns#)`</td>

<td>[Resource Description Framework (RDF): Concepts and Abstract Syntax](http://www.w3.org/TR/2004/REC-rdf-concepts-20040210/)</td>

</tr>

<tr>

<td>`rdfs`</td>

<td>`[http://www.w3.org/2000/01/rdf-schema#](http://www.w3.org/2000/01/rdf-schema#)`</td>

<td>[RDF Vocabulary Description Language 1.0: RDF Schema](http://www.w3.org/TR/2004/REC-rdf-schema-20040210/)</td>

</tr>

<tr>

<td>`schema`</td>

<td>`[http://schema.org/](http://schema.org/)`</td>

<td>[schema.org](http://schema.org/)</td>

</tr>

<tr>

<td>`skos`</td>

<td>`[http://www.w3.org/2004/02/skos/core#](http://www.w3.org/2004/02/skos/core#)`</td>

<td>[SKOS Simple Knowledge Organization System - Reference](http://www.w3.org/TR/2009/REC-skos-reference-20090818/)</td>

</tr>

<tr>

<td>`spdx`</td>

<td>`[http://spdx.org/rdf/terms#](http://spdx.org/rdf/terms#)`</td>

<td>[SPDX Version 2.0](http://spdx.org/rdf/spdx-terms-v2.0/)</td>

</tr>

<tr>

<td>`vcard`</td>

<td>`[http://www.w3.org/2006/vcard/ns#](http://www.w3.org/2006/vcard/ns#)`</td>

<td>[vCard Ontology](http://www.w3.org/TR/2013/WD-vcard-rdf-20130924/)</td>

</tr>

<tr>

<td>`xsd`</td>

<td>`[http://www.w3.org/2001/XMLSchema#](http://www.w3.org/2001/XMLSchema)`</td>

<td>[XML Schema Part 2: Datatypes Second Edition](http://www.w3.org/TR/2004/REC-xmlschema-2-20041028/)</td>

</tr>

</tbody>

</table>



## <a name="ref-code-lists">Reference code lists for metadata elements</a>

<table>

<thead>

<tr>

<th>Specification</th>

<th>Metadata elements</th>

<th>Code list URI</th>

<th>Code lists</th>

<th>Status</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td>Catalogue record change type</td>

<td>`[http://purl.org/adms/changetype](http://purl.org/adms/changetype)`</td>

<td>ADMS Change Type controlled vocabulary [[ADMS-SKOS](https://joinup.ec.europa.eu/svn/adms/ADMS_v1.00/ADMS_SKOS_v1.00.html)]</td>

<td>stable</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td>Degree of conformity</td>

<td>`[http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity](http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity)`</td>

<td>Register operated by the INSPIRE Registry for degrees of conformity, as defined in [[INSPIRE-MD-REG](http://data.europa.eu/eli/reg/2008/1205/2008-12-24)]</td>

<td>stable</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td>Distribution status</td>

<td>`[http://purl.org/adms/status](http://purl.org/adms/status)`</td>

<td>ADMS Status controlled vocabulary [[ADMS-SKOS](https://joinup.ec.europa.eu/svn/adms/ADMS_v1.00/ADMS_SKOS_v1.00.html)]</td>

<td>stable</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td>Format</td>

<td>`[http://publications.europa.eu/resource/authority/file-type](http://publications.europa.eu/resource/authority/file-type)`</td>

<td>File type register operated by the Metadata Registry of the Publications Office of the EU [[MDR-FT](http://publications.europa.eu/mdr/authority/file-type/)]</td>

<td>stable</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td>INSPIRE spatial data themes</td>

<td>`[http://inspire.ec.europa.eu/theme](http://inspire.ec.europa.eu/theme)`</td>

<td>INSPIRE spatial data theme register operated by the INSPIRE Registry</td>

<td>stable</td>

</tr>

<tr>

<td rowspan="4">DCAT-AP 1.1</td>

<td rowspan="4">Geographical names</td>

<td>`[http://publications.europa.eu/resource/authority/continent](http://publications.europa.eu/resource/authority/country)`</td>

<td>Continent register operated by the Metadata Registry of the Publications Office of the EU [[MDR-CONT](http://publications.europa.eu/mdr/authority/continent/)]</td>

<td>stable</td>

</tr>

<tr>

<td>`[http://publications.europa.eu/resource/authority/country](http://publications.europa.eu/resource/authority/country)`</td>

<td>Country register operated by the Metadata Registry of the Publications Office of the EU [[MDR-COUNTRY](http://publications.europa.eu/mdr/authority/country/)]</td>

<td>stable</td>

</tr>

<tr>

<td>`[http://publications.europa.eu/resource/authority/place](http://publications.europa.eu/resource/authority/place)`</td>

<td>Place register operated by the Metadata Registry of the Publications Office of the EU [[MDR-PLACE](http://publications.europa.eu/mdr/authority/place/)]</td>

<td>stable</td>

</tr>

<tr>

<td>`[http://sws.geonames.org/](http://sws.geonames.org/)`</td>

<td>GeoNames gazetteer</td>

<td>stable</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td>Language</td>

<td>`[http://publications.europa.eu/resource/authority/language](http://publications.europa.eu/resource/authority/language)`</td>

<td>Language register operated by the Metadata Registry of the Publications Office of the EU [[MDR-LANG](http://publications.europa.eu/mdr/authority/language/)]</td>

<td>stable</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td>Licence type</td>

<td>`[http://purl.org/adms/licencetype](http://purl.org/adms/licencetype)`</td>

<td>ADMS Licence Type controlled vocabulary [[ADMS-SKOS](https://joinup.ec.europa.eu/svn/adms/ADMS_v1.00/ADMS_SKOS_v1.00.html)]</td>

<td>stable</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td rowspan="2">Maintenance frequency (Maintenance information)</td>

<td>`[http://publications.europa.eu/resource/authority/frequency](http://publications.europa.eu/resource/authority/frequency)`</td>

<td>Frequency code register operated by the Metadata Registry of the Publications Office of the EU [[MDR-FR](http://publications.europa.eu/mdr/authority/frequency/)]</td>

<td>stable</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td>`http://inspire.ec.europa.eu/metadata-codelist/MaintenanceFrequencyCode`</td>

<td>Register operated by the INSPIRE Registry for maintenance frequency codes defined in ISO 19115\. The register is not yet available, and the code list URI is tentative.</td>

<td>**unstable**</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td>MDR Data themes</td>

<td>`[http://publications.europa.eu/resource/authority/theme](http://publications.europa.eu/resource/authority/theme)`</td>

<td>Data theme register operated by the Metadata Registry of the Publications Office of the EU [[MDR-LANG](http://publications.europa.eu/mdr/authority/language/)]</td>

<td>stable</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td>Media type</td>

<td>`[http://www.iana.org/assignments/media-types](http://www.iana.org/assignments/media-types/)`</td>

<td>IANA MIME Media Types register</td>

<td>stable</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td>Publisher</td>

<td>`[http://publications.europa.eu/resource/authority/corporate-body](http://publications.europa.eu/resource/authority/corporate-body)`</td>

<td>Corporate body register operated by the Metadata Registry of the Publications Office of the EU [[MDR-CB](http://publications.europa.eu/mdr/authority/corporate-body/)]</td>

<td>stable</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td>Publisher type</td>

<td>`[http://purl.org/adms/publishertype](http://purl.org/adms/publishertype)`</td>

<td>ADMS Publisher Type controlled vocabulary [[ADMS-SKOS](https://joinup.ec.europa.eu/svn/adms/ADMS_v1.00/ADMS_SKOS_v1.00.html)]</td>

<td>stable</td>

</tr>

<tr>

<td rowspan="2">GeoDCAT-AP 1.0</td>

<td rowspan="2">Reference system type</td>

<td>`[http://inspire.ec.europa.eu/glossary/SpatialReferenceSystem](http://inspire.ec.europa.eu/glossary/SpatialReferenceSystem)`</td>

<td rowspan="2">The reference system type (spatial or temporal) is denoted by using the relevant terms from the [glossary](http://inspire.ec.europa.eu/glossary) operated by the INSPIRE Registry.</td>

<td rowspan="2">_testing_</td>

</tr>

<tr>

<td>`[http://inspire.ec.europa.eu/glossary/TemporalReferenceSystem](http://inspire.ec.europa.eu/glossary/TemporalReferenceSystem)`</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td>Resource type</td>

<td>`[http://inspire.ec.europa.eu/metadata-codelist/ResourceType](http://inspire.ec.europa.eu/metadata-codelist/ResourceType)`</td>

<td>Register operated by the INSPIRE Registry for resource types defined in ISO 19115</td>

<td>stable</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td>Responsible party role</td>

<td>`[http://inspire.ec.europa.eu/metadata-codelist/ResponsiblePartyRole](http://inspire.ec.europa.eu/metadata-codelist/ResponsiblePartyRole)`</td>

<td>Register operated by the INSPIRE Registry for responsible party roles, as defined in [[INSPIRE-MD-REG](http://data.europa.eu/eli/reg/2008/1205/2008-12-24)]</td>

<td>stable</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td>Service type</td>

<td>`[http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType](http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType)`</td>

<td>Register operated by the INSPIRE Registry for service types, as defined in [[INSPIRE-MD-REG](http://data.europa.eu/eli/reg/2008/1205/2008-12-24)]</td>

<td>stable</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td>Spatial data service categories</td>

<td>`[http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory](http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory)`</td>

<td>Register operated by the INSPIRE Registry for spatial data service categories defined in ISO 19119</td>

<td>stable</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td>Spatial representation type</td>

<td>`http://inspire.ec.europa.eu/metadata-codelist/SpatialRepresentationTypeCode`</td>

<td>Register operated by the INSPIRE Registry for spatial representation type codes defined in ISO 19115\. The register is not yet available, and the code list URI is tentative.</td>

<td>**unstable**</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td>Topic category</td>

<td>`[http://inspire.ec.europa.eu/metadata-codelist/TopicCategory](http://inspire.ec.europa.eu/metadata-codelist/TopicCategory)`</td>

<td>Register operated by the INSPIRE Registry for topic categories defined in ISO 19115</td>

<td>stable</td>

</tr>

</tbody>

</table>





## <a name="mapping-summary">Mapping summary</a>

The following section summarises the alignments defined in DCAT-AP+Schema.org.

The alignments are grouped as follows:

*   Alignments for DCAT-AP classes
*   Alignments for DCAT-AP properties concerning:
    *   mandatory classes
    *   recommended classes
    *   optional classes

### <a name="mapping-classes">Classes</a>

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>[Agent](#mapping-properties-agent "Detailed mapping")</td>

<td>[`foaf:Agent`](http://xmlns.com/foaf/spec/#term_Agent "http://xmlns.com/foaf/0.1/Agent")</td>

<td>[`schema:Organization`](http://schema.org/Organization "http://schema.org/Organization") <span>|</span> [`schema:Person`](http://schema.org/Person "http://schema.org/Person")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>[Catalogue](#mapping-properties-catalogue "Detailed mapping")</td>

<td>[`dcat:Catalog`](https://www.w3.org/TR/vocab-dcat/#class-catalog "http://www.w3.org/ns/dcat#Catalog")</td>

<td>[`schema:DataCatalog`](http://schema.org/DataCatalog "http://schema.org/DataCatalog")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>[Dataset](#mapping-properties-dataset "Detailed mapping")</td>

<td>[`dcat:Dataset`](https://www.w3.org/TR/vocab-dcat/#class-dataset "http://www.w3.org/ns/dcat#Dataset")</td>

<td>[`schema:Dataset`](http://schema.org/Dataset "http://schema.org/Dataset")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>[Category](#mapping-properties-category "Detailed mapping")</td>

<td>[`skos:Concept`](https://www.w3.org/TR/vocab-dcat/#class-concept "http://www.w3.org/2004/02/skos/core#Concept")</td>

<td>[`schema:Thing`](http://schema.org/Thing "http://schema.org/Thing")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>[Category Scheme](#mapping-properties-category-scheme "Detailed mapping")</td>

<td>[`skos:ConceptScheme`](https://www.w3.org/TR/vocab-dcat/#class-concept-scheme "http://www.w3.org/2004/02/skos/core#ConceptScheme")</td>

<td>[`schema:Enumeration`](http://schema.org/Enumeration "http://schema.org/Enumeration")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>[Distribution](#mapping-properties-distribution "Detailed mapping")</td>

<td>[`dcat:Distribution`](https://www.w3.org/TR/vocab-dcat/#class-distribution "http://www.w3.org/ns/dcat#Distribution")</td>

<td>[`schema:DataDownload`](http://schema.org/DataDownload "http://schema.org/DataDownload")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>[Licence Document](#mapping-properties-licence "Detailed mapping")</td>

<td>[`dct:LicenseDocument`](http://dublincore.org/documents/dcmi-terms/#terms-LicenseDocument "http://purl.org/dc/terms/LicenseDocument")</td>

<td>[`schema:CreativeWork`](http://schema.org/CreativeWork "http://schema.org/CreativeWork") <span>|</span> [`schema:URL`](http://schema.org/URL "http://schema.org/URL")</td>

<td>TDB</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Catalogue Record](#mapping-properties-catalogue-record "Detailed mapping")</td>

<td>[`dcat:CatalogRecord`](https://www.w3.org/TR/vocab-dcat/#class-catalog-record "http://www.w3.org/ns/dcat#CatalogRecord")</td>

<td>[`schema:ListItem`](http://schema.org/ListItem "http://schema.org/ListItem")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Checksum](#mapping-properties-checksum "Detailed mapping")</td>

<td>[`spdx:Checksum`](http://spdx.org/rdf/terms#Checksum "http://spdx.org/rdf/terms/classes/Checksum___-238837136.html")</td>

<td>[`schema:Thing`](http://schema.org/Thing "http://schema.org/Thing")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Document](#mapping-properties-document "Detailed mapping")</td>

<td>[`foaf:Document`](http://xmlns.com/foaf/spec/#term_Document "http://xmlns.com/foaf/0.1/Document")</td>

<td>[`schema:CreativeWork`](http://schema.org/CreativeWork "http://schema.org/CreativeWork") <span>|</span> [`schema:URL`](http://schema.org/URL "http://schema.org/URL")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Identifier](#mapping-properties-identifier "Detailed mapping")</td>

<td>[`adms:Identifier`](https://www.w3.org/TR/vocab-adms/#dt_identifier "http://www.w3.org/ns/adms#Identifier")</td>

<td>[`schema:Thing`](http://schema.org/Thing "http://schema.org/Thing")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Kind](#mapping-properties-kind "Detailed mapping")</td>

<td>[`vcard:Kind`](https://www.w3.org/TR/vcard-rdf/#d4e1819 "http://www.w3.org/2006/vcard/ns#Kind")</td>

<td>[`schema:ContactPoint`](http://schema.org/ContactPoint "http://schema.org/ContactPoint")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Location](#mapping-properties-location "Detailed mapping")</td>

<td>[`dct:Location`](http://dublincore.org/documents/dcmi-terms/#terms-Location "http://purl.org/dc/terms/Location")</td>

<td>[`schema:Place`](http://schema.org/Place "http://schema.org/Place")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Media Type or Extent](#mapping-properties-media-type "Detailed mapping")</td>

<td>[`dct:MediaTypeOrExtent`](http://dublincore.org/documents/dcmi-terms/#terms-MediaTypeOrExtent "http://purl.org/dc/terms/MediaTypeOrExtent")</td>

<td>[`schema:Text`](http://schema.org/Text "http://schema.org/Text") <span>|</span> [`schema:URL`](http://schema.org/URL "http://schema.org/URL")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Period of Time](#mapping-properties-period-of-time "Detailed mapping")</td>

<td>[`dct:PeriodOfTime`](http://dublincore.org/documents/dcmi-terms/#terms-PeriodOfTime "http://purl.org/dc/terms/PeriodOfTime")</td>

<td>[`schema:DateTime`](http://schema.org/DateTime "http://schema.org/DateTime")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Reference System](#mapping-properties-reference-system "Detailed mapping")</td>

<td>[`dct:Standard`](http://dublincore.org/documents/dcmi-terms/#terms-Standard "http://purl.org/dc/terms/Standard")</td>

<td>[`schema:CreativeWork`](http://schema.org/CreativeWork "http://schema.org/CreativeWork") <span>|</span> [`schema:URL`](http://schema.org/URL "http://schema.org/URL")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Rights Statement](#mapping-properties-rights "Detailed mapping")</td>

<td>[`dct:RightsStatement`](http://dublincore.org/documents/dcmi-terms/#terms-RightsStatement "http://purl.org/dc/terms/RightsStatement")</td>

<td>[`schema:CreativeWork`](http://schema.org/CreativeWork "http://schema.org/CreativeWork") <span>|</span> [`schema:URL`](http://schema.org/URL "http://schema.org/URL")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Service](#mapping-properties-service "Detailed mapping")</td>

<td>[`dctype:Service`](http://dublincore.org/documents/2012/06/14/dcmi-terms/#dcmitype-Service "http://purl.org/dc/dcmitype/Service")</td>

<td>[`schema:Service`](http://schema.org/Service "http://schema.org/Service")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>[Standard](#mapping-properties-standard "Detailed mapping")</td>

<td>[`dct:Standard`](http://dublincore.org/documents/dcmi-terms/#terms-Standard "http://purl.org/dc/terms/Standard")</td>

<td>[`schema:CreativeWork`](http://schema.org/CreativeWork "http://schema.org/CreativeWork") <span>|</span> [`schema:URL`](http://schema.org/URL "http://schema.org/URL")</td>

<td>TBD</td>

</tr>

</tbody>

</table>



### <a name="mapping-properties-mandatory">Properties for mandatory classes</a>

#### <a name="mapping-properties-agent">Agent</a>

These properties should be used with [`schema:Organization`](http://schema.org/Organization) or [`schema:Person`](http://schema.org/Person). [[formal definition](#mapping-formal-agent)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>name</td>

<td>[`foaf:name`](http://xmlns.com/foaf/spec/#term_name "http://xmlns.com/foaf/0.1/name")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>type</td>

<td>[`dct:type`](http://dublincore.org/documents/dcmi-terms/#terms-type "http://purl.org/dc/terms/type")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>email</td>

<td>[`foaf:mbox`](http://xmlns.com/foaf/spec/#term_mbox "http://xmlns.com/foaf/0.1/mbox")</td>

<td>[`schema:email`](http://schema.org/email "http://schema.org/email")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>homepage</td>

<td>[`foaf:workplaceHomepage`](http://xmlns.com/foaf/spec/#term_workplaceHomepage "http://xmlns.com/foaf/0.1/workplaceHomepage")</td>

<td>[`schema:url`](http://schema.org/url "http://schema.org/url")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-catalogue">Catalogue</a>

These properties should be used with [`schema:DataCatalog`](http://schema.org/DataCatalog). [[formal definition](#mapping-formal-catalogue)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>dataset</td>

<td>[`dcat:dataset`](https://www.w3.org/TR/vocab-dcat/#property-dataset "http://www.w3.org/ns/dcat#dataset")</td>

<td>[`schema:dataset`](http://schema.org/dataset "http://schema.org/dataset")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>description</td>

<td>[`dct:description`](http://dublincore.org/documents/dcmi-terms/#terms-description "http://purl.org/dc/terms/description")</td>

<td>[`schema:description`](http://schema.org/description "http://schema.org/description")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>publisher</td>

<td>[`dct:publisher`](http://dublincore.org/documents/dcmi-terms/#terms-publisher "http://purl.org/dc/terms/publisher")</td>

<td>[`schema:publisher`](http://schema.org/publisher "http://schema.org/publisher")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>title</td>

<td>[`dct:title`](http://dublincore.org/documents/dcmi-terms/#terms-title "http://purl.org/dc/terms/title")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>homepage</td>

<td>[`foaf:homepage`](http://xmlns.com/foaf/spec/#term_homepage "http://xmlns.com/foaf/0.1/homepage")</td>

<td>[`schema:url`](http://schema.org/url "http://schema.org/url")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>language</td>

<td>[`dct:language`](http://dublincore.org/documents/dcmi-terms/#terms-language "http://purl.org/dc/terms/language")</td>

<td>[`schema:inLanguage`](http://schema.org/inLanguage "http://schema.org/inLanguage")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>licence</td>

<td>[`dct:license`](http://dublincore.org/documents/dcmi-terms/#terms-license "http://purl.org/dc/terms/license")</td>

<td>[`schema:license`](http://schema.org/license "http://schema.org/license")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>release date</td>

<td>[`dct:issued`](http://dublincore.org/documents/dcmi-terms/#terms-issued "http://purl.org/dc/terms/issued")</td>

<td>[`schema:datePublished`](http://schema.org/datePublished "http://schema.org/datePublished")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>themes</td>

<td>[`dcat:themeTaxonomy`](https://www.w3.org/TR/vocab-dcat/#property-themeTaxonomy "http://www.w3.org/ns/dcat#themeTaxonomy")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>update / modification date</td>

<td>[`dct:modified`](http://dublincore.org/documents/dcmi-terms/#terms-modified "http://purl.org/dc/terms/modified")</td>

<td>[`schema:dateModified`](http://schema.org/dateModified "http://schema.org/dateModified")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>has part</td>

<td>[`dct:hasPart`](http://dublincore.org/documents/dcmi-terms/#terms-hasPart "http://purl.org/dc/terms/hasPart")</td>

<td>[`schema:hasPart`](http://schema.org/hasPart "http://schema.org/hasPart")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>is part of</td>

<td>[`dct:isPartOf`](http://dublincore.org/documents/dcmi-terms/#terms-isPartOf "http://purl.org/dc/terms/isPartOf")</td>

<td>[`schema:isPartOf`](http://schema.org/isPartOf "http://schema.org/isPartOf")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>record</td>

<td>[`dcat:record`](https://www.w3.org/TR/vocab-dcat/#property-record "http://www.w3.org/ns/dcat#record")</td>

<td>[`schema:itemListElement`](http://schema.org/itemListElement "http://schema.org/itemListElement")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>rights</td>

<td>[`dct:rights`](http://dublincore.org/documents/dcmi-terms/#terms-rights "http://purl.org/dc/terms/rights")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>spatial / geographic coverage</td>

<td>[`dct:spatial`](http://dublincore.org/documents/dcmi-terms/#terms-spatial "http://purl.org/dc/terms/spatial")</td>

<td>[`schema:spatial`](http://schema.org/spatial "http://schema.org/spatial")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-dataset">Dataset</a>

These properties should be used with [`schema:Dataset`](http://schema.org/Dataset). [[formal definition](#mapping-formal-dataset)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>description</td>

<td>[`dct:description`](http://dublincore.org/documents/dcmi-terms/#terms-description "http://purl.org/dc/terms/description")</td>

<td>[`schema:description`](http://schema.org/description "http://schema.org/description")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>title</td>

<td>[`dct:title`](http://dublincore.org/documents/dcmi-terms/#terms-title "http://purl.org/dc/terms/title")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>contact point</td>

<td>[`dcat:contactPoint`](https://www.w3.org/TR/vocab-dcat/#property-contactPoint "http://www.w3.org/ns/dcat#contactPoint")</td>

<td>[`schema:contactPoint`](http://schema.org/contactPoint "http://schema.org/contactPoint")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>dataset distribution</td>

<td>[`dcat:distribution`](https://www.w3.org/TR/vocab-dcat/#property-distribution "http://www.w3.org/ns/dcat#distribution")</td>

<td>[`schema:distribution`](http://schema.org/distribution "http://schema.org/distribution")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>keyword</td>

<td>[`dcat:keyword`](https://www.w3.org/TR/vocab-dcat/#property-keyword "http://www.w3.org/ns/dcat#keyword")</td>

<td>[`schema:keywords`](http://schema.org/keywords "http://schema.org/keywords")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>publisher</td>

<td>[`dct:publisher`](http://dublincore.org/documents/dcmi-terms/#terms-publisher "http://purl.org/dc/terms/publisher")</td>

<td>[`schema:publisher`](http://schema.org/publisher "http://schema.org/publisher")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>theme / category</td>

<td>[`dcat:theme`](https://www.w3.org/TR/vocab-dcat/#property-theme "http://www.w3.org/ns/dcat#theme")</td>

<td>[`schema:about`](http://schema.org/about "http://schema.org/about")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>access rights</td>

<td>[`dct:accessRights`](http://dublincore.org/documents/dcmi-terms/#terms-accessRights "http://purl.org/dc/terms/accessRights")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>author</td>

<td>[`dct:creator`](http://dublincore.org/documents/dcmi-terms/#terms-creator "http://purl.org/dc/terms/creator")</td>

<td>[`schema:creator`](http://schema.org/creator "http://schema.org/creator")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>conformance result / conformity (data quality)</td>

<td>[`dct:conformsTo`](http://dublincore.org/documents/dcmi-terms/#terms-conformsTo "http://purl.org/dc/terms/conformsTo")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>conforms to</td>

<td>[`dct:conformsTo`](http://dublincore.org/documents/dcmi-terms/#terms-conformsTo "http://purl.org/dc/terms/conformsTo")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>creation date</td>

<td>[`dct:created`](http://dublincore.org/documents/dcmi-terms/#terms-created "http://purl.org/dc/terms/created")</td>

<td>[`schema:dateCreated`](http://schema.org/dateCreated "http://schema.org/dateCreated")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>documentation</td>

<td>[`foaf:page`](http://xmlns.com/foaf/spec/#term_page "http://xmlns.com/foaf/0.1/page")</td>

<td>[`schema:mainEntityOfPage`](http://schema.org/mainEntityOfPage "http://schema.org/mainEntityOfPage")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>frequency</td>

<td>[`dct:accrualPeriodicity`](http://dublincore.org/documents/dcmi-terms/#terms-accrualPeriodicity "http://purl.org/dc/terms/accrualPeriodicity")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>has version</td>

<td>[`dct:hasVersion`](http://dublincore.org/documents/dcmi-terms/#terms-hasVersion "http://purl.org/dc/terms/hasVersion")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>identifier</td>

<td>[`dct:identifier`](http://dublincore.org/documents/dcmi-terms/#terms-identifier "http://purl.org/dc/terms/identifier")</td>

<td>[`schema:productID`](http://schema.org/productID "http://schema.org/productID")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>is version of</td>

<td>[`dct:isVersionOf`](http://dublincore.org/documents/dcmi-terms/#terms-isVersionOf "http://purl.org/dc/terms/isVersionOf")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>landing page</td>

<td>[`dcat:landingPage`](https://www.w3.org/TR/vocab-dcat/#property-landingPage "http://www.w3.org/ns/dcat#landingPage")</td>

<td>[`schema:url`](http://schema.org/url "http://schema.org/url")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>language</td>

<td>[`dct:language`](http://dublincore.org/documents/dcmi-terms/#terms-language "http://purl.org/dc/terms/language")</td>

<td>[`schema:inLanguage`](http://schema.org/inLanguage "http://schema.org/inLanguage")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>other identifier</td>

<td>[`amds:identifier`](https://www.w3.org/TR/vocab-adms/#adms_identifier "http://www.w3.org/ns/adms#identifier")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>owner</td>

<td>[`dct:rightsHolder`](http://dublincore.org/documents/dcmi-terms/#terms-rightsHolder "http://purl.org/dc/terms/rightsHolder")</td>

<td>[`schema:copyrightHolder`](http://schema.org/copyrightHolder "http://schema.org/copyrightHolder")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>provenance</td>

<td>[`dct:provenance`](http://dublincore.org/documents/dcmi-terms/#terms-provenance "http://purl.org/dc/terms/provenance")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>reference system</td>

<td>[`dct:conformsTo`](http://dublincore.org/documents/dcmi-terms/#terms-conformsTo "http://purl.org/dc/terms/conformsTo")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>related resource</td>

<td>[`dct:relation`](http://dublincore.org/documents/dcmi-terms/#terms-relation "http://purl.org/dc/terms/relation")</td>

<td>[`schema:mentions`](http://schema.org/mentions "http://schema.org/mentions")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>release date</td>

<td>[`dct:issued`](http://dublincore.org/documents/dcmi-terms/#terms-issued "http://purl.org/dc/terms/issued")</td>

<td>[`schema:datePublished`](http://schema.org/datePublished "http://schema.org/datePublished")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>sample</td>

<td>[`amds:sample`](https://www.w3.org/TR/vocab-adms/#adms_sample "http://www.w3.org/ns/adms#sample")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>source</td>

<td>[`dct:source`](http://dublincore.org/documents/dcmi-terms/#terms-source "http://purl.org/dc/terms/source")</td>

<td>[`schema:isBasedOnUrl`](http://schema.org/isBasedOnUrl "http://schema.org/isBasedOnUrl")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>spatial / geographic coverage</td>

<td>[`dct:spatial`](http://dublincore.org/documents/dcmi-terms/#terms-spatial "http://purl.org/dc/terms/spatial")</td>

<td>[`schema:spatial`](http://schema.org/spatial "http://schema.org/spatial")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>temporal coverage</td>

<td>[`dct:temporal`](http://dublincore.org/documents/dcmi-terms/#terms-temporal "http://purl.org/dc/terms/temporal")</td>

<td>[`schema:datasetTimeInterval`](http://schema.org/datasetTimeInterval "http://schema.org/datasetTimeInterval")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>topic category</td>

<td>[`dct:subject`](http://dublincore.org/documents/dcmi-terms/#terms-subject "http://purl.org/dc/terms/subject")</td>

<td>[`schema:about`](http://schema.org/about "http://schema.org/about")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>type</td>

<td>[`dct:type`](http://dublincore.org/documents/dcmi-terms/#terms-type "http://purl.org/dc/terms/type")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>update / modification date</td>

<td>[`dct:modified`](http://dublincore.org/documents/dcmi-terms/#terms-modified "http://purl.org/dc/terms/modified")</td>

<td>[`schema:dateModified`](http://schema.org/dateModified "http://schema.org/dateModified")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>version</td>

<td>[`owl:versionInfo`](https://www.w3.org/TR/owl-ref/#versionInfo-def "http://www.w3.org/2002/07/owl#versionInfo")</td>

<td>[`schema:version`](http://schema.org/version "http://schema.org/version")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>version notes</td>

<td>[`adms:versionNotes`](https://www.w3.org/TR/vocab-adms/#adms-versionnotes "http://www.w3.org/ns/adms#version")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

</tbody>

</table>

### <a name="mapping-properties-recommended">Properties for recommended classes</a>

#### <a name="mapping-properties-category">Category</a>

TBD [[formal definition](#mapping-formal-category)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>preferred label</td>

<td>[`skos:prefLabel`](https://www.w3.org/2009/08/skos-reference/skos.html#prefLabel "http://www.w3.org/2004/02/skos/core#prefLabel")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>originating controlled vocabulary</td>

<td>[`skos:inScheme`](https://www.w3.org/TR/vocab-dcat/#class-inScheme "http://www.w3.org/2004/02/skos/core#inScheme")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-category-scheme">Category scheme</a>

These properties should be used with [`schema:Enumeration`](http://schema.org/Enumeration "http://schema.org/Enumeration"). [[formal definition](#mapping-formal-category-scheme)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>title</td>

<td>[`dct:title`](http://dublincore.org/documents/dcmi-terms/#terms-title "http://purl.org/dc/terms/title")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>creation date</td>

<td>[`dct:created`](http://dublincore.org/documents/dcmi-terms/#terms-created "http://purl.org/dc/terms/created")</td>

<td>[`schema:dateCreated`](http://schema.org/dateCreated "http://schema.org/dateCreated")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>release date</td>

<td>[`dct:issued`](http://dublincore.org/documents/dcmi-terms/#terms-issued "http://purl.org/dc/terms/issued")</td>

<td>[`schema:datePublished`](http://schema.org/datePublished "http://schema.org/datePublished")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>update / modification date</td>

<td>[`dct:modified`](http://dublincore.org/documents/dcmi-terms/#terms-modified "http://purl.org/dc/terms/modified")</td>

<td>[`schema:dateModified`](http://schema.org/dateModified "http://schema.org/dateModified")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-distribution">Distribution</a>

These properties should be used with [`schema:DataDownload`](http://schema.org/DataDownload). [[formal definition](#mapping-formal-distribution)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>access URL</td>

<td>[`dcat:accessURL`](https://www.w3.org/TR/vocab-dcat/#property-accessURL "http://www.w3.org/ns/dcat#accessURL")</td>

<td>[`schema:contentURL`](http://schema.org/contentURL "http://schema.org/contentURL")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>description</td>

<td>[`dct:description`](http://dublincore.org/documents/dcmi-terms/#terms-description "http://purl.org/dc/terms/description")</td>

<td>[`schema:description`](http://schema.org/description "http://schema.org/description")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>format</td>

<td>[`dct:format`](http://dublincore.org/documents/dcmi-terms/#terms-format "http://purl.org/dc/terms/format")</td>

<td>[`schema:encodingFormat`](http://schema.org/encodingFormat "http://schema.org/encodingFormat")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>licence</td>

<td>[`dct:license`](http://dublincore.org/documents/dcmi-terms/#terms-license "http://purl.org/dc/terms/license")</td>

<td>[`schema:license`](http://schema.org/license "http://schema.org/license")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>byte size</td>

<td>[`dcat:byteSize`](https://www.w3.org/TR/vocab-dcat/#property-byteSize "http://www.w3.org/ns/dcat#byteSize")</td>

<td>[`schema:contentSize`](http://schema.org/contentSize "http://schema.org/contentSize")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>character encoding</td>

<td>[`cnt:characterEncoding`](https://www.w3.org/TR/Content-in-RDF10/#characterEncodingProperty "http://www.w3.org/2011/content#characterEncoding")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>checksum</td>

<td>[`spdx:checksum`](http://spdx.org/rdf/terms/objectproperties/checksum___-303481264.html "http://spdx.org/rdf/terms#checksum")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>documentation</td>

<td>[`foaf:page`](http://xmlns.com/foaf/spec/#term_page "http://xmlns.com/foaf/0.1/page")</td>

<td>[`schema:mainEntityOfPage`](http://schema.org/?? "http://schema.org/mainEntityOfPage")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>download URL</td>

<td>[`dcat:downloadURL`](https://www.w3.org/TR/vocab-dcat/#property-downloadURL "http://www.w3.org/ns/dcat#downloadURL")</td>

<td>[`schema:contentURL`](http://schema.org/contentURL "http://schema.org/contentURL")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>language</td>

<td>[`dct:language`](http://dublincore.org/documents/dcmi-terms/#terms-language "http://purl.org/dc/terms/language")</td>

<td>[`schema:inLanguage`](http://schema.org/inLanguage "http://schema.org/inLanguage")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>linked schemas</td>

<td>[`dct:conformsTo`](http://dublincore.org/documents/dcmi-terms/#terms-conformsTo "http://purl.org/dc/terms/conformsTo")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>media type</td>

<td>[`dcat:mediaType`](https://www.w3.org/TR/vocab-dcat/#property-mediaType "http://www.w3.org/ns/dcat#mediaType")</td>

<td>[`schema:fileFormat`](http://schema.org/fileFormat "http://schema.org/fileFormat")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>release date</td>

<td>[`dct:issued`](http://dublincore.org/documents/dcmi-terms/#terms-issued "http://purl.org/dc/terms/issued")</td>

<td>[`schema:datePublished`](http://schema.org/datePublished "http://schema.org/datePublished")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>rights</td>

<td>[`dct:rights`](http://dublincore.org/documents/dcmi-terms/#terms-rights "http://purl.org/dc/terms/rights")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>spatial representation type</td>

<td>[`amds:representationTechnique`](https://www.w3.org/TR/vocab-adms/#adms_representationTechnique "http://www.w3.org/ns/adms#representationTechnique")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>status</td>

<td>[`amds:status`](https://www.w3.org/TR/vocab-adms/#adms_status "http://www.w3.org/ns/adms#status")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>title</td>

<td>[`dct:title`](http://dublincore.org/documents/dcmi-terms/#terms-title "http://purl.org/dc/terms/title")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>update / modification date</td>

<td>[`dct:modified`](http://dublincore.org/documents/dcmi-terms/#terms-modified "http://purl.org/dc/terms/modified")</td>

<td>[`schema:dateModified`](http://schema.org/dateModified "http://schema.org/dateModified")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-licence">Licence document</a>

TBD [[formal definition](#mapping-formal-licence)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>licence type</td>

<td>[`dct:type`](http://dublincore.org/documents/dcmi-terms/#terms-type "http://purl.org/dc/terms/type")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>name / description</td>

<td>[`rdfs:label`](http://www.w3.org/TR/2004/REC-rdf-schema-20040210/#ch_label "http://www.w3.org/2000/01/rdf-schema#label")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

</tbody>

</table>





### <a name="mapping-properties-optional">Properties for optional classes</a>

#### <a name="mapping-properties-catalogue-record">Catalogue record</a>

These properties should be used with [`schema:ListItem`](http://schema.org/ListItem). [[formal definition](#mapping-formal-catalogue-record)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>primary topic</td>

<td>[`foaf:primaryTopic`](http://xmlns.com/foaf/spec/#term_primaryTopic "http://xmlns.com/foaf/0.1/primaryTopic")</td>

<td>[`schema:item`](http://schema.org/item "http://schema.org/item")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>update / modification date</td>

<td>[`dct:modified`](http://dublincore.org/documents/dcmi-terms/#terms-modified "http://purl.org/dc/terms/modified")</td>

<td>[`schema:dateModified`](http://schema.org/dateModified "http://schema.org/dateModified")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>application profile</td>

<td>[`dct:conformsTo`](http://dublincore.org/documents/dcmi-terms/#terms-conformsTo "http://purl.org/dc/terms/conformsTo")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>change type</td>

<td>[`amds:status`](https://www.w3.org/TR/vocab-adms/#adms_status "http://www.w3.org/ns/adms#status")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Recommended">R</abbr></td>

<td>listing date</td>

<td>[`dct:issued`](http://dublincore.org/documents/dcmi-terms/#terms-issued "http://purl.org/dc/terms/issued")</td>

<td>[`schema:datePublished`](http://schema.org/datePublished "http://schema.org/datePublished")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>character encoding</td>

<td>[`cnt:characterEncoding`](https://www.w3.org/TR/Content-in-RDF10/#characterEncodingProperty "http://www.w3.org/2011/content#characterEncoding")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>contact point</td>

<td>[`dcat:contactPoint`](https://www.w3.org/TR/vocab-dcat/#property-contactPoint "http://www.w3.org/ns/dcat#contactPoint")</td>

<td>[`schema:contactPoint`](http://schema.org/contactPoint "http://schema.org/contactPoint")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>description</td>

<td>[`dct:description`](http://dublincore.org/documents/dcmi-terms/#terms-description "http://purl.org/dc/terms/description")</td>

<td>[`schema:description`](http://schema.org/description "http://schema.org/description")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>identifier</td>

<td>[`dct:identifier`](http://dublincore.org/documents/dcmi-terms/#terms-identifier "http://purl.org/dc/terms/identifier")</td>

<td>[`schema:productID`](http://schema.org/productID "http://schema.org/productID")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>language</td>

<td>[`dct:language`](http://dublincore.org/documents/dcmi-terms/#terms-language "http://purl.org/dc/terms/language")</td>

<td>[`schema:inLanguage`](http://schema.org/inLanguage "http://schema.org/inLanguage")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>source metadata</td>

<td>[`dct:source`](http://dublincore.org/documents/dcmi-terms/#terms-source "http://purl.org/dc/terms/source")</td>

<td>[`schema:isBasedOnUrl`](http://schema.org/isBasedOnUrl "http://schema.org/isBasedOnUrl")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>title</td>

<td>[`dct:title`](http://dublincore.org/documents/dcmi-terms/#terms-title "http://purl.org/dc/terms/title")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-checksum">Checksum</a>

TBD [[formal definition](#mapping-formal-checksum)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>algorithm</td>

<td>[`spdx:algorithm`](http://spdx.org/rdf/spdx-terms-v2.0/objectproperties/algorithm___-1614899588.html "http://spdx.org/rdf/terms#algorithm")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>checksum value</td>

<td>[`spdx:checksumValue`](http://spdx.org/rdf/spdx-terms-v2.0/dataproperties/checksumValue___-1263904517.html "http://spdx.org/rdf/terms#checksumValue")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-document">Document</a>

TBD [[formal definition](#mapping-formal-document)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>description</td>

<td>[`dct:description`](http://dublincore.org/documents/dcmi-terms/#terms-description "http://purl.org/dc/terms/description")</td>

<td>[`schema:description`](http://schema.org/description "http://schema.org/description")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>title</td>

<td>[`dct:title`](http://dublincore.org/documents/dcmi-terms/#terms-title "http://purl.org/dc/terms/title")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-identifier">Identifier</a>

TBD [[formal definition](#mapping-formal-identifier)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Mandatory">M</abbr></td>

<td>notation</td>

<td>[`skos:notation`](https://www.w3.org/2009/08/skos-reference/skos.html#notation "http://www.w3.org/2004/02/skos/core#notation")</td>

<td>[`schema:productID`](http://schema.org/productID "http://schema.org/productID")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-kind">Kind</a>

These properties should be used with [`schema:ContactPoint`](http://schema.org/ContactPoint). [[formal definition](#mapping-formal-kind)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP IG</td>

<td><abbr title="Recommended">R</abbr></td>

<td>name</td>

<td>[`vcard:fn`](https://www.w3.org/TR/vcard-rdf/#d4e891 "http://www.w3.org/2006/vcard/ns#fn")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>DCAT-AP IG</td>

<td><abbr title="Recommended">R</abbr></td>

<td rowspan="2">email</td>

<td rowspan="2">[`vcard:hasEmail`](https://www.w3.org/TR/vcard-rdf/#d4e183 "http://www.w3.org/2006/vcard/ns#hasEmail")</td>

<td rowspan="2">[`schema:email`](http://schema.org/email "http://schema.org/email")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>organisation name</td>

<td>[`vcard:organization-name`](https://www.w3.org/TR/vcard-rdf/#d4e1077 "http://www.w3.org/2006/vcard/ns#organization-name")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td rowspan="2"><abbr title="Optional">O</abbr></td>

<td rowspan="2">homepage</td>

<td rowspan="2">[`vcard:hasURL`](https://www.w3.org/TR/vcard-rdf/#d4e605 "http://www.w3.org/2006/vcard/ns#hasURL")</td>

<td rowspan="2">[`schema:url`](http://schema.org/url "http://schema.org/url")</td>

</tr>

<tr>

<td>DCAT-AP IG</td>

</tr>

<tr>

<td>DCAT-AP IG</td>

<td><abbr title="Optional">O</abbr></td>

<td>telephone</td>

<td>[`vcard:hasTelephone`](https://www.w3.org/TR/vcard-rdf/#d4e563 "http://www.w3.org/2006/vcard/ns#hasTelephone")</td>

<td>[`schema:telephone`](http://schema.org/name "http://schema.org/telephone")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-location">Location</a>

These properties should be used with [`schema:Place`](http://schema.org/Place). [[formal definition](#mapping-formal-location)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>geographical identifier</td>

<td>[`dct:identifier`](http://dublincore.org/documents/dcmi-terms/#terms-identifier "http://purl.org/dc/terms/identifier")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>geographical identifier / name authority</td>

<td>[`skos:inScheme`](https://www.w3.org/TR/vocab-dcat/#class-inScheme "http://www.w3.org/2004/02/skos/core#inScheme")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD. The "authority" denotes the reference register for the geographical name / identifier (typically, a gazetteer).</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>geographical name</td>

<td>[`skos:prefLabel`](https://www.w3.org/TR/vocab-dcat/#class-prefLabel "http://www.w3.org/2004/02/skos/core#prefLabel")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>geometry</td>

<td>[`locn:geometry`](http://dublincore.org/documents/dcmi-terms/#terms-identifier "http://purl.org/dc/terms/identifier")</td>

<td>[`schema:geo`](http://schema.org/geo "http://schema.org/geo")</td>

<td>

Schema.org expects as value an instance of [`schema:GeoCoordinates`](http://schema.org/GeoCoordinates "http://schema.org/GeoCoordinates") (for points) or [`schema:GeoShape`](http://schema.org/GeoShape "http://schema.org/GeoShape") (for more complex geometries).

LOCN allows any type of geometry, and any type of geometry encoding / representation—including those supported by Schema.org.

As a consequence, the [`locn:geometry`](http://www.w3.org/ns/locn#locn:geometry "http://www.w3.org/ns/locn#geometry") mapping might require further processing to encode the geometry according the encodings supported in Schema.org.

</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-media-type">Media type or extent</a>

TBD [[formal definition](#mapping-formal-media-type)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>label</td>

<td>[`rdfs:label`](http://www.w3.org/TR/2004/REC-rdf-schema-20040210/#ch_label "http://www.w3.org/2000/01/rdf-schema#label")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/startDate")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-period-of-time">Period of time</a>

These properties should be used with [`schema:DateTime`](http://schema.org/DateTime). [[formal definition](#mapping-formal-period-of-time)]

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>start date / time</td>

<td>[`schema:startDate`](http://schema.org/startDate "http://schema.org/startDate")</td>

<td>[`schema:startDate`](http://schema.org/startDate "http://schema.org/startDate")</td>

</tr>

<tr>

<td>DCAT-AP 1.1</td>

<td><abbr title="Optional">O</abbr></td>

<td>end date / time</td>

<td>[`schema:endDate`](http://schema.org/endDate "http://schema.org/endDate")</td>

<td>[`schema:endDate`](http://schema.org/endDate "http://schema.org/endDate")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-reference-system">Reference system</a>

TBD

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>reference system authority</td>

<td>[`skos:inScheme`](https://www.w3.org/TR/vocab-dcat/#class-inScheme "http://www.w3.org/2004/02/skos/core#inScheme")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD. The "authority" denotes the reference register for the reference system.</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>reference system identifier</td>

<td>[`dct:identifier`](http://dublincore.org/documents/dcmi-terms/#terms-identifier "http://purl.org/dc/terms/identifier")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>reference system name</td>

<td>[`skos:prefLabel`](https://www.w3.org/TR/vocab-dcat/#class-prefLabel "http://www.w3.org/2004/02/skos/core#prefLabel")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>reference system type (e.g., spatial, temporal)</td>

<td>[`dct:type`](http://dublincore.org/documents/dcmi-terms/#terms-type "http://purl.org/dc/terms/type")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>reference system version</td>

<td>[`owl:versionInfo`](https://www.w3.org/TR/owl-ref/#versionInfo-def "http://www.w3.org/2002/07/owl#versionInfo")</td>

<td>[`schema:version`](http://schema.org/version "http://schema.org/version")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-rights">Rights statement</a>

TBD

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>name / description</td>

<td>[`rdfs:label`](http://www.w3.org/TR/2004/REC-rdf-schema-20040210/#ch_label "http://www.w3.org/2000/01/rdf-schema#label")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-service">Service</a>

These properties should be used with [`schema:Service`](http://schema.org/Service).

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>access rights</td>

<td>[`dct:accessRights`](http://dublincore.org/documents/dcmi-terms/#terms-accessRights "http://purl.org/dc/terms/accessRights")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>author</td>

<td>[`dct:creator`](http://dublincore.org/documents/dcmi-terms/#terms-creator "http://purl.org/dc/terms/creator")</td>

<td>[`schema:creator`](http://schema.org/creator "http://schema.org/creator")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>conformance result / conformity (data quality)</td>

<td>[`dct:conformsTo`](http://dublincore.org/documents/dcmi-terms/#terms-conformsTo "http://purl.org/dc/terms/conformsTo")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>conforms to</td>

<td>[`dct:conformsTo`](http://dublincore.org/documents/dcmi-terms/#terms-conformsTo "http://purl.org/dc/terms/conformsTo")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>contact point</td>

<td>[`dcat:contactPoint`](https://www.w3.org/TR/vocab-dcat/#property-contactPoint "http://www.w3.org/ns/dcat#contactPoint")</td>

<td>[`schema:contactPoint`](http://schema.org/contactPoint "http://schema.org/contactPoint")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>coupled resource</td>

<td>[`dct:hasPart`](http://dublincore.org/documents/dcmi-terms/#terms-hasPart "http://purl.org/dc/terms/hasPart")</td>

<td>[`schema:hasPart`](http://schema.org/hasPart "http://schema.org/hasPart")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>creation date</td>

<td>[`dct:created`](http://dublincore.org/documents/dcmi-terms/#terms-created "http://purl.org/dc/terms/created")</td>

<td>[`schema:dateCreated`](http://schema.org/dateCreated "http://schema.org/dateCreated")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>description</td>

<td>[`dct:description`](http://dublincore.org/documents/dcmi-terms/#terms-description "http://purl.org/dc/terms/description")</td>

<td>[`schema:description`](http://schema.org/description "http://schema.org/description")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>keyword (free text)</td>

<td>[`dc:subject`](http://dublincore.org/documents/dcmi-terms/#elements-subject "http://purl.org/dc/elements/1.1/subject")</td>

<td>[`schema:keywords`](http://schema.org/keywords "http://schema.org/keywords")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>keyword (from a controlled vocabulary)</td>

<td>[`dct:subject`](http://dublincore.org/documents/dcmi-terms/#terms-subject "http://purl.org/dc/terms/subject")</td>

<td>[`schema:about`](http://schema.org/about "http://schema.org/about")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>language</td>

<td>[`dct:language`](http://dublincore.org/documents/dcmi-terms/#terms-language "http://purl.org/dc/terms/language")</td>

<td>[`schema:inLanguage`](http://schema.org/inLanguage "http://schema.org/inLanguage")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>publisher</td>

<td>[`dct:publisher`](http://dublincore.org/documents/dcmi-terms/#terms-publisher "http://purl.org/dc/terms/publisher")</td>

<td>[`schema:publisher`](http://schema.org/publisher "http://schema.org/publisher")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>release date</td>

<td>[`dct:issued`](http://dublincore.org/documents/dcmi-terms/#terms-issued "http://purl.org/dc/terms/issued")</td>

<td>[`schema:datePublished`](http://schema.org/datePublished "http://schema.org/datePublished")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>resource locator</td>

<td>[`foaf:homepage`](http://xmlns.com/foaf/spec/#term_homepage "http://xmlns.com/foaf/0.1/homepage")</td>

<td>[`schema:url`](http://schema.org/url "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>spatial / geographic coverage</td>

<td>[`dct:spatial`](http://dublincore.org/documents/dcmi-terms/#terms-spatial "http://purl.org/dc/terms/spatial")</td>

<td>[`schema:spatial`](http://schema.org/spatial "http://schema.org/spatial")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>spatial data service category</td>

<td>[`dct:type`](http://dublincore.org/documents/dcmi-terms/#terms-type "http://purl.org/dc/terms/type")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>spatial data service type</td>

<td>[`dct:type`](http://dublincore.org/documents/dcmi-terms/#terms-type "http://purl.org/dc/terms/type")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>temporal coverage</td>

<td>[`dct:temporal`](http://dublincore.org/documents/dcmi-terms/#terms-temporal "http://purl.org/dc/terms/temporal")</td>

<td>[`schema:datasetTimeInterval`](http://schema.org/datasetTimeInterval "http://schema.org/datasetTimeInterval")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>title</td>

<td>[`dct:title`](http://dublincore.org/documents/dcmi-terms/#terms-title "http://purl.org/dc/terms/title")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>type</td>

<td>[`dct:type`](http://dublincore.org/documents/dcmi-terms/#terms-type "http://purl.org/dc/terms/type")</td>

<td>[`schema:??`](http://schema.org/?? "http://schema.org/??")</td>

<td>TBD</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>update / modification date</td>

<td>[`dct:modified`](http://dublincore.org/documents/dcmi-terms/#terms-modified "http://purl.org/dc/terms/modified")</td>

<td>[`schema:dateModified`](http://schema.org/dateModified "http://schema.org/dateModified")</td>

</tr>

</tbody>

</table>



#### <a name="mapping-properties-standard">Standard</a>

TBD

<table>

<thead>

<tr>

<th colspan="4">DCAT-AP</th>

<th rowspan="2">Schema.org</th>

<th rowspan="2">Comments</th>

</tr>

<tr>

<th>Specification</th>

<th><abbr title="Obligation">Obl.</abbr></th>

<th>Label</th>

<th>QName</th>

</tr>

</thead>

<tbody>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>creation date</td>

<td>[`dct:created`](http://dublincore.org/documents/dcmi-terms/#terms-created "http://purl.org/dc/terms/created")</td>

<td>[`schema:dateCreated`](http://schema.org/dateCreated "http://schema.org/dateCreated")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>release date</td>

<td>[`dct:issued`](http://dublincore.org/documents/dcmi-terms/#terms-issued "http://purl.org/dc/terms/issued")</td>

<td>[`schema:datePublished`](http://schema.org/datePublished "http://schema.org/datePublished")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>title</td>

<td>[`dct:title`](http://dublincore.org/documents/dcmi-terms/#terms-title "http://purl.org/dc/terms/title")</td>

<td>[`schema:name`](http://schema.org/name "http://schema.org/name")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>update / modification date</td>

<td>[`dct:modified`](http://dublincore.org/documents/dcmi-terms/#terms-modified "http://purl.org/dc/terms/modified")</td>

<td>[`schema:dateModified`](http://schema.org/dateModified "http://schema.org/dateModified")</td>

</tr>

<tr>

<td>GeoDCAT-AP 1.0</td>

<td><abbr title="Optional">O</abbr></td>

<td>version</td>

<td>[`owl:versionInfo`](https://www.w3.org/TR/owl-ref/#versionInfo-def "http://www.w3.org/2002/07/owl#versionInfo")</td>

<td>[`schema:version`](http://schema.org/version "http://schema.org/version")</td>

</tr>

</tbody>

</table>

