# Containers
- e.g. Docker
- Containerized applications run inside a container.
- To orchestrate/handle/communicate between containers, need a 'container orchestration tool' like Kubernates. (e.g GKE - Google Kubernestes Engine)


# Docker Image
- Contains code, libraries, tools and all dependencies.
- Command: docker build


# How to store maven dependencies in docker image
1. Pull a maven image (normally you call this stage the 'builder' - it's just a name)
2. Copy your pom.xml file into a working directory
3. Run maven once to get your dependencies and then again to package it up
4. Create a new image base from openjdk
5. Copy the result of step 3 into your app image
6. Expose a port
7. Provide an entry point

Here's what that looks like in a Dockerfile:

FROM maven AS builder
WORKDIR /usr/src/analytics
COPY pom.xml .
RUN mvn -B dependency:go-offline

COPY . .
RUN mvn package

FROM openjdk:8-jdk-alpine
WORKDIR /analytics-service
COPY --from=builder /usr/src/analytics/target/YOUR_JAR_FILENAME.jar .
EXPOSE 80
ENTRYPOINT ["java", "-jar", "/analytics-service/YOUR_JAR_FILENAME.jar"]