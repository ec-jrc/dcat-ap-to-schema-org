<article>
<header>
<h1>Mappings defined in DCAT-AP+Schema.org (3/3)</h1>
<p><a href="./Mappings.md">Part 1</a> | <a href="./Mappings-continued.md">Part 2</a> | Part 3</p>
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
<p>A SPARQL implementation of the defined mappings is available in a dedicated folder (<a href="../sparql/"><code>../sparql/</code></a>).</p>
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
<li><a href="./Mappings-continued.md#mapping-properties-mandatory">Properties for mandatory classes</a></li>
<li><a href="./Mappings-continued.md#mapping-properties-recommended">Properties for recommended classes</a></li>
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
<p><em>continues from <a href="./Mappings-continued.md">part 2</a></em>&hellip;</p>
<!-- Properties -->
<section id="mapping-properties-optional">
<h3><a name="mapping-properties-optional">Properties for optional classes</a></h3>
<!-- Properties: Catalogue record -->
<section id="mapping-properties-catalogue-record">
<h4><a name="mapping-properties-catalogue-record">Catalogue record</a></h4>
<p>These properties should be used with <a target="_blank" href="http://schema.org/ListItem"><code>schema:ListItem</code></a>. [<a href="../sparql/catalogue-record.req">formal definition</a>]</p>
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
<p>TBD <!--[<a href="../sparql/checksum.req">formal definition</a>]--></p>
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
<p>TBD [<a href="../sparql/document.req">formal definition</a>]</p>
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
<p>TBD [<a href="../sparql/identifier.req">formal definition</a>]</p>
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
<p>These properties should be used with <a target="_blank" href="http://schema.org/ContactPoint"><code>schema:ContactPoint</code></a>. [<a href="../sparql/kind.req">formal definition</a>]</p>
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
<p>These properties should be used with <a target="_blank" href="http://schema.org/Place"><code>schema:Place</code></a>. [<a href="../sparql/location.req">formal definition</a>]</p>
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
<p>TBD [<a href="../sparql/media-type.req">formal definition</a>]</p>
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
<p>These properties should be used with <a target="_blank" href="http://schema.org/DateTime"><code>schema:DateTime</code></a>. [<a href="../sparql/period-of-time.req">formal definition</a>]</p>
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
