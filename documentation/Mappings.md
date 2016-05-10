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

<section id="mapping-formal">
  <h2><a name="mapping-formal">Formal definition</a></h2>
  <p>The following sections provide a tentative formal definition, in the form of <a target="_blank" href="https://www.w3.org/TR/sparql11-query/#construct">SPARQL <code>CONSTRUCT</code> queries</a>, of the mappings illustrated in the previous section.</p>
  <p>The mappings have been defined in a modular way, with a separate SPARQL query for each of the DCAT-AP classes, and related properties. A complete representation of a given resource (e.g., a dataset) and related resource (e.g., distribution, licence, publisher) can be obtained by combining the relevant SPARQL queries.</p>
  <p>The defined SPARQL queries can be tested on the SPARQL endpoint of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a>, that makes available a snapshot of the metadata records, in GeoDCAT-AP format, harvested by the <a target="_blank" href="http://inspire-geoportal.ec.europa.eu/">INSPIRE Geoportal</a>.</p>
<section id="mapping-formal-mandatory">
<h3><a name="mapping-formal-mandatory">Mandatory classes</a></h3>

<section id="mapping-formal-agent">
<h4><a name="mapping-formal-agent">Agent</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FAgent+%0D%0A++++a+%3FschemaPerson+%3B%0D%0A++++a+%3FschemaOrganization+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAgentType+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aurl+%3FworkplaceHomepage%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AAgent+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3APerson+BIND%28schema%3APerson+AS+%3FschemaPerson%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AOrganization+BIND%28schema%3AOrganization+AS+%3FschemaOrganization%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Aname+%3Fname+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FAgent+dct%3Atype+%3FAgentType+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Ambox+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3AworkplaceHomepage+%3FworkplaceHomepage+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FAgent+%0D%0A++++a+%3FschemaPerson+%3B%0D%0A++++a+%3FschemaOrganization+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAgentType+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aurl+%3FworkplaceHomepage%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AAgent+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3APerson+BIND%28schema%3APerson+AS+%3FschemaPerson%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AOrganization+BIND%28schema%3AOrganization+AS+%3FschemaOrganization%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Aname+%3Fname+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FAgent+dct%3Atype+%3FAgentType+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Ambox+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3AworkplaceHomepage+%3FworkplaceHomepage+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FAgent+%0D%0A++++a+%3FschemaPerson+%3B%0D%0A++++a+%3FschemaOrganization+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAgentType+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aurl+%3FworkplaceHomepage%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AAgent+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3APerson+BIND%28schema%3APerson+AS+%3FschemaPerson%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+a+foaf%3AOrganization+BIND%28schema%3AOrganization+AS+%3FschemaOrganization%29+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Aname+%3Fname+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FAgent+dct%3Atype+%3FAgentType+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3Ambox+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FAgent+foaf%3AworkplaceHomepage+%3FworkplaceHomepage+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX foaf:   &lt;http://xmlns.com/foaf/0.1/&gt;
PREFIX schema: &lt;http://schema.org/&gt;

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
}</code></pre>
</section>

<section id="mapping-formal-catalogue">
<h4><a name="mapping-formal-catalogue">Catalogue</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogue+a+schema%3ADataCatalog+%3B%0D%0A++++schema%3Adataset+%3FDataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3Aurl+%3Fhomepage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3AhasPart+%3FChildCatalogue+%3B%0D%0A++++schema%3AitemListElement+%3FCatalogueRecord+%3B%0D%0A++++schema%3Aspatial+%3FLocation%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogue+a+dcat%3ACatalog+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Adataset+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+foaf%3Ahomepage+%3Fhomepage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dcat%3AthemeTaxonomy+%3FCategoryScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3AhasPart+%3FChildCatalogue+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Arecord+%3FCatalogueRecord+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aspatial+%3FLocation+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogue+a+schema%3ADataCatalog+%3B%0D%0A++++schema%3Adataset+%3FDataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3Aurl+%3Fhomepage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3AhasPart+%3FChildCatalogue+%3B%0D%0A++++schema%3AitemListElement+%3FCatalogueRecord+%3B%0D%0A++++schema%3Aspatial+%3FLocation%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogue+a+dcat%3ACatalog+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Adataset+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+foaf%3Ahomepage+%3Fhomepage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dcat%3AthemeTaxonomy+%3FCategoryScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3AhasPart+%3FChildCatalogue+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Arecord+%3FCatalogueRecord+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aspatial+%3FLocation+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogue+a+schema%3ADataCatalog+%3B%0D%0A++++schema%3Adataset+%3FDataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3Aurl+%3Fhomepage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3AhasPart+%3FChildCatalogue+%3B%0D%0A++++schema%3AitemListElement+%3FCatalogueRecord+%3B%0D%0A++++schema%3Aspatial+%3FLocation%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogue+a+dcat%3ACatalog+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Adataset+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+foaf%3Ahomepage+%3Fhomepage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dcat%3AthemeTaxonomy+%3FCategoryScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3AhasPart+%3FChildCatalogue+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dcat%3Arecord+%3FCatalogueRecord+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogue+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogue+dct%3Aspatial+%3FLocation+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dcat:   &lt;http://www.w3.org/ns/dcat#&gt;
PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX foaf:   &lt;http://xmlns.com/foaf/0.1/&gt;
PREFIX schema: &lt;http://schema.org/&gt;

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
}</code></pre>

