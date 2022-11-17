# PostgreSQL Envoy TLS Proxy

TLS terminating PostgreSQL proxy. As PostgreSQL implements TLS on application level you need this to provide valid certificate to the client. This is needed when you need connect from Power BI cloud service to AWS Aurora RDS service.

See extension [documentation](https://www.envoyproxy.io/docs/envoy/latest/api-v3/extensions/filters/network/postgres_proxy/v3alpha/postgres_proxy.proto]

## Features

1. TLS termination
2. Automated certificate rotation using [cert-manager](https://cert-manager.io/docs/)
3. Enforce user using PGBouncer to support read only users
4. Exposing service using [ExternalDNS](https://github.com/kubernetes-sigs/external-dns)

## Usage

```bash
$ helm repo add orgis https://orgis.github.io/charts/
$ helm search repo orgis
$ helm install proxy orgis/postgresql-envoy-tls-proxy
```
