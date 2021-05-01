<h1>SPARQL implementation of DCAT-AP+Schema.org</h1>
<p>This folder includes a set of <code>.rq</code> files, specifying a tentative implementation of the mappings defined in DCAT-AP+Schema.org, in the form of <a target="_blank" href="https://www.w3.org/TR/sparql11-query/#construct">SPARQL <code>CONSTRUCT</code> queries</a>.</p>
<p>The mappings have been defined in a modular way, with a separate SPARQL query for each of the DCAT-AP classes, and related properties. A complete representation of a given resource (e.g., a dataset) and related resource (e.g., distribution, licence, publisher) can be obtained by combining the relevant SPARQL queries.</p>
<!--
<p>The defined SPARQL queries can be tested on the SPARQL endpoint of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a>, that makes available a snapshot of the metadata records, in GeoDCAT-AP format, harvested by the <a target="_blank" href="http://inspire-geoportal.ec.europa.eu/">INSPIRE Geoportal</a>.</p>
-->
<h2>Mappings for mandatory classes</h2>
<ul>
<li><a href="./agent.rq"><code>agent.rq</code></a>: Mappings for class "Agent" and related properties</li>
<li><a href="./catalogue.rq"><code>catalogue.rq</code></a>: Mappings for class "Catalogue" and related properties</li>
<li><a href="./dataset.rq"><code>dataset.rq</code></a>: Mappings for class "Dataset" and related properties</li>
</ul>
<h2>Mappings for recommended classes</h2>
<ul>
<li><a href="./category.rq"><code>category.rq</code></a>: Mappings for class "Category" and related properties</li>
<li><a href="./category-scheme.rq"><code>category-scheme.rq</code></a>: Mappings for class "Category scheme" and related properties</li>
<li><a href="./distribution.rq"><code>distribution.rq</code></a>: Mappings for class "Distribution" and related properties</li>
<li><a href="./licence.rq"><code>licence.rq</code></a>: Mappings for class "Licence document" and related properties</li>
</ul>
<h2>Mappings for optional classes</h2>
<ul>
<li><a href="./address-agent.rq"><code>address-agent.rq</code></a>: Mappings for class "Address" (<code>locn:Address</code>) and related properties</li>
<li><a href="./address-kind.rq"><code>address-kind.rq</code></a>: Mappings for class "Address" (<code>vcard:Address</code>) and related properties</li>
<li><a href="./catalogue-record.rq"><code>catalogue-record.rq</code></a>: Mappings for class "Catalogue record" and related properties</li>
<li><a href="./checksum.rq"><code>checksum.rq</code></a>: Mappings for class "Checksum" and related properties</li>
<li><a href="./data-service.rq"><code>data-service.rq</code></a>: Mappings for class "Data service" and related properties</li>
<li><a href="./document.rq"><code>document.rq</code></a>: Mappings for class "Document" and related properties</li>
<li><a href="./identifier.rq"><code>identifier.rq</code></a>: Mappings for class "Identifier" and related properties</li>
<li><a href="./kind.rq"><code>kind.rq</code></a>: Mappings for class "Kind" and related properties</li>
<li><a href="./location.rq"><code>location.rq</code></a>: Mappings for class "Location" and related properties</li>
<li><a href="./media-type.rq"><code>media-type.rq</code></a>: Mappings for class "Media type or extent" and related properties</li>
<li><a href="./period-of-time.rq"><code>period-of-time.rq</code></a>: Mappings for class "Period of time" and related properties</li>
<li><a href="./provenance.rq"><code>provenance.rq</code></a>: Mappings for class "Provenance statement" and related properties</li>
<li><a href="./quality-measurement.rq"><code>quality-measurement.rq</code></a>: Mappings for class "Quality measurement" and related properties</li>
<!--
<li><a href="./reference-system.rq"><code>reference-system.rq</code></a>: Mappings for class "Reference system" and related properties</li>
-->
<li><a href="./rights.rq"><code>rights.rq</code></a>: Mappings for class "Rights statement" and related properties</li>
<!--
<li><a href="./service.rq"><code>service.rq</code></a>: Mappings for class "Service" and related properties</li>
-->
<li><a href="./standard.rq"><code>standard.rq</code></a>: Mappings for class "Standard" and related properties</li>
</ul>

