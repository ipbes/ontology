# Ontology
A standardized RDF vocabulary for representing information from IPBES products on the Semantic Web. These products are listed on https://github.com/IPBES-Data/IPBES_LOD. This repository will host different IPBES ontologies.

The first one that has been developed is REPORT which represents intergovernmental reports and the broad topics and information that they cover. More information about this ontology can be found at: https://github.com/IPBES-Data/IPBES_Ontology

## Example Usage
1. In RDF/Turtle Syntax
```
@prefix ipbes: <http://ontology.ipbes.net/report> .

<http://ontology.ipbes.net/report/bgm/IAS23-A> a ipbes:BackgroundMessage ;
    ipbes:Report <http://ontology.ipbes.net/report/IAS23> ;
    ipbes:hasDescription "Invasive alien species are a major threat to nature, nature’s contributions to people, and good quality of life" ;
    ipbes:identifier "A" ;
```
2. In SPARQL Query
```
@prefix ipbes: <http://ontology.ipbes.net/report> .

SELECT ?Report ?Chapter
WHERE {
    ?report ipbes:Report ?Report .
    FILTER(CONTAINS(?Report, "Invasive"))  # Find reports with "Invasive" in their title
}
```