</section>

<section id="mapping-formal-dataset">
<h4><a name="mapping-formal-dataset">Dataset</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDataset+a+schema%3ADataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adistribution+%3FDistribution+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A%23++++schema%3A%3F%3F+%3FFrequency+%3B%0D%0A%23++++schema%3A%3F%3F+%3FPreviousDatasetVersion+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3FNextDatasetVersion+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAlternateIdentifier+%3B%0D%0A++++schema%3Aurl+%3FLandingPage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AcopyrightHolder+%3FCopyrightHolder+%3B%0D%0A%23++++schema%3A%3F%3F+%3FProvenanceStatement+%3B%0D%0A++++schema%3Amentions+%3FRelatedResource+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FDatasetSample+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceDataset+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aabout+%3FSubject+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aversion+%3FversionNumber+%0D%0A%23++++schema%3A%3F%3F+%3FversionNotes+%3B%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDataset+a+dcat%3ADataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Adistribution+%3FDistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Akeyword+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Atheme+%3FCategory+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+foaf%3Apage+%3FDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccrualPeriodicity+%3FFrequency+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AhasVersion+%3FPreviousDatasetVersion+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AisVersionOf+%3FNextDatasetVersion+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Aidentifier+%3FAlternateIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AlandingPage+%3FLandingPage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3ArightsHolder+%3FCopyrightHolder+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3Aprovenance+%3FProvenanceStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Arelation+%3FRelatedResource+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Asample+%3FDatasetSample+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asource+%3FSourceDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asubject+%3FSubject+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+owl%3AversionInfo+%3FversionNumber+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3AversionNotes+%3FversionNotes+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDataset+a+schema%3ADataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adistribution+%3FDistribution+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A%23++++schema%3A%3F%3F+%3FFrequency+%3B%0D%0A%23++++schema%3A%3F%3F+%3FPreviousDatasetVersion+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3FNextDatasetVersion+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAlternateIdentifier+%3B%0D%0A++++schema%3Aurl+%3FLandingPage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AcopyrightHolder+%3FCopyrightHolder+%3B%0D%0A%23++++schema%3A%3F%3F+%3FProvenanceStatement+%3B%0D%0A++++schema%3Amentions+%3FRelatedResource+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FDatasetSample+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceDataset+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aabout+%3FSubject+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aversion+%3FversionNumber+%0D%0A%23++++schema%3A%3F%3F+%3FversionNotes+%3B%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDataset+a+dcat%3ADataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Adistribution+%3FDistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Akeyword+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Atheme+%3FCategory+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+foaf%3Apage+%3FDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccrualPeriodicity+%3FFrequency+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AhasVersion+%3FPreviousDatasetVersion+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AisVersionOf+%3FNextDatasetVersion+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Aidentifier+%3FAlternateIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AlandingPage+%3FLandingPage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3ArightsHolder+%3FCopyrightHolder+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3Aprovenance+%3FProvenanceStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Arelation+%3FRelatedResource+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Asample+%3FDatasetSample+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asource+%3FSourceDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asubject+%3FSubject+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+owl%3AversionInfo+%3FversionNumber+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3AversionNotes+%3FversionNotes+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDataset+a+schema%3ADataset+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adistribution+%3FDistribution+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A%23++++schema%3A%3F%3F+%3FFrequency+%3B%0D%0A%23++++schema%3A%3F%3F+%3FPreviousDatasetVersion+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3FNextDatasetVersion+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAlternateIdentifier+%3B%0D%0A++++schema%3Aurl+%3FLandingPage+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AcopyrightHolder+%3FCopyrightHolder+%3B%0D%0A%23++++schema%3A%3F%3F+%3FProvenanceStatement+%3B%0D%0A++++schema%3Amentions+%3FRelatedResource+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FDatasetSample+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceDataset+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aabout+%3FSubject+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aversion+%3FversionNumber+%0D%0A%23++++schema%3A%3F%3F+%3FversionNotes+%3B%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDataset+a+dcat%3ADataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Adistribution+%3FDistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Akeyword+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3Atheme+%3FCategory+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+foaf%3Apage+%3FDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AaccrualPeriodicity+%3FFrequency+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AhasVersion+%3FPreviousDatasetVersion+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3AisVersionOf+%3FNextDatasetVersion+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Aidentifier+%3FAlternateIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dcat%3AlandingPage+%3FLandingPage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3ArightsHolder+%3FCopyrightHolder+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+dct%3Aprovenance+%3FProvenanceStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Arelation+%3FRelatedResource+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3Asample+%3FDatasetSample+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asource+%3FSourceDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Asubject+%3FSubject+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+dct%3Amodified+%3Fmodified+.+%7D%0D%0A++OPTIONAL+%7B+%3FDataset+owl%3AversionInfo+%3FversionNumber+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDataset+adms%3AversionNotes+%3FversionNotes+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX adms:   &lt;http://www.w3.org/ns/adms#&gt;
PREFIX cnt:    &lt;http://www.w3.org/2011/content#&gt;
PREFIX dcat:   &lt;http://www.w3.org/ns/dcat#&gt;
PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX foaf:   &lt;http://xmlns.com/foaf/0.1/&gt;
PREFIX owl:    &lt;http://www.w3.org/2002/07/owl#&gt;
PREFIX schema: &lt;http://schema.org/&gt;

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
}</code></pre>
</section>

