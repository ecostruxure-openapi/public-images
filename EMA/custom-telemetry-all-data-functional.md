```mermaid
sequenceDiagram
actor M as MGCC
actor C as client
participant E as EMA V4 WS
 
M ->> C: Provide siteId
C ->> E: Request resource available for the site
E ->> C: Return resource list with ids
C ->> E: Request specific monitoring telemetry informations for the resource
E ->> C : Return telemetry list 
```