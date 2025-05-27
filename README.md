
# Telecom Mission Control Backend Design

This repository describes a scalable backend system architechture for a telecom mission control SAAS platform.
The system helps enterprise to monitor the mobile device usage at the network edge via carrier shared cell towers.
Policies are defined by enterprises. The system enforces these policies on the users based on subscriptions.
User actions are monitored 
New Devices can be registered
supports features like auto-remediation for premium users
supports real time dashboards

## Project Structure

docs/ 
|- architecture.md # system architecture write-up
|- erd.png # ER diagram
|- architecture-diagram.png#   
|- assumptions.md 
|- API Spec 


## Technologies
**Backend Framework**: Java, Spring boot
**Messaging** : Kafka
**Database**: SQL, Elastic Search

## following a microservice architecture 

## Designed by Asha 

- [Architecture](docs/architecture.md)
- [Data flow](docs/dataflow.md)
- [Entities](docs/entities.md)
- [API spec](docs/APIs.md)
- [Assumptions](docs/assumptions.md)
- [System Design Diagram](diagrams/telecommissoncontrol.drawio.png)

