```mermaid

sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser: HTML document
    server-->>browser: 200 OK
    deactivate server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser: 201 Created
    deactivate server
   
    browser->>server: {content: " >^.^< ", date: "2026-10-12T10:09:39.810Z"}
    activate server
    server-->>browser: {message: "note created"}
    deactivate server