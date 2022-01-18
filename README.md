# nats playground

This playground uses docker to set up an environment that reflects a SaaS <-> on-premise(s) network deployment using nats.io.

A Docker network is created for the SaaS and a 3 node nats.io server cluster, is configured within this network.

Two other docker networks are defined to represent two separate organisations connecting to the SaaS network. One represented with the label hsbc and the other with the label diaego.

The diaego network like the SaaS network has a 3 node nats.io server cluster.

The hsbc network contains two 3 node nats.io server cluster, both clusters run in the same network. This configuration simulates an environment where each nats server is servicing a subset of the total nats publisher / subscriber within an organisation.

nats.io provides support natively for this type of deployment, its describes using the term leaf, further information is available in this article -- https://docs.nats.io/running-a-nats-service/configuration/leafnodes

## requirements

- Docker
- [Docker Compose](https://docs.docker.com/compose/)
- [Tmuxinator](https://github.com/tmuxinator/tmuxinator)

The solution uses TLS to encrypt the traffic, see [this document](./TLS.md) for details. If you plan to interact externally with the docker containers (through exposed ports), read this document to understand how to do this.

## usage

To start up a [tmuxinator](https://github.com/tmuxinator/tmuxinator) session.

```shell
mux local
```

When running the playground can be stopped as follows.

```shell
mux stop nats
```
