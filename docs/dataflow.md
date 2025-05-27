# Data flow
- Device performs an action .
- connects to edge . (equipment on edge will detect action)
- Tower will send an app-usage-event to kafka topic . 
- Monitoring service will consume this event
- Policy service using policy engine and make a decision to allow/deny.
- policy engine will publish a decisionevent to Kafka topic.
- Monitoring service consumes this for real time dashboard and to raise alerts.
- This event is logged to elastic search. (ex: how many denies did deviceid 133 received in last 1 hour?)