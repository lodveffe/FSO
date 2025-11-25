```mermaid
sequenceDiagram
    participant U as user
    participant B as browser
    participant S as server

    U->>B: User writes a note and clicks "save"
    B->>S: POST /new_note
    S->>B: 302 redirect to /exampleapp/notes
    B->>S: GET /exampleapp/notes
    S->>B: HTML content
    B->>S: GET exampleapp/main.css
    S->>B: CSS content
    B->>S: GET exampleapp/main.js
    S->>B: JS content
    B->>S: GET exampleapp/data.json
    S->>B: JSON content
    B->>B: JS callback parses JSON and updates DOM
    B->>U: Page updated with new note
```