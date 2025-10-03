```mermaid
sequenceDiagram
actor M as MGCC
actor C as client
participant E as EMA V4 WS
 
M ->> C: Provide siteId
C ->> E: /v1.0/m2m/site/<siteId>/resources
E ->> C: [{"id":"<resourceId>","name":"<ressource_name>", "type":"<resource_type>"},...]
C ->> E:  /v1.0/m2m/site/<siteId>/specificMonitoring/properties
E ->> C: [{"resourceId":"<resourceId>","tags":["property1","property2",...]},...]
C ->> E: /v1.0/m2m/resource/<resourceId>/specificMonitoring?startDate=<startDate>&endDate=<endDate>&property=<property>
E ->> C : [{"timestamp":"<timestamp>","resourceId":"<resourceId>","property":"<property>","value":"<value>"},...]
```