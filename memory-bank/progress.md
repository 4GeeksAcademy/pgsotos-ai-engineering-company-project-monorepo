# Progress

## Hecho
- Briefing agregado al repo.
- `AGENTS.md` y `.gitignore` (PR #1 mergeado).
- Landing `index.html` construida en la rama `feat/landing-page`: header, hero, servicios, why HealthCore, sedes, contacto y footer implementados.
- Verificación de la landing (2026-11-16):
  - Textos y datos contra `BRIEFING.md`: coinciden (hero, 3 servicios, 4 puntos de Why HealthCore, 6 sedes de EE. UU., contacto, footer, Schema.org con 6 `MedicalClinic`).
  - Navegador a 390, 768 y 1280 px: sin scroll horizontal, imágenes cargan, un solo `<h1>`. Consola sin errores salvo `favicon.ico` 404.
  - 29 enlaces/botones miden menos de 44 px a 390 px (no exigido por el briefing; sin revisar).
- Infraestructura de agentes: `memory-bank/`, `AGENTS.md`, `.agents/` (rama `chore/agent-infra`).

## Siguiente
- Abrir PR de `feat/landing-page` a `main`.
- Formulario `application.html` + `validation.js` según "Patient enquiry form fields" y "Specific validations" del briefing. Los 3 botones "Request an appointment" apuntan a `application.html`, que aún no existe (404).

## Decisiones
- 2026-10-22: la landing vive en la raíz como excepción documentada, porque el enunciado del Hito 1 lo exige (ver `techContext.md`). Todo frontend público nuevo va en `uis/website/`.
- 2026-10-22: el briefing pide EN+ES; por decisión del desarrollador esta tarea es solo en inglés y el español no se implementa.

## Pendiente
- Publicar la URL pública.
- Agregar favicon (404 en consola).
