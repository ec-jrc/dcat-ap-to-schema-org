  <article>
  <header>
    <h1>DCAT-AP+Schema.org: Background &amp; methodology</h1>
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
    <p>This document describes the background and methodology for the design of the Schema.org profile of DCAT-AP (DCAT-AP+Schema.org).</p>
<!--
    <p>This document presents a proposal for mapping the relevant terms from the <a target="_blank" href="https://joinup.ec.europa.eu/asset/dcat_application_profile/">DCAT Application Profile for European Data Portals</a> (DCAT-AP) to the <a target="_blank" href="http://schema.org/">Schema.org vocabulary</a>.</p>
-->
    <p>The mappings defined in DCAT-AP+Schema.org are illustrated in a separate document:</p>
    <p><a href="./Mappings.md"><cite>Mappings defined in DCAT-AP+Schema.org</cite></a></p>
  </section>
  <nav>
    <h2>Table of contents</h2>
    <ul>
      <li><a href="#background">Background</a>
        <ul>
          <li><a href="#background-dcat-ap">The <em>DCAT Application Profile for Data Portals in Europe</em> (DCAT-AP)</a></li>
          <li><a href="#background-schema.org">Schema.org</a></li>
          <li><a href="#background-why">Aligning DCAT-AP with Schema.org</a></li>
        </ul>
      </li>
      <li><a href="#methodology">Methodology</a></li>
<!--
      <li><a href="#comparison">Schema.org and DCAT-AP at a glance</a>
        <ul>
          <li><a href="#comparison-schema.org-vs-dcat-ap">Schema.org metadata elements supported in DCAT-AP</a></li>
          <li><a href="#comparison-dcat-ap-vs-schema.org">DCAT-AP classes and properties supported in Schema.org</a></li>
        </ul>
      </li>
-->
      <li><a href="#alignment-issues">Summary of alignment issues</a>
    </ul>

  </nav>
  <section>
    <h2><a name="background">Background</a></h2>
    <section>
      <h3><a name="background-dcat-ap">The <em>DCAT Application Profile for Data Portals in Europe</em> (DCAT-AP)</a></h3>
      <p>DCAT-AP [<a href="https://joinup.ec.europa.eu/asset/dcat_application_profile/">DCAT-AP</a>] is a metadata profile developed in the framework of the EU Programme <a href="http://ec.europa.eu/isa/"><em>Interoperability Solutions for European Public Administrations</em></a> (ISA), and based on and compliant with the <a href="http://www.w3.org/TR/2014/REC-vocab-dcat-20140116/">W3C Data Catalog vocabulary</a> (DCAT) - currently, one of the most widely used Semantic Web vocabularies for describing datasets and data catalogues.</p>
      <p>The purpose of DCAT-AP is to define a common interchange metadata format for data portals of the EU and of EU Member States. In order to achieve this, DCAT-AP defines a set of classes and properties, grouped into mandatory, recommended and optional. Such classes and properties correspond to information on datasets and data catalogues that are shared by many European data portals, aiding interoperability. Although DCAT-AP is designed to be independent from its actual implementation, RDF [<a href="http://www.w3.org/TR/2004/REC-rdf-concepts-20040210/">RDF</a>] and Linked Data [<a href="http://linkeddatabook.com/book">LDBOOK</a>] are the reference technologies.</p>
    </section>
    <section>
      <h3><a name="background-schema.org">Schema.org</a></h3>
      <p>Schema.org [<a href="http://schema.org/">Schema.org</a>] is an initiative promoted by Google, Microsoft, Yahoo and Yandex, aiming to develop and maintain metadata vocabularies for the description of Web resources, to be re-used by search engines to enhance online content indexing and discovery.</p>
      <p>From its launch in 2011, Schema.org has incrementally grown to cover a variety of domains, also through the re-use of existing popular vocabularies - as Dublin Core [<a href="http://dublincore.org/documents/dcmi-terms/">DC</a>], the Friend Of A Friend (FOAF) vocabulary [<a href="http://xmlns.com/foaf/spec/">FOAF</a>], vCard [<a href="https://www.w3.org/TR/vcard-rdf/">vCard</a>], as well as DCAT. According to an estimation reported in [<a href="http://queue.acm.org/detail.cfm?id=2857276">Guha &amp; al., 2015</a>], at the end of 2015 the adoption of Schema.org concerned around 12,000,000 Web sites.</p>
      <p>Typically, Schema.org is used to embed metadata in Web pages, using mechanisms as Microdata [<a href="https://html.spec.whatwg.org/multipage/microdata.html">Microdata</a>], RDFa [<a href="https://www.w3.org/TR/html-rdfa/">RDFa</a>] and JSON-LD [<a href="https://www.w3.org/TR/json-ld/">JSON-LD</a>]. The data model is based on and compliant with RDF.</p>
    </section>
    <section>
      <h3><a name="background-why">Aligning DCAT-AP with Schema.org</a></h3>
