sequenceDiagram

    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser:  css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: JavaScript file
    deactivate server

    Note right of browser: The browser sends the new_note  to the server and the text itself is stored in note

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser:HTML document
    deactivate server

    Note right of browser: The browser begins to execute the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate serve
    server-->>browser: [{ "content": "fullstack", "date": "2023-6-17" }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes }, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes
