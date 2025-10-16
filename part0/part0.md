Exercise 0.4 sequenceDiagram participant B as Browser participant S as Server

B->>S: POST /new_note (note data)
S-->>B: 302 Redirect to /notes

B->>S: GET /notes
S-->>B: HTML page

B->>S: GET /main.css
S-->>B: CSS

B->>S: GET /main.js
S-->>B: JS

B->>S: GET /data.json
S-->>B: JSON with all notes


Exercise 0.5 
sequenceDiagram participant B as Browser participant S as Server

B->>S: POST /new_note_spa (JSON note data)
S-->>B: 201 Created
The app updates the notes list
without reloading the page



Exercise 0.6

sequenceDiagram
    actor User
    participant Browser as Browser (SPA)
    participant Server

    User->>Browser: Writes note and clicks "Save"
    note over Browser: JS intercepts form submit and prevents page reload

    Browser->>Browser: Create note object { content, date }
    Browser->>Server: POST /exampleapp/new_note_spa (JSON data)
    activate Server

    Server-->>Server: Save the note
    Server-->>Browser: 201 Created (note saved)
    deactivate Server

    Browser->>Browser: Add note to list and re-render
    Browser-->>User: New note appears instantly on screen