</section>

<section id="mapping-formal-recommended">
<h3><a name="mapping-formal-recommended">Recommended classes</a></h3>

<section id="mapping-formal-category">
<h4><a name="mapping-formal-category">Category</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategory+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3FprefLabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategory+a+skos%3AConcept+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategory+skos%3AprefLabel+%3FprefLabel+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCategory+skos%3AinScheme+%3FCategoryScheme+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategory+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3FprefLabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategory+a+skos%3AConcept+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategory+skos%3AprefLabel+%3FprefLabel+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCategory+skos%3AinScheme+%3FCategoryScheme+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategory+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3FprefLabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategory+a+skos%3AConcept+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategory+skos%3AprefLabel+%3FprefLabel+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCategory+skos%3AinScheme+%3FCategoryScheme+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX schema: &lt;http://schema.org/&gt;
PREFIX skos:   &lt;http://www.w3.org/2004/02/skos/core#&gt;

CONSTRUCT {
  ?Category 
#    a schema:?? ;
    schema:name ?prefLabel 
} WHERE {
  OPTIONAL { ?Category a skos:Concept . }
  OPTIONAL { ?Category skos:prefLabel ?prefLabel . }
#  OPTIONAL { ?Category skos:inScheme ?CategoryScheme . }
}</code></pre>
</section>
  
<section id="mapping-formal-category-scheme">
<h4><a name="mapping-formal-category-scheme">Category scheme</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategoryScheme+a+schema%3AEnumeration+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+a+skos%3AConceptScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategoryScheme+a+schema%3AEnumeration+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+a+skos%3AConceptScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCategoryScheme+a+schema%3AEnumeration+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+a+skos%3AConceptScheme+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FCategoryScheme+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX schema: &lt;http://schema.org/&gt;
PREFIX skos:   &lt;http://www.w3.org/2004/02/skos/core#&gt;

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
}</code></pre>
</section>

<section id="mapping-formal-distribution">
<h4><a name="mapping-formal-distribution">Distribution</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+spdx%3A+++%3Chttp%3A%2F%2Fspdx.org%2Frdf%2Fterms%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDistribution+a+schema%3ADataDownload+%3B%0D%0A++++schema%3AcontentURL+%3FaccessURL+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AencodingFormat+%3FFormat+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AcontentSize+%3FbyteSize+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A++++schema%3AcontentURL+%3FdownloadURL+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AfileFormat+%3FMediaType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDistribution+a+dcat%3ADistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AaccessURL+%3FaccessURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aformat+%3FFormat+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AbyteSize+%3FbyteSize+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+spdx%3Achecksum+%3FChecksum+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+foaf%3Apage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AdownloadURL+%3FdownloadURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AmediaType+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3Arights+%3FRights+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3ArepresentationTechnique+%3FSpatialRepresentationType+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3Astatus+%3FStatus+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+spdx%3A+++%3Chttp%3A%2F%2Fspdx.org%2Frdf%2Fterms%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDistribution+a+schema%3ADataDownload+%3B%0D%0A++++schema%3AcontentURL+%3FaccessURL+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AencodingFormat+%3FFormat+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AcontentSize+%3FbyteSize+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A++++schema%3AcontentURL+%3FdownloadURL+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AfileFormat+%3FMediaType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDistribution+a+dcat%3ADistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AaccessURL+%3FaccessURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aformat+%3FFormat+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AbyteSize+%3FbyteSize+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+spdx%3Achecksum+%3FChecksum+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+foaf%3Apage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AdownloadURL+%3FdownloadURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AmediaType+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3Arights+%3FRights+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3ArepresentationTechnique+%3FSpatialRepresentationType+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3Astatus+%3FStatus+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+spdx%3A+++%3Chttp%3A%2F%2Fspdx.org%2Frdf%2Fterms%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDistribution+a+schema%3ADataDownload+%3B%0D%0A++++schema%3AcontentURL+%3FaccessURL+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AencodingFormat+%3FFormat+%3B%0D%0A++++schema%3Alicense+%3FLicence+%3B%0D%0A++++schema%3AcontentSize+%3FbyteSize+%3B%0D%0A++++schema%3AmainEntityOfPage+%3FDocument+%3B%0D%0A++++schema%3AcontentURL+%3FdownloadURL+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AfileFormat+%3FMediaType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDistribution+a+dcat%3ADistribution+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AaccessURL+%3FaccessURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aformat+%3FFormat+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AbyteSize+%3FbyteSize+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+spdx%3Achecksum+%3FChecksum+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+foaf%3Apage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AdownloadURL+%3FdownloadURL+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dcat%3AmediaType+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+dct%3Arights+%3FRights+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3ArepresentationTechnique+%3FSpatialRepresentationType+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FDistribution+adms%3Astatus+%3FStatus+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FDistribution+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX adms:   &lt;http://www.w3.org/ns/adms#&gt;
PREFIX cnt:    &lt;http://www.w3.org/2011/content#&gt;
PREFIX dcat:   &lt;http://www.w3.org/ns/dcat#&gt;
PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX foaf:   &lt;http://xmlns.com/foaf/0.1/&gt;
PREFIX schema: &lt;http://schema.org/&gt;
PREFIX spdx:   &lt;http://spdx.org/rdf/terms#&gt;

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
}</code></pre>
</section>

