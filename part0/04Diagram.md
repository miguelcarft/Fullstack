sequenceDiagram
    participant User
    participant Browser
    participant Server

    User->>Browser: Submit new note
    Browser->>Server: POST /exampleapp/new_note
    Server-->>Browser: 302 Found (Redirect)
    Browser->>Server: GET /new_location (Redirected)
    Server-->>Browser: 200 OK (New page content)
    Browser->>User: Display new page

    User->>Browser: Request to view notes
    Browser->>Server: GET /exampleapp/notes
    Server-->>Browser: 200 OK (List of notes)
    Browser->>User: Display list of notes
