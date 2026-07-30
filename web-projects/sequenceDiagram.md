sequenceDiagram
    participant browser
    participant server

    browser->>server: GET [new-note](https://studies.cs.helsinki.fi/exampleapp/new_note)
    activate server
    server-->>browser: 302 found (redirect)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{"content": "Kurdistan thanks you for this course",
        "date": "2026-07-30T22:15:21.159Z"},... ]
    deactivate server
