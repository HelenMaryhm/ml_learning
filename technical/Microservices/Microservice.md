# Microservice architecture



# TRY - CONFIG SERVER NOT HEALTHY


config_v2: digest: sha256:41e4b4e2a41cd19f7545bf4eded4bae2a06a4d0dd2ff9e2d413d51a6d89c4b3e size: 1788
(base) hmaryt@R06VTWRMW5 config % curl --fail --silent localhost:8071/actuator/health/readiness | grep UP         
(base) hmaryt@R06VTWRMW5 config % curl --fail --silent localhost:8071/actuator/health/readiness          
(base) hmaryt@R06VTWRMW5 config % curl localhost:8071/actuator/health/readiness
curl: (7) Failed to connect to localhost port 8071 after 0 ms: Couldn't connect to server
(base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/health 
curl: (7) Failed to connect to localhost port 8071 after 0 ms: Couldn't connect to server
(base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/health
curl: (52) Empty reply from server
(base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/health
curl: (52) Empty reply from server
(base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/health
curl: (52) Empty reply from server
(base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/health
curl: (52) Empty reply from server
(base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/health
curl: (52) Empty reply from server
(base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/health
curl: (52) Empty reply from server
(base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/health
curl: (52) Empty reply from server
(base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/health
^[[A{"timestamp":"2024-05-12T03:48:13.797+00:00","status":404,"error":"Not Found","path":"/health"}%              (base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/health
{"timestamp":"2024-05-12T03:48:17.029+00:00","status":404,"error":"Not Found","path":"/health"}%                  (base) hmaryt@R06VTWRMW5 config % curl -k -X GET http://localhost:8071/actuator/health
{"status":"DOWN","components":{"binders":{"status":"DOWN","components":{"rabbit":{"status":"DOWN","details":{"error":"org.springframework.amqp.AmqpConnectException: java.net.ConnectException: Connection refused"}}}},"clientConfigServer":{"status":"UNKNOWN","details":{"error":"no property sources located"}},"configServer":{"status":"UP","details":{"repositories":[{"name":"app","profiles":["default"],"label":null}]}},"discoveryComposite":{"description":"Discovery Client not initialized","status":"UNKNOWN","components":{"discoveryClient":{"description":"Discovery Client not initialized","status":"UNKNOWN"}}},"diskSpace":{"status":"UP","details":{"total":105088212992,"free":76442419200,"threshold":10485760,"path":"/.","exists":true}},"livenessState":{"status":"UP"},"ping":{"status":"UP"},"rabbit":{"status":"DOWN","details":{"error":"org.springframework.amqp.AmqpConnectException: java.net.ConnectException: Connection refused"}},"reactiveDiscoveryClients":{"description":"Discovery Client not initialized","status":"UNKNOWN","components":{"Simple Reactive Discovery Client":{"description":"Discovery Client not initialized","status":"UNKNOWN"}}},"readinessState":{"status":"UP"},"refreshScope":{"status"(base) hmaryt@R06VTWRMW5 config %

# ---------------------------

503 Service Unavailable

{
    "status": "DOWN",
    "components": {
        "binders": {
            "status": "DOWN",
            "components": {
                "rabbit": {
                    "status": "DOWN",
                    "details": {
                        "error": "org.springframework.amqp.AmqpConnectException: java.net.ConnectException: Connection refused"
                    }
                }
            }
        },
        "clientConfigServer": {
            "status": "UNKNOWN",
            "details": {
                "error": "no property sources located"
            }
        },
        "configServer": {
            "status": "UP",
            "details": {
                "repositories": [
                    {
                        "name": "app",
                        "profiles": [
                            "default"
                        ],
                        "label": null
                    }
                ]
            }
        },
        "discoveryComposite": {
            "description": "Discovery Client not initialized",
            "status": "UNKNOWN",
            "components": {
                "discoveryClient": {
                    "description": "Discovery Client not initialized",
                    "status": "UNKNOWN"
                }
            }
        },
        "diskSpace": {
            "status": "UP",
            "details": {
                "total": 105088212992,
                "free": 76442357760,
                "threshold": 10485760,
                "path": "/.",
                "exists": true
            }
        },
        "livenessState": {
            "status": "UP"
        },
        "ping": {
            "status": "UP"
        },
        "rabbit": {
            "status": "DOWN",
            "details": {
                "error": "org.springframework.amqp.AmqpConnectException: java.net.ConnectException: Connection refused"
            }
        },
        "reactiveDiscoveryClients": {
            "description": "Discovery Client not initialized",
            "status": "UNKNOWN",
            "components": {
                "Simple Reactive Discovery Client": {
                    "description": "Discovery Client not initialized",
                    "status": "UNKNOWN"
                }
            }
        },
        "readinessState": {
            "status": "UP"
        },
        "refreshScope": {
            "status": "UP"
        }
    },
    "groups": [
        "liveness",
        "readiness"
    ]
}

# ---------------------------

To be removed:
"credsStore": "osxkeychain",
  "currentContext": "rancher-desktop"



# STORING CONFIG IN GETHUB REPO:

https://github.com/HelenMaryhm/st-ignatius-church-virudhunagar-config.git





# PROFILES

Run -> Modify -> Run configurations

CLI
Program arguments -> --spring.profiles.active=prod

1. CLI
2. JVM
3. Environment Variables

Has disadvantages.
Github action, jenkins - can do.

# SOLUTION
Store and maintain in different repo.
Auditing configuration.
spring cloud config server.

# SPRING CLOUD CONFIG
- acts as a centralized config server.
- join as clients

- choose a location to store.

******************************************************************************
# CLOUD NATIVE APPLICATIONS

- s/w developed mainly for cloud.
- CNCF Cloud Naive Computing Foundation
- resilient (failure management); fault tolerant
- scale application using kuberentes
- devops practices
- loadbalancing

CI (OR) CD (OR) CD
continuous integration (OR) continuous deployment (OR) continuous delivery


******************************************************************************

# DOCKER EXTENSIONS

Logs Explorer

******************************************************************************

# Common docker commands

docker images
docker image inspect <image-id>
docker image rm <image-id>
docker image prune
docker image push <container-registry/username:tag>
docker image pull <container-registry/username:tag>
docker rmi <image-id>

docker build . -t <image-name>
docker run -p <host-port>:<container-port> <image-name>
docker ps
docker ps -a

docker system prune
docker login -u <username>
docker logout
docker history <image-name>
docker exec -it <container-id> sh

docker compose up
docker compose down

docker container start <container-id>
docker container pause <container-id>
docker container unpause <container-id>
docker container stop <container-id>
docker container kill <container-id>
docker container restart <container-id>
docker container inspect <container-id>
docker container logs <container-id>
docker container logs -F <container-id>
docker container rm <container-id>
docker container prune
docker container stats

******************************************************************************




# DOCKER COMPOSE

- tool for defining and running multiple ms (run commands)
- single yaml file
- http://docs.docker.com/compose/
- docker compose version

Docker Compose version v2.24.7

Step1: Create a config file in any one microservice
Step2: docker-compose.yml
Step3: need a 'tab' space

services:
    <service-name>:
        image: "xxx"
        container_name: "stignatius-ms"
        ports:
            - "8080:8080"
        deploy:
            resources:
                limits:
                    memory: 700m

YAML -> '-' hyphen to give multiple elements.
m    -> MB

# Tag all images in same n/w so that all microservices can communicate with each other

- give networks

# How to give 'docker compose up' command.
Run from the MS where this file is present.

In detached mode.

docker compose up -d

# To remove containers

docker compose down

docker compose start
docker compose stop




***********************************************

## CHALLENGE 3

DEPLOYMENT, PORTABILITY & SCALABILITY

* namespace
* cg groups (control groups)

Namespace -> isolated environment on same OS kernel(Linux).

Linux          -> Docker engine
MacOS, Windows -> Docker client. A light weight virtual machine is configured with Linux and docker server component in installed within it.

# APPROACH TO GENERATE DOCKER IMAGE

(i) Dockerfile
(ii) Buildpacks
(iii) google gib (Java)

build to get jar. 

# MAVEN COMMAND
mvn spring-boot:run

# GRADLE COMMAND
./gradlew bootRun

# JAVA COMMAND
java -jar build/libs/stignatius-0.0.1-SNAPSHOT.jar

# CREATE DOCKER FILE
Dockerfile without extension

Tell docker has a dependency on java. Provide base image with tag(version). Colon is mandatory

FROM openjdk:23-ea-17-jdk-slim

COPY loc jar
Please take jar and make a 

ENTRYPOINT 

# RUNNING DOCKER

docker version

docker build . -t 

(docker image name - standard format
docker-account-username/microserice-name:v1
easybytes/accounts:v1
)

<username/servicename:version>

helenmaryhm77dockerhub/stignatius:v1

docker build . -t <tagname>

docker build . -t helenmaryhm77/stignatius:v1


# RUN CONTAINER
Do port mapping - expose the container outside of the docker network.
Docker container starts as 8080

-p PORT

docker run -p 8080:8080 <imagename>

# RUN CONTAINER IN DETACHED MODE

-d DEETACHED

containerId is displayed.

# LIST RUNNING CONTAINERS

docker ps

docker ps -a

docker start <containername>


# Any number of containers can be created, but different port number should be given

2nd port number - is docker.

docker run -d -p 8081:8080 <imagename>

docker run -d -p 8081:8080 helenmaryhm77dockerhub/stignatius:v1

c52f71173e8cd4d99441720c873b2b7ccdcac8bf56e7d86db54b81a77c5bc430


# PRIVATE 

helenmaryhm77
docker run -d -p 8081:8080 helenmaryhm77/stignatius:v1


# DOCKER PUSH WITH CREDENTIALS

Step1: Docker login
Step2: Docker push

$ docker login --username=xxx --email=xxxx@xx.com

$ docker push xxx/yyy


# DOCKER CREDENTIALS SAVED IN

C:\Users\<username>\.docker\config.json


# LOCAL CONFIG VALUE AFTER LOGIN
{
 "auths": {
  "https://index.docker.io/v1/": {}
 },
 "credsStore": "osxkeychain",
 "currentContext": "rancher-desktop"
}

OTHERS:
{
"credsStore": "osxkeychain",
 "currentContext": "rancher-desktop"
}


# CREATING DOCKER IMAGE -> METHOD2

- Build packs -> packeto (slow and consumes some space but less than Dockerfile). Scans our files.


# CREATING DOCKER IMAGE -> METHOD3

- Google jib (only for java, but fast and less space). Scans our files.


***********************************************

(base) hmaryt@R06VTWRMW5 stignatius % docker build . -t helenmaryhm77dockerhub/stignatius:v1
[+] Building 52.0s (5/7)                                                                                                                                                                                                      docker:rancher-desktop
 => [internal] load .dockerignore                                                                                                                                                                                                               0.0s
 => => transferring context: 2B                                                                                                                                                                                                                 0.0s
 => [internal] load build definition from Dockerfile                                                                                                                                                                                            0.0s
 => => transferring dockerfile: 280B                                                                                                                                                                                                            0.0s
 => [internal] load metadata for docker.io/library/openjdk:23-ea-17-jdk-slim                                                                                                                                                                    5.4s
 => [auth] library/openjdk:pull token for registry-1.docker.io                                                                                                                                                                                  0.0s
 => [internal] load build context                                                                                                                                                                                                               0.3s
 => => transferring context: 56.63MB                                                                                                                                                                                                            0.3s
 => [1/2] FROM docker.io/library/openjdk:23-ea-17-jdk-slim@sha256:36d1737696e66fe14af53ea3617c28b8e4170baf9814c95c24a653e430f4cdab                                                                                                             46.6s
 => => resolve docker.io/library/openjdk:23-ea-17-jdk-slim@sha256:36d1737696e66fe14af53ea3617c28b8e4170baf9814c95c24a653e430f4cdab                                                                                                              0.0s
 => => sha256:36d1737696e66fe14af53ea3617c28b8e4170baf9814c95c24a653e430f4cdab 2.59kB / 2.59kB                                                                                                                                                  0.0s
 => => sha256:a8f70eeaa46fe90eaf7f77f82b7cf348d3cdfa540ffa83e9bde0b296aa035ffe 1.58kB / 1.58kB                                                                                                                                                  [+] Building 363.1s (8/8) FINISHED                       docker:rancher-desktop
 => [internal] load .dockerignore                                          0.0s3 => => transferring context: 2B                                            0.0s  => [internal] load build definition from Dockerfile                       0.0s  => => transferring dockerfile: 280B                                       0.0s
 => [internal] load metadata for docker.io/library/openjdk:23-ea-17-jdk-s  5.4s8 => [auth] library/openjdk:pull token for registry-1.docker.io             0.0s  => [internal] load build context                                          0.3s4 => => transferring context: 56.63MB                                       0.3s
 => [1/2] FROM docker.io/library/openjdk:23-ea-17-jdk-slim@sha256:36d17  357.3s3 => => resolve docker.io/library/openjdk:23-ea-17-jdk-slim@sha256:36d1737  0.0s  => => sha256:36d1737696e66fe14af53ea3617c28b8e4170baf981 2.59kB / 2.59kB  0.0s1 => => sha256:a8f70eeaa46fe90eaf7f77f82b7cf348d3cdfa540ff 1.58kB / 1.58kB  0.0s
 => => sha256:a4774a97685eef1a79b9ac3c4fb2c219fb35407305a 3.87kB / 3.87kB  0.0s2 => => sha256:26070551e657534bdf420d43107e85b972b2e8c 29.16MB / 29.16MB  106.1s  => => sha256:231b1ea269ca1003ddaff994cead172b326871cafa 3.82MB / 3.82MB  16.7s4 => => sha256:0006b7c43c3bab73a399d7012a4999a715c48 208.90MB / 208.90MB  354.2s
 => => extracting sha256:26070551e657534bdf420d43107e85b972b2e8c212413bbb  1.3s
 => => extracting sha256:231b1ea269ca1003ddaff994cead172b326871cafa79e4d1  0.1s
 => => extracting sha256:0006b7c43c3bab73a399d7012a4999a715c48b73d1b6bab0  3.0s
 => [2/2] COPY build/libs/stignatius-0.0.1-SNAPSHOT.jar stignatius-0.0.1-  0.2s
 => exporting to image                                                     0.1s
 => => exporting layers                                                    0.1s
 => => writing image sha256:d7cfa3d3fc76b9983e3a9efed511ea3a0671ffec51370  0.0s
 => => naming to docker.io/helenmaryhm77dockerhub/stignatius:v1            0.0s

View build details: docker-desktop://dashboard/build/rancher-desktop/rancher-desktop/wyvf2lr5yhwubcjl3ft3w9hhc

***********************************************************

# docker images

helenmaryhm77dockerhub/stignatius                   v1                     d7cfa3d3fc76   9 minutes ago   523MB

# docker inspect image d7cf

[
    {
        "Id": "sha256:d7cfa3d3fc76b9983e3a9efed511ea3a0671ffec513701ce1281441efded5a3b",
        "RepoTags": [
            "helenmaryhm77dockerhub/stignatius:v1"
        ],
        "RepoDigests": [],
        "Parent": "",
        "Comment": "buildkit.dockerfile.v0",
        "Created": "2024-04-23T13:48:42.447478045Z",
        "Container": "",
        "ContainerConfig": {
            "Hostname": "",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": null,
            "Cmd": null,
            "Image": "",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": null,
            "OnBuild": null,
            "Labels": null
        },
        "DockerVersion": "",
        "Author": "helenmary.hm77@gmail.com",
        "Config": {
            "Hostname": "",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/openjdk-23/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "JAVA_HOME=/usr/local/openjdk-23",
                "LANG=C.UTF-8",
                "JAVA_VERSION=23-ea+17"
            ],
            "Cmd": null,
            "ArgsEscaped": true,
            "Image": "",
            "Volumes": null,
            "WorkingDir": "",
            "Entrypoint": [
                "java",
                "-jar",
                "stignatius-0.0.1-SNAPSHOT.jar"
            ],
            "OnBuild": null,
            "Labels": null
        },
        "Architecture": "arm64",
        "Os": "linux",
        "Size": 523328816,
        "VirtualSize": 523328816,
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay2/c50ce5bafe6d2d26382ed7c2055ab7b477c7818f959e9c5de8f37d4f1cee3e21/diff:/var/lib/docker/overlay2/d3b10a30d1f3580ee8653fadd3c4acd89323d1392254e60fd043fd6b1169a865/diff:/var/lib/docker/overlay2/80f0bb7bbbd486720bbd33923402c08928e29d9b582c6679e00f737d089dcf2e/diff",
                "MergedDir": "/var/lib/docker/overlay2/c8i8zvnfamcu9eu4442sgsll3/merged",
                "UpperDir": "/var/lib/docker/overlay2/c8i8zvnfamcu9eu4442sgsll3/diff",
                "WorkDir": "/var/lib/docker/overlay2/c8i8zvnfamcu9eu4442sgsll3/work"
            },
            "Name": "overlay2"
        },
        "RootFS": {
            "Type": "layers",
            "Layers": [
                "sha256:6e5a1bc9659a34c2721239cd7ba5c8a14200f98c6e2c49531ba6559aa1c43f67",
                "sha256:494d6ed1960e6978eeef75f3d06e72962f0b85bc5f654439a2fd4b7fbd947a04",
                "sha256:eb316fa2afa74bcb5949411af68859474e1b6a15e30f39d0013023cd8180dc4b",
                "sha256:944bdf432db20caaa02b801e5de0306cb914b66174dee4108cb3c74bca0a1b8f"
            ]
        },
        "Metadata": {
            "LastTagTime": "2024-04-23T13:48:42.566349462Z"
        }
    }
]
Error: No such object: image
(base) hmaryt@R06VTWRMW5 stignatius % 







-----------------------------------------------------
## CHALLENGE 2

- Identify right size and identify service boundaries.

TWO MAIN APPROACHES:
(i) Domain-Driven sizing -> discuss with experienced people/domain experts to get domain knowledge.
Time consuming. Atleast 6 months. Then brain storming session with many people. Then start with some assumptions. If operational overhead, resize and fine tune.

(ii) Even Storming sizing -> a fun session.
a stick note. Sample events are identified.
Then identify the commands (example -> click button, reaction is fund transfered)
Lucidchart -> lucidchart.com/blog/ddd-event-storming

# Example: 
CEO - Bank application

# Team 1
Saving Account
Trading Account
Cards
Loans

# Team 2
Saving Account
Trading Account
(
    Credit Card,
    Debit card
)
(
    Home Loan,
    Vehicle Loan,
    Personal Loan
)

# To select ?
Team1 is correct.

Team2 is not correct because all loans have similar functionality.

No sizing is correct initially.

-----------------------------------------------------

# Migrating monolithic to microservices
- Monolithic -> single database

Client apps(mobile / web app)  ->  API gateway(docker host)  ->  microservices(RDBMS, mongoDB(NoSQL), Redis cache)  -> EventBus(event streaming)

Adavantage: seperate team.

-----------------------------------------------------


## SECTION 1

Backend - Java
Java based web applications.

# Challenge 1
Build, package, deploy -> SpringBoot framework

ADVANTAGES:
1. Self contained/fat/uber jars. (They will have all the dependencies)

2. Embedded tomcat server, Jetty or Undertow. No need external server.

3. Autoconfiguration by itself (default). Can override with properties.

4. Production support - metrics, health monitoring with dependencies like springboot actuator.

5. Quickly bootstrap (starter project).

6. Cloud ready. (Deploy in kubernates platform, containerize in docker, deploy in cloud providers like gcp, aws, )

7. REST API - synchronous communication.

# Basics of Spring framework
- Autowiring

# REST services
- Lightweight - JSON (light weight)

# Standards
1. CRUD
2. Input validation
3. Exceptional handling
4. Documentation - OpenAPI, Swagger. 

# DTO pattern
- DTO class
- mapper (or) aggregation
Advantage:
- Reduce traffic
- encapusate serialization
- decouples layers
