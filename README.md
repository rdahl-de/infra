# rdahl.de infastructure

This repository host an infrastructure-as-code definition of the rdahl.de server.

## public domains

[torge.rdahl.de](https://torge.rdahl.de) - Torge Rosendahl's personal homepage.  
[victoria.rdahl.de](https://victoria.rdahl.de) - Victoria Fricke's personal homepage.

## running this

Just clone the repository into /opt and do a quick `docker compose up -d`.

You need to create `./letsencrypt/acme.json` with 600 permissions (root) after cloning.

Watchtower will take care of automatically deploying the latest images of all services.
