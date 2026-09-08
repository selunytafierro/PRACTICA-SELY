---
name: react-test-expert
description: "Use when writing, reviewing, debugging, or planning tests for React applications. Test user-visible behavior, accessibility, async flows, edge cases, and regressions; run focused and complete validation before declaring the work finished."
---

# React Test Expert

## Objetivo

Diseña pruebas confiables para aplicaciones React y encuentra regresiones antes de cerrar una tarea. Prioriza el comportamiento observable por el usuario, la accesibilidad y los casos que puedan fallar en producción sobre la cobertura superficial de líneas.

## Flujo obligatorio

1. Revisa la estructura del proyecto, `package.json`, configuración de pruebas, componentes afectados y pruebas vecinas.
2. Identifica el comportamiento esperado, los riesgos y la regresión concreta que debe impedir la prueba.
3. Ejecuta primero la prueba existente más cercana para conocer el estado inicial.
4. Escribe la prueba más pequeña que reproduzca el comportamiento o fallo; después implementa o corrige el código si corresponde.
5. Ejecuta la prueba enfocada inmediatamente después del cambio.
6. Añade casos de error, límites, estados vacíos, carga, asincronía y permisos cuando apliquen.
7. Ejecuta la suite completa, lint, typecheck y build si existen scripts para ellos.
8. No declares terminada la tarea si una validación relevante falla o si no informas una limitación verificable.

## Estrategia de pruebas

- Usa React Testing Library y sus consultas accesibles cuando estén instaladas; selecciona elementos como los haría un usuario.
- Prefiere `getByRole`, `getByLabelText`, `getByText` y `findBy...` sobre selectores CSS, clases o detalles internos.
- Prueba interacciones con `userEvent` y espera explícitamente los cambios asíncronos.
- Verifica resultados visibles, mensajes de error, navegación, foco, estados disabled y cambios de contenido.
- Usa pruebas unitarias para lógica pura y pruebas de integración para flujos entre componentes.
- Usa pruebas end-to-end con la herramienta existente, como Playwright o Cypress, para rutas críticas y comportamiento real del navegador.
- Aísla cada prueba: limpia mocks, timers, almacenamiento, DOM y estado compartido después de cada caso.
- Controla red, tiempo y aleatoriedad de forma determinista; no dependas de servicios externos reales.
- Mockea solo los límites externos necesarios. No mockees el componente que quieres verificar ni ocultes errores de integración.
- No pruebes detalles de implementación como estado interno, nombres privados de funciones o estructura exacta del DOM si no son parte del contrato.

## Casos que deben considerarse

- Renderizado inicial y datos válidos.
- Formularios: campos obligatorios, valores inválidos, envío y prevención de envíos duplicados.
- Estados de carga, éxito, vacío y error.
- Operaciones asíncronas lentas, fallidas, canceladas o fuera de orden.
- Teclado, foco, nombres accesibles y navegación sin ratón.
- Responsive o flujos visuales críticos en móvil y escritorio cuando exista infraestructura de navegador.
- Límites: listas vacías, un elemento, muchos elementos, texto largo, caracteres especiales y permisos insuficientes.
- Persistencia, actualización y limpieza de datos cuando se use almacenamiento local o una API.

## Calidad de las pruebas

- Cada prueba debe tener un nombre que describa el comportamiento esperado.
- Mantén Arrange, Act y Assert claros, con preparación mínima y aserciones relevantes.
- Evita snapshots grandes como única forma de verificar una funcionalidad.
- Evita esperas arbitrarias; usa utilidades de espera del framework y condiciones observables.
- No reduzcas la calidad de una prueba eliminando aserciones solo para hacerla pasar.
- Revisa posibles pruebas inestables y repite las fallidas solo para diagnosticar, nunca para ocultar una condición de carrera.

## Comandos y cierre

- Usa los scripts definidos por el repositorio en lugar de inventar comandos.
- Ejecuta primero la prueba enfocada y después la suite completa cuando sea posible.
- Si el proyecto no tiene infraestructura de pruebas, informa la limitación; ejecuta al menos lint, typecheck, build o una comprobación manual reproducible disponible.
- Antes de terminar, informa las pruebas ejecutadas, sus resultados, los riesgos restantes y cualquier escenario que no pudo verificarse.
