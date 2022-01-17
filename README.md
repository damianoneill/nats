# nats playground

## requirements

- Docker
- [Docker Compose](https://docs.docker.com/compose/)
- Tmuxinator

The solution uses TLS to encrypt/authenticate, see [this document](./TLS.md) for details.  If you plan to interact externally with the docker containers (through exposed ports), read this document to understand how to do this.

## usage

To start up a [tmuxinator](https://github.com/tmuxinator/tmuxinator) session.

```shell
mux local
```

When running the playground can be stopped as follows.

```shell
mux stop nats
```
