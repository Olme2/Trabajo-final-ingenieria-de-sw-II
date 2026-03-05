# Trabajo de Equiparación: Distintos Tipos de Pruebas de Software

## Introducción
La Ingeniería de Software es una disciplina que trata de la construcción de grandes sistemas que no puede manejar un único individuo. Utiliza principios metodológicos para sistematizar el desarrollo de sistemas de manera rentable. 

Dentro de este proceso constructivo, surge una etapa con un sentido destructivo llamadas las pruebas del software. Según Glenford Myers, una prueba es el "proceso de ejecutar un programa intentando descubrir un error". El objetivo principal es descubrir defectos que no fueron vistos anteriormente, sabiendo que una prueba nunca puede asegurar la ausencia total de errores, sino únicamente demostrar que existen defectos en el software.

## Desarrollo del tema
El flujo de información en el proceso de pruebas sigue un ciclo sistemático. Comienza con la configuración del software y la configuración de prueba, cuyos resultados de la prueba se evalúan frente a los resultados esperados. Si se encuentran fallas, se pasa a la etapa de depuración para su corrección y se recolectan datos de tasa de error para un modelo de fiabilidad.

Existen dos grandes enfoques metodológicos para diseñar estos casos de prueba:
* **Pruebas de Caja Negra:** Centrados en los requisitos funcionales del software. Operan sobre la interfaz del software para demostrar que sus funciones son operativas, que la entrada es correcta y la salida es correcta, sin tener en cuenta la estructura lógica interna.
* **Pruebas de Caja Blanca:** Aseguran que la operación interna se ajusta a las especificaciones basándose en un preciso examen de los detalles procedimentales. Garantizan que se pruebe por lo menos una vez todos los caminos independientes y se ejerciten todas las decisiones lógicas.
