# Tech Context — HealthCore (contexto técnico)

## Stack
- HTML5 semántico + Tailwind CSS v4 por CDN (`https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4`) + JavaScript vanilla.
- Sin build ni librerías extra.
- Servidor de desarrollo: `npx http-server . -p 3000 -a 0.0.0.0`

## Decisiones y restricciones
- Datos exactos del `BRIEFING.md`: textos, clínicas, teléfonos, horarios, atributos `name` y mensajes de error.
- Schema.org en JSON-LD: `MedicalOrganization` + un `MedicalClinic` por cada una de las 6 sedes de EE.UU. (`name`, `telephone`, `openingHours`, `parentOrganization`).
- Accesibilidad: HTML semántico, un solo `h1`, ARIA cuando haga falta, `alt` descriptivo en imágenes.
- Responsive mobile-first (probar a 390, 768 y 1280 px).
- Tailwind por utilidades; `styles.css` solo si es imprescindible.
- Formulario: validación en `validation.js`, envío simulado.

## Dónde vive el código
- `/uis`: todos los frontends.
  - `./uis/website`: web corporativa pública (ruta `/`, marca y copy alineados con `BRIEFING.md`).
  - `./uis/backoffice`: app interna, con layout propio y separado del sitio público (entrada en `/`).
- `/services`: APIs y backend.
- NO se crean árboles paralelos de frontend/API en otros sitios. Antes de poner algo en una carpeta, se lee el README de esa carpeta.

## Excepción vigente
La landing del Hito 1 vive en la RAÍZ (`index.html`, `application.html`, `validation.js`, `assets/`) porque el enunciado de ese hito lo exige. Todo frontend público NUEVO va en `uis/website/`. Esto NO es un precedente.
