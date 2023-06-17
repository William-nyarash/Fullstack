# Fullstack
## New note in single page App diagram

  
sequenceDiagram
    participant browser
    participant server


    browser->server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    server-->>browser:HTML document
    deactivate server

    browser->server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser:css file
    deactivate server

    browser->server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: javaScript file
    deactivate server

    Note right of browser: The browser sends a request to create a new_note_spa the server responds with a message note created
    browser->server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser:application/json
    deactivate server

     Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "Web development is fun", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
