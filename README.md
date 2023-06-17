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

     Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": " ", "date": "2023-1-1" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
