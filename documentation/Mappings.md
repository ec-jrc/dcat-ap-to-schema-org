<article>

<header>

# Mappings defined in DCAT-AP+Schema.org

</header>

<section>

## Status of this document

This document presents a proposal for mapping the relevant terms from the [DCAT Application Profile for European Data Portals](https://joinup.ec.europa.eu/asset/dcat_application_profile/) (DCAT-AP) to the [Schema.org vocabulary](http://schema.org/).

This document is a draft meant to report work in progress. As such, it can be updated any time and it must be considered as unstable.

</section>

<section>

## Abstract

This documents illustrates the mappings defined in DCAT-AP+Schema.org.

The background and methodology for the design of DCAT-AP+Schema.org are illustrated in a separate document:

[<cite>DCAT-AP+Schema.org: Background & methodology</cite>](./Background.md)

</section>

<nav>

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

</nav>

<section id="introduction">

## <a name="introduction">Introduction</a>

The mappings illustrated in this document cover the metadata elements defined in the following specifications:

*   [DCAT-AP v1.1](https://joinup.ec.europa.eu/asset/dcat_application_profile/asset_release/dcat-ap-v11) (<time datetime="2015-10-23">23 October 2015</time>)
*   [GeoDCAT-AP v1.0](https://joinup.ec.europa.eu/asset/dcat_application_profile/asset_release/geodcat-ap-v10) (<time datetime="2015-12-23">23 December 2015</time>)
*   [DCAT-AP Implementation Guidelines](https://joinup.ec.europa.eu/asset/dcat-ap_implementation_guidelines/) (DCAT-AP IG)

For each of the mapped elements and the reference controlled vocabularies, the relevant specification is referred to in the tables included in the following sections.

For Schema.org, the reference specification is [Schema.org 2.2](http://schema.org/version/2.2/) (<time datetime="2015-11-05">5 November 2015</time>).

This document includes, in a separate section, also a tentative formal definition of the mappings, in form of SPARQL queries.

**NB**: In the current version, this document does not include mappings concerning the GeoDCAT-AP representation of agent roles and conformance results based on the W3C PROV Ontology [[PROV-O](https://www.w3.org/TR/prov-o/)].

</section>

<section id="used-namespaces">

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

</section>

<section id="ref-code-lists">

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

</section>

<section>

## <a name="mapping-summary">Mapping summary</a>

The following section summarises the alignments defined in DCAT-AP+Schema.org.

The alignments are grouped as follows:

*   Alignments for DCAT-AP classes
*   Alignments for DCAT-AP properties concerning:
    *   mandatory classes
    *   recommended classes
    *   optional classes

<section id="mapping-classes">

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

</section>

<section id="mapping-properties-mandatory">

### <a name="mapping-properties-mandatory">Properties for mandatory classes</a>

<section id="mapping-properties-agent">

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

</section>

<section id="mapping-properties-catalogue">

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

</section>

<section id="mapping-properties-dataset">

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

</section>

</section>

<section id="mapping-properties-recommended">

### <a name="mapping-properties-recommended">Properties for recommended classes</a>

<section id="mapping-properties-category">

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

</section>

<section id="mapping-properties-category-scheme">

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

</section>

<section id="mapping-properties-distribution">

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

</section>

<section id="mapping-properties-licence">

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

</section>

</section>

<section id="mapping-properties-optional">

### <a name="mapping-properties-optional">Properties for optional classes</a>

<section id="mapping-properties-catalogue-record">

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

</section>

<section id="mapping-properties-checksum">

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

</section>

<section id="mapping-properties-document">

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

</section>

<section id="mapping-properties-identifier">

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

</section>

<section id="mapping-properties-kind">

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

</section>

<section id="mapping-properties-location">

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

</section>

<section id="mapping-properties-media-type">

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

</section>

<section id="mapping-properties-period-of-time">

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

</section>

<section id="mapping-properties-reference-system">

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

</section>

<section id="mapping-properties-rights">

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

</section>

<section id="mapping-properties-service">

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

</section>

<section id="mapping-properties-standard">

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

</section>

</section>

</section>

<section id="mapping-formal">

## <a name="mapping-formal">Formal definition</a>

The following sections provide a tentative formal definition, in the form of [SPARQL `CONSTRUCT` queries](https://www.w3.org/TR/sparql11-query/#construct), of the mappings illustrated in the previous section.

The mappings have been defined in a modular way, with a separate SPARQL query for each of the DCAT-AP classes, and related properties. A complete representation of a given resource (e.g., a dataset) and related resource (e.g., distribution, licence, publisher) can be obtained by combining the relevant SPARQL queries.

The defined SPARQL queries can be tested on the SPARQL endpoint of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/), that makes available a snapshot of the metadata records, in GeoDCAT-AP format, harvested by the [INSPIRE Geoportal](http://inspire-geoportal.ec.europa.eu/).

<section id="mapping-formal-mandatory">

### <a name="mapping-formal-mandatory">Mandatory classes</a>

<section id="mapping-formal-agent">

#### <a name="mapping-formal-agent">Agent</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FAgent+%0D%0A++++a+%3FschemaPerson+%3B%0D%0A++++a+%3FschemaOrganization+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAgentType+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aurl+%3FworkplaceHomepage%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AAgent+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3APerson+BIND%28schema%3APerson+AS+%3FschemaPerson%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AOrganization+BIND%28schema%3AOrganization+AS+%3FschemaOrganization%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Aname+%3Fname+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FAgent+dct%3Atype+%3FAgentType+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Ambox+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3AworkplaceHomepage+%3FworkplaceHomepage+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FAgent+%0D%0A++++a+%3FschemaPerson+%3B%0D%0A++++a+%3FschemaOrganization+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAgentType+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aurl+%3FworkplaceHomepage%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AAgent+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3APerson+BIND%28schema%3APerson+AS+%3FschemaPerson%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AOrganization+BIND%28schema%3AOrganization+AS+%3FschemaOrganization%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Aname+%3Fname+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FAgent+dct%3Atype+%3FAgentType+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Ambox+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3AworkplaceHomepage+%3FworkplaceHomepage+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FAgent+%0D%0A++++a+%3FschemaPerson+%3B%0D%0A++++a+%3FschemaOrganization+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAgentType+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aurl+%3FworkplaceHomepage%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AAgent+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3APerson+BIND%28schema%3APerson+AS+%3FschemaPerson%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AOrganization+BIND%28schema%3AOrganization+AS+%3FschemaOrganization%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Aname+%3Fname+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FAgent+dct%3Atype+%3FAgentType+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Ambox+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3AworkplaceHomepage+%3FworkplaceHomepage+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX foaf:   <http://xmlns.com/foaf/0.1/>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?Agent 
        a ?schemaPerson ;
        a ?schemaOrganization ;
        schema:name ?name ;
    #    schema:?? ?AgentType ;
        schema:email ?email ;
        schema:url ?workplaceHomepage
    } WHERE {
      OPTIONAL { ?Agent a foaf:Agent . }
      OPTIONAL { ?Agent a foaf:Person BIND(schema:Person AS ?schemaPerson) . }
      OPTIONAL { ?Agent a foaf:Organization BIND(schema:Organization AS ?schemaOrganization) . }
      OPTIONAL { ?Agent foaf:name ?name . }
    #  OPTIONAL { ?Agent dct:type ?AgentType . }
      OPTIONAL { ?Agent foaf:mbox ?email . }
      OPTIONAL { ?Agent foaf:workplaceHomepage ?workplaceHomepage . }
    }

</section>

<section id="mapping-formal-catalogue">

#### <a name="mapping-formal-catalogue">Catalogue</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogue+a+schema%3ADataCatalog+%3B%0D%0A++++schema%3Adataset+%3FDataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3Aurl+%3Fhomepage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3AhasPart+%3FChildCatalogue+%3B%0D%0A++++schema%3AitemListElement+%3FCatalogueRecord+%3B%0D%0A++++schema%3Aspatial+%3FLocation%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogue+a+dcat%3ACatalog+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Adataset+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+foaf%3Ahomepage+%3Fhomepage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dcat%3AthemeTaxonomy+%3FCategoryScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3AhasPart+%3FChildCatalogue+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Arecord+%3FCatalogueRecord+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aspatial+%3FLocation+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogue+a+schema%3ADataCatalog+%3B%0D%0A++++schema%3Adataset+%3FDataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3Aurl+%3Fhomepage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3AhasPart+%3FChildCatalogue+%3B%0D%0A++++schema%3AitemListElement+%3FCatalogueRecord+%3B%0D%0A++++schema%3Aspatial+%3FLocation%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogue+a+dcat%3ACatalog+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Adataset+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+foaf%3Ahomepage+%3Fhomepage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dcat%3AthemeTaxonomy+%3FCategoryScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3AhasPart+%3FChildCatalogue+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Arecord+%3FCatalogueRecord+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aspatial+%3FLocation+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogue+a+schema%3ADataCatalog+%3B%0D%0A++++schema%3Adataset+%3FDataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3Aurl+%3Fhomepage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3AhasPart+%3FChildCatalogue+%3B%0D%0A++++schema%3AitemListElement+%3FCatalogueRecord+%3B%0D%0A++++schema%3Aspatial+%3FLocation%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogue+a+dcat%3ACatalog+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Adataset+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+foaf%3Ahomepage+%3Fhomepage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dcat%3AthemeTaxonomy+%3FCategoryScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3AhasPart+%3FChildCatalogue+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Arecord+%3FCatalogueRecord+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aspatial+%3FLocation+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dcat:   <http://www.w3.org/ns/dcat#>
    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX foaf:   <http://xmlns.com/foaf/0.1/>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?Catalogue a schema:DataCatalog ;
        schema:dataset ?Dataset ;
        schema:description ?description ;
        schema:publisher ?Publisher ;
        schema:name ?title ;
        schema:url ?homepage ;
        schema:inLanguage ?Language ;
        schema:license ?Licence ;
        schema:datePublished ?issued ;
        schema:dateModified ?modified ;
        schema:hasPart ?ChildCatalogue ;
        schema:itemListElement ?CatalogueRecord ;
        schema:spatial ?Location
    } WHERE {
      OPTIONAL { ?Catalogue a dcat:Catalog . }
      OPTIONAL { ?Catalogue dcat:dataset ?Dataset . }
      OPTIONAL { ?Catalogue dct:description ?description . }
      OPTIONAL { ?Catalogue dct:publisher ?Publisher . }
      OPTIONAL { ?Catalogue dct:title ?title . }
      OPTIONAL { ?Catalogue foaf:homepage ?homepage . }
      OPTIONAL { ?Catalogue dct:language ?Language . }
      OPTIONAL { ?Catalogue dct:license ?Licence . }
      OPTIONAL { ?Catalogue dct:issued ?issued . }
    #  OPTIONAL { ?Catalogue dcat:themeTaxonomy ?CategoryScheme . }
      OPTIONAL { ?Catalogue dct:modified ?modified . }
      OPTIONAL { ?Catalogue dct:hasPart ?ChildCatalogue . }
      OPTIONAL { ?Catalogue dcat:record ?CatalogueRecord . }
    #  OPTIONAL { ?Catalogue dct:rights ?Rights . }
      OPTIONAL { ?Catalogue dct:spatial ?Location . }
    }

</section>

<section id="mapping-formal-dataset">

#### <a name="mapping-formal-dataset">Dataset</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDataset+a+schema%3ADataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adistribution+%3FDistribution+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A%23++++schema%3A%3F%3F+%3FFrequency+%3B%0D%0A%23++++schema%3A%3F%3F+%3FPreviousDatasetVersion+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3FNextDatasetVersion+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAlternateIdentifier+%3B%0D%0A++++schema%3Aurl+%3FLandingPage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AcopyrightHolder+%3FCopyrightHolder+%3B%0D%0A%23++++schema%3A%3F%3F+%3FProvenanceStatement+%3B%0D%0A++++schema%3Amentions+%3FRelatedResource+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FDatasetSample+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceDataset+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aabout+%3FSubject+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aversion+%3FversionNumber+%0D%0A%23++++schema%3A%3F%3F+%3FversionNotes+%3B%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDataset+a+dcat%3ADataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Adistribution+%3FDistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Akeyword+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Atheme+%3FCategory+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+foaf%3Apage+%3FDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccrualPeriodicity+%3FFrequency+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AhasVersion+%3FPreviousDatasetVersion+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AisVersionOf+%3FNextDatasetVersion+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Aidentifier+%3FAlternateIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AlandingPage+%3FLandingPage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3ArightsHolder+%3FCopyrightHolder+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3Aprovenance+%3FProvenanceStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Arelation+%3FRelatedResource+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Asample+%3FDatasetSample+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asource+%3FSourceDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asubject+%3FSubject+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+owl%3AversionInfo+%3FversionNumber+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3AversionNotes+%3FversionNotes+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDataset+a+schema%3ADataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adistribution+%3FDistribution+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A%23++++schema%3A%3F%3F+%3FFrequency+%3B%0D%0A%23++++schema%3A%3F%3F+%3FPreviousDatasetVersion+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3FNextDatasetVersion+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAlternateIdentifier+%3B%0D%0A++++schema%3Aurl+%3FLandingPage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AcopyrightHolder+%3FCopyrightHolder+%3B%0D%0A%23++++schema%3A%3F%3F+%3FProvenanceStatement+%3B%0D%0A++++schema%3Amentions+%3FRelatedResource+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FDatasetSample+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceDataset+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aabout+%3FSubject+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aversion+%3FversionNumber+%0D%0A%23++++schema%3A%3F%3F+%3FversionNotes+%3B%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDataset+a+dcat%3ADataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Adistribution+%3FDistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Akeyword+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Atheme+%3FCategory+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+foaf%3Apage+%3FDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccrualPeriodicity+%3FFrequency+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AhasVersion+%3FPreviousDatasetVersion+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AisVersionOf+%3FNextDatasetVersion+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Aidentifier+%3FAlternateIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AlandingPage+%3FLandingPage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3ArightsHolder+%3FCopyrightHolder+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3Aprovenance+%3FProvenanceStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Arelation+%3FRelatedResource+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Asample+%3FDatasetSample+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asource+%3FSourceDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asubject+%3FSubject+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+owl%3AversionInfo+%3FversionNumber+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3AversionNotes+%3FversionNotes+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDataset+a+schema%3ADataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adistribution+%3FDistribution+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A%23++++schema%3A%3F%3F+%3FFrequency+%3B%0D%0A%23++++schema%3A%3F%3F+%3FPreviousDatasetVersion+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3FNextDatasetVersion+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAlternateIdentifier+%3B%0D%0A++++schema%3Aurl+%3FLandingPage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AcopyrightHolder+%3FCopyrightHolder+%3B%0D%0A%23++++schema%3A%3F%3F+%3FProvenanceStatement+%3B%0D%0A++++schema%3Amentions+%3FRelatedResource+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FDatasetSample+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceDataset+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aabout+%3FSubject+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aversion+%3FversionNumber+%0D%0A%23++++schema%3A%3F%3F+%3FversionNotes+%3B%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDataset+a+dcat%3ADataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Adistribution+%3FDistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Akeyword+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Atheme+%3FCategory+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+foaf%3Apage+%3FDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccrualPeriodicity+%3FFrequency+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AhasVersion+%3FPreviousDatasetVersion+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AisVersionOf+%3FNextDatasetVersion+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Aidentifier+%3FAlternateIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AlandingPage+%3FLandingPage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3ArightsHolder+%3FCopyrightHolder+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3Aprovenance+%3FProvenanceStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Arelation+%3FRelatedResource+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Asample+%3FDatasetSample+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asource+%3FSourceDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asubject+%3FSubject+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+owl%3AversionInfo+%3FversionNumber+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3AversionNotes+%3FversionNotes+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX adms:   <http://www.w3.org/ns/adms#>
    PREFIX cnt:    <http://www.w3.org/2011/content#>
    PREFIX dcat:   <http://www.w3.org/ns/dcat#>
    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX foaf:   <http://xmlns.com/foaf/0.1/>
    PREFIX owl:    <http://www.w3.org/2002/07/owl#>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?Dataset a schema:Dataset ;
        schema:description ?description ;
        schema:name ?title ;
        schema:contactPoint ?Kind ;
        schema:distribution ?Distribution ;
        schema:keywords ?keyword ;
        schema:publisher ?Publisher ;
        schema:about ?Category ;
    #    schema:?? ?AccessRights ;
        schema:creator ?Author ;
    #    schema:?? ?Standard ;
        schema:dateCreated ?created ;
        schema:mainEntityOfPage ?Document ;
    #    schema:?? ?Frequency ;
    #    schema:?? ?PreviousDatasetVersion ;
        schema:productID ?identifier ;
    #    schema:?? ?NextDatasetVersion ;
    #    schema:?? ?AlternateIdentifier ;
        schema:url ?LandingPage ;
        schema:inLanguage ?Language ;
        schema:copyrightHolder ?CopyrightHolder ;
    #    schema:?? ?ProvenanceStatement ;
        schema:mentions ?RelatedResource ;
        schema:datePublished ?issued ;
    #    schema:?? ?DatasetSample ;
        schema:isBasedOnUrl ?SourceDataset ;
        schema:spatial ?Location ;
        schema:datasetTimeInterval ?PeriodOfTime ;
        schema:about ?Subject ;
        schema:dateModified ?modified ;
        schema:version ?versionNumber 
    #    schema:?? ?versionNotes ;
    } WHERE {
      OPTIONAL { ?Dataset a dcat:Dataset . }
      OPTIONAL { ?Dataset dct:description ?description . }
      OPTIONAL { ?Dataset dct:title ?title . }
      OPTIONAL { ?Dataset dcat:contactPoint ?Kind . }
      OPTIONAL { ?Dataset dcat:distribution ?Distribution . }
      OPTIONAL { ?Dataset dcat:keyword ?keyword . }
      OPTIONAL { ?Dataset dct:publisher ?Publisher . }
      OPTIONAL { ?Dataset dcat:theme ?Category . }
    #  OPTIONAL { ?Dataset dct:accessRights ?AccessRights . }
      OPTIONAL { ?Dataset dct:creator ?Author . }
    #  OPTIONAL { ?Dataset dct:conformsTo ?Standard . }
      OPTIONAL { ?Dataset dct:created ?created . }
      OPTIONAL { ?Dataset foaf:page ?Document . }
    #  OPTIONAL { ?Dataset dct:accrualPeriodicity ?Frequency . }
    #  OPTIONAL { ?Dataset dct:hasVersion ?PreviousDatasetVersion . }
      OPTIONAL { ?Dataset dct:identifier ?identifier . }
    #  OPTIONAL { ?Dataset dct:isVersionOf ?NextDatasetVersion . }
    #  OPTIONAL { ?Dataset adms:identifier ?AlternateIdentifier . }
      OPTIONAL { ?Dataset dcat:landingPage ?LandingPage . }
      OPTIONAL { ?Dataset dct:language ?Language . }
      OPTIONAL { ?Dataset dct:rightsHolder ?CopyrightHolder . }
    #  OPTIONAL { ?Dataset dct:provenance ?ProvenanceStatement . }
      OPTIONAL { ?Dataset dct:relation ?RelatedResource . }
      OPTIONAL { ?Dataset dct:issued ?issued . }
    #  OPTIONAL { ?Dataset adms:sample ?DatasetSample . }
      OPTIONAL { ?Dataset dct:source ?SourceDataset . }
      OPTIONAL { ?Dataset dct:spatial ?Location . }
      OPTIONAL { ?Dataset dct:temporal ?PeriodOfTime . }
      OPTIONAL { ?Dataset dct:subject ?Subject . }
      OPTIONAL { ?Dataset dct:modified ?modified . }
      OPTIONAL { ?Dataset owl:versionInfo ?versionNumber . }
    #  OPTIONAL { ?Dataset adms:versionNotes ?versionNotes . }
    }

</section>

</section>

<section id="mapping-formal-recommended">

### <a name="mapping-formal-recommended">Recommended classes</a>

<section id="mapping-formal-category">

#### <a name="mapping-formal-category">Category</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategory+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3FprefLabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategory+a+skos%3AConcept+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategory+skos%3AprefLabel+%3FprefLabel+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCategory+skos%3AinScheme+%3FCategoryScheme+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategory+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3FprefLabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategory+a+skos%3AConcept+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategory+skos%3AprefLabel+%3FprefLabel+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCategory+skos%3AinScheme+%3FCategoryScheme+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategory+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3FprefLabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategory+a+skos%3AConcept+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategory+skos%3AprefLabel+%3FprefLabel+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCategory+skos%3AinScheme+%3FCategoryScheme+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX schema: <http://schema.org/>
    PREFIX skos:   <http://www.w3.org/2004/02/skos/core#>

    CONSTRUCT {
      ?Category 
    #    a schema:?? ;
        schema:name ?prefLabel 
    } WHERE {
      OPTIONAL { ?Category a skos:Concept . }
      OPTIONAL { ?Category skos:prefLabel ?prefLabel . }
    #  OPTIONAL { ?Category skos:inScheme ?CategoryScheme . }
    }

</section>

<section id="mapping-formal-category-scheme">

#### <a name="mapping-formal-category-scheme">Category scheme</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategoryScheme+a+schema%3AEnumeration+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+a+skos%3AConceptScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategoryScheme+a+schema%3AEnumeration+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+a+skos%3AConceptScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategoryScheme+a+schema%3AEnumeration+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+a+skos%3AConceptScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX schema: <http://schema.org/>
    PREFIX skos:   <http://www.w3.org/2004/02/skos/core#>

    CONSTRUCT {
      ?CategoryScheme a schema:Enumeration ;
        schema:name ?title ;
        schema:dateCreated ?created ;
        schema:datePublished ?issued ;
        schema:dateModified ?modified 
    } WHERE {
      OPTIONAL { ?CategoryScheme a skos:ConceptScheme . }
      OPTIONAL { ?CategoryScheme dct:title ?title . }
      OPTIONAL { ?CategoryScheme dct:created ?created . }
      OPTIONAL { ?CategoryScheme dct:issued ?issued . }
      OPTIONAL { ?CategoryScheme dct:modified ?modified . }
    }

</section>

<section id="mapping-formal-distribution">

#### <a name="mapping-formal-distribution">Distribution</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+spdx%3A+++%3Chttp%3A%2F%2Fspdx.org%2Frdf%2Fterms%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDistribution+a+schema%3ADataDownload+%3B%0D%0A++++schema%3AcontentURL+%3FaccessURL+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AencodingFormat+%3FFormat+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AcontentSize+%3FbyteSize+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A++++schema%3AcontentURL+%3FdownloadURL+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AfileFormat+%3FMediaType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDistribution+a+dcat%3ADistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AaccessURL+%3FaccessURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aformat+%3FFormat+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AbyteSize+%3FbyteSize+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+spdx%3Achecksum+%3FChecksum+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+foaf%3Apage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AdownloadURL+%3FdownloadURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AmediaType+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3Arights+%3FRights+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3ArepresentationTechnique+%3FSpatialRepresentationType+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3Astatus+%3FStatus+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+spdx%3A+++%3Chttp%3A%2F%2Fspdx.org%2Frdf%2Fterms%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDistribution+a+schema%3ADataDownload+%3B%0D%0A++++schema%3AcontentURL+%3FaccessURL+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AencodingFormat+%3FFormat+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AcontentSize+%3FbyteSize+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A++++schema%3AcontentURL+%3FdownloadURL+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AfileFormat+%3FMediaType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDistribution+a+dcat%3ADistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AaccessURL+%3FaccessURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aformat+%3FFormat+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AbyteSize+%3FbyteSize+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+spdx%3Achecksum+%3FChecksum+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+foaf%3Apage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AdownloadURL+%3FdownloadURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AmediaType+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3Arights+%3FRights+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3ArepresentationTechnique+%3FSpatialRepresentationType+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3Astatus+%3FStatus+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+spdx%3A+++%3Chttp%3A%2F%2Fspdx.org%2Frdf%2Fterms%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDistribution+a+schema%3ADataDownload+%3B%0D%0A++++schema%3AcontentURL+%3FaccessURL+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AencodingFormat+%3FFormat+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AcontentSize+%3FbyteSize+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A++++schema%3AcontentURL+%3FdownloadURL+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AfileFormat+%3FMediaType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDistribution+a+dcat%3ADistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AaccessURL+%3FaccessURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aformat+%3FFormat+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AbyteSize+%3FbyteSize+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+spdx%3Achecksum+%3FChecksum+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+foaf%3Apage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AdownloadURL+%3FdownloadURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AmediaType+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3Arights+%3FRights+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3ArepresentationTechnique+%3FSpatialRepresentationType+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3Astatus+%3FStatus+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX adms:   <http://www.w3.org/ns/adms#>
    PREFIX cnt:    <http://www.w3.org/2011/content#>
    PREFIX dcat:   <http://www.w3.org/ns/dcat#>
    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX foaf:   <http://xmlns.com/foaf/0.1/>
    PREFIX schema: <http://schema.org/>
    PREFIX spdx:   <http://spdx.org/rdf/terms#>

    CONSTRUCT {
      ?Distribution a schema:DataDownload ;
        schema:contentURL ?accessURL ;
        schema:description ?description ;
        schema:encodingFormat ?Format ;
        schema:license ?Licence ;
        schema:contentSize ?byteSize ;
        schema:mainEntityOfPage ?Document ;
        schema:contentURL ?downloadURL ;
        schema:inLanguage ?Language ;
        schema:fileFormat ?MediaType ;
        schema:datePublished ?issued ;
        schema:dateModified ?modified ;
        schema:name ?title 
    } WHERE {
      OPTIONAL { ?Distribution a dcat:Distribution . }
      OPTIONAL { ?Distribution dcat:accessURL ?accessURL . }
      OPTIONAL { ?Distribution dct:description ?description . }
      OPTIONAL { ?Distribution dct:format ?Format . }
      OPTIONAL { ?Distribution dct:license ?Licence . }
      OPTIONAL { ?Distribution dcat:byteSize ?byteSize . }
      OPTIONAL { ?Distribution cnt:characterEncoding ?characterEncoding . }
      OPTIONAL { ?Distribution spdx:checksum ?Checksum . }
      OPTIONAL { ?Distribution foaf:page ?Document . }
      OPTIONAL { ?Distribution dcat:downloadURL ?downloadURL . }
      OPTIONAL { ?Distribution dct:language ?Language . }
    #  OPTIONAL { ?Distribution dct:conformsTo ?Standard . }
      OPTIONAL { ?Distribution dcat:mediaType ?MediaType . }
      OPTIONAL { ?Distribution dct:issued ?issued . }
    #  OPTIONAL { ?Distribution dct:rights ?Rights . }
    #  OPTIONAL { ?Distribution adms:representationTechnique ?SpatialRepresentationType . }
    #  OPTIONAL { ?Distribution adms:status ?Status . }
      OPTIONAL { ?Distribution dct:title ?title . }
      OPTIONAL { ?Distribution dct:modified ?modified . }
    }

</section>

<section id="mapping-formal-licence">

#### <a name="mapping-formal-licence">Licence document</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLicence+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FLicenceType+%3B%0D%0A++++schema%3Aname+%3Flabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+a+dct%3ALicenseDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLicence+dct%3Atype+%3FLicenceType+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLicence+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FLicenceType+%3B%0D%0A++++schema%3Aname+%3Flabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+a+dct%3ALicenseDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLicence+dct%3Atype+%3FLicenceType+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLicence+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FLicenceType+%3B%0D%0A++++schema%3Aname+%3Flabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+a+dct%3ALicenseDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLicence+dct%3Atype+%3FLicenceType+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?Licence 
    #    a schema:?? ;
    #    schema:?? ?LicenceType ;
        schema:name ?label 
    } WHERE {
      OPTIONAL { ?Resource dct:license ?Licence . }
      OPTIONAL { ?Licence a dct:LicenseDocument . }
    #  OPTIONAL { ?Licence dct:type ?LicenceType . }
      OPTIONAL { ?Licence rdfs:label ?label . }
    }

</section>

</section>

<section id="mapping-formal-optional">

### <a name="mapping-formal-optional">Optional classes</a>

<section id="mapping-formal-catalogue-record">

#### <a name="mapping-formal-catalogue-record">Catalogue record</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogueRecord+a+schema%3AListItem+%3B%0D%0A++++schema%3Aitem+%3FDataset+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A%23++++schema%3A%3F%3F+%3FMetadataStandard+%3B%0D%0A%23++++schema%3A%3F%3F+%3FChangeType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FcharacterEncoding+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceMetadata+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+a+dcat%3ACatalogRecord+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+foaf%3AprimaryTopic+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+dct%3AconformsTo+%3FMetadataStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+adms%3Astatus+%3FChangeType+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Asource+%3FSourceMetadata+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogueRecord+a+schema%3AListItem+%3B%0D%0A++++schema%3Aitem+%3FDataset+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A%23++++schema%3A%3F%3F+%3FMetadataStandard+%3B%0D%0A%23++++schema%3A%3F%3F+%3FChangeType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FcharacterEncoding+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceMetadata+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+a+dcat%3ACatalogRecord+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+foaf%3AprimaryTopic+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+dct%3AconformsTo+%3FMetadataStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+adms%3Astatus+%3FChangeType+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Asource+%3FSourceMetadata+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogueRecord+a+schema%3AListItem+%3B%0D%0A++++schema%3Aitem+%3FDataset+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A%23++++schema%3A%3F%3F+%3FMetadataStandard+%3B%0D%0A%23++++schema%3A%3F%3F+%3FChangeType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FcharacterEncoding+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceMetadata+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+a+dcat%3ACatalogRecord+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+foaf%3AprimaryTopic+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+dct%3AconformsTo+%3FMetadataStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+adms%3Astatus+%3FChangeType+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Asource+%3FSourceMetadata+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX adms:   <http://www.w3.org/ns/adms#>
    PREFIX cnt:    <http://www.w3.org/2011/content#>
    PREFIX dcat:   <http://www.w3.org/ns/dcat#>
    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX foaf:   <http://xmlns.com/foaf/0.1/>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?CatalogueRecord a schema:ListItem ;
        schema:item ?Dataset ;
        schema:dateModified ?modified ;
    #    schema:?? ?MetadataStandard ;
    #    schema:?? ?ChangeType ;
        schema:datePublished ?issued ;
    #    schema:?? ?characterEncoding ;
        schema:contactPoint ?Kind ;
        schema:description ?description ;
        schema:productID ?identifier ;
        schema:inLanguage ?Language ;
        schema:isBasedOnUrl ?SourceMetadata ;
        schema:name ?title 
    } WHERE {
      OPTIONAL { ?CatalogueRecord a dcat:CatalogRecord . }
      OPTIONAL { ?CatalogueRecord foaf:primaryTopic ?Dataset . }
      OPTIONAL { ?CatalogueRecord dct:modified ?modified . }
    #  OPTIONAL { ?CatalogueRecord dct:conformsTo ?MetadataStandard . }
    #  OPTIONAL { ?CatalogueRecord adms:status ?ChangeType . }
      OPTIONAL { ?CatalogueRecord dct:issued ?issued . }
    #  OPTIONAL { ?CatalogueRecord cnt:characterEncoding ?characterEncoding . }
      OPTIONAL { ?CatalogueRecord dcat:contactPoint ?Kind . }
      OPTIONAL { ?CatalogueRecord dct:description ?description . }
      OPTIONAL { ?CatalogueRecord dct:identifier ?identifier . }
      OPTIONAL { ?CatalogueRecord dct:language ?Language . }
      OPTIONAL { ?CatalogueRecord dct:source ?SourceMetadata . }
      OPTIONAL { ?CatalogueRecord dct:title ?title . }
    }

</section>

<section id="mapping-formal-checksum">

#### <a name="mapping-formal-checksum">Checksum</a>

No mappings have been defined for the relevant properties.

</section>

<section id="mapping-formal-document">

#### <a name="mapping-formal-document">Document</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDocument+%0D%0A%23++++a+schema%3ACreativeWork+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDocument+a+foaf%3ADocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDocument+%0D%0A%23++++a+schema%3ACreativeWork+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDocument+a+foaf%3ADocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDocument+%0D%0A%23++++a+schema%3ACreativeWork+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDocument+a+foaf%3ADocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX foaf:   <http://xmlns.com/foaf/0.1/>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?Document 
    #    a schema:CreativeWork ;
        schema:description ?description ;
        schema:name ?title 
    } WHERE {
      OPTIONAL { ?Document a foaf:Document . }
      OPTIONAL { ?Document dct:description ?description . }
      OPTIONAL { ?Document dct:title ?title . }
    }

</section>

<section id="mapping-formal-optional-identifier">

#### <a name="mapping-formal-optional-identifier">Identifier</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FIdentifier+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AproductID+%3Fnotation+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FIdentifier+a+adms%3AIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FIdentifier+skos%3Anotation+%3Fnotation+.+%7D%0D%0A%7D&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FIdentifier+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AproductID+%3Fnotation+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FIdentifier+a+adms%3AIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FIdentifier+skos%3Anotation+%3Fnotation+.+%7D%0D%0A%7D&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FIdentifier+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AproductID+%3Fnotation+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FIdentifier+a+adms%3AIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FIdentifier+skos%3Anotation+%3Fnotation+.+%7D%0D%0A%7D&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX adms:   <http://www.w3.org/ns/adms#>
    PREFIX schema: <http://schema.org/>
    PREFIX skos:   <http://www.w3.org/2004/02/skos/core#>

    CONSTRUCT {
      ?Identifier 
    #    a schema:?? ;
        schema:productID ?notation 
    } WHERE {
      OPTIONAL { ?Identifier a adms:Identifier . }
      OPTIONAL { ?Identifier skos:notation ?notation . }
    }

</section>

<section id="mapping-formal-kind">

#### <a name="mapping-formal-kind">Kind</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+vcard%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2006%2Fvcard%2Fns%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FKind+a+schema%3AContactPoint+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aname+%3ForganisationName+%3B%0D%0A++++schema%3Aurl+%3Furl+%3B%0D%0A++++schema%3Atelephone+%3Ftelephone+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AIndividual+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AOrganization+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Afn+%3Fname+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasEmail+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Aorganization-name+%3ForganisationName+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasURL+%3Furl+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasTelephone+%3Ftelephone+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+vcard%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2006%2Fvcard%2Fns%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FKind+a+schema%3AContactPoint+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aname+%3ForganisationName+%3B%0D%0A++++schema%3Aurl+%3Furl+%3B%0D%0A++++schema%3Atelephone+%3Ftelephone+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AIndividual+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AOrganization+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Afn+%3Fname+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasEmail+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Aorganization-name+%3ForganisationName+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasURL+%3Furl+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasTelephone+%3Ftelephone+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+vcard%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2006%2Fvcard%2Fns%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FKind+a+schema%3AContactPoint+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aname+%3ForganisationName+%3B%0D%0A++++schema%3Aurl+%3Furl+%3B%0D%0A++++schema%3Atelephone+%3Ftelephone+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AIndividual+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AOrganization+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Afn+%3Fname+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasEmail+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Aorganization-name+%3ForganisationName+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasURL+%3Furl+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasTelephone+%3Ftelephone+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX vcard:   <http://www.w3.org/2006/vcard/ns#>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?Kind a schema:ContactPoint ;
        schema:name ?name ;
        schema:email ?email ;
        schema:name ?organisationName ;
        schema:url ?url ;
        schema:telephone ?telephone 
    } WHERE {
      OPTIONAL { ?Resource dcat:contactPoint ?Kind . }
      OPTIONAL { ?Kind a vcard:Kind . }
      OPTIONAL { ?Kind a vcard:Individual . }
      OPTIONAL { ?Kind a vcard:Organization . }
      OPTIONAL { ?Kind vcard:fn ?name . }
      OPTIONAL { ?Kind vcard:hasEmail ?email . }
      OPTIONAL { ?Kind vcard:organization-name ?organisationName . }
      OPTIONAL { ?Kind vcard:hasURL ?url . }
      OPTIONAL { ?Kind vcard:hasTelephone ?telephone . }
    }

</section>

<section id="mapping-formal-location">

#### <a name="mapping-formal-location">Location</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+locn%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Flocn%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLocation+a+schema%3APlace+%3B%0D%0A%23++++schema%3A%3F%3F+%3FgeographicalIdentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3Fauthority+%3B%0D%0A++++schema%3Aname+%3FgeographicalName+%3B%0D%0A++++schema%3Ageo+%3Fgeometry+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+a+dct%3ALocation+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+dct%3Aidentifier+%3FgeographicalIdentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+skos%3AinScheme+%3Fauthority+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+skos%3AprefLabel+%3FgeographicalName+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+locn%3Ageometry+%3Fgeometry+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+locn%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Flocn%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLocation+a+schema%3APlace+%3B%0D%0A%23++++schema%3A%3F%3F+%3FgeographicalIdentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3Fauthority+%3B%0D%0A++++schema%3Aname+%3FgeographicalName+%3B%0D%0A++++schema%3Ageo+%3Fgeometry+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+a+dct%3ALocation+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+dct%3Aidentifier+%3FgeographicalIdentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+skos%3AinScheme+%3Fauthority+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+skos%3AprefLabel+%3FgeographicalName+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+locn%3Ageometry+%3Fgeometry+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+locn%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Flocn%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLocation+a+schema%3APlace+%3B%0D%0A%23++++schema%3A%3F%3F+%3FgeographicalIdentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3Fauthority+%3B%0D%0A++++schema%3Aname+%3FgeographicalName+%3B%0D%0A++++schema%3Ageo+%3Fgeometry+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+a+dct%3ALocation+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+dct%3Aidentifier+%3FgeographicalIdentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+skos%3AinScheme+%3Fauthority+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+skos%3AprefLabel+%3FgeographicalName+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+locn%3Ageometry+%3Fgeometry+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX locn:   <http://www.w3.org/ns/locn#>
    PREFIX schema: <http://schema.org/>
    PREFIX skos:   <http://www.w3.org/2004/02/skos/core#>

    CONSTRUCT {
      ?Location a schema:Place ;
    #    schema:?? ?geographicalIdentifier ;
    #    schema:?? ?authority ;
        schema:name ?geographicalName ;
        schema:geo ?geometry 
    } WHERE {
      OPTIONAL { ?Resource dct:spatial ?Location . }
      OPTIONAL { ?Location a dct:Location . }
    #  OPTIONAL { ?Location dct:identifier ?geographicalIdentifier . }
    #  OPTIONAL { ?Location skos:inScheme ?authority . }
      OPTIONAL { ?Location skos:prefLabel ?geographicalName . }
      OPTIONAL { ?Location locn:geometry ?geometry . }
    }

</section>

<section id="mapping-formal-media-type">

#### <a name="mapping-formal-media-type">Media type or extent</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FMediaType+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aformat+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+a+dct%3AMediaTypeOrExtent+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FMediaType+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aformat+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+a+dct%3AMediaTypeOrExtent+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FMediaType+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aformat+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+a+dct%3AMediaTypeOrExtent+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?MediaType 
    #    a schema:?? ;
        schema:name ?label
    } WHERE {
      OPTIONAL { ?Resource dct:format ?MediaType . }
      OPTIONAL { ?MediaType a dct:MediaTypeOrExtent . }
      OPTIONAL { ?MediaType rdfs:label ?label . }
    }