<section id="mapping-formal-licence">
<h4><a name="mapping-formal-licence">Licence document</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLicence+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FLicenceType+%3B%0D%0A++++schema%3Aname+%3Flabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+a+dct%3ALicenseDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLicence+dct%3Atype+%3FLicenceType+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLicence+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FLicenceType+%3B%0D%0A++++schema%3Aname+%3Flabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+a+dct%3ALicenseDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLicence+dct%3Atype+%3FLicenceType+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLicence+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FLicenceType+%3B%0D%0A++++schema%3Aname+%3Flabel+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Alicense+%3FLicence+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+a+dct%3ALicenseDocument+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLicence+dct%3Atype+%3FLicenceType+.+%7D%0D%0A++OPTIONAL+%7B+%3FLicence+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX rdfs: &lt;http://www.w3.org/2000/01/rdf-schema#&gt;
PREFIX schema: &lt;http://schema.org/&gt;

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
}</code></pre>
</section>

</section>

<section id="mapping-formal-optional">
<h3><a name="mapping-formal-optional">Optional classes</a></h3>

<section id="mapping-formal-catalogue-record">
<h4><a name="mapping-formal-catalogue-record">Catalogue record</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogueRecord+a+schema%3AListItem+%3B%0D%0A++++schema%3Aitem+%3FDataset+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A%23++++schema%3A%3F%3F+%3FMetadataStandard+%3B%0D%0A%23++++schema%3A%3F%3F+%3FChangeType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FcharacterEncoding+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceMetadata+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+a+dcat%3ACatalogRecord+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+foaf%3AprimaryTopic+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+dct%3AconformsTo+%3FMetadataStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+adms%3Astatus+%3FChangeType+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Asource+%3FSourceMetadata+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogueRecord+a+schema%3AListItem+%3B%0D%0A++++schema%3Aitem+%3FDataset+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A%23++++schema%3A%3F%3F+%3FMetadataStandard+%3B%0D%0A%23++++schema%3A%3F%3F+%3FChangeType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FcharacterEncoding+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceMetadata+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+a+dcat%3ACatalogRecord+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+foaf%3AprimaryTopic+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+dct%3AconformsTo+%3FMetadataStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+adms%3Astatus+%3FChangeType+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Asource+%3FSourceMetadata+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+cnt%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2011%2Fcontent%23%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FCatalogueRecord+a+schema%3AListItem+%3B%0D%0A++++schema%3Aitem+%3FDataset+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%3B%0D%0A%23++++schema%3A%3F%3F+%3FMetadataStandard+%3B%0D%0A%23++++schema%3A%3F%3F+%3FChangeType+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A%23++++schema%3A%3F%3F+%3FcharacterEncoding+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3AproductID+%3Fidentifier+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3AisBasedOnUrl+%3FSourceMetadata+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+a+dcat%3ACatalogRecord+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+foaf%3AprimaryTopic+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+dct%3AconformsTo+%3FMetadataStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+adms%3Astatus+%3FChangeType+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aissued+%3Fissued+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FCatalogueRecord+cnt%3AcharacterEncoding+%3FcharacterEncoding+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Aidentifier+%3Fidentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Asource+%3FSourceMetadata+.+%7D%0D%0A++OPTIONAL+%7B+%3FCatalogueRecord+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX adms:   &lt;http://www.w3.org/ns/adms#&gt;
PREFIX cnt:    &lt;http://www.w3.org/2011/content#&gt;
PREFIX dcat:   &lt;http://www.w3.org/ns/dcat#&gt;
PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX foaf:   &lt;http://xmlns.com/foaf/0.1/&gt;
PREFIX schema: &lt;http://schema.org/&gt;

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
}</code></pre>
</section>

