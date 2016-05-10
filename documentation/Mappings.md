

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

