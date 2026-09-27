# Elección de empresa: HealthCore

## Por qué la elegí

Hace unos años un amigo médico, con un máster en Informática Médica, me habló del
mercado de software clínico en Japón. Desde entonces quiero orientar mi carrera a trabajar en ese sector y en ese país, y HealthCore es el escenario que más se parece a lo que necesitaría dominar.

## Departamentos que más me interesan

1. **Operaciones Clínicas**: las clínicas de EE.UU. y del Reino Unido usan plataformas
   EHR distintas y el historial del paciente no lo sigue entre sedes. Además el
   personal pierde 35 minutos al día en documentación que la IA podría asistir.
2. **Tecnología**: mantiene un mosaico de sistemas heredados sin capa de datos
   compartida, incluidos los dos EHR distintos, y necesita construir la API central
   que los unifique.

## Reto que más quiero construir

La **API unificada de historia clínica**: Operaciones Clínicas pide una API que
exponga datos de ambos sistemas EHR, y Tecnología pide la API central que unifique
datos de pacientes, citas, facturación y personal. Es el mismo problema visto desde
ambos departamentos.

## My AI Agent Idea

**Agente de documentación clínica sobre la API unificada.** Aporta a Operaciones
Clínicas recuperando parte de los "35 minutos al día" que "el personal clínico
dedica... a tareas de documentación que podrían ser asistidas por IA": genera el
borrador de la nota para que el médico solo revise y apruebe. También evita que,
cuando "un paciente se mueve entre sedes o cruza la frontera EE.UU.-Reino Unido, su
historia no le sigue", porque el agente siempre lee y escribe sobre la misma fuente
de datos. A Tecnología le aporta el primer caso de uso real de "una API central de
HealthCore que unifique datos de pacientes, citas, facturación y personal de ambos
sistemas EHR": cualquier dato que el agente registre en un EHR queda disponible de
inmediato para el otro, sin integraciones adicionales.
