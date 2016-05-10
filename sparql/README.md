<h1>SPARQL implementation of DCAT-AP+Schema.org</h1>
<p>This folder includes a set of <code>.req</code> files, specifying a tentative implementation of the mappings defined in DCAT-AP+Schema.org, in the form of <a target="_blank" href="https://www.w3.org/TR/sparql11-query/#construct">SPARQL <code>CONSTRUCT</code> queries</a>.</p>
<p>The mappings have been defined in a modular way, with a separate SPARQL query for each of the DCAT-AP classes, and related properties. A complete representation of a given resource (e.g., a dataset) and related resource (e.g., distribution, licence, publisher) can be obtained by combining the relevant SPARQL queries.</p>
<p>The defined SPARQL queries can be tested on the SPARQL endpoint of the <a target="_blank" href="http://inspire-sandbox.jrc.ec.europa.eu/geodcat-ap/">INSPIRE GeoDCAT-AP Sandbox</a>, that makes available a snapshot of the metadata records, in GeoDCAT-AP format, harvested by the <a target="_blank" href="http://inspire-geoportal.ec.europa.eu/">INSPIRE Geoportal</a>.</p>
<h2>Mappings for mandatory classes</h2>
<ul>
<li><a href="./agent.req"><code>agent.req</code></a>: Mappings for class "Agent" and related properties</li>
<li><a href="./catalogue.req"><code>catalogue.req</code></a>: Mappings for class "Catalogue" and related properties</li>
<li><a href="./dataset.req"><code>dataset.req</code></a>: Mappings for class "Dataset" and related properties</li>
</ul>
<h2>Mappings for recommended classes</h2>
<ul>
<li><a href="./category.req"><code>category.req</code></a>: Mappings for class "Category" and related properties</li>
<li><a href="./category-scheme.req"><code>category-scheme.req</code></a>: Mappings for class "Category scheme" and related properties</li>
<li><a href="./distribution.req"><code>distribution.req</code></a>: Mappings for class "Distribution" and related properties</li>
<li><a href="./licence.req"><code>licence.req</code></a>: Mappings for class "Licence document" and related properties</li>
</ul>
<h2>Mappings for optional classes</h2>
<ul>
<li><a href="./catalogue-record.req"><code>catalogue-record.req</code></a>: Mappings for class "Catalogue record" and related properties</li>
<li><a href="./checksum.req"><code>checksum.req</code></a>: Mappings for class "Checksum" and related properties</li>
<li><a href="./document.req"><code>document.req</code></a>: Mappings for class "Document" and related properties</li>
<li><a href="./identifier.req"><code>identifier.req</code></a>: Mappings for class "Identifier" and related properties</li>
<li><a href="./kind.req"><code>kind.req</code></a>: Mappings for class "Kind" and related properties</li>
<li><a href="./location.req"><code>location.req</code></a>: Mappings for class "Location" and related properties</li>
<li><a href="./media-type.req"><code>media-type.req</code></a>: Mappings for class "Media type or extent" and related properties</li>
<li><a href="./period-of-time.req"><code>period-of-time.req</code></a>: Mappings for class "Period of time" and related properties</li>
<li><a href="./reference-system.req"><code>reference-system.req</code></a>: Mappings for class "Reference system" and related properties</li>
<li><a href="./rights.req"><code>rights.req</code></a>: Mappings for class "Rights statement" and related properties</li>
<li><a href="./service.req"><code>service.req</code></a>: Mappings for class "Service" and related properties</li>
<li><a href="./standard.req"><code>standard.req</code></a>: Mappings for class "Standard" and related properties</li>
</ul>

