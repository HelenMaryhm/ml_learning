# Asynchronous Communication
- Producer (doesn't worry about consumer) -> fire and forget.
- Microservice architecture.
- Broker handles latency.

# To get acknowledgement of messages recieved
- Can make producer as reciever.
- Or can write in a shared database.
- If in same application, can use @EventListener in spring boot.