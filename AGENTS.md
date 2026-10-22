# AGENTS.md

Proyecto de aprendizaje (AI Engineering, 4Geeks Academy) sobre la empresa HealthCore.

## Antes de cualquier tarea

1. Lee `BRIEFING.md`: define el hito actual, el contenido exacto del sitio,
   los campos del formulario y sus reglas de validación.
2. Usa `CONTEXT.md` solo como referencia de la empresa.
3. No modifiques `BRIEFING.md`, `CONTEXT.md` ni sus versiones `.es.md`.

## Cómo trabajamos

- El estudiante pide una tarea a la vez. Haz **solo esa tarea**; no adelantes
  las siguientes ni agregues funcionalidades no pedidas.
- Trabaja en pasos pequeños y explica brevemente el porqué de cada parte.
- Usa los textos, campos y datos **exactamente** como están en `BRIEFING.md`.
  No inventes contenido; si falta algo, pregunta.
- No toques los archivos que el estudiante marque como "míos" sin preguntarle.

## Stack del hito actual

- HTML5 semántico + Tailwind CSS (CDN) + JavaScript vanilla. Sin build ni frameworks.
- Archivos en la raíz:
  - `index.html`: landing page
  - `application.html`: formulario
  - `validation.js`: validación del formulario
  - `styles.css`: solo si Tailwind no alcanza
- Servir en desarrollo: `npx http-server . -p 3000 -a 0.0.0.0`

## Requisitos de calidad

- Responsive (móvil, tablet, escritorio).
- Accesible: HTML semántico, ARIA cuando haga falta, `alt` en imágenes.
- SEO: Schema.org para los datos de la empresa.
- Bilingüe EN/ES según `BRIEFING.md`.
- Evitar CSS escrito a mano.

## Git

- Una rama por funcionalidad, PR y merge a `main`.
- Commits en Conventional Commits, en español.
