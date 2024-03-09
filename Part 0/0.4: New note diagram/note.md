```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST /exampleapp/new_note

    activate server

    Note left of server: Server responds with HTTP status code 302

    deactivate server


    Note right of browser: Browser reloads the Notes page
    
    browser->>server: GET /exampleapp/notes
    activate server
    server-->>browser: HTML file 
    deactivate server
    
    browser->>server: GET /exampleapp/main.css
    activate server
    server-->>browser: CSS file
    deactivate server
    
    browser->>server: GET /exampleapp/main.js
    activate server
    server-->>browser: JavaScript file
    deactivate server
    
    Note right of browser: Browser executes JavaScript code to fetch JSON data
    
    browser->>server: GET /exampleapp/data.json
    activate server
    server-->>browser: JSON data
    deactivate server

    Note right of browser: Browser renders notes using callback function