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