<!--
      <p>The motivation for investigating the possiblity of aligning DCAT-AP metadata with Schema.org is to define an alternative, harmonised representation of records compliant with DCAT-AP and its thematic extensions (e.g., geospatial and statistical), that will enhance their discoverability on the Web.</p>
-->
      <p>The motivation for investigating the possiblity of aligning DCAT-AP metadata with Schema.org is twofold:</p>
      <ol>
	      <li>To identify how to create a DCAT-AP-compliant representation of Schema.org metadata, in order to enable their sharing across DCAT-AP-enabled data catalogues.</li>
	      <li>To identify how to create a Schema.org-compliant representation of DCAT-AP metadata, in order to enhance their discoverability on the Web.</li>
      </ol>
      <p>In both cases, this analysis is not meant to provide a complete representation of all DCAT-AP metadata elements and those included in its thematic extensions (e.g., geospatial and statistical), but only of those supported by Schema.org.</p>
    </section>
  </section>
  <section>
    <h2><a name="methodology">Methodology</a></h2>
    <p>The reference DCAT-AP and Schema.org specifications used in this exercise are the following ones:</p>
    <ul>
      <li><a target="_blank" href="https://joinup.ec.europa.eu/asset/dcat_application_profile/asset_release/dcat-ap-v11">DCAT-AP v1.1</a> (<time datetime="2015-10-23">23 October 2015</time>)</li>
      <li><a target="_blank" href="https://joinup.ec.europa.eu/asset/dcat_application_profile/asset_release/geodcat-ap-v10">GeoDCAT-AP v1.0</a> (<time datetime="2015-12-23">23 December 2015</time>)</li>
      <li><a target="_blank" href="https://joinup.ec.europa.eu/asset/dcat-ap_implementation_guidelines/">DCAT-AP Implementation Guidelines</a> (DCAT-AP IG)</li>
      <li><a target="_blank" href="http://schema.org/version/2.2/">Schema.org 2.2</a> (<time datetime="2015-11-05">5 November 2015</time>)</li>
    </ul>
    <p>
    <p>For the mappings, existing work has been taken into account concerning the mapping of Schema.org to other metadata standards. In particular:</p>
    <ul>
      <li><a target="_blank" href="https://github.com/dcmi/schema.org">Schema.org to Dublin Core Map</a> (<time datetime="2011-12-12">12 December 2011</time>)</li>
      <li><a target="_blank" href="https://www.w3.org/wiki/WebSchemas/SKOS">WebSchemas/SKOS</a> (W3C WebSchemas wiki)</li>
    </ul>
    <p>DCAT-AP+Schema.org re-uses these specifications, and extends them to provide an as much as possible complete mapping of the metadata elements in DCAT-AP 1.1 and GeoDCAT-AP.</p>
<!--    
    <p>The resulting mappings have been grouped into two classes, corresponding to two different DCAT-AP+Schema.org profiles:</p>
    <ul>
    <li><strong>DCAT-AP+Schema.org</strong>: This profile defines alignments for the metadata elements defined in DCAT-AP</li>
    <li><strong>GeoDCAT-AP+Schema.org</strong>: This profile defines alignments covering the geospatial extension of DCAT-AP (GeoDCAT-AP)</li>
    </ul>