</section>

<section id="mapping-formal-period-of-time">

#### <a name="mapping-formal-period-of-time">Period of time</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FPeriodOfTime+a+schema%3ADateTime+%3B%0D%0A++++schema%3AstartDate+%3FstartDate+%3B%0D%0A++++schema%3AendDate+%3FendDate+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+a+dct%3APeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AstartDate+%3FstartDate+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AendDate+%3FendDate+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FPeriodOfTime+a+schema%3ADateTime+%3B%0D%0A++++schema%3AstartDate+%3FstartDate+%3B%0D%0A++++schema%3AendDate+%3FendDate+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+a+dct%3APeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AstartDate+%3FstartDate+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AendDate+%3FendDate+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FPeriodOfTime+a+schema%3ADateTime+%3B%0D%0A++++schema%3AstartDate+%3FstartDate+%3B%0D%0A++++schema%3AendDate+%3FendDate+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+a+dct%3APeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AstartDate+%3FstartDate+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AendDate+%3FendDate+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX rdfs:   <http://www.w3.org/2000/01/rdf-schema#>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?PeriodOfTime a schema:DateTime ;
        schema:startDate ?startDate ;
        schema:endDate ?endDate 
    } WHERE {
      OPTIONAL { ?Resource dct:temporal ?PeriodOfTime . }
      OPTIONAL { ?PeriodOfTime a dct:PeriodOfTime . }
      OPTIONAL { ?PeriodOfTime schema:startDate ?startDate . }
      OPTIONAL { ?PeriodOfTime schema:endDate ?endDate . }
    }

