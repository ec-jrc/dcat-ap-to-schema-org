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

    <section id="mapping-properties-mandatory">
    <h3><a name="mapping-properties-mandatory">Properties for mandatory classes</a></h3>

<!-- Properties: Agent -->

  <section id="mapping-properties-agent">
    <h4><a name="mapping-properties-agent">Agent</a></h4>
    <p>These properties should be used with <a target="_blank" href="http://schema.org/Organization"><code>schema:Organization</code></a> or <a target="_blank" href="http://schema.org/Person"><code>schema:Person</code></a>. [<a href="#mapping-formal-agent">formal definition</a>]</p>
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
        <td><a target="_blank" title="http://xmlns.com/foaf/0.1/name" href="http://xmlns.com/foaf/spec/#term_name"><code>foaf:name</code></a></td>
        <td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Recommended">R</abbr></td>
        <td>type</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/type" href="http://dublincore.org/documents/dcmi-terms/#terms-type"><code>dct:type</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
      </tr>
      <tr>
        <td>GeoDCAT-AP 1.0</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>email</td>
        <td><a target="_blank" title="http://xmlns.com/foaf/0.1/mbox" href="http://xmlns.com/foaf/spec/#term_mbox"><code>foaf:mbox</code></a></td>
        <td><a target="_blank" title="http://schema.org/email" href="http://schema.org/email"><code>schema:email</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>GeoDCAT-AP 1.0</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>homepage</td>
        <td><a target="_blank" title="http://xmlns.com/foaf/0.1/workplaceHomepage" href="http://xmlns.com/foaf/spec/#term_workplaceHomepage"><code>foaf:workplaceHomepage</code></a></td>
        <td><a target="_blank" title="http://schema.org/url" href="http://schema.org/url"><code>schema:url</code></a></td>
        <td></td>
      </tr>
    </tbody>
  </table>
</section>

