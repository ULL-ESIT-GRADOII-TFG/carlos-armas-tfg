# Guión presentación

## INTRODUCCIÓN

## Qué es ghedsh

Es una gema Ruby que consiste en un intérprete de comandos desarrollado para integrar las metodologíasde GitHub Education, viendo las organizaciones como aulas y los repositorios como las asignaciones de los alumnos.

Este Trabajo de Fin de Grado es la segunda versión de la gema `ghedsh` que se inició en otro TFG anterior.

### Herramientas similares

#### Desarrolladas por GitHub

Estas dos herramientas han sido desarrolladas por GitHub.

* Teachers pet: CLI desarrollado previamente a Classroom. Facilita a los profesores la distrubución de código de inicio para las tareas y comprobar el progreso en las mismas.
  * Inconveniente: los comandos se hacían excesivamente largos en determinados casos. Cayó en desuso y se dejó de desarrollar.
* GitHub Classroom: Una plataforma web que simplifica la configuración de las aulas y las asignaciones. Sin embargo, existen algunas limitaciones:
  * Actualmente no dispone de alguna funcionalidad que permita al profesor crear un repositorio de evaluación para calificar las tareas.
  * En muchos casos, el nombre de usuario que ha escogido el alumno al registrarse en GitHub no permite identificarlo. El sistema para añadir información adicional del alumno es incómodo de usar ya que la información adicional hay que insertarla individualmente.

#### Desarrolladas por la comunidad

En cuanto a estas dos herramientas, han sido desarrolladas por la comunidad.

* *ghi* GitHub Issues. Permite gestionar las incidencias (issues).
* *ghs* GitHub Search. Permite realizar búsquedas en repositorios alojados en GitHub. Admite opciones para limitar las búsquedas dentro de organizaciones o usuarios, por ejemplo.

## Objetivos

Esta segunda versión de `ghedsh` busca mejorar el código fuente de la primera versión, teniendo en cuenta aspectos como la mantenibilidad del código para facilitar la incorporación de nuevas funcionalidades. También aportar una solución a algunas de las limitaciones que poseen herramientas anteriormente comentadas y concentrar funcionalidad en una única herramienta.

Por otro lado, una de las prioridades de esta herramienta es dar soporte al proceso de evaluación.

## Tecnologías empleadas

En cuanto a las tecnologías empleadas tenemos:

* Lenguaje de programación: **Ruby**
* Gestión de dependencias: **Bundler**
* Testing: **RSpec**

## Desarrollo del proyecto

Dividimos el desarrollo del proyecto en dos fases bien diferenciadas:

* Análisis, que consistió en estudiar el código de la primera versión para identificar aquellas partes mejorables del diseño e implementación iniciales.

* Refactorización, describe el proceso llevado a cabo para solucionar las debilidades anteriores.

### Primera fase. Análisis

#### Code Smell

Tras estudiar el código de la primera versión de la gema se han detectado diversos *code smell*.
Un Code Smell se define como cualquier característica del código fuente que, posiblemente, indica un problema más profundo.
No son considerados como *bugs*, puesto que no impiden que un programa funcione correctamente.

Sin embargo, estos defectos en el diseño pueden afectar al rendimiento del programa y aumentan la probabilidad de *bugs* en el futuro.

#### Switch Smell

En la imagen se ve un mal uso de las sentencias switch-case, que en Ruby son case-when. El principal problema es que al añadir un nuevo caso, debemos localizar todas estas sentencias y modificarlas.

Este era el más repetido a lo largo del código fuente, por lo que la refactorización se ha centrado sobretodo en este aspecto.

#### Long Method

Long Method} se clasifica a nivel de método. Como su propio nombre indica, consiste en un método que ha crecido demasiado y dificulta saber qué es lo que realmente hace.

#### Large Class

Large Class se clasifica dentro de los smells a nivel de clases. Indica que una clase ha crecido excesivamente en tamaño (God Object) y seguramente su funcionalidad puede descomponerse en clases más pequeñas y fáciles de manejar.
