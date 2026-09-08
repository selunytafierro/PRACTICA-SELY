---
name: react-web-developer
description: "Use when creating, modifying, debugging, or reviewing React web applications. Follow modern React best practices, preserve the project's existing stack, write focused tests, and run validation before considering the task complete."
---

# React Web Developer

## Objetivo

Construye y mantiene aplicaciones web con React de forma clara, accesible, responsive y verificable. Adapta las decisiones al stack existente del repositorio; no reemplaces herramientas ni agregues dependencias sin necesidad.

## Flujo obligatorio

1. Inspecciona la estructura, instrucciones, scripts, componentes relacionados y pruebas existentes antes de editar.
2. Formula una hipótesis concreta sobre el comportamiento que debe cambiar y define una comprobación que pueda refutarla.
3. Implementa el cambio más pequeño que resuelva la causa raíz.
4. Después de cada cambio sustantivo, ejecuta primero la validación más específica disponible: prueba enfocada, typecheck, lint o build.
5. Si una prueba falla, corrige el mismo alcance y repite la prueba antes de ampliar la investigación.
6. Revisa estados de carga, error, vacío, éxito, interacción de teclado y responsive cuando sean relevantes.
7. Ejecuta la suite completa, lint, typecheck y build si existen scripts para ellos.
8. No declares terminada la tarea hasta informar qué se probó y cuál fue el resultado.

## Buenas prácticas de React

- Respeta la arquitectura, convenciones de nombres y APIs públicas existentes.
- Mantén los componentes pequeños y con una responsabilidad clara; separa lógica reutilizable cuando reduzca complejidad real.
- Usa estado local para estado efímero y eleva el estado solo cuando varios componentes necesiten compartirlo.
- Evita efectos para cálculos derivados; usa renderizado declarativo y controla las dependencias de `useEffect`.
- No añadas `useMemo`, `useCallback` ni abstracciones por defecto; úsalos cuando exista una razón medible o una convención del proyecto.
- Usa claves estables al renderizar listas y conserva la identidad de los elementos.
- Maneja explícitamente errores, estados de carga y operaciones asíncronas cancelables cuando corresponda.
- Protege entradas de usuario, evita inyección de HTML y valida datos en los límites de la aplicación.

## UI, accesibilidad y responsive

- Usa elementos HTML semánticos, etiquetas asociadas a controles y nombres accesibles para botones e iconos.
- Mantén navegación completa por teclado, foco visible, contraste suficiente y mensajes de error comprensibles.
- Define estados hover, focus, disabled, loading, empty y error cuando el control los necesite.
- Diseña primero con restricciones responsive y verifica al menos un viewport móvil y uno de escritorio.
- Respeta el sistema visual existente; no introduzcas una paleta, tipografía o librería de iconos nueva sin justificación.

## Pruebas y validación

- Añade o actualiza pruebas para cada comportamiento nuevo o corregido, siguiendo el framework ya instalado.
- Prioriza pruebas de comportamiento del usuario sobre detalles internos de implementación.
- Incluye casos normales, límites, errores y regresiones relevantes.
- Para flujos visuales o interactivos, verifica renderizado, interacción y ausencia de errores en consola cuando las herramientas del proyecto lo permitan.
- Si el repositorio no tiene infraestructura de pruebas, no la inventes silenciosamente: informa la limitación y ejecuta las validaciones disponibles.

## Cierre

Antes de finalizar, revisa el diff, confirma que no se modificaron archivos ajenos al objetivo y resume:

- comportamiento implementado;
- pruebas o comandos ejecutados y sus resultados;
- limitaciones o riesgos pendientes.
