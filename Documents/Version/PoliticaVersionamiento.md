# Política de versionado de productos software

### Política de Versionamiento de Código

#### 1. Objetivo

La política de versionamiento de código tiene como objetivo proporcionar una estructura clara y consistente para gestionar el versionamiento del código en un equipo de desarrollo de software. Esto incluye la identificación de versiones, la gestión de ramas de código, el incremento de versiones y el manejo de pre-lanzamientos.

#### 2. Convenciones de Versionamiento
- **Formato de versión**: Las versiones seguirán el formato "MAJOR.MINOR.PATCH" donde:
  - **MAJOR**: Incrementado para cambios significativos que pueden afectar la compatibilidad hacia atrás o introducir nuevas funcionalidades importantes.
  - **MINOR**: Incrementado para adiciones de nuevas funcionalidades que son compatibles con versiones anteriores.
  - **PATCH**: Incrementado para correcciones de errores y cambios menores que no afectan la compatibilidad hacia atrás.
- **Pre-lanzamientos (Pre-release)**: Se utilizarán etiquetas adicionales como `alpha`, `beta` o `rc` (release candidate) para versiones en desarrollo y pruebas.
- **Ramas de Código**: Cada desarrollador creará una rama de código separada para cada nueva funcionalidad o tarea, utilizando el formato `feature_idtarea`.
- **Integración de Código**: Los cambios se integrarán primero en la rama `developer` a través de solicitudes de extracción (pull requests) y luego en la rama `master` para lanzamientos oficiales.

### 3. Escenarios


<details>
<summary>Escenario 1: Integración de Cambios en un Sprint</summary>
  
<br>

1. **Desarrollo en Ramas de Funcionalidad**: Cada desarrollador crea una rama `developer` y ramas de funcionalidad (`feature_idtarea`) para trabajar en sus tareas asignadas.
2. **Pull Requests a Developer**: Después de completar una tarea, cada desarrollador crea un pull request para fusionar su rama de funcionalidad con la rama `developer`.
3. **Revisión y Pruebas**: El equipo revisa y prueba los cambios en la rama `developer` durante el sprint.
4. **Lanzamiento de Versión**: Al finalizar el sprint, se incrementa la versión del software en el componente correspondiente (major, minor o patch) y se crea un tag de versión en la rama `master`.
5. **Integración en Master**: Los cambios de la rama `developer` se integran en la rama `master` mediante un pull request y se realiza el despliegue del nuevo lanzamiento.
<br>

</details>

<details>
<summary>Escenario 2: Corrección de Bugs en Hotfix</summary>
  
<br>


1. **Detección del Bug**: Se detecta un bug crítico en producción que requiere una corrección inmediata.
2. **Creación de Rama Hotfix**: Se crea una rama `hotfix` desde la rama `master` para abordar el bug.
3. **Resolución del Bug**: Se corrige el bug en la rama `hotfix` y se prueba localmente.
4. **Pull Request a Master**: Después de confirmar que el bug ha sido corregido, se crea un pull request para fusionar la rama `hotfix` con la rama `master`.
5. **Lanzamiento de Versión**: Se incrementa el número de versión en la rama `master` (major, minor o patch) y se crea un tag de versión para el lanzamiento de la corrección de bug.


<br>

</details>


### Ejemplo de Uso

#### Escenario 1: Integración de Cambios en un Sprint
Supongamos que el equipo está trabajando en una nueva funcionalidad de autenticación de usuarios. Cada desarrollador crea una rama `developer` y una rama de funcionalidad (`feature_autenticacion`) para implementar esta funcionalidad.

Al finalizar el sprint, se realizan las siguientes acciones:
- Se fusionan las ramas de funcionalidad en la rama `developer`.
- Se incrementa la versión del software a 2.0.0 (major) debido a la introducción de una nueva funcionalidad importante.
- Se crea un tag de versión en la rama `master` para el lanzamiento oficial.

#### Escenario 2: Corrección de Bugs en Hotfix
Supongamos que se descubre un bug crítico en la función de pago del sistema durante un despliegue en producción. Se sigue el siguiente proceso:
- Se crea una rama `hotfix` desde la rama `master` para abordar el bug.
- Se corrige el bug y se fusiona la rama `hotfix` con la rama `master`.
- Se incrementa la versión del software a 1.0.1 (patch) para reflejar la corrección del bug y se

 crea un tag de versión para el lanzamiento de la corrección.

Espero que este ejemplo detallado te dé una idea clara de cómo se puede implementar una política de versionamiento de código en un equipo de desarrollo que utiliza Scrum y múltiples ramas de código para gestionar el desarrollo de software.


|En los proyectos desarrollados por E3Creatic se deben seguir unas normas de versionado. Esto incluye  |
|-----------|
| ✴️ Uso de tres dígitos para la numeración: **major**, **minor** y **revision**. El cambio de cualquiera de estos números depende del tipo de los cambios que aporte la nueva Versión.  
✴️ Cuarto dígito de control de entregas, opcional. 
✴️ Mecanismos adicionales como el uso de bundles y releases (para proyectos complejos), y una categorización para versiones no finales (alpha, beta, rc).|

La numeración de las versiones de los entregables software permiten expresar de forma normalizada las modificaciones existentes entre las distintas entregas, indicando los cambios que se han producido entre una versión y la siguiente.




