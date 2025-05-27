
# Telecom Mission Control Backend Design

**Requirements**

This document describes a scalable backend system architecture for a telecom mission control SAAS platform.
The system helps enterprise to monitor the mobile device usage at the network edge via carrier shared cell towers.
Policies are defined by enterprises. The system enforces these policies on the users based on subscriptions.
User actions are monitored
New Devices can be registered
supports features like auto-remediation for premium users
analytics and real time dashboards are supported.



**Assumptions**
- Carriers will decide which OS will connect to which towers.
- An equipment on Towers will detect the devices, and report App usage
- Two types of data is being sent a) real time app usage updates b) from the carriers about tower metadata (like which tower supports which carrier, new tower added etc)


**Services**
- Ingestion service 
  - This will simply collect the data from the carriers and tower equipment. 
  - process the data from carriers -like which OS ? device type etc. (this will help in onboarding)
  - process the data from tower equipment - which app, what action (this will help with policy enforcements)
- Device service
  - Registers and manages enterprise devices. CRUD for Devices. (ex: when a new devices connect to a tower it registers its metadata.)
- Tower Service
  - Stores tower - carrierOS mapping (ex: which towers can At&t users connect to)
  - Tower will publish events to KafkaQ regarding the app usage.
- User Service
  - manages User identify and Enterprise role / subscription 
- Policy Service
  - Manages polices given by enterprises 
- Policy Engine
  - Applies the policies (rules) based on the input data and policies defined.
  - publishes the decision event to Kafka Q for monitoring service to consume.
- Edge Application Service (A service that will allow , deny or remediate)
  - sends / denies to tower
  - raises auto-remediation tasks/ alerts
- Monitoring & Analytics Service
  - will consume events from Tower and Policy engine
  - aggregate and analyze events
  - raise alerts if needed.
  - updates elastic search


    