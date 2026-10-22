---
name: briefing-content-check
description: Verifica que un HTML del sitio de HealthCore coincide con BRIEFING.md (landing o formulario). Usar antes de cada commit que toque HTML.
---

# briefing-content-check

## Objetivo único
Verificar que un HTML del sitio coincide con `BRIEFING.md`. No corrige ni modifica nada.

## Inputs
- `ruta`: ruta del HTML (p. ej. `index.html`, `application.html`).
- `seccion`: sección del briefing a contrastar: "Landing page content" o "Patient enquiry form fields".

## Pasos
1. Leer la sección indicada de `BRIEFING.md`.
2. Leer el HTML de `ruta`.
3. Evaluar cada criterio de la sección correspondiente.
4. Abrir la página en navegador (servidor: `npx http-server . -p 3000 -a 0.0.0.0`) y revisar la consola.
5. Entregar la tabla PASA/FALLA.

## Criterios de aceptación

### Landing page (`index.html`)
| Criterio | Cómo comprobarlo |
|---|---|
| 6 sedes con nombre, teléfono y horario exactos | Comparar texto a texto con la tabla Locations (grep de cada nombre, teléfono y horario) |
| 4 datos de contacto exactos | Buscar info@healthcore.com, (512) 340-8800, (305) 510-7700, +44 20 7946 0100 |
| JSON-LD válido con MedicalOrganization + 6 MedicalClinic | Extraer `<script type="application/ld+json">`, `JSON.parse` sin error, contar 1 MedicalOrganization y 6 MedicalClinic |
| Exactamente 1 `h1` | `document.querySelectorAll('h1').length === 1` |
| 0 anclas internas rotas | Para cada `a[href^="#"]`, existe un elemento con ese `id` |
| Todas las `img` con `alt` no vacío | `[...document.images].every(i => i.alt.trim())` |
| 0 errores en consola | Consola del navegador al cargar, a 390/768/1280 px |

### Formulario (`application.html`)
| Criterio | Cómo comprobarlo |
|---|---|
| Todos los `name` del briefing presentes | Buscar los 16 atributos `name` de la tabla, más `patient_id` condicional |
| Mensajes de error textuales | Comparar cada mensaje con "Expected error messages" |
| Mensaje de éxito y nota de partnerships textuales | Comparar con "Success message" y "Specific restriction" |
| 0 errores en consola | Consola del navegador al cargar y al enviar |

## Salida esperada
Tabla con una fila por criterio:

| Criterio | Resultado | Evidencia |
|---|---|---|
| ... | PASA / FALLA | dato concreto |
