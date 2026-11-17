# AGENTS.md

Proyecto de aprendizaje (AI Engineering, 4Geeks Academy): sitio de HealthCore.

## Al inicio de cada sesión
Lee, en este orden:
1. `memory-bank/projectbrief.md`
2. `memory-bank/techContext.md`
3. `memory-bank/progress.md`

Después lee `BRIEFING.md` (única fuente de verdad de contenido y campos).

## Flujo OBLIGATORIO antes de cada commit
1. Verificar los cambios contra `BRIEFING.md` (textos, datos, campos) cuando tocan contenido o HTML.
2. Si hay HTML, probar en navegador a 390, 768 y 1280 px y revisar que la consola no tenga errores.
3. Actualizar `memory-bank/progress.md`.
4. Commit en Conventional Commits, en español, con cuerpo Propósito / Objetivos / Resumen de cambios.
5. Abrir PR (nunca push directo a `main`).

La skill `commit-flow-check` ejecuta y reporta estos pasos sobre los cambios en staging.

## No modificar sin confirmación explícita del desarrollador
- `BRIEFING.md`, `BRIEFING.es.md`
- `.devcontainer/`
- `.gitignore`
- `memory-bank/projectbrief.md`
- `company-choice.md`, `CONTEXT.md`, `CONTEXT.es.md` (entregables del hito de elección de empresa)
- `AGENTS.md` y `.agents/` (solo se cambian cuando el desarrollador lo pide)
- Cualquier archivo que el estudiante marque como "mío".

## Reglas de trabajo
- Una tarea a la vez; no adelantes ni agregues funcionalidades no pedidas.
- Pasos pequeños, explicando brevemente el porqué.
- No inventar datos; si falta algo, preguntar.
- Solo inglés en este hito.
- Al recibir una tarea nueva, sugerir nombre de rama (`tipo/descripcion-corta`).
- Una rama por funcionalidad → PR → merge a `main`.

## Cuándo detenerte y preguntar
- Falta un dato que el briefing no da.
- El cambio tocaría un archivo de la lista de arriba.
- El código nuevo no encaja en `uis/` ni en `services/`.
- El briefing y la tarea se contradicen.

## Reglas y skills
- Reglas: `.agents/rules/` (`briefing-fidelity`, `website-html`, `code-placement`).
- Skills: `.agents/skills/` (`briefing-content-check`, `commit-flow-check`).
- No confundir `.agents/` (configura al agente de código) con `/agents` y `/skills` (código de producto).

## Ubicación del código
No crear frontends fuera de `uis/`, salvo la excepción documentada en `memory-bank/techContext.md`.
