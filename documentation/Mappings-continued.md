<article>
<header>
<h1>Mappings defined in DCAT-AP+Schema.org (2/2)</h1>
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
<li><a href="./Mappings.md#introduction">Introduction</a></li>
<li><a href="./Mappings.md#used-namespaces">Used namespaces</a></li>
<li><a href="./Mappings.md#ref-code-lists">Reference code lists for metadata elements</a></li>
<li><a href="./Mappings.md#mapping-summary">Mapping summary</a>
<ul>
<li><a href="./Mappings.md#mapping-classes">Classes</a></li>
<li><a href="#mapping-properties-mandatory">Properties for mandatory classes</a></li>
<li><a href="#mapping-properties-recommended">Properties for recommended classes</a></li>
<li><a href="#mapping-properties-optional">Properties for optional classes</a></li>
</ul>
</li>
<!--
<li><a href="#mapping-formal">Formal definition</a>
<ul>
<li><a href="#mapping-formal-mandatory">Mandatory classes</a></li>
<li><a href="#mapping-formal-recommended">Recommended classes</a></li>
<li><a href="#mapping-formal-optional">Optional classes</a></li>
</ul>
</li>
-->
</ul>
</nav>
<section>
<h2>Mapping summary</h2>
<p><em>continues</em>&hellip; (<a href="./Mappings.md">go to previous page</a>)</p>
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
</section>
</article>
