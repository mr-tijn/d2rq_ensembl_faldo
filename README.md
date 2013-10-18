d2rq_ensembl_faldo
==================

A d2rq mapping to expose ensembl using FALDO 

Still in EXPERIMENTAL state !

Created using d2rq's generate-mapping on a simplified schema for ensembl,
and manual editing.

Currently works under d2r-server, and can be included as a fuseki graph,
but this needs some (dirty) patching to the d2rq source.

The simplified mapping is tested on d2r-server out of the box.
Better performance is gained when dumping to rdf, and storing in a triplestore.

E.g. using jena:

in d2r folder:
./dump-rdf -o test.rdf -b http://www.boinq.org/homo_sapiens_core_71_37_simple/ homo_sapiens_core_71_37_simple.ttl

in jena/bin folder:
./tdbloader2 --loc DESTFOLDER homo_sapiens_core_71_37_simple.ttl