</section>

<section id="mapping-formal-reference-system">

#### <a name="mapping-formal-reference-system">Reference system</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FReferenceSystem+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemAuthority+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemIdentifier+%3B%0D%0A++++schema%3Aname+%3FreferenceSystemName+%3B%0D%0A%23++++schema%3A%3F%3F+%3FReferenceSystemType+%3B%0D%0A++++schema%3Aversion+%3FreferenceSystemVersionNumber%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AconformsTo+%3FReferenceSystem+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+a+dct%3AStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+skos%3AinScheme+%3FreferenceSystemAuthority+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Aidentifier+%3FreferenceSystemIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+skos%3AprefLabel+%3FreferenceSystemName+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Atype+%3FReferenceSystemType+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+owl%3AversionInfo+%3FreferenceSystemVersionNumber+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FReferenceSystem+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemAuthority+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemIdentifier+%3B%0D%0A++++schema%3Aname+%3FreferenceSystemName+%3B%0D%0A%23++++schema%3A%3F%3F+%3FReferenceSystemType+%3B%0D%0A++++schema%3Aversion+%3FreferenceSystemVersionNumber%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AconformsTo+%3FReferenceSystem+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+a+dct%3AStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+skos%3AinScheme+%3FreferenceSystemAuthority+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Aidentifier+%3FreferenceSystemIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+skos%3AprefLabel+%3FreferenceSystemName+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Atype+%3FReferenceSystemType+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+owl%3AversionInfo+%3FreferenceSystemVersionNumber+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FReferenceSystem+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemAuthority+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemIdentifier+%3B%0D%0A++++schema%3Aname+%3FreferenceSystemName+%3B%0D%0A%23++++schema%3A%3F%3F+%3FReferenceSystemType+%3B%0D%0A++++schema%3Aversion+%3FreferenceSystemVersionNumber%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AconformsTo+%3FReferenceSystem+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+a+dct%3AStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+skos%3AinScheme+%3FreferenceSystemAuthority+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Aidentifier+%3FreferenceSystemIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+skos%3AprefLabel+%3FreferenceSystemName+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Atype+%3FReferenceSystemType+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+owl%3AversionInfo+%3FreferenceSystemVersionNumber+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX owl:    <http://www.w3.org/2002/07/owl#>
    PREFIX schema: <http://schema.org/>
    PREFIX skos:   <http://www.w3.org/2004/02/skos/core#>

    CONSTRUCT {
      ?ReferenceSystem 
    #    a schema:?? ;
    #    schema:?? ?referenceSystemAuthority ;
    #    schema:?? ?referenceSystemIdentifier ;
        schema:name ?referenceSystemName ;
    #    schema:?? ?ReferenceSystemType ;
        schema:version ?referenceSystemVersionNumber
    } WHERE {
      OPTIONAL { ?Resource dct:conformsTo ?ReferenceSystem . }
      OPTIONAL { ?ReferenceSystem a dct:Standard . }
    #  OPTIONAL { ?ReferenceSystem skos:inScheme ?referenceSystemAuthority . }
    #  OPTIONAL { ?ReferenceSystem dct:identifier ?referenceSystemIdentifier . }
      OPTIONAL { ?ReferenceSystem skos:prefLabel ?referenceSystemName . }
    #  OPTIONAL { ?ReferenceSystem dct:type ?ReferenceSystemType . }
      OPTIONAL { ?ReferenceSystem owl:versionInfo ?referenceSystemVersionNumber . }
    }

