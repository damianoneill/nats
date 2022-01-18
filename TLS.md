# TLS

nats.io describes the TLS process in the following documents:

- https://docs.nats.io/using-nats/developer/security/tls
- https://docs.nats.io/running-a-nats-service/configuration/securing_nats/tls#creating-self-signed-certificates-for-testing

The self signing process used in this playground uses [mkcert](https://github.dev/FiloSottile/mkcert) a BSD-3 tool for making locally-trusted development certificates.

I've defined a [Dockerfile](./compose/Dockerfile.nats) that extends the nats:alpine and installs mkcert so that it can be used to create the appropriate infrastructure inside each of the running containers.

## usage

To use the generated CA, install mkcerts on your os of choice. Following the instruction here https://github.com/FiloSottile/mkcert#installation then install the CA generated in docker using the following command.

```shell
CAROOT=config/certs/ca mkcert -install
```

This will install the generated rootCA into your local trust store on osx, windows or linux. Which will allow you to use any docker certificates exposed from the running docker containers.
