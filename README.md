# fullstackopen
This repository contains my exercise submissions for the University of Helsinki's Full Stack Open 2024 course


sequenceDiagram
    participant browser
    participant server
    participant database

    Note right of browser: User writes note and clicks Save

    browser->>browser: User enters note content
    browser->>browser: User clicks Save button
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>database: Store new note data
    activate database
    database-->>server: Confirmation of successful storage
    deactivate database
    server-->>browser: Redirect to https://studies.cs.helsinki.fi/exampleapp/notes
    deactivate server
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: Updated list of notes including new note
    deactivate server
