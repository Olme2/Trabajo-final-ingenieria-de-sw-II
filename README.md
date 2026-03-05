# Trabajo de Equiparación: Distintos Tipos de Pruebas de Software

## Introducción
La Ingeniería de Software es una disciplina que trata de la construcción de grandes sistemas que no puede manejar un único individuo. Utiliza principios metodológicos para sistematizar el desarrollo de sistemas de manera rentable. 

Dentro de este proceso constructivo, surge una etapa con un sentido destructivo llamadas las pruebas del software. Según Glenford Myers, una prueba es el "proceso de ejecutar un programa intentando descubrir un error". El objetivo principal es descubrir defectos que no fueron vistos anteriormente, sabiendo que una prueba nunca puede asegurar la ausencia total de errores, sino únicamente demostrar que existen defectos en el software.

## Desarrollo del tema
El flujo de información en el proceso de pruebas sigue un ciclo sistemático. Comienza con la configuración del software y la configuración de prueba, cuyos resultados de la prueba se evalúan frente a los resultados esperados. Si se encuentran fallas, se pasa a la etapa de depuración para su corrección y se recolectan datos de tasa de error para un modelo de fiabilidad.

Existen dos grandes enfoques metodológicos para diseñar estos casos de prueba:
* **Pruebas de Caja Negra:** Centrados en los requisitos funcionales del software. Operan sobre la interfaz del software para demostrar que sus funciones son operativas, que la entrada es correcta y la salida es correcta, sin tener en cuenta la estructura lógica interna.
* **Pruebas de Caja Blanca:** Aseguran que la operación interna se ajusta a las especificaciones basándose en un preciso examen de los detalles procedimentales. Garantizan que se pruebe por lo menos una vez todos los caminos independientes y se ejerciten todas las decisiones lógicas.

## Desarrollo conceptual
La estrategia de pruebas avanza en forma de espiral, disminuyendo el nivel de abstracción y ampliando el alcance a medida que el sistema crece.

### 1. Pruebas de Unidad
Centran el proceso de verificación en la unidad más pequeña del diseño de software: el componente o módulo. En sistemas orientados a objetos, la menor unidad a probar es la clase u objeto encapsulado. 
* Se prueba la interfaz para asegurar que la información fluye adecuadamente.
* Se controlan las estructuras de datos locales y los caminos de manejo de errores.
* Se validan las condiciones de frontera o límites, ya que el software suele fallar en estos extremos.
* Las pruebas suelen requerir de un "conductor" (driver) que acepte los casos de prueba y de "resguardos" (stubs) que reemplacen a los módulos subordinados.

### 2. Pruebas de Integración
Tienen como objetivo construir sistemáticamente la estructura del sistema de software a la vez que se llevan a cabo pruebas para detectar errores asociados con la interfaz. 
* Se debe evitar la integración "Big-Bang", donde se combinan todos los módulos de golpe.
* **Integración Descendente:** Los módulos se integran al moverse hacia abajo a través de la jerarquía de control, requiriendo resguardos.
* **Integración Ascendente:** Comienza con la construcción y prueba de módulos atómicos, eliminando la necesidad de resguardos pero requiriendo conductores.

### 3. Pruebas de Regresión
Consisten en la ejecución repetida de pruebas que ya se realizaron.
* Aseguran que los cambios o correcciones no propagan efectos colaterales no deseados.
* La automatización de este tipo de pruebas es esencial.

### 4. Pruebas de Validación
Consiste en una prueba de caja negra a gran escala que se realiza cuando el software se encuentra integrado. 
* Su resultado demuestra la conformidad con los requisitos funcionales, de rendimiento y de comportamiento.
* Incluyen la prueba Alfa, conducida por el cliente en un ambiente controlado (lugar de desarrollo), y la prueba Beta, conducida por el usuario final en un entorno no controlado.

## Aplicación práctica
Imaginemos la construcción de un sistema web integral, por ejemplo, un proyecto desarrollado utilizando Next.js para el frontend y una base de datos SQL para manejar datos dinámicos.

1. **Pruebas de Unidad:** El desarrollador aísla la función que calcula precios promedio a partir de una consulta SQL. Utiliza un *driver* para pasar parámetros de entrada (como fechas o categorías) e imprime los resultados, verificando que la lógica algorítmica y los límites no generen desbordes o variables inconsistentes.
2. **Pruebas de Integración:** Se prueba la conexión entre el frontend en Next.js y el backend. Utilizando un enfoque ascendente, se combinan primero los módulos de bajo nivel (consultas a la base de datos) y luego se integran hacia arriba con los componentes de la interfaz de usuario, escribiendo conductores para coordinar la prueba.
3. **Pruebas de Regresión:** Al agregar una nueva funcionalidad en el panel de administración, se corre la suite de pruebas automatizadas para asegurar que los módulos de visualización de usuarios que ya funcionaban no presenten comportamientos no planeados.
4. **Pruebas de Validación:** Se realiza una prueba Alfa con el cliente en el entorno de desarrollo para garantizar que el diseño de las vistas y la documentación cumplan estrictamente con las expectativas comerciales iniciales.
