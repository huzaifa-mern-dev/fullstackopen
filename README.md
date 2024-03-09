```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: HTTP POST /exampleapp/new_note_spa
    activate server
    server-->>browser: Status code 201 Created
    Note left of server: Browser stays on the same page\nNo further requests sent.
    deactivate server
