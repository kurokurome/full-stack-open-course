sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server->>server: Create new note object from POST data and add it into notes array
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server ->>browser: Get the HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server ->>browser: Get the CSS file (main.css)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server ->>browser: Get the JavaScript file (main.js)
    deactivate server

    browser->>server: GET  https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server ->>browser: Get the JSON file. The notes that is stored in server data (data.json)
    deactivate server
