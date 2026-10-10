```mermaid

sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server

    server-->>browser: 200 OK
    deactivate server

    Note right of browser: User types text in the field and clicks Save. The form has action=/exampleapp/new_note and method=POST

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    browser->>server: note=+++%3E%5E.%5E%3C+++
    activate server

    server-->>browser: 302 Found
    server-->>browser: location /exampleapp/notes
    deactivate server
    

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes/data.json
    activate server
    server-->>browser: [{ "content": "   >^.^<   ",   "date": "2026-10-09T15:31:41.640Z"}, ... ]
    deactivate server
