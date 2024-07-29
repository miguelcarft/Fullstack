 ```mermaid

    participant Usuario
    participant Navegador
    participant Servidor

    Usuario->>Navegador: Envía nueva nota
    Navegador->>Servidor: POST /exampleapp/new_note
    Servidor->>Navegador: 302 Found (Redirige)
    Navegador->>Servidor: GET /nueva_ubicacion (Redirigido)
    Servidor->>Navegador: 200 OK (Contenido de la nueva página)
    Navegador->>Usuario: Muestra nueva página
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_not
 
