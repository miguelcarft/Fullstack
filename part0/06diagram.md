```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Submit new note
    Browser->>Server: POST /exampleapp/new_note_spa
    activate Server
    Server-->>Browser: 201 Created (JSON response)
    deactivate Server
    Browser->>User: Display notes
