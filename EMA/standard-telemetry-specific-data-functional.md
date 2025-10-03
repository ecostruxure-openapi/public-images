```mermaid
sequenceDiagram
actor M as MGCC
actor C as client
participant E as EMA V4 WS
 
M ->> C: Provide siteId
C ->> E: Request resource available for the site
E ->> C: Return resource list with static ids
C ->> E: Request available standard properties with selected resource
E ->> C: Return dynamic available properties list
C ->> E: Request standard telemetry information for the resource/property couple
E ->> C : Return telemetry list 
```