
```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note

    activate server

    Note left of server: server responds with HTTP status code 302 and asks the browser to do a new HTTP GET request

    deactivate server


    Note right of browser: The browser reloads the Notes page
    
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: The HTML file 
    deactivate server
    
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: The CSS file
    deactivate server
    
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: The Javascript file
    deactivate server
    
    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON data from the server
    
    browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-09-21" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
