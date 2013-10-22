d2rq_ensembl_faldo
==================

A d2rq mapping to expose ensembl core features using FALDO 

Still in beta state: only use for testing.

Created using d2rq's generate-mapping on a simplified schema for ensembl,
and manual editing.

The simplified mapping should run on d2r-server out of the box. To run:
* download a version of ensembl core (tested with 71_37 and 72_37)
* create an extra column for the purl in the ensembl core db (see info in the ttl file)
* edit the ttl file to point to your local database + edit username/password
* download d2rq from d2rq.org (tested with 0.8.1)
* start d2r-server using the mapping file: ./d2r-server homo_sapiens_core_71_37_simple.ttl
* browse to your localhost:3030

Better performance is obtained when dumping to rdf, and storing in a triplestore. E.g. using jena with a TDB backend:

in d2r folder:
./dump-rdf -o ensembl_simple.ttl -b http://www.boinq.org/homo_sapiens_core_71_37_simple/ homo_sapiens_core_71_37_simple.ttl

in jena/bin folder:
./tdbloader2 --loc TDB_FOLDER ensembl_simple.ttl
