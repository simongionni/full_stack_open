# 0.5: SPA New Note diagram

```mermaid
sequenceDiagram
    participant browser
    participant server

    Note right of browser: The user writes a note in the text field and clicks Save

    Note right of browser: spa.js handles the form submit event and prevents the default form submission

    Note right of browser: The browser creates a new note object with content and date

    Note right of browser: The browser adds the new note to the notes list and redraws the notes on the page

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    Note left of server: The request contains the new note as JSON data
    server-->>browser: HTTP 201 Created
    deactivate server

    Note right of browser: The page stays open and no redirect or reload happens