<section id="mapping-formal-checksum">
<h4><a name="mapping-formal-checksum">Checksum</a></h4>
<p>No mappings have been defined for the relevant properties.</p>
</section>

<section id="mapping-formal-document">
<h4><a name="mapping-formal-document">Document</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDocument+%0D%0A%23++++a+schema%3ACreativeWork+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDocument+a+foaf%3ADocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDocument+%0D%0A%23++++a+schema%3ACreativeWork+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDocument+a+foaf%3ADocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FDocument+%0D%0A%23++++a+schema%3ACreativeWork+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Aname+%3Ftitle+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FDocument+a+foaf%3ADocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FDocument+dct%3Atitle+%3Ftitle+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX foaf:   &lt;http://xmlns.com/foaf/0.1/&gt;
PREFIX schema: &lt;http://schema.org/&gt;

CONSTRUCT {
  ?Document 
#    a schema:CreativeWork ;
    schema:description ?description ;
    schema:name ?title 
} WHERE {
  OPTIONAL { ?Document a foaf:Document . }
  OPTIONAL { ?Document dct:description ?description . }
  OPTIONAL { ?Document dct:title ?title . }
}</code></pre>
</section>

<section id="mapping-formal-optional-identifier">
<h4><a name="mapping-formal-optional-identifier">Identifier</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FIdentifier+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AproductID+%3Fnotation+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FIdentifier+a+adms%3AIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FIdentifier+skos%3Anotation+%3Fnotation+.+%7D%0D%0A%7D&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FIdentifier+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AproductID+%3Fnotation+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FIdentifier+a+adms%3AIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FIdentifier+skos%3Anotation+%3Fnotation+.+%7D%0D%0A%7D&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+adms%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fadms%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FIdentifier+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AproductID+%3Fnotation+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FIdentifier+a+adms%3AIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FIdentifier+skos%3Anotation+%3Fnotation+.+%7D%0D%0A%7D&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX adms:   &lt;http://www.w3.org/ns/adms#&gt;
PREFIX schema: &lt;http://schema.org/&gt;
PREFIX skos:   &lt;http://www.w3.org/2004/02/skos/core#&gt;

CONSTRUCT {
  ?Identifier 
#    a schema:?? ;
    schema:productID ?notation 
} WHERE {
  OPTIONAL { ?Identifier a adms:Identifier . }
  OPTIONAL { ?Identifier skos:notation ?notation . }
}</code></pre>
</section>
  
<section id="mapping-formal-kind">
<h4><a name="mapping-formal-kind">Kind</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+vcard%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2006%2Fvcard%2Fns%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FKind+a+schema%3AContactPoint+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aname+%3ForganisationName+%3B%0D%0A++++schema%3Aurl+%3Furl+%3B%0D%0A++++schema%3Atelephone+%3Ftelephone+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AIndividual+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AOrganization+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Afn+%3Fname+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasEmail+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Aorganization-name+%3ForganisationName+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasURL+%3Furl+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasTelephone+%3Ftelephone+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+vcard%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2006%2Fvcard%2Fns%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FKind+a+schema%3AContactPoint+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aname+%3ForganisationName+%3B%0D%0A++++schema%3Aurl+%3Furl+%3B%0D%0A++++schema%3Atelephone+%3Ftelephone+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AIndividual+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AOrganization+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Afn+%3Fname+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasEmail+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Aorganization-name+%3ForganisationName+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasURL+%3Furl+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasTelephone+%3Ftelephone+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+vcard%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2006%2Fvcard%2Fns%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FKind+a+schema%3AContactPoint+%3B%0D%0A++++schema%3Aname+%3Fname+%3B%0D%0A++++schema%3Aemail+%3Femail+%3B%0D%0A++++schema%3Aname+%3ForganisationName+%3B%0D%0A++++schema%3Aurl+%3Furl+%3B%0D%0A++++schema%3Atelephone+%3Ftelephone+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AIndividual+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+a+vcard%3AOrganization+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Afn+%3Fname+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasEmail+%3Femail+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3Aorganization-name+%3ForganisationName+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasURL+%3Furl+.+%7D%0D%0A++OPTIONAL+%7B+%3FKind+vcard%3AhasTelephone+%3Ftelephone+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX vcard:   &lt;http://www.w3.org/2006/vcard/ns#&gt;
PREFIX schema: &lt;http://schema.org/&gt;

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
}</code></pre>
</section>

