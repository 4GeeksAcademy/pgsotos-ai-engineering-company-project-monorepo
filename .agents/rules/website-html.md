---
name: website-html
alcance: POR PATRÓN
globs:
  - "/*.html"
  - "uis/website/**/*.html"
---

# HTML del sitio público

Alcance: POR PATRÓN. Aplica a `/*.html` en la raíz y a `uis/website/**/*.html`.

- HTML5 semántico (`header`, `nav`, `main`, `section`, `footer`).
- Un solo `h1` por página.
- ARIA donde corresponda (navegación, errores de formulario, contador en vivo).
- `alt` descriptivo en toda imagen.
- Tailwind por utilidades; sin CSS a mano salvo `styles.css` si es imprescindible.
- Mobile-first con breakpoints (`md:`, `lg:`).
- JSON-LD de Schema.org según el briefing: `MedicalOrganization` + `MedicalClinic` por cada sede de EE.UU.
