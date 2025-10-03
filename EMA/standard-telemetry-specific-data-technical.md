```mermaid
sequenceDiagram
actor M as MGCC
actor C as client
participant E as EMA V4 WS
 
M ->> C: Provide siteId
C ->> E: /v1.0/m2m/site/<siteId>/resources
E ->> C: [{"id":"<resourceId>","name":"<ressource_name>", "type":"<resource_type>"},...]
C ->> E:  /v1.0/m2m/site/<siteId>/monitoring/properties
E ->> C: {"siteProperties":["property1",...],"resources":[{"resourceId":"<resourceId>","tags":["property1",...]},...]}
C ->> E: /v1.0/m2m/resource/<resourceId>/monitoring?startDate=<startDate>&endDate=<endDate>&property=<property>
E ->> C : [{"timestamp":"<timestamp>","resourceId":"<resourceId>","property":"<property>","value":"<value>"},...]
```