---
name: commit-flow-check
description: Ejecuta y reporta el flujo obligatorio previo al commit de AGENTS.md sobre los cambios en staging de este monorepo. Usar justo antes de cada commit. No modifica nada.
---

# commit-flow-check

## Objetivo único
Comprobar que los cambios en staging y el mensaje de commit cumplen el flujo previo al commit de `AGENTS.md`. Solo informa: no corrige, no hace commit ni push.

## Inputs
- `staging`: los cambios en staging (`git diff --cached`).
- `mensaje`: el texto del mensaje de commit que se va a usar.
- `confirmados` (opcional): archivos protegidos que el desarrollador autorizó tocar en esta tarea.

## Pasos
1. Ejecutar cada comprobación de la tabla de criterios, en orden.
2. Si hay HTML en staging, ejecutar también la skill `briefing-content-check` sobre cada HTML.
3. Entregar la tabla de resultados y el veredicto.

## Criterios de aceptación
| # | Criterio | Cómo comprobarlo | PASA si |
|---|---|---|---|
| 1 | La rama no es `main` | `git branch --show-current` | la salida no es `main` |
| 2 | No se tocan archivos protegidos sin confirmación | `git diff --cached --name-only \| grep -E '^(BRIEFING(\.es)?\.md\|\.devcontainer/\|\.gitignore\|memory-bank/projectbrief\.md\|company-choice\.md\|CONTEXT(\.es)?\.md\|AGENTS\.md\|\.agents/)'` | no hay coincidencias, o todas están en `confirmados` |
| 3 | `progress.md` está actualizado | `git diff --cached --name-only \| grep -x 'memory-bank/progress.md'` | el archivo aparece en staging |
| 4 | No hay frontends fuera de `uis/` | `git diff --cached --name-only --diff-filter=A \| grep -E '\.(html\|jsx\|tsx\|vue\|svelte)$' \| grep -vE '^(uis/\|index\.html$\|application\.html$)'` | no hay coincidencias |
| 5 | Los HTML coinciden con el briefing | skill `briefing-content-check` sobre cada HTML en staging | todas sus filas PASA, o no hay HTML (NO APLICA) |
| 6 | No hay secretos | `git diff --cached \| grep -nEi '^\+.*(api[_-]?key\|secret\|password\|token)[a-z_]*\s*[:=]\s*["'\'']?[A-Za-z0-9_-]{12,}'` | no hay coincidencias |
| 7 | El asunto es Conventional Commit | primera línea de `mensaje` con `grep -E '^(feat\|fix\|docs\|chore\|refactor\|test\|style\|perf)(\([a-z0-9-]+\))?: .+'` | coincide |
| 8 | El cuerpo tiene Propósito, Objetivos y Resumen de cambios | `grep -E '^(Propósito\|Objetivos\|Resumen de cambios)'` sobre `mensaje` | aparecen las 3 líneas |
| 9 | No hay atribución de IA | `grep -iE 'co-authored-by\|generated with'` sobre `mensaje` | no hay coincidencias |

## Salida esperada
Una tabla con una fila por criterio:

| # | Criterio | Resultado | Evidencia |
|---|---|---|---|
| 1 | ... | PASA / FALLA / NO APLICA | salida del comando o archivo concreto |

Veredicto final: `LISTO PARA COMMIT` si no hay ningún `FALLA`; si no, `NO LISTO` con el número de cada criterio que falló.

## Qué no hace
No edita archivos, no hace commit ni push y no decide si un archivo protegido se puede tocar: eso lo confirma el desarrollador.
