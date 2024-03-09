sequenceDiagram
    participant Browser
    participant Server
    
    Browser->>Server: HTTP GET /exampleapp/spa
    Server->>Browser: HTML document
    
    Browser->>Server: HTTP GET /exampleapp/main.css
    Server->>Browser: CSS file
    
    Browser->>Server: HTTP GET /exampleapp/spa.js
    Server->>Browser: JavaScript file
    
    Note right of Browser: JavaScript fetches data.json
    
    Browser->>Server: Request for data.json
    Server->>Browser: JSON Response
    
    Note right of Browser: Callback function renders notes   