<section id="mapping-formal-location">
<h4><a name="mapping-formal-location">Location</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+locn%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Flocn%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLocation+a+schema%3APlace+%3B%0D%0A%23++++schema%3A%3F%3F+%3FgeographicalIdentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3Fauthority+%3B%0D%0A++++schema%3Aname+%3FgeographicalName+%3B%0D%0A++++schema%3Ageo+%3Fgeometry+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+a+dct%3ALocation+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+dct%3Aidentifier+%3FgeographicalIdentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+skos%3AinScheme+%3Fauthority+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+skos%3AprefLabel+%3FgeographicalName+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+locn%3Ageometry+%3Fgeometry+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+locn%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Flocn%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLocation+a+schema%3APlace+%3B%0D%0A%23++++schema%3A%3F%3F+%3FgeographicalIdentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3Fauthority+%3B%0D%0A++++schema%3Aname+%3FgeographicalName+%3B%0D%0A++++schema%3Ageo+%3Fgeometry+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+a+dct%3ALocation+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+dct%3Aidentifier+%3FgeographicalIdentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+skos%3AinScheme+%3Fauthority+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+skos%3AprefLabel+%3FgeographicalName+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+locn%3Ageometry+%3Fgeometry+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+locn%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Flocn%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FLocation+a+schema%3APlace+%3B%0D%0A%23++++schema%3A%3F%3F+%3FgeographicalIdentifier+%3B%0D%0A%23++++schema%3A%3F%3F+%3Fauthority+%3B%0D%0A++++schema%3Aname+%3FgeographicalName+%3B%0D%0A++++schema%3Ageo+%3Fgeometry+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+a+dct%3ALocation+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+dct%3Aidentifier+%3FgeographicalIdentifier+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FLocation+skos%3AinScheme+%3Fauthority+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+skos%3AprefLabel+%3FgeographicalName+.+%7D%0D%0A++OPTIONAL+%7B+%3FLocation+locn%3Ageometry+%3Fgeometry+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX locn:   &lt;http://www.w3.org/ns/locn#&gt;
PREFIX schema: &lt;http://schema.org/&gt;
PREFIX skos:   &lt;http://www.w3.org/2004/02/skos/core#&gt;

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
}</code></pre>
</section>

<section id="mapping-formal-media-type">
<h4><a name="mapping-formal-media-type">Media type or extent</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FMediaType+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aformat+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+a+dct%3AMediaTypeOrExtent+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FMediaType+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aformat+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+a+dct%3AMediaTypeOrExtent+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FMediaType+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Aformat+%3FMediaType+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+a+dct%3AMediaTypeOrExtent+.+%7D%0D%0A++OPTIONAL+%7B+%3FMediaType+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX rdfs: &lt;http://www.w3.org/2000/01/rdf-schema#&gt;
PREFIX schema: &lt;http://schema.org/&gt;

CONSTRUCT {
  ?MediaType 
#    a schema:?? ;
    schema:name ?label
} WHERE {
  OPTIONAL { ?Resource dct:format ?MediaType . }
  OPTIONAL { ?MediaType a dct:MediaTypeOrExtent . }
  OPTIONAL { ?MediaType rdfs:label ?label . }
}</code></pre>
</section>

<section id="mapping-formal-period-of-time">
<h4><a name="mapping-formal-period-of-time">Period of time</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FPeriodOfTime+a+schema%3ADateTime+%3B%0D%0A++++schema%3AstartDate+%3FstartDate+%3B%0D%0A++++schema%3AendDate+%3FendDate+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+a+dct%3APeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AstartDate+%3FstartDate+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AendDate+%3FendDate+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FPeriodOfTime+a+schema%3ADateTime+%3B%0D%0A++++schema%3AstartDate+%3FstartDate+%3B%0D%0A++++schema%3AendDate+%3FendDate+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+a+dct%3APeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AstartDate+%3FstartDate+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AendDate+%3FendDate+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FPeriodOfTime+a+schema%3ADateTime+%3B%0D%0A++++schema%3AstartDate+%3FstartDate+%3B%0D%0A++++schema%3AendDate+%3FendDate+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+a+dct%3APeriodOfTime+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AstartDate+%3FstartDate+.+%7D%0D%0A++OPTIONAL+%7B+%3FPeriodOfTime+schema%3AendDate+%3FendDate+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX rdfs:   &lt;http://www.w3.org/2000/01/rdf-schema#&gt;
PREFIX schema: &lt;http://schema.org/&gt;

CONSTRUCT {
  ?PeriodOfTime a schema:DateTime ;
    schema:startDate ?startDate ;
    schema:endDate ?endDate 
} WHERE {
  OPTIONAL { ?Resource dct:temporal ?PeriodOfTime . }
  OPTIONAL { ?PeriodOfTime a dct:PeriodOfTime . }
  OPTIONAL { ?PeriodOfTime schema:startDate ?startDate . }
  OPTIONAL { ?PeriodOfTime schema:endDate ?endDate . }
}</code></pre>
</section>

