```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: documento html
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: documento css
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: documento js
    deactivate server

    Nota no browser : o browser executa o javascript para puxar os dados do server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "HTML+ CSS + JS é mamao com açúcar", "date": "2026-9-6" }, ... ]
    deactivate server

    Nota no browser: O browser vai executar a function pra mostrar as notas

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    server-->>browser: documento html, css e json das notas

    Nota aperece no browser:  js executou mandando pro servidor e apareceu na pagina


```
