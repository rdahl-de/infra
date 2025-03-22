# rdahl.de infastructure

This repository host an infrastructure-as-code definition of the rdahl.de server.

## public domains

[rdahl.de](https://rdahl.de) - Serves this repository's `www` directory.

[torge.rdahl.de](https://torge.rdahl.de) - Torge Rosendahl's personal website.

<!--[victoria.rdahl.de](https://victoria.rdahl.de) - Victoria Fricke's personal website.-->

[matrix.rdahl.de](https://matrix.rdahl.de) - A synapse matrix server.

<!--
I deliberately left out the wedding website here, because I want to avoid too many people finding it early.
If you read this, congratulations, you sneaky son. keep slaying! 💅

[wedding.rdahl.de](https://wedding.rdahl.de) - Nothing to see here 👀.
-->

## running this

Just clone the repository into `/opt` and do a quick `docker compose up -d`.

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

### dotenv

To configure some services, a `.env` file is required.

Please rename `example.env` to `.env` after cloning and change the secrets to something secret.