<!-- Properties: Catalogue -->

  <section id="mapping-properties-catalogue">
    <h4><a name="mapping-properties-catalogue">Catalogue</a></h4>
      <p>These properties should be used with <a target="_blank" href="http://schema.org/DataCatalog"><code>schema:DataCatalog</code></a>. [<a href="#mapping-formal-catalogue">formal definition</a>]</p>
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
            <td><a target="_blank" title="http://www.w3.org/ns/dcat#dataset" href="https://www.w3.org/TR/vocab-dcat/#property-dataset"><code>dcat:dataset</code></a></td>
            <td><a target="_blank" title="http://schema.org/dataset" href="http://schema.org/dataset"><code>schema:dataset</code></a></td>
            <td></td>
          </tr>
          <tr>
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Mandatory">M</abbr></td>
            <td>description</td>
            <td><a target="_blank" title="http://purl.org/dc/terms/description" href="http://dublincore.org/documents/dcmi-terms/#terms-description"><code>dct:description</code></a></td>
            <td><a target="_blank" title="http://schema.org/description" href="http://schema.org/description"><code>schema:description</code></a></td>
            <td></td>
          </tr>
          <tr>
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Mandatory">M</abbr></td>
            <td>publisher</td>
            <td><a target="_blank" title="http://purl.org/dc/terms/publisher" href="http://dublincore.org/documents/dcmi-terms/#terms-publisher"><code>dct:publisher</code></a></td>
            <td><a target="_blank" title="http://schema.org/publisher" href="http://schema.org/publisher"><code>schema:publisher</code></a></td>
            <td></td>
          </tr>
          <tr>
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Mandatory">M</abbr></td>
            <td>title</td>
            <td><a target="_blank" title="http://purl.org/dc/terms/title" href="http://dublincore.org/documents/dcmi-terms/#terms-title"><code>dct:title</code></a></td>
            <td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
            <td></td>
          </tr>
          <tr>
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Recommended">R</abbr></td>
            <td>homepage</td>
            <td><a target="_blank" title="http://xmlns.com/foaf/0.1/homepage" href="http://xmlns.com/foaf/spec/#term_homepage"><code>foaf:homepage</code></a></td>
            <td><a target="_blank" title="http://schema.org/url" href="http://schema.org/url"><code>schema:url</code></a></td>
            <td></td>
          </tr>
          <tr>
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Recommended">R</abbr></td>
            <td>language</td>
            <td><a target="_blank" title="http://purl.org/dc/terms/language" href="http://dublincore.org/documents/dcmi-terms/#terms-language"><code>dct:language</code></a></td>
            <td><a target="_blank" title="http://schema.org/inLanguage" href="http://schema.org/inLanguage"><code>schema:inLanguage</code></a></td>
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
            <td><abbr title="Recommended">R</abbr></td>
            <td>release date</td>
            <td><a target="_blank" title="http://purl.org/dc/terms/issued" href="http://dublincore.org/documents/dcmi-terms/#terms-issued"><code>dct:issued</code></a></td>
            <td><a target="_blank" title="http://schema.org/datePublished" href="http://schema.org/datePublished"><code>schema:datePublished</code></a></td>
            <td></td>
          </tr>
          <tr>
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Recommended">R</abbr></td>
            <td>themes</td>
            <td><a target="_blank" title="http://www.w3.org/ns/dcat#themeTaxonomy" href="https://www.w3.org/TR/vocab-dcat/#property-themeTaxonomy"><code>dcat:themeTaxonomy</code></a></td>
            <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
            <td>TBD</td>
          </tr>
          <tr>
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Recommended">R</abbr></td>
            <td>update / modification date</td>
            <td><a target="_blank" title="http://purl.org/dc/terms/modified" href="http://dublincore.org/documents/dcmi-terms/#terms-modified"><code>dct:modified</code></a></td>
            <td><a target="_blank" title="http://schema.org/dateModified" href="http://schema.org/dateModified"><code>schema:dateModified</code></a></td>
            <td></td>
          </tr>
          <tr>
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Optional">O</abbr></td>
            <td>has part</td>
            <td><a target="_blank" title="http://purl.org/dc/terms/hasPart" href="http://dublincore.org/documents/dcmi-terms/#terms-hasPart"><code>dct:hasPart</code></a></td>
            <td><a target="_blank" title="http://schema.org/hasPart" href="http://schema.org/hasPart"><code>schema:hasPart</code></a></td>
            <td></td>
          </tr>
          <tr>
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Optional">O</abbr></td>
            <td>is part of</td>
            <td><a target="_blank" title="http://purl.org/dc/terms/isPartOf" href="http://dublincore.org/documents/dcmi-terms/#terms-isPartOf"><code>dct:isPartOf</code></a></td>
            <td><a target="_blank" title="http://schema.org/isPartOf" href="http://schema.org/isPartOf"><code>schema:isPartOf</code></a></td>
            <td></td>
          </tr>
          <tr>
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Optional">O</abbr></td>
            <td>record</td>
            <td><a target="_blank" title="http://www.w3.org/ns/dcat#record" href="https://www.w3.org/TR/vocab-dcat/#property-record"><code>dcat:record</code></a></td>
            <td><a target="_blank" title="http://schema.org/itemListElement" href="http://schema.org/itemListElement"><code>schema:itemListElement</code></a></td>
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
            <td>DCAT-AP 1.1</td>
            <td><abbr title="Optional">O</abbr></td>
            <td>spatial / geographic coverage</td>
            <td><a target="_blank" title="http://purl.org/dc/terms/spatial" href="http://dublincore.org/documents/dcmi-terms/#terms-spatial"><code>dct:spatial</code></a></td>
            <td><a target="_blank" title="http://schema.org/spatial" href="http://schema.org/spatial"><code>schema:spatial</code></a></td>
            <td></td>
          </tr>
        </tbody>
      </table>
    </section>

