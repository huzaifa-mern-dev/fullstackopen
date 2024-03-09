```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: HTTP POST /exampleapp/new_note_spa
    activate server
    server-->>browser: Status code 201 Created
    Note left of server: Browser stays on the same page\nNo further requests sent.
    deactivate server

    %% Styling
    style browser fill:#5cb85c,stroke:#333,stroke-width:2px,font-size:16px,font-weight:bold;
    style server fill:#5bc0de,stroke:#333,stroke-width:2px,font-size:16px,font-weight:bold;
