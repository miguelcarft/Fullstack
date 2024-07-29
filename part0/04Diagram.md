```mermaid
sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Submit new note
    Browser->>Server: POST /exampleapp/new_note
    Server-->>Browser: 302 Found (Redirect)
    Browser->>Server: GET /exampleapp/notes (Redirected)
    Server-->>Browser: 200 OK (HTML document)
    
    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate Server
    Server-->>Browser: the CSS file
    deactivate Server

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate Server
    Server-->>Browser: the JavaScript file
    deactivate Server

    Note right of Browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    Browser->>Server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate Server
    Server-->>Browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ... ]
    deactivate Server

    Note right of Browser: The browser executes the callback function that renders the notes

    Browser->>User: Display new page with notes

    Note right of Browser: The browser executes the callback function that renders the notes

