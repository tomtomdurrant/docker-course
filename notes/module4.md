# Module 4 - Microservices and Containers

Traditional monoliths difficult to scale. 

Microservices are easy to scale. 

Microservices can lead to less silod app architecture. Groups teams by features. 



Microservice architecture patterns

api gateway

fine grain over data in microservice

Api gateway acts as entrypoint for all access to microservices by encapsulating the internal system design. 

Handle security on this entrypoint. 



Service discovery pattern

built in docker compose

discover service dynamically using service registry



Scaling - microservice can take advantage of different hardware at different infrastrcture sites. 



Data

Each microservice owns its own model/data

state typically scoped for the microservice

remote storage for cold data

Bounded context pattern

Bounded context == "Business Microservice" boundary

Each bounded context has: 

- its own domain model - database
- its own context, invariants, rules, code
- autonomous

Important to use asynchronous communication methods such as event bus. 
Data is usually read only. 