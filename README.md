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
Para ilustrar cómo se implementan los distintos tipos de pruebas en un entorno real, plantearemos el escenario ficticio del desarrollo de una plataforma para gestionar las ventas de una polleria. El equipo de desarrollo utiliza C# para realizar este sistema y para probarlo usamos pruebas de escritorio.

### Escenario Ficticio: Sistema de gestion de polleria
El sistema necesita una función central que calcule el total de una venta sumando los detalles que conlleva esa venta. Hicimos una prueba unitaria para esto, luego una prueba de integracion que integran los modulos de venta con su controller, una prueba de validacion que utiliza views para probar que siga siendo funcional y por ultimo la prueba de validacion que ejecuta el sistema completo para realizarle pruebas de caja negra en vivo. 

Las primeras 3 pruebas se encuentran en el siguiente repositorio: https://github.com/frc11/Repositorio-parte-practica-trabajo-ing-II/

El sistema completo se encuentra en este repositorio: https://github.com/Olme2/Programa

## Mejores Prácticas:
* Las pruebas unitarias y de integración deben ser realizadas por el desarrollador, pero las validaciones de mayor escala deben incluir a un grupo de prueba independiente para evitar conflictos de interés.
* Mantener una alta cohesión en el diseño del código, ya que esto simplifica drásticamente la escritura de los casos de prueba unitarios.

## Beneficios de implementar la técnica
* **Detección eficiente:** La integración incremental permite construir y probar en pequeños segmentos fáciles de aislar y corregir.
* **Fiabilidad demostrable:** Los datos que se van recogiendo proporcionan un buen indicador de la fiabilidad y calidad del sistema como un todo.
* **Prevención de colapsos en producción:** Probar exhaustivamente los límites previene fallos críticos en condiciones extremas de uso.

## Desafíos y consideraciones
* **La prueba no genera calidad:** La calidad se incorpora al software durante el proceso de ingeniería, aplicando métodos y revisiones adecuadas; la prueba solo la evalúa.
* **Límites de cobertura:** Un testeo completo y exhaustivo es imposible y poco práctico, por lo que prima el principio de la economía de las pruebas.
* **Complejidad del ecosistema:** Escribir resguardos en la integración descendente o aislar dependencias en sistemas orientados a objetos puede añadir una "sobrecarga" de trabajo significativa.
* **El arte de la depuración:** Conectar el error detectado en la prueba con su causa raíz sigue siendo un proceso complejo; a veces un síntoma aparece intermitentemente o su causa real está ubicada en un módulo muy alejado.

## Conclusión
La prueba del software es un conjunto de actividades que se deben planificar y llevar a cabo sistemáticamente, no como un evento aislado al final de la programación. Dominar la distinción y la aplicación secuencial de las pruebas de unidad, integración, regresión y validación permite a los ingenieros de software construir estructuras sólidas, garantizando que el producto final cumpla exactamente con lo que el cliente solicitó.

## Referencias
* Pressman, Roger S. Software engineering: a practitioner's approach. 7th edition. Palgrave Macmillan, 2010.
* Myers, Glenford J., Corey Sandler, y Tom Badgett. The art of software testing. John Wiley & Sons, 2011.
* Mentz, María Isabel. Ingeniería de Software II. Facultad de Ciencias Exactas y Tecnología, Universidad Nacional de Tucumán, 2014.
* Valdecantos, Mg. Héctor A. Pruebas del Software. Facultad de Ciencias Exactas y Tecnología, Universidad Nacional de Tucumán.
