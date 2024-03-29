## Development

To start your application in the dev profile, simply run:

    ./mvnw

For further instructions on how to develop with JHipster, have a look at [Using JHipster in development][].

## Building for production

To optimize the smd application for production, run:

    ./mvnw -Pprod clean package

To ensure everything worked, run:

    java -jar target/*.war

Refer to [Using JHipster in production][] for more details.

## Testing

To launch your application's tests, run:

    ./mvnw clean test

For more information, refer to the [Running tests page][].

### Code quality

Sonar is used to analyse code quality. You can start a local Sonar server (accessible on http://localhost:9001) with:

```
docker-compose -f src/main/docker/sonar.yml up -d
```

Then, run a Sonar analysis:

```
./mvnw -Pprod clean test sonar:sonar
```

For more information, refer to the [Code quality page][].

## Using Docker to simplify development (optional)

You can use Docker to improve your JHipster development experience. A number of docker-compose configuration are available in the [src/main/docker](src/main/docker) folder to launch required third party services.

For example, to start a oracle database in a docker container, run:

    docker-compose -f src/main/docker/oracle.yml up -d

To stop it and remove the container, run:

    docker-compose -f src/main/docker/oracle.yml down

You can also fully dockerize your application and all the services that it depends on.
To achieve this, first build a docker image of your app by running:

    ./mvnw package -Pprod verify jib:dockerBuild

Then run:

    docker-compose -f src/main/docker/app.yml up -d

For more information refer to [Using Docker and Docker-Compose][], this page also contains information on the docker-compose sub-generator (`jhipster docker-compose`), which is able to generate docker configurations for one or several JHipster applications.

## Continuous Integration (optional)

To configure CI for your project, run the ci-cd sub-generator (`jhipster ci-cd`), this will let you generate configuration files for a number of Continuous Integration systems. Consult the [Setting up Continuous Integration][] page for more information.

[jhipster homepage and latest documentation]: https://www.jhipster.tech
[jhipster 5.7.2 archive]: https://www.jhipster.tech/documentation-archive/v5.7.2
[doing microservices with jhipster]: https://www.jhipster.tech/documentation-archive/v5.7.2/microservices-architecture/
[using jhipster in development]: https://www.jhipster.tech/documentation-archive/v5.7.2/development/
[service discovery and configuration with the jhipster-registry]: https://www.jhipster.tech/documentation-archive/v5.7.2/microservices-architecture/#jhipster-registry
[using docker and docker-compose]: https://www.jhipster.tech/documentation-archive/v5.7.2/docker-compose
[using jhipster in production]: https://www.jhipster.tech/documentation-archive/v5.7.2/production/
[running tests page]: https://www.jhipster.tech/documentation-archive/v5.7.2/running-tests/
[code quality page]: https://www.jhipster.tech/documentation-archive/v5.7.2/code-quality/
[setting up continuous integration]: https://www.jhipster.tech/documentation-archive/v5.7.2/setting-up-ci/
