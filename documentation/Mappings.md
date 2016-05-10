<article>
<header>
<h1>Mappings defined in DCAT-AP+Schema.org</h1>
</header>
<section>
<h2>Status of this document</h2>
<p>This document presents a proposal for mapping the relevant terms from the <a target="_blank" href="https://joinup.ec.europa.eu/asset/dcat_application_profile/">DCAT Application Profile for European Data Portals</a> (DCAT-AP) to the <a target="_blank" href="http://schema.org/">Schema.org vocabulary</a>.</p>
<p>This document is a draft meant to report work in progress. As such, it can be updated any time and it must be considered as unstable.</p>
<!--    
<p>Comments and queries should be sent to the <a href="https://joinup.ec.europa.eu/asset/dcat_application_profile/">DCAT-AP Working Group</a> via <a href="mailto:dcat_application_profile@joinup.ec.europa.eu">dcat_application_profile@joinup.ec.europa.eu</a>.</p>
-->    
</section>
<section>
<h2>Abstract</h2>
<!--
<p>This document presents a proposal for mapping the relevant terms from the <a target="_blank" href="https://joinup.ec.europa.eu/asset/dcat_application_profile/">DCAT Application Profile for European Data Portals</a> (DCAT-AP) to the <a target="_blank" href="http://schema.org/">Schema.org vocabulary</a>.</p>
-->
<p>This documents illustrates the mappings defined in DCAT-AP+Schema.org<!--, as implemented in the <a href="../datacite-to-dcat-ap.xsl"><code>datacite-to-dcat-ap.xsl</code></a> XSLT-->.</p>
<p>The background and methodology for the design of DCAT-AP+Schema.org are illustrated in a separate document:</p>
<p><a href="./Background.md"><cite>DCAT-AP+Schema.org: Background &amp; methodology</cite></a></p>
</section>
<nav>
<h2>Table of contents</h2>
<ul>
<li><a href="#introduction">Introduction</a></li>
<li><a href="#used-namespaces">Used namespaces</a></li>
<li><a href="#ref-code-lists">Reference code lists for metadata elements</a></li>
<li><a href="#mapping-summary">Mapping summary</a>
<ul>
<li><a href="#mapping-classes">Classes</a></li>
<li><a href="#mapping-properties-mandatory">Properties for mandatory classes</a></li>
<li><a href="#mapping-properties-recommended">Properties for recommended classes</a></li>
<li><a href="#mapping-properties-optional">Properties for optional classes</a></li>
</ul>
</li>
<li><a href="#mapping-formal">Formal definition</a>
<ul>
<li><a href="#mapping-formal-mandatory">Mandatory classes</a></li>
<li><a href="#mapping-formal-recommended">Recommended classes</a></li>
<li><a href="#mapping-formal-optional">Optional classes</a></li>
</ul>
</li>
</ul>
</nav>
<section id="introduction">
<h2><a name="introduction">Introduction</a></h2>
<p>The mappings illustrated in this document cover the metadata elements defined in the following specifications:</p>
<ul>
<li><a target="_blank" href="https://joinup.ec.europa.eu/asset/dcat_application_profile/asset_release/dcat-ap-v11">DCAT-AP v1.1</a> (<time datetime="2015-10-23">23 October 2015</time>)</li>
<li><a target="_blank" href="https://joinup.ec.europa.eu/asset/dcat_application_profile/asset_release/geodcat-ap-v10">GeoDCAT-AP v1.0</a> (<time datetime="2015-12-23">23 December 2015</time>)</li>
<li><a target="_blank" href="https://joinup.ec.europa.eu/asset/dcat-ap_implementation_guidelines/">DCAT-AP Implementation Guidelines</a> (DCAT-AP IG)</li>
</ul>
<p>For each of the mapped elements and the reference controlled vocabularies, the relevant specification is referred to in the tables included in the following sections.</p>
<p>For Schema.org, the reference specification is <a target="_blank" href="http://schema.org/version/2.2/">Schema.org 2.2</a> (<time datetime="2015-11-05">5 November 2015</time>).</p>
<p>This document includes, in a separate section, also a tentative formal definition of the mappings, in form of SPARQL queries.</p>
<p><strong>NB</strong>: In the current version, this document does not include mappings concerning the GeoDCAT-AP representation of agent roles and conformance results based on the W3C PROV Ontology [<a target="_blank" href="https://www.w3.org/TR/prov-o/">PROV-O</a>].</p>
</section>
<section id="used-namespaces">
<h2><a name="used-namespaces">Used namespaces</a></h2>
<table>
<thead>
<tr>
<th>Prefix</th>
<th>Namespace URI</th>
<th>Schema &amp; documentation</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>adms</code></td>
<td><code><a target="_blank" href="http://www.w3.org/ns/adms#">http://www.w3.org/ns/adms#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/TR/2013/NOTE-vocab-adms-20130801/" title="ADMS">Asset Description Metadata Schema</a></td>
</tr>
<tr>
<td><code>cnt</code></td>
<td><code><a target="_blank" href="http://www.w3.org/2011/content#">http://www.w3.org/2011/content#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/TR/2011/WD-Content-in-RDF10-20110510/">Representing Content in RDF 1.0</a></td>
</tr>
<tr>
<td><code>dc</code></td>
<td><code><a target="_blank" href="http://purl.org/dc/elements/1.1/">http://purl.org/dc/elements/1.1/</a></code></td>
<td><a target="_blank" href="http://dublincore.org/documents/2012/06/14/dces/">Dublin Core Metadata Element Set, Version 1.1</a></td>
</tr>
<tr>
<td><code>dcat</code></td>
<td><code><a target="_blank" href="http://www.w3.org/ns/dcat#">http://www.w3.org/ns/dcat#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/TR/2014/REC-vocab-dcat-20140116/" title="DCAT">Data Catalog Vocabulary</a></td>
</tr>
<tr>
<td><code>dct</code></td>
<td><code><a target="_blank" href="http://purl.org/dc/terms/">http://purl.org/dc/terms/</a></code></td>
<td><a target="_blank" href="http://dublincore.org/documents/2012/06/14/dcmi-terms/">DCMI Metadata Terms</a></td>
</tr>
<tr>
<td><code>dctype</code></td>
<td><code><a target="_blank" href="http://purl.org/dc/dcmitype/">http://purl.org/dc/dcmitype/</a></code></td>
<td><a target="_blank" href="http://dublincore.org/documents/2012/06/14/dcmi-terms/#H7">DCMI Type Vocabulary</a></td>
</tr>
<tr>
<td><code>foaf</code></td>
<td><code><a target="_blank" href="http://xmlns.com/foaf/0.1/">http://xmlns.com/foaf/0.1/</a></code></td>
<td><a target="_blank" href="http://xmlns.com/foaf/spec/20140114.html">FOAF Vocabulary</a></td>
</tr>
<tr>
<td><code>gsp</code></td>
<td><code><a target="_blank" href="http://www.opengis.net/ont/geosparql#">http://www.opengis.net/ont/geosparql#</a></code></td>
<td><a target="_blank" href="http://www.opengeospatial.org/standards/geosparql">GeoSPARQL - A Geographic Query Language for RDF Data</a></td>
</tr>
<tr>
<td><code>locn</code></td>
<td><code><a target="_blank" href="http://www.w3.org/ns/locn#">http://www.w3.org/ns/locn#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/ns/locn">ISA Programme Core Location Vocabulary</a></td>
</tr>
<tr>
<td><code>owl</code></td>
<td><code><a target="_blank" href="http://www.w3.org/2002/07/owl#">http://www.w3.org/2002/07/owl#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/TR/2004/REC-owl-ref-20040210/">OWL Web Ontology Language Reference</a></td>
</tr>
<tr>
<td><code>prov</code></td>
<td><code><a target="_blank" href="http://www.w3.org/ns/prov#">http://www.w3.org/ns/prov#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/TR/2013/REC-prov-o-20130430/">PROV-O: The PROV Ontology</a></td>
</tr>
<tr>
<td><code>rdf</code></td>
<td><code><a target="_blank" href="http://www.w3.org/1999/02/22-rdf-syntax-ns#">http://www.w3.org/1999/02/22-rdf-syntax-ns#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/TR/2004/REC-rdf-concepts-20040210/">Resource Description Framework (RDF): Concepts and Abstract Syntax</a></td>
</tr>
<tr>
<td><code>rdfs</code></td>
<td><code><a target="_blank" href="http://www.w3.org/2000/01/rdf-schema#">http://www.w3.org/2000/01/rdf-schema#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/TR/2004/REC-rdf-schema-20040210/">RDF Vocabulary Description Language 1.0: RDF Schema</a></td>
</tr>
<tr>
<td><code>schema</code></td>
<td><code><a target="_blank" href="http://schema.org/">http://schema.org/</a></code></td>
<td><a target="_blank" href="http://schema.org/">schema.org</a></td>
</tr>
<tr>
<td><code>skos</code></td>
<td><code><a target="_blank" href="http://www.w3.org/2004/02/skos/core#">http://www.w3.org/2004/02/skos/core#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/TR/2009/REC-skos-reference-20090818/">SKOS Simple Knowledge Organization System - Reference</a></td>
</tr>
<tr>
<td><code>spdx</code></td>
<td><code><a target="_blank" href="http://spdx.org/rdf/terms#">http://spdx.org/rdf/terms#</a></code></td>
<td><a target="_blank" href="http://spdx.org/rdf/spdx-terms-v2.0/">SPDX Version 2.0</a></td>
</tr>
<tr>
<td><code>vcard</code></td>
<td><code><a target="_blank" href="http://www.w3.org/2006/vcard/ns#">http://www.w3.org/2006/vcard/ns#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/TR/2013/WD-vcard-rdf-20130924/">vCard Ontology</a></td>
</tr>
<tr>
<td><code>xsd</code></td>
<td><code><a target="_blank" href="http://www.w3.org/2001/XMLSchema">http://www.w3.org/2001/XMLSchema#</a></code></td>
<td><a target="_blank" href="http://www.w3.org/TR/2004/REC-xmlschema-2-20041028/">XML Schema Part 2: Datatypes Second Edition</a></td>
</tr>
</tbody>
</table>
</section>
<section id="ref-code-lists">
<h2><a name="ref-code-lists">Reference code lists for metadata elements</a></h2>
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
<td><code><a target="_blank" href="http://purl.org/adms/changetype">http://purl.org/adms/changetype</a></code></td>
<td>ADMS Change Type controlled vocabulary [<a target="_blank" href="https://joinup.ec.europa.eu/svn/adms/ADMS_v1.00/ADMS_SKOS_v1.00.html">ADMS-SKOS</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td>Degree of conformity</td>
<td><code><a target="_blank" href="http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity">http://inspire.ec.europa.eu/metadata-codelist/DegreeOfConformity</a></code></td>
<td>Register operated by the INSPIRE Registry for degrees of conformity, as defined in [<a target="_blank" href="http://data.europa.eu/eli/reg/2008/1205/2008-12-24">INSPIRE-MD-REG</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td>Distribution status</td>
<td><code><a target="_blank" href="http://purl.org/adms/status">http://purl.org/adms/status</a></code></td>
<td>ADMS Status controlled vocabulary [<a target="_blank" href="https://joinup.ec.europa.eu/svn/adms/ADMS_v1.00/ADMS_SKOS_v1.00.html">ADMS-SKOS</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td>Format</td>
<td><code><a target="_blank" href="http://publications.europa.eu/resource/authority/file-type">http://publications.europa.eu/resource/authority/file-type</a></code></td>
<td>File type register operated by the Metadata Registry of the Publications Office of the EU [<a target="_blank" href="http://publications.europa.eu/mdr/authority/file-type/">MDR-FT</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td>INSPIRE spatial data themes</td>
<td><code><a target="_blank" href="http://inspire.ec.europa.eu/theme">http://inspire.ec.europa.eu/theme</a></code></td>
<td>INSPIRE spatial data theme register operated by the INSPIRE Registry</td>
<td>stable</td>
</tr>
<tr>
<td rowspan="4">DCAT-AP 1.1</td>
<td rowspan="4">Geographical names</td>
<td><code><a target="_blank" href="http://publications.europa.eu/resource/authority/country">http://publications.europa.eu/resource/authority/continent</a></code></td>
<td>Continent register operated by the Metadata Registry of the Publications Office of the EU [<a target="_blank" href="http://publications.europa.eu/mdr/authority/continent/">MDR-CONT</a>]</td>
<td>stable</td>
</tr>
<tr>
<td><code><a target="_blank" href="http://publications.europa.eu/resource/authority/country">http://publications.europa.eu/resource/authority/country</a></code></td>
<td>Country register operated by the Metadata Registry of the Publications Office of the EU [<a target="_blank" href="http://publications.europa.eu/mdr/authority/country/">MDR-COUNTRY</a>]</td>
<td>stable</td>
</tr>
<tr>
<td><code><a target="_blank" href="http://publications.europa.eu/resource/authority/place">http://publications.europa.eu/resource/authority/place</a></code></td>
<td>Place register operated by the Metadata Registry of the Publications Office of the EU [<a target="_blank" href="http://publications.europa.eu/mdr/authority/place/">MDR-PLACE</a>]</td>
<td>stable</td>
</tr>
<tr>
<td><code><a target="_blank" href="http://sws.geonames.org/">http://sws.geonames.org/</a></code></td>
<td>GeoNames gazetteer</td>
<td>stable</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td>Language</td>
<td><code><a target="_blank" href="http://publications.europa.eu/resource/authority/language">http://publications.europa.eu/resource/authority/language</a></code></td>
<td>Language register operated by the Metadata Registry of the Publications Office of the EU [<a target="_blank" href="http://publications.europa.eu/mdr/authority/language/">MDR-LANG</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td>Licence type</td>
<td><code><a target="_blank" href="http://purl.org/adms/licencetype">http://purl.org/adms/licencetype</a></code></td>
<td>ADMS Licence Type controlled vocabulary [<a target="_blank" href="https://joinup.ec.europa.eu/svn/adms/ADMS_v1.00/ADMS_SKOS_v1.00.html">ADMS-SKOS</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td rowspan="2">Maintenance frequency (Maintenance information)</td>
<td><code><a target="_blank" href="http://publications.europa.eu/resource/authority/frequency">http://publications.europa.eu/resource/authority/frequency</a></code></td>
<td>Frequency code register operated by the Metadata Registry of the Publications Office of the EU [<a target="_blank" href="http://publications.europa.eu/mdr/authority/frequency/">MDR-FR</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><code>http://inspire.ec.europa.eu/metadata-codelist/MaintenanceFrequencyCode</code></td>
<td>Register operated by the INSPIRE Registry for maintenance frequency codes defined in ISO 19115. The register is not yet available, and the code list URI is tentative.</td>
<td><strong>unstable</strong></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td>MDR Data themes</td>
<td><code><a target="_blank" href="http://publications.europa.eu/resource/authority/theme">http://publications.europa.eu/resource/authority/theme</a></code></td>
<td>Data theme register operated by the Metadata Registry of the Publications Office of the EU [<a target="_blank" href="http://publications.europa.eu/mdr/authority/language/">MDR-LANG</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td>Media type</td>
<td><code><a target="_blank" href="http://www.iana.org/assignments/media-types/">http://www.iana.org/assignments/media-types</a></code></td>
<td>IANA MIME Media Types register</td>
<td>stable</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td>Publisher</td>
<td><code><a target="_blank" href="http://publications.europa.eu/resource/authority/corporate-body">http://publications.europa.eu/resource/authority/corporate-body</a></code></td>
<td>Corporate body register operated by the Metadata Registry of the Publications Office of the EU [<a target="_blank" href="http://publications.europa.eu/mdr/authority/corporate-body/">MDR-CB</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td>Publisher type</td>
<td><code><a target="_blank" href="http://purl.org/adms/publishertype">http://purl.org/adms/publishertype</a></code></td>
<td>ADMS Publisher Type controlled vocabulary [<a target="_blank" href="https://joinup.ec.europa.eu/svn/adms/ADMS_v1.00/ADMS_SKOS_v1.00.html">ADMS-SKOS</a>]</td>
<td>stable</td>
</tr>
<tr>
<td rowspan="2">GeoDCAT-AP 1.0</td>
<td rowspan="2">Reference system type</td>
<td><code><a target="_blank" href="http://inspire.ec.europa.eu/glossary/SpatialReferenceSystem">http://inspire.ec.europa.eu/glossary/SpatialReferenceSystem</a></code></td>
<td rowspan="2">The reference system type (spatial or temporal) is denoted by using the relevant terms from the <a target="_blank" href="http://inspire.ec.europa.eu/glossary">glossary</a> operated by the INSPIRE Registry.</td>
<td rowspan="2"><em>testing</em></td>
</tr>
<tr>
<td><code><a target="_blank" href="http://inspire.ec.europa.eu/glossary/TemporalReferenceSystem">http://inspire.ec.europa.eu/glossary/TemporalReferenceSystem</a></code></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td>Resource type</td>
<td><code><a target="_blank" href="http://inspire.ec.europa.eu/metadata-codelist/ResourceType">http://inspire.ec.europa.eu/metadata-codelist/ResourceType</a></code></td>
<td>Register operated by the INSPIRE Registry for resource types defined in ISO 19115</td>
<td>stable</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td>Responsible party role</td>
<td><code><a target="_blank" href="http://inspire.ec.europa.eu/metadata-codelist/ResponsiblePartyRole">http://inspire.ec.europa.eu/metadata-codelist/ResponsiblePartyRole</a></code></td>
<td>Register operated by the INSPIRE Registry for responsible party roles, as defined in [<a target="_blank" href="http://data.europa.eu/eli/reg/2008/1205/2008-12-24">INSPIRE-MD-REG</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td>Service type</td>
<td><code><a target="_blank" href="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType">http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceType</a></code></td>
<td>Register operated by the INSPIRE Registry for service types, as defined in [<a target="_blank" href="http://data.europa.eu/eli/reg/2008/1205/2008-12-24">INSPIRE-MD-REG</a>]</td>
<td>stable</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td>Spatial data service categories</td>
<td><code><a target="_blank" href="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory">http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory</a></code></td>
<td>Register operated by the INSPIRE Registry for spatial data service categories defined in ISO 19119</td>
<td>stable</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td>Spatial representation type</td>
<td><code>http://inspire.ec.europa.eu/metadata-codelist/SpatialRepresentationTypeCode</code></td>
<td>Register operated by the INSPIRE Registry for spatial representation type codes defined in ISO 19115. The register is not yet available, and the code list URI is tentative.</td>
<td><strong>unstable</strong></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td>Topic category</td>
<td><code><a target="_blank" href="http://inspire.ec.europa.eu/metadata-codelist/TopicCategory">http://inspire.ec.europa.eu/metadata-codelist/TopicCategory</a></code></td>
<td>Register operated by the INSPIRE Registry for topic categories defined in ISO 19115</td>
<td>stable</td>
</tr>
</tbody>
</table>
</section>
<section>
<h2><a name="mapping-summary">Mapping summary</a></h2>
<p>The following section summarises the alignments defined in DCAT-AP+Schema.org.</p>
<p>The alignments are grouped as follows:</p>
<ul>
<li>Alignments for DCAT-AP classes</li>
<li>Alignments for DCAT-AP properties concerning:
<ul>
<li>mandatory classes</li>
<li>recommended classes</li>
<li>optional classes</li>
</ul>
</li>
</ul>
<section id="mapping-classes">
<h3><a name="mapping-classes">Classes</a></h3>
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
<td><a title="Detailed mapping" href="#mapping-properties-agent">Agent</a></td>
<td><a target="_blank" title="http://xmlns.com/foaf/0.1/Agent" href="http://xmlns.com/foaf/spec/#term_Agent"><code>foaf:Agent</code></a></td>
<td>
<a target="_blank" title="http://schema.org/Organization" href="http://schema.org/Organization"><code>schema:Organization</code></a>
<span>|</span>
<a target="_blank" title="http://schema.org/Person" href="http://schema.org/Person"><code>schema:Person</code></a>
</td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Mandatory">M</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-catalogue">Catalogue</a></td>
<td><a target="_blank" title="http://www.w3.org/ns/dcat#Catalog" href="https://www.w3.org/TR/vocab-dcat/#class-catalog"><code>dcat:Catalog</code></a></td>
<td><a target="_blank" title="http://schema.org/DataCatalog" href="http://schema.org/DataCatalog"><code>schema:DataCatalog</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Mandatory">M</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-dataset">Dataset</a></td>
<td><a target="_blank" title="http://www.w3.org/ns/dcat#Dataset" href="https://www.w3.org/TR/vocab-dcat/#class-dataset"><code>dcat:Dataset</code></a></td>
<td><a target="_blank" title="http://schema.org/Dataset" href="http://schema.org/Dataset"><code>schema:Dataset</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Recommended">R</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-category">Category</a></td>
<td><a target="_blank" title="http://www.w3.org/2004/02/skos/core#Concept" href="https://www.w3.org/TR/vocab-dcat/#class-concept"><code>skos:Concept</code></a></td>
<td><a target="_blank" title="http://schema.org/Thing" href="http://schema.org/Thing"><code>schema:Thing</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Recommended">R</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-category-scheme">Category Scheme</a></td>
<td><a target="_blank" title="http://www.w3.org/2004/02/skos/core#ConceptScheme" href="https://www.w3.org/TR/vocab-dcat/#class-concept-scheme"><code>skos:ConceptScheme</code></a></td>
<td><a target="_blank" title="http://schema.org/Enumeration" href="http://schema.org/Enumeration"><code>schema:Enumeration</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Recommended">R</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-distribution">Distribution</a></td>
<td><a target="_blank" title="http://www.w3.org/ns/dcat#Distribution" href="https://www.w3.org/TR/vocab-dcat/#class-distribution"><code>dcat:Distribution</code></a></td>
<td><a target="_blank" title="http://schema.org/DataDownload" href="http://schema.org/DataDownload"><code>schema:DataDownload</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Recommended">R</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-licence">Licence Document</a></td>
<td><a target="_blank" title="http://purl.org/dc/terms/LicenseDocument" href="http://dublincore.org/documents/dcmi-terms/#terms-LicenseDocument"><code>dct:LicenseDocument</code></a></td>
<td>
<a target="_blank" title="http://schema.org/CreativeWork" href="http://schema.org/CreativeWork"><code>schema:CreativeWork</code></a>
<span>|</span>
<a target="_blank" title="http://schema.org/URL" href="http://schema.org/URL"><code>schema:URL</code></a>
</td>
<td>TDB</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-catalogue-record">Catalogue Record</a></td>
<td><a target="_blank" title="http://www.w3.org/ns/dcat#CatalogRecord" href="https://www.w3.org/TR/vocab-dcat/#class-catalog-record"><code>dcat:CatalogRecord</code></a></td>
<td><a target="_blank" title="http://schema.org/ListItem" href="http://schema.org/ListItem"><code>schema:ListItem</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-checksum">Checksum</a></td>
<td><a target="_blank" title="http://spdx.org/rdf/terms/classes/Checksum___-238837136.html" href="http://spdx.org/rdf/terms#Checksum"><code>spdx:Checksum</code></a></td>
<td><a target="_blank" title="http://schema.org/Thing" href="http://schema.org/Thing"><code>schema:Thing</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-document">Document</a></td>
<td><a target="_blank" title="http://xmlns.com/foaf/0.1/Document" href="http://xmlns.com/foaf/spec/#term_Document"><code>foaf:Document</code></a></td>
<td>
<a target="_blank" title="http://schema.org/CreativeWork" href="http://schema.org/CreativeWork"><code>schema:CreativeWork</code></a>
<span>|</span>
<a target="_blank" title="http://schema.org/URL" href="http://schema.org/URL"><code>schema:URL</code></a>
</td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-identifier">Identifier</a></td>
<td><a target="_blank" title="http://www.w3.org/ns/adms#Identifier" href="https://www.w3.org/TR/vocab-adms/#dt_identifier"><code>adms:Identifier</code></a></td>
<td><a target="_blank" title="http://schema.org/Thing" href="http://schema.org/Thing"><code>schema:Thing</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-kind">Kind</a></td>
<td><a target="_blank" title="http://www.w3.org/2006/vcard/ns#Kind" href="https://www.w3.org/TR/vcard-rdf/#d4e1819"><code>vcard:Kind</code></a></td>
<td>
<a target="_blank" title="http://schema.org/ContactPoint" href="http://schema.org/ContactPoint"><code>schema:ContactPoint</code></a>
</td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-location">Location</a></td>
<td><a target="_blank" title="http://purl.org/dc/terms/Location" href="http://dublincore.org/documents/dcmi-terms/#terms-Location"><code>dct:Location</code></a></td>
<td><a target="_blank" title="http://schema.org/Place" href="http://schema.org/Place"><code>schema:Place</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-media-type">Media Type or Extent</a></td>
<td><a target="_blank" title="http://purl.org/dc/terms/MediaTypeOrExtent" href="http://dublincore.org/documents/dcmi-terms/#terms-MediaTypeOrExtent"><code>dct:MediaTypeOrExtent</code></a></td>
<td>
<a target="_blank" title="http://schema.org/Text" href="http://schema.org/Text"><code>schema:Text</code></a>
<span>|</span>
<a target="_blank" title="http://schema.org/URL" href="http://schema.org/URL"><code>schema:URL</code></a>
</td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-period-of-time">Period of Time</a></td>
<td><a target="_blank" title="http://purl.org/dc/terms/PeriodOfTime" href="http://dublincore.org/documents/dcmi-terms/#terms-PeriodOfTime"><code>dct:PeriodOfTime</code></a></td>
<td><a target="_blank" title="http://schema.org/DateTime" href="http://schema.org/DateTime"><code>schema:DateTime</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-reference-system">Reference System</a></td>
<td><a target="_blank" title="http://purl.org/dc/terms/Standard" href="http://dublincore.org/documents/dcmi-terms/#terms-Standard"><code>dct:Standard</code></a></td>
<td>
<a target="_blank" title="http://schema.org/CreativeWork" href="http://schema.org/CreativeWork"><code>schema:CreativeWork</code></a>
<span>|</span>
<a target="_blank" title="http://schema.org/URL" href="http://schema.org/URL"><code>schema:URL</code></a>
</td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-rights">Rights Statement</a></td>
<td><a target="_blank" title="http://purl.org/dc/terms/RightsStatement" href="http://dublincore.org/documents/dcmi-terms/#terms-RightsStatement"><code>dct:RightsStatement</code></a></td>
<td>
<a target="_blank" title="http://schema.org/CreativeWork" href="http://schema.org/CreativeWork"><code>schema:CreativeWork</code></a>
<span>|</span>
<a target="_blank" title="http://schema.org/URL" href="http://schema.org/URL"><code>schema:URL</code></a>
</td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-service">Service</a></td>
<td><a target="_blank" title="http://purl.org/dc/dcmitype/Service" href="http://dublincore.org/documents/2012/06/14/dcmi-terms/#dcmitype-Service"><code>dctype:Service</code></a></td>
<td><a target="_blank" title="http://schema.org/Service" href="http://schema.org/Service"><code>schema:Service</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td><a title="Detailed mapping" href="#mapping-properties-standard">Standard</a></td>
<td><a target="_blank" title="http://purl.org/dc/terms/Standard" href="http://dublincore.org/documents/dcmi-terms/#terms-Standard"><code>dct:Standard</code></a></td>
<td>
<a target="_blank" title="http://schema.org/CreativeWork" href="http://schema.org/CreativeWork"><code>schema:CreativeWork</code></a>
<span>|</span>
<a target="_blank" title="http://schema.org/URL" href="http://schema.org/URL"><code>schema:URL</code></a>
</td>
<td>TBD</td>
</tr>
</tbody>
</table>
</section>
<!-- Properties -->
<section id="mapping-properties-recommended">
<h3><a name="mapping-properties-recommended">Properties for recommended classes</a></h3>
<!-- Properties: Category -->
<section id="mapping-properties-category">
<h4><a name="mapping-properties-category">Category</a></h4>
<p>TBD [<a href="#mapping-formal-category">formal definition</a>]</p>
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
<td><a target="_blank" title="http://www.w3.org/2004/02/skos/core#prefLabel" href="https://www.w3.org/2009/08/skos-reference/skos.html#prefLabel"><code>skos:prefLabel</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>originating controlled vocabulary</td>
<td><a target="_blank" title="http://www.w3.org/2004/02/skos/core#inScheme" href="https://www.w3.org/TR/vocab-dcat/#class-inScheme"><code>skos:inScheme</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Category scheme -->
<section id="mapping-properties-category-scheme">
<h4><a name="mapping-properties-category-scheme">Category scheme</a></h4>
<p>These properties should be used with <a target="_blank" title="http://schema.org/Enumeration" href="http://schema.org/Enumeration"><code>schema:Enumeration</code></a>. [<a href="#mapping-formal-category-scheme">formal definition</a>]</p>
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
<td><a target="_blank" title="http://purl.org/dc/terms/title" href="http://dublincore.org/documents/dcmi-terms/#terms-title"><code>dct:title</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>creation date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/created" href="http://dublincore.org/documents/dcmi-terms/#terms-created"><code>dct:created</code></a></td>
<td><a target="_blank" title="http://schema.org/dateCreated" href="http://schema.org/dateCreated"><code>schema:dateCreated</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>release date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/issued" href="http://dublincore.org/documents/dcmi-terms/#terms-issued"><code>dct:issued</code></a></td>
<td><a target="_blank" title="http://schema.org/datePublished" href="http://schema.org/datePublished"><code>schema:datePublished</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>update / modification date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/modified" href="http://dublincore.org/documents/dcmi-terms/#terms-modified"><code>dct:modified</code></a></td>
<td><a target="_blank" title="http://schema.org/dateModified" href="http://schema.org/dateModified"><code>schema:dateModified</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Distribution -->
<section id="mapping-properties-distribution">
<h4><a name="mapping-properties-distribution">Distribution</a></h4>
<p>These properties should be used with <a target="_blank" href="http://schema.org/DataDownload"><code>schema:DataDownload</code></a>. [<a href="#mapping-formal-distribution">formal definition</a>]</p>
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
<td><a target="_blank" title="http://www.w3.org/ns/dcat#accessURL" href="https://www.w3.org/TR/vocab-dcat/#property-accessURL"><code>dcat:accessURL</code></a></td>
<td><a target="_blank" title="http://schema.org/contentURL" href="http://schema.org/contentURL"><code>schema:contentURL</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Recommended">R</abbr></td>
<td>description</td>
<td><a target="_blank" title="http://purl.org/dc/terms/description" href="http://dublincore.org/documents/dcmi-terms/#terms-description"><code>dct:description</code></a></td>
<td><a target="_blank" title="http://schema.org/description" href="http://schema.org/description"><code>schema:description</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Recommended">R</abbr></td>
<td>format</td>
<td><a target="_blank" title="http://purl.org/dc/terms/format" href="http://dublincore.org/documents/dcmi-terms/#terms-format"><code>dct:format</code></a></td>
<td><a target="_blank" title="http://schema.org/encodingFormat" href="http://schema.org/encodingFormat"><code>schema:encodingFormat</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Recommended">R</abbr></td>
<td>licence</td>
<td><a target="_blank" title="http://purl.org/dc/terms/license" href="http://dublincore.org/documents/dcmi-terms/#terms-license"><code>dct:license</code></a></td>
<td><a target="_blank" title="http://schema.org/license" href="http://schema.org/license"><code>schema:license</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>byte size</td>
<td><a target="_blank" title="http://www.w3.org/ns/dcat#byteSize" href="https://www.w3.org/TR/vocab-dcat/#property-byteSize"><code>dcat:byteSize</code></a></td>
<td><a target="_blank" title="http://schema.org/contentSize" href="http://schema.org/contentSize"><code>schema:contentSize</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>character encoding</td>
<td><a target="_blank" title="http://www.w3.org/2011/content#characterEncoding" href="https://www.w3.org/TR/Content-in-RDF10/#characterEncodingProperty"><code>cnt:characterEncoding</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>checksum</td>
<td><a target="_blank" title="http://spdx.org/rdf/terms#checksum" href="http://spdx.org/rdf/terms/objectproperties/checksum___-303481264.html"><code>spdx:checksum</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>documentation</td>
<td><a target="_blank" title="http://xmlns.com/foaf/0.1/page" href="http://xmlns.com/foaf/spec/#term_page"><code>foaf:page</code></a></td>
<td><a target="_blank" title="http://schema.org/mainEntityOfPage" href="http://schema.org/??"><code>schema:mainEntityOfPage</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>download URL</td>
<td><a target="_blank" title="http://www.w3.org/ns/dcat#downloadURL" href="https://www.w3.org/TR/vocab-dcat/#property-downloadURL"><code>dcat:downloadURL</code></a></td>
<td><a target="_blank" title="http://schema.org/contentURL" href="http://schema.org/contentURL"><code>schema:contentURL</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>language</td>
<td><a target="_blank" title="http://purl.org/dc/terms/language" href="http://dublincore.org/documents/dcmi-terms/#terms-language"><code>dct:language</code></a></td>
<td><a target="_blank" title="http://schema.org/inLanguage" href="http://schema.org/inLanguage"><code>schema:inLanguage</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>linked schemas</td>
<td><a target="_blank" title="http://purl.org/dc/terms/conformsTo" href="http://dublincore.org/documents/dcmi-terms/#terms-conformsTo"><code>dct:conformsTo</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>media type</td>
<td><a target="_blank" title="http://www.w3.org/ns/dcat#mediaType" href="https://www.w3.org/TR/vocab-dcat/#property-mediaType"><code>dcat:mediaType</code></a></td>
<td><a target="_blank" title="http://schema.org/fileFormat" href="http://schema.org/fileFormat"><code>schema:fileFormat</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>release date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/issued" href="http://dublincore.org/documents/dcmi-terms/#terms-issued"><code>dct:issued</code></a></td>
<td><a target="_blank" title="http://schema.org/datePublished" href="http://schema.org/datePublished"><code>schema:datePublished</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>rights</td>
<td><a target="_blank" title="http://purl.org/dc/terms/rights" href="http://dublincore.org/documents/dcmi-terms/#terms-rights"><code>dct:rights</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>spatial representation type</td>
<td><a target="_blank" title="http://www.w3.org/ns/adms#representationTechnique" href="https://www.w3.org/TR/vocab-adms/#adms_representationTechnique"><code>amds:representationTechnique</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>status</td>
<td><a target="_blank" title="http://www.w3.org/ns/adms#status" href="https://www.w3.org/TR/vocab-adms/#adms_status"><code>amds:status</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>title</td>
<td><a target="_blank" title="http://purl.org/dc/terms/title" href="http://dublincore.org/documents/dcmi-terms/#terms-title"><code>dct:title</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>update / modification date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/modified" href="http://dublincore.org/documents/dcmi-terms/#terms-modified"><code>dct:modified</code></a></td>
<td><a target="_blank" title="http://schema.org/dateModified" href="http://schema.org/dateModified"><code>schema:dateModified</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Licence document -->
<section id="mapping-properties-licence">
<h4><a name="mapping-properties-licence">Licence document</a></h4>
<p>TBD [<a href="#mapping-formal-licence">formal definition</a>]</p>
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
<td><a target="_blank" title="http://purl.org/dc/terms/type" href="http://dublincore.org/documents/dcmi-terms/#terms-type"><code>dct:type</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>name / description</td>
<td><a target="_blank" title="http://www.w3.org/2000/01/rdf-schema#label" href="http://www.w3.org/TR/2004/REC-rdf-schema-20040210/#ch_label"><code>rdfs:label</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
</tbody>
</table>
</section>
</section>
<section id="mapping-properties-optional">
<h3><a name="mapping-properties-optional">Properties for optional classes</a></h3>
<!-- Properties: Catalogue record -->
<section id="mapping-properties-catalogue-record">
<h4><a name="mapping-properties-catalogue-record">Catalogue record</a></h4>
<p>These properties should be used with <a target="_blank" href="http://schema.org/ListItem"><code>schema:ListItem</code></a>. [<a href="#mapping-formal-catalogue-record">formal definition</a>]</p>
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
<td><a target="_blank" title="http://xmlns.com/foaf/0.1/primaryTopic" href="http://xmlns.com/foaf/spec/#term_primaryTopic"><code>foaf:primaryTopic</code></a></td>
<td><a target="_blank" title="http://schema.org/item" href="http://schema.org/item"><code>schema:item</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Mandatory">M</abbr></td>
<td>update / modification date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/modified" href="http://dublincore.org/documents/dcmi-terms/#terms-modified"><code>dct:modified</code></a></td>
<td><a target="_blank" title="http://schema.org/dateModified" href="http://schema.org/dateModified"><code>schema:dateModified</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Recommended">R</abbr></td>
<td>application profile</td>
<td><a target="_blank" title="http://purl.org/dc/terms/conformsTo" href="http://dublincore.org/documents/dcmi-terms/#terms-conformsTo"><code>dct:conformsTo</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Recommended">R</abbr></td>
<td>change type</td>
<td><a target="_blank" title="http://www.w3.org/ns/adms#status" href="https://www.w3.org/TR/vocab-adms/#adms_status"><code>amds:status</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Recommended">R</abbr></td>
<td>listing date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/issued" href="http://dublincore.org/documents/dcmi-terms/#terms-issued"><code>dct:issued</code></a></td>
<td><a target="_blank" title="http://schema.org/datePublished" href="http://schema.org/datePublished"><code>schema:datePublished</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>character encoding</td>
<td><a target="_blank" title="http://www.w3.org/2011/content#characterEncoding" href="https://www.w3.org/TR/Content-in-RDF10/#characterEncodingProperty"><code>cnt:characterEncoding</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>contact point</td>
<td><a target="_blank" title="http://www.w3.org/ns/dcat#contactPoint" href="https://www.w3.org/TR/vocab-dcat/#property-contactPoint"><code>dcat:contactPoint</code></a></td>
<td><a target="_blank" title="http://schema.org/contactPoint" href="http://schema.org/contactPoint"><code>schema:contactPoint</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>description</td>
<td><a target="_blank" title="http://purl.org/dc/terms/description" href="http://dublincore.org/documents/dcmi-terms/#terms-description"><code>dct:description</code></a></td>
<td><a target="_blank" title="http://schema.org/description" href="http://schema.org/description"><code>schema:description</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>identifier</td>
<td><a target="_blank" title="http://purl.org/dc/terms/identifier" href="http://dublincore.org/documents/dcmi-terms/#terms-identifier"><code>dct:identifier</code></a></td>
<td><a target="_blank" title="http://schema.org/productID" href="http://schema.org/productID"><code>schema:productID</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>language</td>
<td><a target="_blank" title="http://purl.org/dc/terms/language" href="http://dublincore.org/documents/dcmi-terms/#terms-language"><code>dct:language</code></a></td>
<td><a target="_blank" title="http://schema.org/inLanguage" href="http://schema.org/inLanguage"><code>schema:inLanguage</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>source metadata</td>
<td><a target="_blank" title="http://purl.org/dc/terms/source" href="http://dublincore.org/documents/dcmi-terms/#terms-source"><code>dct:source</code></a></td>
<td><a target="_blank" title="http://schema.org/isBasedOnUrl" href="http://schema.org/isBasedOnUrl"><code>schema:isBasedOnUrl</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>title</td>
<td><a target="_blank" title="http://purl.org/dc/terms/title" href="http://dublincore.org/documents/dcmi-terms/#terms-title"><code>dct:title</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Checksum -->
<section id="mapping-properties-checksum">
<h4><a name="mapping-properties-checksum">Checksum</a></h4>
<p>TBD [<a href="#mapping-formal-checksum">formal definition</a>]</p>
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
<td><a target="_blank" title="http://spdx.org/rdf/terms#algorithm" href="http://spdx.org/rdf/spdx-terms-v2.0/objectproperties/algorithm___-1614899588.html"><code>spdx:algorithm</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Mandatory">M</abbr></td>
<td>checksum value</td>
<td><a target="_blank" title="http://spdx.org/rdf/terms#checksumValue" href="http://spdx.org/rdf/spdx-terms-v2.0/dataproperties/checksumValue___-1263904517.html"><code>spdx:checksumValue</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Document -->
<section id="mapping-properties-document">
<h4><a name="mapping-properties-document">Document</a></h4>
<p>TBD [<a href="#mapping-formal-document">formal definition</a>]</p>
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
<td><a target="_blank" title="http://purl.org/dc/terms/description" href="http://dublincore.org/documents/dcmi-terms/#terms-description"><code>dct:description</code></a></td>
<td><a target="_blank" title="http://schema.org/description" href="http://schema.org/description"><code>schema:description</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>title</td>
<td><a target="_blank" title="http://purl.org/dc/terms/title" href="http://dublincore.org/documents/dcmi-terms/#terms-title"><code>dct:title</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Identifier -->
<section id="mapping-properties-identifier">
<h4><a name="mapping-properties-identifier">Identifier</a></h4>
<p>TBD [<a href="#mapping-formal-identifier">formal definition</a>]</p>
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
<td><a target="_blank" title="http://www.w3.org/2004/02/skos/core#notation" href="https://www.w3.org/2009/08/skos-reference/skos.html#notation"><code>skos:notation</code></a></td>
<td><a target="_blank" title="http://schema.org/productID" href="http://schema.org/productID"><code>schema:productID</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Kind -->
<section id="mapping-properties-kind">
<h4><a name="mapping-properties-kind">Kind</a></h4>
<p>These properties should be used with <a target="_blank" href="http://schema.org/ContactPoint"><code>schema:ContactPoint</code></a>. [<a href="#mapping-formal-kind">formal definition</a>]</p>
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
<td><a target="_blank" title="http://www.w3.org/2006/vcard/ns#fn" href="https://www.w3.org/TR/vcard-rdf/#d4e891"><code>vcard:fn</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP IG</td>
<td><abbr title="Recommended">R</abbr></td>
<td rowspan="2">email</td>
<td rowspan="2"><a target="_blank" title="http://www.w3.org/2006/vcard/ns#hasEmail" href="https://www.w3.org/TR/vcard-rdf/#d4e183"><code>vcard:hasEmail</code></a></td>
<td rowspan="2"><a target="_blank" title="http://schema.org/email" href="http://schema.org/email"><code>schema:email</code></a></td>
<td rowspan="2"></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>organisation name</td>
<td><a target="_blank" title="http://www.w3.org/2006/vcard/ns#organization-name" href="https://www.w3.org/TR/vcard-rdf/#d4e1077"><code>vcard:organization-name</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td rowspan="2"><abbr title="Optional">O</abbr></td>
<td rowspan="2">homepage</td>
<td rowspan="2"><a target="_blank" title="http://www.w3.org/2006/vcard/ns#hasURL" href="https://www.w3.org/TR/vcard-rdf/#d4e605"><code>vcard:hasURL</code></a></td>
<td rowspan="2"><a target="_blank" title="http://schema.org/url" href="http://schema.org/url"><code>schema:url</code></a></td>
<td rowspan="2"></td>
</tr>
<tr>
<td>DCAT-AP IG</td>
</tr>
<tr>
<td>DCAT-AP IG</td>
<td><abbr title="Optional">O</abbr></td>
<td>telephone</td>
<td><a target="_blank" title="http://www.w3.org/2006/vcard/ns#hasTelephone" href="https://www.w3.org/TR/vcard-rdf/#d4e563"><code>vcard:hasTelephone</code></a></td>
<td><a target="_blank" title="http://schema.org/telephone" href="http://schema.org/name"><code>schema:telephone</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Location -->
<section id="mapping-properties-location">
<h4><a name="mapping-properties-location">Location</a></h4>
<p>These properties should be used with <a target="_blank" href="http://schema.org/Place"><code>schema:Place</code></a>. [<a href="#mapping-formal-location">formal definition</a>]</p>
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
<td><a target="_blank" title="http://purl.org/dc/terms/identifier" href="http://dublincore.org/documents/dcmi-terms/#terms-identifier"><code>dct:identifier</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>geographical identifier / name authority</td>
<td><a target="_blank" title="http://www.w3.org/2004/02/skos/core#inScheme" href="https://www.w3.org/TR/vocab-dcat/#class-inScheme"><code>skos:inScheme</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD. The "authority" denotes the reference register for the geographical name / identifier (typically, a gazetteer).</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>geographical name</td>
<td><a target="_blank" title="http://www.w3.org/2004/02/skos/core#prefLabel" href="https://www.w3.org/TR/vocab-dcat/#class-prefLabel"><code>skos:prefLabel</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>geometry</td>
<td><a target="_blank" title="http://purl.org/dc/terms/identifier" href="http://dublincore.org/documents/dcmi-terms/#terms-identifier"><code>locn:geometry</code></a></td>
<td><a target="_blank" title="http://schema.org/geo" href="http://schema.org/geo"><code>schema:geo</code></a></td>
<td>
<p>Schema.org expects as value an instance of <a target="_blank" title="http://schema.org/GeoCoordinates" href="http://schema.org/GeoCoordinates"><code>schema:GeoCoordinates</code></a> (for points) or <a target="_blank" title="http://schema.org/GeoShape" href="http://schema.org/GeoShape"><code>schema:GeoShape</code></a> (for more complex geometries).</p>
<p>LOCN allows any type of geometry, and any type of geometry encoding / representation&mdash;including those supported by Schema.org.</p>
<p>As a consequence, the <a target="_blank" title="http://www.w3.org/ns/locn#geometry" href="http://www.w3.org/ns/locn#locn:geometry"><code>locn:geometry</code></a> mapping might require further processing to encode the geometry according the encodings supported in Schema.org.</p>
</td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Media type or extent -->
<section id="mapping-properties-media-type">
<h4><a name="mapping-properties-media-type">Media type or extent</a></h4>
<p>TBD [<a href="#mapping-formal-media-type">formal definition</a>]</p>
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
<td><a target="_blank" title="http://www.w3.org/2000/01/rdf-schema#label" href="http://www.w3.org/TR/2004/REC-rdf-schema-20040210/#ch_label"><code>rdfs:label</code></a></td>
<td><a target="_blank" title="http://schema.org/startDate" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Period of time -->
<section id="mapping-properties-period-of-time">
<h4><a name="mapping-properties-period-of-time">Period of time</a></h4>
<p>These properties should be used with <a target="_blank" href="http://schema.org/DateTime"><code>schema:DateTime</code></a>. [<a href="#mapping-formal-period-of-time">formal definition</a>]</p>
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
<td><a target="_blank" title="http://schema.org/startDate" href="http://schema.org/startDate"><code>schema:startDate</code></a></td>
<td><a target="_blank" title="http://schema.org/startDate" href="http://schema.org/startDate"><code>schema:startDate</code></a></td>
<td></td>
</tr>
<tr>
<td>DCAT-AP 1.1</td>
<td><abbr title="Optional">O</abbr></td>
<td>end date / time</td>
<td><a target="_blank" title="http://schema.org/endDate" href="http://schema.org/endDate"><code>schema:endDate</code></a></td>
<td><a target="_blank" title="http://schema.org/endDate" href="http://schema.org/endDate"><code>schema:endDate</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>

<!-- Properties: Reference system -->

<section id="mapping-properties-reference-system">
<h4><a name="mapping-properties-reference-system">Reference system</a></h4>
<p>TBD</p>
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
<td><a target="_blank" title="http://www.w3.org/2004/02/skos/core#inScheme" href="https://www.w3.org/TR/vocab-dcat/#class-inScheme"><code>skos:inScheme</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD. The "authority" denotes the reference register for the reference system.</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>reference system identifier</td>
<td><a target="_blank" title="http://purl.org/dc/terms/identifier" href="http://dublincore.org/documents/dcmi-terms/#terms-identifier"><code>dct:identifier</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>reference system name</td>
<td><a target="_blank" title="http://www.w3.org/2004/02/skos/core#prefLabel" href="https://www.w3.org/TR/vocab-dcat/#class-prefLabel"><code>skos:prefLabel</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>reference system type (e.g., spatial, temporal)</td>
<td><a target="_blank" title="http://purl.org/dc/terms/type" href="http://dublincore.org/documents/dcmi-terms/#terms-type"><code>dct:type</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>reference system version</td>
<td><a target="_blank" title="http://www.w3.org/2002/07/owl#versionInfo" href="https://www.w3.org/TR/owl-ref/#versionInfo-def"><code>owl:versionInfo</code></a></td>
<td><a target="_blank" title="http://schema.org/version" href="http://schema.org/version"><code>schema:version</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Rights statement -->
<section id="mapping-properties-rights">
<h4><a name="mapping-properties-rights">Rights statement</a></h4>
<p>TBD</p>
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
<td><a target="_blank" title="http://www.w3.org/2000/01/rdf-schema#label" href="http://www.w3.org/TR/2004/REC-rdf-schema-20040210/#ch_label"><code>rdfs:label</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Service -->
<section id="mapping-properties-service">
<h4><a name="mapping-properties-service">Service</a></h4>
<p>These properties should be used with <a target="_blank" href="http://schema.org/Service"><code>schema:Service</code></a>.</p>
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
<td><a target="_blank" title="http://purl.org/dc/terms/accessRights" href="http://dublincore.org/documents/dcmi-terms/#terms-accessRights"><code>dct:accessRights</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>author</td>
<td><a target="_blank" title="http://purl.org/dc/terms/creator" href="http://dublincore.org/documents/dcmi-terms/#terms-creator"><code>dct:creator</code></a></td>
<td><a target="_blank" title="http://schema.org/creator" href="http://schema.org/creator"><code>schema:creator</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>conformance result / conformity (data quality)</td>
<td><a target="_blank" title="http://purl.org/dc/terms/conformsTo" href="http://dublincore.org/documents/dcmi-terms/#terms-conformsTo"><code>dct:conformsTo</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>conforms to</td>
<td><a target="_blank" title="http://purl.org/dc/terms/conformsTo" href="http://dublincore.org/documents/dcmi-terms/#terms-conformsTo"><code>dct:conformsTo</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>contact point</td>
<td><a target="_blank" title="http://www.w3.org/ns/dcat#contactPoint" href="https://www.w3.org/TR/vocab-dcat/#property-contactPoint"><code>dcat:contactPoint</code></a></td>
<td><a target="_blank" title="http://schema.org/contactPoint" href="http://schema.org/contactPoint"><code>schema:contactPoint</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>coupled resource</td>
<td><a target="_blank" title="http://purl.org/dc/terms/hasPart" href="http://dublincore.org/documents/dcmi-terms/#terms-hasPart"><code>dct:hasPart</code></a></td>
<td><a target="_blank" title="http://schema.org/hasPart" href="http://schema.org/hasPart"><code>schema:hasPart</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>creation date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/created" href="http://dublincore.org/documents/dcmi-terms/#terms-created"><code>dct:created</code></a></td>
<td><a target="_blank" title="http://schema.org/dateCreated" href="http://schema.org/dateCreated"><code>schema:dateCreated</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>description</td>
<td><a target="_blank" title="http://purl.org/dc/terms/description" href="http://dublincore.org/documents/dcmi-terms/#terms-description"><code>dct:description</code></a></td>
<td><a target="_blank" title="http://schema.org/description" href="http://schema.org/description"><code>schema:description</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>keyword (free text)</td>
<td><a target="_blank" title="http://purl.org/dc/elements/1.1/subject" href="http://dublincore.org/documents/dcmi-terms/#elements-subject"><code>dc:subject</code></a></td>
<td><a target="_blank" title="http://schema.org/keywords" href="http://schema.org/keywords"><code>schema:keywords</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>keyword (from a controlled vocabulary)</td>
<td><a target="_blank" title="http://purl.org/dc/terms/subject" href="http://dublincore.org/documents/dcmi-terms/#terms-subject"><code>dct:subject</code></a></td>
<td><a target="_blank" title="http://schema.org/about" href="http://schema.org/about"><code>schema:about</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>language</td>
<td><a target="_blank" title="http://purl.org/dc/terms/language" href="http://dublincore.org/documents/dcmi-terms/#terms-language"><code>dct:language</code></a></td>
<td><a target="_blank" title="http://schema.org/inLanguage" href="http://schema.org/inLanguage"><code>schema:inLanguage</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>publisher</td>
<td><a target="_blank" title="http://purl.org/dc/terms/publisher" href="http://dublincore.org/documents/dcmi-terms/#terms-publisher"><code>dct:publisher</code></a></td>
<td><a target="_blank" title="http://schema.org/publisher" href="http://schema.org/publisher"><code>schema:publisher</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>release date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/issued" href="http://dublincore.org/documents/dcmi-terms/#terms-issued"><code>dct:issued</code></a></td>
<td><a target="_blank" title="http://schema.org/datePublished" href="http://schema.org/datePublished"><code>schema:datePublished</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>resource locator</td>
<td><a target="_blank" title="http://xmlns.com/foaf/0.1/homepage" href="http://xmlns.com/foaf/spec/#term_homepage"><code>foaf:homepage</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/url"><code>schema:url</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>spatial / geographic coverage</td>
<td><a target="_blank" title="http://purl.org/dc/terms/spatial" href="http://dublincore.org/documents/dcmi-terms/#terms-spatial"><code>dct:spatial</code></a></td>
<td><a target="_blank" title="http://schema.org/spatial" href="http://schema.org/spatial"><code>schema:spatial</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>spatial data service category</td>
<td><a target="_blank" title="http://purl.org/dc/terms/type" href="http://dublincore.org/documents/dcmi-terms/#terms-type"><code>dct:type</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>spatial data service type</td>
<td><a target="_blank" title="http://purl.org/dc/terms/type" href="http://dublincore.org/documents/dcmi-terms/#terms-type"><code>dct:type</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>temporal coverage</td>
<td><a target="_blank" title="http://purl.org/dc/terms/temporal" href="http://dublincore.org/documents/dcmi-terms/#terms-temporal"><code>dct:temporal</code></a></td>
<td><a target="_blank" title="http://schema.org/datasetTimeInterval" href="http://schema.org/datasetTimeInterval"><code>schema:datasetTimeInterval</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>title</td>
<td><a target="_blank" title="http://purl.org/dc/terms/title" href="http://dublincore.org/documents/dcmi-terms/#terms-title"><code>dct:title</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>type</td>
<td><a target="_blank" title="http://purl.org/dc/terms/type" href="http://dublincore.org/documents/dcmi-terms/#terms-type"><code>dct:type</code></a></td>
<td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
<td>TBD</td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>update / modification date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/modified" href="http://dublincore.org/documents/dcmi-terms/#terms-modified"><code>dct:modified</code></a></td>
<td><a target="_blank" title="http://schema.org/dateModified" href="http://schema.org/dateModified"><code>schema:dateModified</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>
<!-- Properties: Standard -->
<section id="mapping-properties-standard">
<h4><a name="mapping-properties-standard">Standard</a></h4>
<p>TBD</p>
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
<td><a target="_blank" title="http://purl.org/dc/terms/created" href="http://dublincore.org/documents/dcmi-terms/#terms-created"><code>dct:created</code></a></td>
<td><a target="_blank" title="http://schema.org/dateCreated" href="http://schema.org/dateCreated"><code>schema:dateCreated</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>release date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/issued" href="http://dublincore.org/documents/dcmi-terms/#terms-issued"><code>dct:issued</code></a></td>
<td><a target="_blank" title="http://schema.org/datePublished" href="http://schema.org/datePublished"><code>schema:datePublished</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>title</td>
<td><a target="_blank" title="http://purl.org/dc/terms/title" href="http://dublincore.org/documents/dcmi-terms/#terms-title"><code>dct:title</code></a></td>
<td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>update / modification date</td>
<td><a target="_blank" title="http://purl.org/dc/terms/modified" href="http://dublincore.org/documents/dcmi-terms/#terms-modified"><code>dct:modified</code></a></td>
<td><a target="_blank" title="http://schema.org/dateModified" href="http://schema.org/dateModified"><code>schema:dateModified</code></a></td>
<td></td>
</tr>
<tr>
<td>GeoDCAT-AP 1.0</td>
<td><abbr title="Optional">O</abbr></td>
<td>version</td>
<td><a target="_blank" title="http://www.w3.org/2002/07/owl#versionInfo" href="https://www.w3.org/TR/owl-ref/#versionInfo-def"><code>owl:versionInfo</code></a></td>
<td><a target="_blank" title="http://schema.org/version" href="http://schema.org/version"><code>schema:version</code></a></td>
<td></td>
</tr>
</tbody>
</table>
</section>
</section>
</section>
</article>
