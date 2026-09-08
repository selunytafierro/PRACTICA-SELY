# Instrucciones del proyecto

## Stack y ejecución

- El proyecto es una aplicación estática en `index.html`.
- Usa HTML5, CSS3 y JavaScript vanilla; no asumas React, Vite, TailwindCSS ni TypeScript.
- No hay dependencias npm, scripts de build ni suite de pruebas configurada.
- Para probar la aplicación, abre `index.html` directamente en un navegador.

## Arquitectura

- Mantén la estructura, los estilos y la lógica de la aplicación dentro de `index.html`, salvo que el usuario solicite separar archivos.
- La aplicación es un generador y evaluador de exámenes: conserva el flujo de creación de preguntas, inicio de prueba, respuestas y resultados.
- Usa `localStorage` con la clave `exams` para guardar el historial de exámenes; no agregues bases de datos ni Prisma.

## Convenciones

- Usa `camelCase` para variables, funciones e identificadores de JavaScript.
- Usa nombres en inglés para variables y funciones; conserva en español el texto visible de la interfaz.
- Usa indentación de dos espacios, comillas simples en JavaScript y punto y coma.
- Conserva el idioma español de la interfaz y el atributo `lang="es"`.

## Diseño visual

- Conserva el diseño responsivo existente y sus variables CSS en `:root`.
- Prioriza colores suaves, contraste suficiente y controles legibles en escritorio y móvil.
- Evita agregar dependencias visuales externas cuando CSS vanilla sea suficiente.

## Reglas

- No ejecutes ni agregues comandos de base de datos: este proyecto no usa bases de datos.
- Antes de cambiar el formato de almacenamiento o la estructura principal, revisa los datos existentes en `localStorage` y el flujo completo de la aplicación.
