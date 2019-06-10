# Spring Boot Metrics Example

A Spring Boot application capturing metrics using [Micrometer](http://micrometer.io/).
[Prometheus](https://prometheus.io/) scrapes and stores the metrics whilst reporting is done in [Grafana](https://grafana.com/).

## Start the Example

Prometheus scrapes the metrics using a HTTP call and therefore needs access to the running application.
An easy way to achieve this, is to run the Spring Boot application in a Docker container too.

We therefore build a Docker image using [jib](https://github.com/GoogleContainerTools/jib) and start it using Docker Compose.

```sh
./gradlew jibDockerBuild
docker-compose up -d
```

The example is accessible on:

* Spring Boot: http://localhost:8080
* Grafana: http://localhost:3000
    * User: admin
    * Password: admin
* Prometheus: http://localhost:9090

The Prometheus data source and a [JVM dashboard](https://grafana.com/dashboards/4701) are automatically provisioned in Grafana.