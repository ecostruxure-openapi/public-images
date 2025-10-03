```mermaid
sequenceDiagram
actor M as MGCC
actor C as client
participant E as EMA V4 WS
 
M ->> C: Provide siteId
C ->> E:  /v1.0/DemandResponse/<siteId>/unitaryDR/calculate?power=<power>&startDate=<startDate>&endDate=<endDate>
E ->> C: [{"tenderId":"<tenderId>","status":"Computing","power":<power>,"startDate":"<startDate>","endDate":"<endDate>",...}]
C ->> E:  /v1.0/DemandResponse/<siteId>/unitaryDR/offer
E ->> C: [{"tenderId":"<tenderId>","status":"Proposed","power":<possiblePower>,"startDate":"<startDate>","endDate":"<endDate>",...}]
C ->> E: /v1.0/DemandResponse/<tenderId>/activate
E ->> C : [{"tenderId":"<tenderId>","status":"Activated","power":<possiblePower>,"startDate":"<startDate>","endDate":"<endDate>",...}]
C ->> E: /v1.0/DemandResponse/<tenderId>/cancel
E ->> C : [{"tenderId":"<tenderId>","status":"Canceled","power":<possiblePower>,"startDate":"<startDate>","endDate":"<endDate>",...}]
```