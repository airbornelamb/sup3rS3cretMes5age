# Secretmessage!

A simple, secure self-destructing message service, using HashiCorp Vault product as a backend.

This repo is forked from the algolia version. It is updated to include the linux x64 binary (so you don't have to figure out how to compile golang like I did) and for use with Traefik v2.

<img width="610" alt="secretmsg" src="https://user-images.githubusercontent.com/357094/29357449-e9268adc-8277-11e7-8fef-b1eabfe62444.png">

Read more about the reasoning behind the algolia version in this [relevant](https://blog.algolia.com/secure-tool-for-one-time-self-destructing-messages/) blog post.

### Prerequisites

* [Go](https://golang.org/doc/install) (for building on other platforms than linux x64)
* [Docker](https://docs.docker.com/engine/installation/)
* [Docker-Compose](https://docs.docker.com/compose/install/)
* Traefik
* Make

### How to use

1. Clone this repo
2. Ensure you have `docker` and `docker-compose` installed on server
3. Edit `docker-compose.yml` to replace `VAULT_DEV_ROOT_TOKEN_ID` and `VAULT_TOKEN` with a token you have generated (such as from pwgen)
4. Replace references in `docker-compose.yml` to `secretmessage.example.org` with your domain.
5. Bring it up! `docker-compose up -d && docker-compose logs -f`


### Security notice!

You should always run this behind SSL/TLS; otherwise, a message will be sent unencrypted!

### Contributing

Pull requests are very welcome!
