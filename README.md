# Manual de despliegues

Guía paso a paso, con capturas reales, para llevar una aplicación completa a la nube con planes gratuitos: base de datos, backend y frontend, conectados entre sí. El ejemplo es un tablero Kanban.

## Contenido

| Parte | Tema | Herramientas | Estado |
|---|---|---|---|
| 1 | Base de datos PostgreSQL | Supabase | Completo |
| 2 | Backend Spring Boot (Docker) | Eclipse, GitHub, Render | Completo (falta la captura de `/actuator/health`) |
| 3 | Frontend Angular y conexión con el backend | GitHub, Vercel | Completo |
| Anexo | Conectarse a la base con HeidiSQL | HeidiSQL | Completo |
| Anexo | Publicar un sitio estático en GitHub Pages | GitHub Pages | Completo |

## Orden del proceso

La base de datos va primero, luego el backend y al final el frontend. Cada parte entrega un dato a la siguiente:

1. **Base de datos:** de Supabase salen los datos de conexión (host, puerto, usuario, contraseña).
2. **Backend:** esos datos se escriben como variables de entorno en Render, que entrega la URL pública de la API.
3. **Frontend:** Vercel reenvía las llamadas `/api` a esa URL con un archivo `vercel.json`.

## Archivos

- Versión web: `index.html` (se publica con GitHub Pages). Contiene las tres partes y los anexos.
- Versión Markdown de la parte del frontend: [MANUAL-VERCEL-ANGULAR.md](MANUAL-VERCEL-ANGULAR.md).
- Capturas: carpeta `img/`.

## Para que se vea como página

1. Abre el repo en GitHub y entra a **Settings → Pages**.
2. En **Source** elige *Deploy from a branch*.
3. Selecciona la rama `main`, la carpeta `/ (root)`, y pulsa **Save**.
4. En uno o dos minutos queda en `https://cbarralesp.github.io/manual_despliegues/`.
