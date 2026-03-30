```mermaid

sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note left of server: The server processes the JSON data and saves the new note to its database
    server-->>browser: HTTP status code 201 Created ({"message":"note created"})
    deactivate server

    Note right of browser: The browser stays on the same page, no further HTTP requests are made
