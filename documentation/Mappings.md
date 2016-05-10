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