</section>

<section id="mapping-formal-rights-statement">

#### <a name="mapping-formal-rights-statement">Rights statement</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FRights%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AaccessRights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+a+dct%3ARightsStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FRights%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AaccessRights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+a+dct%3ARightsStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FRights%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AaccessRights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+a+dct%3ARightsStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX rdfs:   <http://www.w3.org/2000/01/rdf-schema#>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?Rights
    #    a schema:?? ;
        schema:name ?label
    } WHERE {
      OPTIONAL { ?Resource dct:rights ?Rights . }
      OPTIONAL { ?Resource dct:accessRights ?Rights . }
      OPTIONAL { ?Rights a dct:RightsStatement . }
      OPTIONAL { ?Rights rdfs:label ?label . }
    }

</section>

<section id="mapping-formal-service">

#### <a name="mapping-formal-service">Service</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dc%3A+++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+dctype%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fdcmitype%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FService+a+schema%3AService+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3AhasPart+%3FDataset+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aurl+%3FDocument+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A%23++++schema%3A%3F%3F+%3FType+%3B%0D%0A++++schema%3AdateModified+%3Fmodified%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FService+a+dctype%3AService+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3AhasPart+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dc%3Asubject+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Asubject+%3FCategory+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+foaf%3Ahomepage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3Atype+%3FType+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dc%3A+++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+dctype%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fdcmitype%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FService+a+schema%3AService+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3AhasPart+%3FDataset+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aurl+%3FDocument+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A%23++++schema%3A%3F%3F+%3FType+%3B%0D%0A++++schema%3AdateModified+%3Fmodified%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FService+a+dctype%3AService+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3AhasPart+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dc%3Asubject+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Asubject+%3FCategory+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+foaf%3Ahomepage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3Atype+%3FType+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dc%3A+++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+dctype%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fdcmitype%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FService+a+schema%3AService+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3AhasPart+%3FDataset+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aurl+%3FDocument+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A%23++++schema%3A%3F%3F+%3FType+%3B%0D%0A++++schema%3AdateModified+%3Fmodified%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FService+a+dctype%3AService+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3AhasPart+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dc%3Asubject+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Asubject+%3FCategory+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+foaf%3Ahomepage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3Atype+%3FType+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dc:     <http://purl.org/dc/elements/1.1/>
    PREFIX dcat:   <http://www.w3.org/ns/dcat#>
    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX dctype: <http://purl.org/dc/dcmitype/>
    PREFIX foaf:   <http://xmlns.com/foaf/0.1/>
    PREFIX schema: <http://schema.org/>

    CONSTRUCT {
      ?Service a schema:Service ;
    #    schema:?? ?AccessRights ;
        schema:creator ?Author ;
    #    schema:?? ?Standard ;
        schema:contactPoint ?Kind ;
        schema:hasPart ?Dataset ;
        schema:dateCreated ?created ;
        schema:description ?description ;
        schema:keywords ?keyword ;
        schema:about ?Category ;
        schema:inLanguage ?Language ;
        schema:publisher ?Publisher ;
        schema:datePublished ?issued ;
        schema:url ?Document ;
        schema:spatial ?Location ;
        schema:datasetTimeInterval ?PeriodOfTime ;
        schema:name ?title ;
    #    schema:?? ?Type ;
        schema:dateModified ?modified
    } WHERE {
      OPTIONAL { ?Service a dctype:Service . }
    #  OPTIONAL { ?Service dct:accessRights ?AccessRights . }
      OPTIONAL { ?Service dct:creator ?Author . }
    #  OPTIONAL { ?Service dct:conformsTo ?Standard . }
      OPTIONAL { ?Service dcat:contactPoint ?Kind . }
      OPTIONAL { ?Service dct:hasPart ?Dataset . }
      OPTIONAL { ?Service dct:created ?created . }
      OPTIONAL { ?Service dct:description ?description . }
      OPTIONAL { ?Service dc:subject ?keyword . }
      OPTIONAL { ?Service dct:subject ?Category . }
      OPTIONAL { ?Service dct:language ?Language . }
      OPTIONAL { ?Service dct:publisher ?Publisher . }
      OPTIONAL { ?Service dct:issued ?issued . }
      OPTIONAL { ?Service foaf:homepage ?Document . }
      OPTIONAL { ?Service dct:spatial ?Location . }
      OPTIONAL { ?Service dct:temporal ?PeriodOfTime . }
    #  OPTIONAL { ?Service dct:type ?Type . }
      OPTIONAL { ?Service dct:title ?title . }
      OPTIONAL { ?Service dct:modified ?modified . }
    }

