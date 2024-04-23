# Microservice architecture


## SECTION 2

# Challenge 2

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
