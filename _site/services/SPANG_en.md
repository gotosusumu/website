# SPANG
### What is SPANG?
SPANG is a command-line SPARQL client supporting query generation for distributed RDF databases.

### Features of SPANG
* Generates simple SPARQL queries
* Calls SPARQL libraries on the Web
* Enables combinatorial execution of multiple queries

### Usage
* Using SPARQL shortcuts
```
    spang uniprot -S tax:511145
    spang uniprot -S tax:511145 -a
    spang uniprot -S tax:511145 -q
    spang uniprot -S tax:511145 -f rdfxml
    spang uniprot -S tax:511145 -P up:otherName
    spang uniprot -S tax:511145 -P rdfs:subClassOf+/up:scientificName
    spang uniprot -P a -O up:Protein -N
    spang mbgd -L 10
    spang mbgd -G
    spang mbgd -O tax:511145 -G
    spang mbgd -F mbgdr:organism -O tax:511145
```
* Using SPARQL templates
```
    spang uniprot taxtree_ancestor 511145 -vac
    spang uniprot taxtree_ancestor 511145 -f json
    spang chembl list_dataset -vac
    spang chembl count_each_graph -vac
    spang mbgd search_each_class 'cyanobacteri*' -vac
    spang mbgd search_with_class orthology:OrthologsCluster 'photosystem ii' -vac
    spang mbgd mbgdl:get_ortholog K9Z723 | spang uniprot -S 1 -P rdfs:label
    spang mbgd mbgdl:get_ortholog K9Z723 | spang uniprot uniprot_xref PDB
    spang mbgd path/to/query.rq
```
* Typing SPARQL directly
```
    spang mbgd 'select * where {?s ?p ?o} limit 10'
```
* Using SPARQL code saved in clipboard
```
    pbpaste | spang uniprot -
```  

### Reference
Hirokazu Chiba and Ikuo Uchiyama. SPANG: a SPARQL client supporting generation and reuse of queries for distributed RDF databases. *BMC Bioinformatics*, 18:93 (2017).
