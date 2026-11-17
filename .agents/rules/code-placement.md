---
name: code-placement
alcance: POR PATRÓN
globs:
  - "uis/**"
  - "services/**"
  - "agents/**"
  - "skills/**"
  - "/*.html"
---

# Dónde va cada cosa en el monorepo

Alcance: POR PATRÓN. Aplica al trabajar en `uis/**`, `services/**`, `agents/**`, `skills/**` y en los `*.html` de la raíz.

| Qué | Dónde |
|---|---|
| Web pública (ruta `/`, marca y copy del briefing) | `uis/website/` |
| App interna (layout propio, separado del sitio público; vista de entrada en `/`) | `uis/backoffice/` |
| Otro frontend de la empresa (portal, Streamlit, Gradio…) | subcarpeta de `uis/` |
| API o worker | `services/<nombre-del-servicio>/` (un servicio por subcarpeta) |
| Agentes e integraciones de la empresa (producto) | `agents/` y `skills/` |
| Reglas y skills del agente de código | `.agents/` |

- Antes de crear algo en una carpeta, leer su `README.md` (`uis/`, `services/`, `agents/`, `skills/`).
- No crear árboles paralelos de frontend o API (`frontend/`, `api/`, `backend/`, `src/`…) fuera de esas rutas.
- Cada app o servicio nuevo lleva su propio `README.md` con objetivo, tecnología y cómo ejecutarlo.
- `uis/website/`, `uis/backoffice/` y las subcarpetas de `services/` aún no existen: se crean cuando una tarea lo pida, no antes.
- Excepción vigente: la landing del Hito 1 vive en la raíz (`index.html`, `application.html`, `validation.js`, `assets/`) porque el enunciado de ese hito lo exige. No es un precedente: todo frontend público nuevo va en `uis/website/`.