<section id="mapping-formal-reference-system">
<h4><a name="mapping-formal-reference-system">Reference system</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FReferenceSystem+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemAuthority+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemIdentifier+%3B%0D%0A++++schema%3Aname+%3FreferenceSystemName+%3B%0D%0A%23++++schema%3A%3F%3F+%3FReferenceSystemType+%3B%0D%0A++++schema%3Aversion+%3FreferenceSystemVersionNumber%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AconformsTo+%3FReferenceSystem+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+a+dct%3AStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+skos%3AinScheme+%3FreferenceSystemAuthority+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Aidentifier+%3FreferenceSystemIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+skos%3AprefLabel+%3FreferenceSystemName+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Atype+%3FReferenceSystemType+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+owl%3AversionInfo+%3FreferenceSystemVersionNumber+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FReferenceSystem+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemAuthority+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemIdentifier+%3B%0D%0A++++schema%3Aname+%3FreferenceSystemName+%3B%0D%0A%23++++schema%3A%3F%3F+%3FReferenceSystemType+%3B%0D%0A++++schema%3Aversion+%3FreferenceSystemVersionNumber%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AconformsTo+%3FReferenceSystem+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+a+dct%3AStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+skos%3AinScheme+%3FreferenceSystemAuthority+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Aidentifier+%3FreferenceSystemIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+skos%3AprefLabel+%3FreferenceSystemName+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Atype+%3FReferenceSystemType+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+owl%3AversionInfo+%3FreferenceSystemVersionNumber+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FReferenceSystem+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemAuthority+%3B%0D%0A%23++++schema%3A%3F%3F+%3FreferenceSystemIdentifier+%3B%0D%0A++++schema%3Aname+%3FreferenceSystemName+%3B%0D%0A%23++++schema%3A%3F%3F+%3FReferenceSystemType+%3B%0D%0A++++schema%3Aversion+%3FreferenceSystemVersionNumber%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AconformsTo+%3FReferenceSystem+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+a+dct%3AStandard+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+skos%3AinScheme+%3FreferenceSystemAuthority+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Aidentifier+%3FreferenceSystemIdentifier+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+skos%3AprefLabel+%3FreferenceSystemName+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FReferenceSystem+dct%3Atype+%3FReferenceSystemType+.+%7D%0D%0A++OPTIONAL+%7B+%3FReferenceSystem+owl%3AversionInfo+%3FreferenceSystemVersionNumber+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX owl:    &lt;http://www.w3.org/2002/07/owl#&gt;
PREFIX schema: &lt;http://schema.org/&gt;
PREFIX skos:   &lt;http://www.w3.org/2004/02/skos/core#&gt;

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
}</code></pre>
</section>

<section id="mapping-formal-rights-statement">
<h4><a name="mapping-formal-rights-statement">Rights statement</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FRights%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AaccessRights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+a+dct%3ARightsStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FRights%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AaccessRights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+a+dct%3ARightsStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FRights%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3Aname+%3Flabel%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FResource+dct%3Arights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FResource+dct%3AaccessRights+%3FRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+a+dct%3ARightsStatement+.+%7D%0D%0A++OPTIONAL+%7B+%3FRights+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX rdfs:   &lt;http://www.w3.org/2000/01/rdf-schema#&gt;
PREFIX schema: &lt;http://schema.org/&gt;

CONSTRUCT {
  ?Rights
#    a schema:?? ;
    schema:name ?label
} WHERE {
  OPTIONAL { ?Resource dct:rights ?Rights . }
  OPTIONAL { ?Resource dct:accessRights ?Rights . }
  OPTIONAL { ?Rights a dct:RightsStatement . }
  OPTIONAL { ?Rights rdfs:label ?label . }
}</code></pre>
</section>

