# rdahl.de infastructure

This repository host an infrastructure-as-code definition of the rdahl.de server.

## public domains

[rdahl.de](https://rdahl.de) - Serves this repository's `www` directory.

[torge.rdahl.de](https://torge.rdahl.de) - Torge Rosendahl's personal homepage.

<!--[victoria.rdahl.de](https://victoria.rdahl.de) - Victoria Fricke's personal homepage.-->

[matrix.rdahl.de](https://matrix.rdahl.de) - A synapse matrix server.

## running this

Just clone the repository into /opt and do a quick `docker compose up -d`.

Watchtower will take care of automatically deploying the latest images of all services.

### letsencrypt

You need to create `./letsencrypt/acme.json` with 600 permissions (root) after cloning:

```bash
mkdir -p letsencrypt && touch letsencrypt/acme.json && chmod 600 letsencrypt/acme.json
```

### synapse (matrix)

You need to create the synapse config:

```bash
docker compose run -it --rm synapse generate
```

Now, you can edit the homeserver.yaml file if necessary.
