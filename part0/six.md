```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: The user types a new note and clicks Save

    Note right of browser: JS execution: JS intercepts form submit, adds note to local array, and re-renders the DOM list locally


    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note right of browser: Payload: { "content": "user's new note", "date": "2026-07-30" }
    server-->>browser: HTTP status 201 created (JSON: {"message": "note created"})
    deactivate server
    ```