<!-- Properties: Dataset -->

  <section id="mapping-properties-dataset">
    <h4><a name="mapping-properties-dataset">Dataset</a></h4>
    <p>These properties should be used with <a target="_blank" href="http://schema.org/Dataset"><code>schema:Dataset</code></a>. [<a href="#mapping-formal-dataset">formal definition</a>]</p>
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
        <td><a target="_blank" title="http://purl.org/dc/terms/description" href="http://dublincore.org/documents/dcmi-terms/#terms-description"><code>dct:description</code></a></td>
        <td><a target="_blank" title="http://schema.org/description" href="http://schema.org/description"><code>schema:description</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Mandatory">M</abbr></td>
        <td>title</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/title" href="http://dublincore.org/documents/dcmi-terms/#terms-title"><code>dct:title</code></a></td>
        <td><a target="_blank" title="http://schema.org/name" href="http://schema.org/name"><code>schema:name</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Recommended">R</abbr></td>
        <td>contact point</td>
        <td><a target="_blank" title="http://www.w3.org/ns/dcat#contactPoint" href="https://www.w3.org/TR/vocab-dcat/#property-contactPoint"><code>dcat:contactPoint</code></a></td>
        <td><a target="_blank" title="http://schema.org/contactPoint" href="http://schema.org/contactPoint"><code>schema:contactPoint</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Recommended">R</abbr></td>
        <td>dataset distribution</td>
        <td><a target="_blank" title="http://www.w3.org/ns/dcat#distribution" href="https://www.w3.org/TR/vocab-dcat/#property-distribution"><code>dcat:distribution</code></a></td>
        <td><a target="_blank" title="http://schema.org/distribution" href="http://schema.org/distribution"><code>schema:distribution</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Recommended">R</abbr></td>
        <td>keyword</td>
        <td><a target="_blank" title="http://www.w3.org/ns/dcat#keyword" href="https://www.w3.org/TR/vocab-dcat/#property-keyword"><code>dcat:keyword</code></a></td>
        <td><a target="_blank" title="http://schema.org/keywords" href="http://schema.org/keywords"><code>schema:keywords</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Recommended">R</abbr></td>
        <td>publisher</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/publisher" href="http://dublincore.org/documents/dcmi-terms/#terms-publisher"><code>dct:publisher</code></a></td>
        <td><a target="_blank" title="http://schema.org/publisher" href="http://schema.org/publisher"><code>schema:publisher</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Recommended">R</abbr></td>
        <td>theme / category</td>
        <td><a target="_blank" title="http://www.w3.org/ns/dcat#theme" href="https://www.w3.org/TR/vocab-dcat/#property-theme"><code>dcat:theme</code></a></td>
        <td><a target="_blank" title="http://schema.org/about" href="http://schema.org/about"><code>schema:about</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
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
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>conforms to</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/conformsTo" href="http://dublincore.org/documents/dcmi-terms/#terms-conformsTo"><code>dct:conformsTo</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
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
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>documentation</td>
        <td><a target="_blank" title="http://xmlns.com/foaf/0.1/page" href="http://xmlns.com/foaf/spec/#term_page"><code>foaf:page</code></a></td>
        <td><a target="_blank" title="http://schema.org/mainEntityOfPage" href="http://schema.org/mainEntityOfPage"><code>schema:mainEntityOfPage</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>frequency</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/accrualPeriodicity" href="http://dublincore.org/documents/dcmi-terms/#terms-accrualPeriodicity"><code>dct:accrualPeriodicity</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>has version</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/hasVersion" href="http://dublincore.org/documents/dcmi-terms/#terms-hasVersion"><code>dct:hasVersion</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>identifier</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/identifier" href="http://dublincore.org/documents/dcmi-terms/#terms-identifier"><code>dct:identifier</code></a></td>
        <td><a target="_blank" title="http://schema.org/productID" href="http://schema.org/productID"><code>schema:productID</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>is version of</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/isVersionOf" href="http://dublincore.org/documents/dcmi-terms/#terms-isVersionOf"><code>dct:isVersionOf</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>landing page</td>
        <td><a target="_blank" title="http://www.w3.org/ns/dcat#landingPage" href="https://www.w3.org/TR/vocab-dcat/#property-landingPage"><code>dcat:landingPage</code></a></td>
        <td><a target="_blank" title="http://schema.org/url" href="http://schema.org/url"><code>schema:url</code></a></td>
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
        <td>other identifier</td>
        <td><a target="_blank" title="http://www.w3.org/ns/adms#identifier" href="https://www.w3.org/TR/vocab-adms/#adms_identifier"><code>amds:identifier</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
      </tr>
      <tr>
        <td>GeoDCAT-AP 1.0</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>owner</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/rightsHolder" href="http://dublincore.org/documents/dcmi-terms/#terms-rightsHolder"><code>dct:rightsHolder</code></a></td>
        <td><a target="_blank" title="http://schema.org/copyrightHolder" href="http://schema.org/copyrightHolder"><code>schema:copyrightHolder</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>provenance</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/provenance" href="http://dublincore.org/documents/dcmi-terms/#terms-provenance"><code>dct:provenance</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
      </tr>
      <tr>
        <td>GeoDCAT-AP 1.0</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>reference system</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/conformsTo" href="http://dublincore.org/documents/dcmi-terms/#terms-conformsTo"><code>dct:conformsTo</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>related resource</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/relation" href="http://dublincore.org/documents/dcmi-terms/#terms-relation"><code>dct:relation</code></a></td>
        <td><a target="_blank" title="http://schema.org/mentions" href="http://schema.org/mentions"><code>schema:mentions</code></a></td>
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
        <td>sample</td>
        <td><a target="_blank" title="http://www.w3.org/ns/adms#sample" href="https://www.w3.org/TR/vocab-adms/#adms_sample"><code>amds:sample</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>source</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/source" href="http://dublincore.org/documents/dcmi-terms/#terms-source"><code>dct:source</code></a></td>
        <td><a target="_blank" title="http://schema.org/isBasedOnUrl" href="http://schema.org/isBasedOnUrl"><code>schema:isBasedOnUrl</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>spatial / geographic coverage</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/spatial" href="http://dublincore.org/documents/dcmi-terms/#terms-spatial"><code>dct:spatial</code></a></td>
        <td><a target="_blank" title="http://schema.org/spatial" href="http://schema.org/spatial"><code>schema:spatial</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>temporal coverage</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/temporal" href="http://dublincore.org/documents/dcmi-terms/#terms-temporal"><code>dct:temporal</code></a></td>
        <td><a target="_blank" title="http://schema.org/datasetTimeInterval" href="http://schema.org/datasetTimeInterval"><code>schema:datasetTimeInterval</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>GeoDCAT-AP 1.0</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>topic category</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/subject" href="http://dublincore.org/documents/dcmi-terms/#terms-subject"><code>dct:subject</code></a></td>
        <td><a target="_blank" title="http://schema.org/about" href="http://schema.org/about"><code>schema:about</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>type</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/type" href="http://dublincore.org/documents/dcmi-terms/#terms-type"><code>dct:type</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>update / modification date</td>
        <td><a target="_blank" title="http://purl.org/dc/terms/modified" href="http://dublincore.org/documents/dcmi-terms/#terms-modified"><code>dct:modified</code></a></td>
        <td><a target="_blank" title="http://schema.org/dateModified" href="http://schema.org/dateModified"><code>schema:dateModified</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>version</td>
        <td><a target="_blank" title="http://www.w3.org/2002/07/owl#versionInfo" href="https://www.w3.org/TR/owl-ref/#versionInfo-def"><code>owl:versionInfo</code></a></td>
        <td><a target="_blank" title="http://schema.org/version" href="http://schema.org/version"><code>schema:version</code></a></td>
        <td></td>
      </tr>
      <tr>
        <td>DCAT-AP 1.1</td>
        <td><abbr title="Optional">O</abbr></td>
        <td>version notes</td>
        <td><a target="_blank" title="http://www.w3.org/ns/adms#version" href="https://www.w3.org/TR/vocab-adms/#adms-versionnotes"><code>adms:versionNotes</code></a></td>
        <td><a target="_blank" title="http://schema.org/??" href="http://schema.org/??"><code>schema:??</code></a></td>
        <td>TBD</td>
      </tr>
    </tbody>
  </table>
</section>
</section>
</article>
