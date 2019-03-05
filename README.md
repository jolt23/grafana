# Grafana

Grafana HA deployment using Redis and Postgres as backends. Redis is used for
distributed session management, and Postgres is used to save dashboard and
state.

## Getting Started

Using `docker-compose` you can easily start the Grafana instances which will be
configured with Redis and Postgres backends.

```bash
$ docker-compose up -d
```

Grafana UI will be available at `http://localhost:8080` initial username and
password will be admin/password.

### Persisted Data

Postgres data is being saved to under local directory of repository `./data`.
No other container data is being persisted.

### NGINX Load Balancing

A simple NGINX Load Balancer is used to direct traffic to, two running grafana
instances.

This configuration can be configured through `./config/nginx.conf` file.

## Authors

- jolt23
