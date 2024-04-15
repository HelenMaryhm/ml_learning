# Microservice Architecture
- Split based on business functionality.

Pros:
- Feature level releases are independent.
- Scalable.
- Each module can have different language platform, different google service too (tech-stack).

e.g. 
Module1
- App Engine (python, mySQL)

Module2
- Cloud Function (Nodejs, MongoDB)


# Communication
1. Synchronous - http(s)
2. Asynchronous Messaging - pub-sub/kafka