</section>

<section id="mapping-formal-standard">

#### <a name="mapping-formal-standard">Standard</a>

Test it on the [SPARQL endpoint](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql) of the [INSPIRE GeoDCAT-AP Sandbox](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/) [[RDF/XML](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FStandard+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FStandard+a+dct%3AStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[Turtle](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FStandard+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FStandard+a+dct%3AStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)] [[JSON-LD](http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FStandard+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FStandard+a+dct%3AStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on)]

    PREFIX dct:    <http://purl.org/dc/terms/>
    PREFIX owl:    <http://www.w3.org/2002/07/owl#>
    PREFIX schema: <http://schema.org/>
    PREFIX skos:   <http://www.w3.org/2004/02/skos/core#>

    CONSTRUCT {
      ?Standard 
    #    a schema:?? ;
        schema:dateCreated ?created ;
        schema:datePublished ?issued ;
        schema:name ?title ;
        schema:dateModified ?modified 
    } WHERE {
      OPTIONAL { ?Standard a dct:Standard . }
      OPTIONAL { ?Standard dct:created ?created . }
      OPTIONAL { ?Standard dct:issued ?issued . }
      OPTIONAL { ?Standard dct:title ?title . }
      OPTIONAL { ?Standard dct:modified ?modified . }
    }

</section>

</section>

</section>

</article>
