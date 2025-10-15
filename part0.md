
Exercise 0.4
sequenceDiagram
    participant B as Browser
    participant S as Server

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
sequenceDiagram
    participant B as Browser
    participant S as Server

    B->>S: POST /new_note_spa (JSON note data)
    S-->>B: 201 Created

 The app updates the notes list<br>without reloading the page
