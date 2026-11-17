# Progress

## Hito: Ingeniería impulsada por IA (rama `feature/agent-memory-bank`)
La infraestructura de agentes ya estaba en `main` (PR #2). En esta rama se revisa contra el enunciado y se mejora por etapas, un commit por etapa:
- [x] Etapa 1, banco de memoria: `techContext.md` documenta la configuración de agentes y la diferencia entre `.agents/` y `/agents` y `/skills`.
- [x] Etapa 2, `AGENTS.md`: flujo previo al commit con la skill que lo ejecuta, lista ampliada de archivos protegidos y cuándo detenerse a preguntar.
- [x] Etapa 3, reglas de `.agents/`: nueva regla `code-placement` (por patrón) con dónde va el código de `/uis`, `/services`, `/agents` y `/skills`.
- [x] Etapa 4, skills: nueva skill `commit-flow-check` (objetivo único, inputs y 9 criterios verificables). Sus comandos se probaron con casos que pasan y casos que fallan.

## Hecho
- Briefing agregado al repo.
- `AGENTS.md` y `.gitignore` (PR #1 mergeado).
- Landing `index.html` construida en la rama `feat/landing-page`: header, hero, servicios, why HealthCore, sedes, contacto y footer implementados. Falta verificación final y PR.
- Infraestructura de agentes: `memory-bank/`, `AGENTS.md`, `.agents/` (rama `chore/agent-infra`).

## Siguiente
- Formulario `application.html` + `validation.js` según "Patient enquiry form fields" y "Specific validations" del briefing.

## Decisiones
- 2026-10-22: la landing vive en la raíz como excepción documentada, porque el enunciado del Hito 1 lo exige (ver `techContext.md`). Todo frontend público nuevo va en `uis/website/`.
- 2026-10-22: el briefing pide EN+ES; por decisión del desarrollador esta tarea es solo en inglés y el español no se implementa.

## Pendiente
- Publicar la URL pública.
