```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Navigate to https://studies.cs.helsinki.fi/exampleapp
    activate Browser
    Browser->>Server: GET /exampleapp/spa
    activate Server
    Server-->>Browser: 200 OK (spa)
    deactivate Server
    Browser->>Server: GET /exampleapp/main.css
    activate Server
    Server-->>Browser: 200 OK (main.css)
    deactivate Server
    Browser->>Server: GET /exampleapp/main.js
    activate Server
    Server-->>Browser: 200 OK (main.js)
    deactivate Server
    Browser->>Server: GET /exampleapp/data.json
    activate Server
    Server-->>Browser: 200 OK (data.json)
    deactivate Server
    deactivate Browser
    Browser-->>User: Display notes data