-->    
  </section>
  <section>
    <h2><a name="alignment-issues">Summary of alignment issues</a></h2>
    <p>A general issue is determined by the fact that Schema.org and DCAT-AP address different use cases. More precisely, the main purpose of Schema.org is to enhance discovery and indexing of online resources via search engines. As such, it is addressing more general objectives compared with DCAT-AP, that is instead meant to model in detail information on datasets and data catalogues.</p>
    <p>One of the main consequences is that some information that is relevant in DCAT-AP it is not modelled in Schema.org with specific terms. This results in a relevant amount of (a) "missing" and (b) "many-to-one" mappings - i.e., different metadata elements of DCAT-AP are mapped to the same element in Schema.org.</p>
    <p>This is not necessarily a problem, since the objective of mapping DCAT-AP and Schema.org is to enhance discoverability of DCAT-AP metadata on the Web, which does not require a complete, 1-to-1 representation of DCAT-AP metadata. Actually, the result of this exercise can also include the identification of the subset of DCAT-AP metadata elements that is worth representing in a Schema.org-based description. On the other hand, this situation also implies that a reverse mapping (i.e., from Schema.org to DCAT-AP) may be problematic or not possible.</p>
    <p>The following sections describe the DCAT-AP metadata elements posing mapping issues.</p>
    <section>
     <h3>Identifiers</h3>
     <p>This concerns properties<a target="_blank" title="http://purl.org/dc/terms/identifier" href="http://dublincore.org/documents/dcmi-terms/#terms-identifier"><code>dct:identifier</code></a> and <a target="_blank" title="http://www.w3.org/ns/adms#identifier" href="https://www.w3.org/TR/vocab-adms/#adms_identifier"><code>amds:identifier</code></a>, and class <a target="_blank" title="http://www.w3.org/ns/adms#Identifier" href="https://www.w3.org/TR/vocab-adms/#dt_identifier"><code>adms:Identifier</code></a>.</p>
     <p>Schema.org does not have generic properties for identifiers, but models identifiers only for some classes - e.g., <a target="_blank" title="http://schema.org/productID" href="http://schema.org/productID"><code>schema:productID</code></a>, which denotes the identifier of a <a target="_blank" title="http://schema.org/Product" href="http://schema.org/Product"><code>schema:Product</code></a>.</p>
     <p>It is to be investigated if properties as <a target="_blank" title="http://schema.org/productID" href="http://schema.org/productID"><code>schema:productID</code></a> could be used more broadly.</p>
     </section>
     <section>
     <h3>Categories and category schemes</h3>
     <p>This concerns classes <a target="_blank" title="http://www.w3.org/2004/02/skos/core#ConceptScheme" href="https://www.w3.org/TR/vocab-dcat/#class-concept-scheme"><code>skos:ConceptScheme</code></a> and <a target="_blank" title="http://www.w3.org/2004/02/skos/core#Concept" href="https://www.w3.org/TR/vocab-dcat/#class-concept"><code>skos:Concept</code></a>.</p>
     <p>Only few of the categories and categories schemes used in DCAT-AP are supported in Schema.org. The re-use of "external" controlled vocabularies is allowed in Schema.org, but how this can be modelled is unclear.</p>
     <p>Based on the documentation found online [<a target="_blank" href="https://www.w3.org/wiki/WebSchemas/ExternalEnumerations">WebSchemas-EE</a>], the approach seems to be based on the use of <a target="_blank" title="http://schema.org/Enumeration" href="http://schema.org/Enumeration"><code>schema:Enumeration</code></a> for <a target="_blank" title="http://www.w3.org/2004/02/skos/core#ConceptScheme" href="https://www.w3.org/TR/vocab-dcat/#class-concept-scheme"><code>skos:ConceptScheme</code></a>, but it is unclear how to state that a given <a target="_blank" title="http://www.w3.org/2004/02/skos/core#Concept" href="https://www.w3.org/TR/vocab-dcat/#class-concept"><code>skos:Concept</code></a> is in a given <a target="_blank" title="http://www.w3.org/2004/02/skos/core#ConceptScheme" href="https://www.w3.org/TR/vocab-dcat/#class-concept-scheme"><code>skos:ConceptScheme</code></a>.</p>
     <p>Another option could be to use <a target="_blank" title="http://schema.org/ItemList" href="http://schema.org/ItemList"><code>schema:ItemList</code></a> for <a target="_blank" title="http://www.w3.org/2004/02/skos/core#ConceptScheme" href="https://www.w3.org/TR/vocab-dcat/#class-concept-scheme"><code>skos:ConceptScheme</code></a>'s, and <a target="_blank" title="http://schema.org/ListItem" href="http://schema.org/ListItem"><code>schema:ListItem</code></a> for <a target="_blank" title="http://www.w3.org/2004/02/skos/core#Concept" href="https://www.w3.org/TR/vocab-dcat/#class-concept"><code>skos:Concept</code></a>'s, and to link the two with <a target="_blank" title="http://schema.org/itemListElement" href="http://schema.org/itemListElement"><code>schema:itemListElement</code></a>.</p>
     </section>
     <section>
     <h3>Resource "types"</h3>
     <p>This concerns properties denoting the "type" of a resource, by using a <a target="_blank" title="http://www.w3.org/2004/02/skos/core#Concept" href="https://www.w3.org/TR/vocab-dcat/#class-concept"><code>skos:Concept</code></a>. In DCAT-AP, this is typically done by using property <a target="_blank" title="http://purl.org/dc/terms/type" href="http://dublincore.org/documents/dcmi-terms/#terms-type"><code>dct:type</code></a>.</p>
     <p>Schema.org has a generic property, namely <a target="_blank" title="http://schema.org/additionalType" href="http://schema.org/additionalType"><code>schema:additionalType</code></a> - defined as a sub-property of <a target="_blank" title="http://www.w3.org/1999/02/22-rdf-syntax-ns#type" href="https://www.w3.org/TR/rdf-schema/#ch_type"><code>rdf:type</code></a>, that is meant to be used to associated multiple types with the same resource. It is to be investigated whether it can be used for this purpose.</p>
     </section>
     <section>
     <h3>Provenance</h3>
     <p>DCAT-AP uses property <a target="_blank" title="http://purl.org/dc/terms/provenance" href="http://dublincore.org/documents/dcmi-terms/#terms-provenance"><code>dct:provenance</code></a> to specify "provenance statements" about datasets (typically, their lineage).</p>
     <p>Schema.org does not have specific terms for this purpose, so a possible option is to use more generic ones, like <a target="_blank" title="http://schema.org/description" href="http://schema.org/description"><code>schema:description</code></a>.</p>
     </section>
     <section>
     <h3>Conformance</h3>
     <p>This concerns properties denoting the conformance of a resource with a standard. In DCAT-AP, this is typically done by using property <a target="_blank" title="http://purl.org/dc/terms/conformsTo" href="http://dublincore.org/documents/dcmi-terms/#terms-conformsTo"><code>dct:conformsTo</code></a>, which is used in different context (namely, to express conformance with a metadata standard, with a data schema, with a reference system, with given quality criteria).</p>
     <p>Schema.org does not have properties for this purpose, and it seems there are no suitable candidates that can be used.</p>
     </section>
     <section>
     <h3>Checksum</h3>
     <p>DCAT-AP allows the specification of the checksum of a dataset distribution by using specific classes and properties from the Software Package Data Exchange (SDPX) vocabulary [<a target="_blank" href="https://spdx.org/">SPDX</a>].</p>
     <p>Schema.org does not have terms for this purpose, and it seems there are no suitable candidates that can be used.</p>
     </section>
     <section>
     <h3>Licences, standards &amp; al.</h3>
     <p>Resources as licences and standards are modelled by specific classes and properties in DCAT-AP.</p>
     <p>In Schema.org, there is a general "type", namely <a target="_blank" title="http://schema.org/CreativeWork" href="http://schema.org/CreativeWork"><code>schema:CreativeWork</code></a>, further refined with a number of "sub-types" (e.g., <a target="_blank" title="http://schema.org/Dataset" href="http://schema.org/Dataset"><code>schema:Dataset</code></a> is one of these sub-types). However, none of them is specifically modelling resources as, e.g., licences and standards.</p>
     </section>
  </section>
  </article>