<section id="mapping-formal-service">
<h4><a name="mapping-formal-service">Service</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dc%3A+++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+dctype%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fdcmitype%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FService+a+schema%3AService+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3AhasPart+%3FDataset+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aurl+%3FDocument+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A%23++++schema%3A%3F%3F+%3FType+%3B%0D%0A++++schema%3AdateModified+%3Fmodified%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FService+a+dctype%3AService+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3AhasPart+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dc%3Asubject+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Asubject+%3FCategory+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+foaf%3Ahomepage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3Atype+%3FType+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dc%3A+++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+dctype%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fdcmitype%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FService+a+schema%3AService+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3AhasPart+%3FDataset+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aurl+%3FDocument+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A%23++++schema%3A%3F%3F+%3FType+%3B%0D%0A++++schema%3AdateModified+%3Fmodified%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FService+a+dctype%3AService+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3AhasPart+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dc%3Asubject+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Asubject+%3FCategory+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+foaf%3Ahomepage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3Atype+%3FType+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dc%3A+++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Felements%2F1.1%2F%3E%0D%0APREFIX+dcat%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2Fns%2Fdcat%23%3E%0D%0APREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+dctype%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fdcmitype%2F%3E%0D%0APREFIX+foaf%3A+++%3Chttp%3A%2F%2Fxmlns.com%2Ffoaf%2F0.1%2F%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FService+a+schema%3AService+%3B%0D%0A%23++++schema%3A%3F%3F+%3FAccessRights+%3B%0D%0A++++schema%3Acreator+%3FAuthor+%3B%0D%0A%23++++schema%3A%3F%3F+%3FStandard+%3B%0D%0A++++schema%3AcontactPoint+%3FKind+%3B%0D%0A++++schema%3AhasPart+%3FDataset+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3Adescription+%3Fdescription+%3B%0D%0A++++schema%3Akeywords+%3Fkeyword+%3B%0D%0A++++schema%3Aabout+%3FCategory+%3B%0D%0A++++schema%3AinLanguage+%3FLanguage+%3B%0D%0A++++schema%3Apublisher+%3FPublisher+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aurl+%3FDocument+%3B%0D%0A++++schema%3Aspatial+%3FLocation+%3B%0D%0A++++schema%3AdatasetTimeInterval+%3FPeriodOfTime+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A%23++++schema%3A%3F%3F+%3FType+%3B%0D%0A++++schema%3AdateModified+%3Fmodified%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FService+a+dctype%3AService+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AaccessRights+%3FAccessRights+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreator+%3FAuthor+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3AconformsTo+%3FStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dcat%3AcontactPoint+%3FKind+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3AhasPart+%3FDataset+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Adescription+%3Fdescription+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dc%3Asubject+%3Fkeyword+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Asubject+%3FCategory+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Alanguage+%3FLanguage+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Apublisher+%3FPublisher+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+foaf%3Ahomepage+%3FDocument+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Aspatial+%3FLocation+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atemporal+%3FPeriodOfTime+.+%7D%0D%0A%23++OPTIONAL+%7B+%3FService+dct%3Atype+%3FType+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FService+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dc:     &lt;http://purl.org/dc/elements/1.1/&gt;
PREFIX dcat:   &lt;http://www.w3.org/ns/dcat#&gt;
PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX dctype: &lt;http://purl.org/dc/dcmitype/&gt;
PREFIX foaf:   &lt;http://xmlns.com/foaf/0.1/&gt;
PREFIX schema: &lt;http://schema.org/&gt;

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
}</code></pre>
</section>


<section id="mapping-formal-standard">
<h4><a name="mapping-formal-standard">Standard</a></h4>
<p>Test it on the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql">SPARQL endpoint</a> of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a> [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FStandard+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FStandard+a+dct%3AStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Frdf%2Bxml&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">RDF/XML</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FStandard+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FStandard+a+dct%3AStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=text%2Fturtle&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">Turtle</a>] [<a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/sparql?default-graph-uri=http%3A%2F%2Finspire-geoportal.ec.europa.eu%2F&query=PREFIX+dct%3A++++%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+owl%3A++++%3Chttp%3A%2F%2Fwww.w3.org%2F2002%2F07%2Fowl%23%3E%0D%0APREFIX+schema%3A+%3Chttp%3A%2F%2Fschema.org%2F%3E%0D%0APREFIX+skos%3A+++%3Chttp%3A%2F%2Fwww.w3.org%2F2004%2F02%2Fskos%2Fcore%23%3E%0D%0A%0D%0ACONSTRUCT+%7B%0D%0A++%3FStandard+%0D%0A%23++++a+schema%3A%3F%3F+%3B%0D%0A++++schema%3AdateCreated+%3Fcreated+%3B%0D%0A++++schema%3AdatePublished+%3Fissued+%3B%0D%0A++++schema%3Aname+%3Ftitle+%3B%0D%0A++++schema%3AdateModified+%3Fmodified+%0D%0A%7D+WHERE+%7B%0D%0A++OPTIONAL+%7B+%3FStandard+a+dct%3AStandard+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Acreated+%3Fcreated+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Aissued+%3Fissued+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Atitle+%3Ftitle+.+%7D%0D%0A++OPTIONAL+%7B+%3FStandard+dct%3Amodified+%3Fmodified+.+%7D%0D%0A%7D+LIMIT+10&should-sponge=&format=application%2Fld%2Bjson&CXML_redir_for_subjs=121&CXML_redir_for_hrefs=&timeout=0&debug=on">JSON-LD</a>]</p>
<pre><code>PREFIX dct:    &lt;http://purl.org/dc/terms/&gt;
PREFIX owl:    &lt;http://www.w3.org/2002/07/owl#&gt;
PREFIX schema: &lt;http://schema.org/&gt;
PREFIX skos:   &lt;http://www.w3.org/2004/02/skos/core#&gt;

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
}</code></pre>
</section>


</section>
</section>
</article>
