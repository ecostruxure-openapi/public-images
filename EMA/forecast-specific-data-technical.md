```mermaid
sequenceDiagram
actor M as MGCC
actor C as client
participant E as EMA V4 WS
 
M ->> C: Provide siteId
C ->> E: /v1.0/m2m/site/<siteId>/resources
E ->> C: [{"id":"<resourceId>","name":"<ressource_name>", "type":"<resource_type>"},...]
C ->> E:  /v1.0/m2m/forecast/properties?resourceId=<resourceId>&startDate=<startDate>&endDate=<endDate>
E ->> C: {"resourceId":"<resourceId>","tags":["property1","property2","property3",...]}
C ->> E: /v1.0/m2m/forecast?property=<property>&resourceId=<resourceId>&startDate=<startDate>&endDate=<endDate>&property=<property>
E ->> C : [{"timestamp":"<timestamp>","providerId":"providerId","resourceId":"<resourceId>","property":"<property>","value":"<value>"},...]
```