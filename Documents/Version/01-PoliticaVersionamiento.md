# Política de versionado de productos software


### 1. Objetivo

La política de versionamiento de código tiene como objetivo proporcionar una estructura clara y consistente para gestionar el versionamiento del código en un equipo de desarrollo de software. Esto incluye la identificación de versiones, la gestión de ramas de código, el incremento de versiones y el manejo de pre-lanzamientos.

### 2. Convenciones de Versionamiento
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

1. **Desarrollo en Ramas de Funcionalidad**: Cada desarrollador crea una rama de funcionalidad (`feature_idtarea`) a partir de developer para trabajar en sus tareas asignadas.
2. **Pull Requests a Developer**: Después de completar una tarea, cada desarrollador crea un pull request para fusionar su rama de funcionalidad con la rama `developer`.
3. **Revisión y Pruebas**: El equipo revisa y prueba los cambios en la rama `developer` durante el sprint.
4. **Lanzamiento de Versión**: Al finalizar el sprint, se incrementa la versión del software en el componente correspondiente (major, minor o patch) y se crea un tag de versión en la rama `master`.
5. **Integración en Master**: Los cambios de la rama `developer` se integran en la rama `master` mediante un pull request y se realiza el despliegue del nuevo lanzamiento.
    <details>
    <summary>Ejemplo:</summary>
    <br>
    Supongamos que el equipo está trabajando en una nueva funcionalidad de autenticación de usuarios. Cada desarrollador crea una rama de funcionalidad (`feature_idtarea`) para implementar esta funcionalidad.
    
    Al finalizar el sprint, se realizan las siguientes acciones:
    - Se fusionan las ramas de funcionalidad en la rama `developer`.
    - Se incrementa la versión del software de 2.1.0 (minor) a 2.2.0 debido a la introducción de una nueva funcionalidad importante. Sin embargo, es importante tener en cuenta que en ciertos casos, si los cambios son significativos, puede ser necesario incrementar la versión en el (major), por ejemplo, pasando de 2.1.0 a 3.0.0..  
    - Se crea un tag de versión (este número de versión debe concordar con la versión especificada en el código fuente) en la rama `master` para el lanzamiento oficial.
      
    
    </details>
</details>


<details>
<summary>Escenario 2: Corrección de Bugs en Hotfix</summary>
  
<br>


1. **Detección del Bug**: Se detecta un bug crítico en producción que requiere una corrección inmediata.
2. **Creación de Rama Hotfix**: Se crea una rama `hotfix` desde la rama `master` para abordar el bug.
3. **Resolución del Bug**: Se corrige el bug en la rama `hotfix` y se prueba localmente.
4. **Pull Request a Master**: Después de confirmar que el bug ha sido corregido, se crea un pull request para fusionar la rama `hotfix` con la rama `master`.
5. **Lanzamiento de Versión**: Se incrementa el número de versión en la rama `master` (major, minor o patch) y se crea un tag de versión para el lanzamiento de la corrección de bug.
      <details>
      <summary>Ejemplo:</summary>
      <br>
      
      Supongamos que se descubre un bug crítico en la función de pago del sistema durante un despliegue en producción. Se sigue el siguiente proceso:
      
      - Se crea una rama `hotfix` desde la rama `master` para abordar el bug.
      - Se corrige el bug y se fusiona la rama `hotfix` con la rama `master`.
      - Se incrementa la versión del software a 1.0.1 (patch) para reflejar la corrección del bug y se crea un tag de versión para el lanzamiento de la corrección.
      
      Espero que este ejemplo detallado te dé una idea clara de cómo se puede implementar una política de versionamiento de código en un equipo de desarrollo que utiliza Scrum y múltiples ramas de código para gestionar el desarrollo de software.
      
      </details>


</details>
</details>

### 4.Tag-Comentarios

En la industria del software, los comentarios en los tags suelen proporcionar información valiosa sobre los cambios incluidos en esa versión específica del software. Estos comentarios pueden ayudar a los desarrolladores, administradores de sistemas y usuarios a comprender los cambios realizados, las nuevas características agregadas, las correcciones de errores y cualquier otra información relevante sobre la versión.

**Plantilla**

```markdown
Versión [número_de_versión] - "[título_del_lanzamiento]"
-------------------------------------------------------------

[Resumen breve de los cambios y mejoras realizados en esta versión.]

### Cambios Principales:
- [Descripción detallada de las nuevas características implementadas.]
- [Mejoras significativas realizadas en el sistema.]
- [Correcciones de errores importantes abordadas en esta versión.]

### Acciones Requeridas:
- [Instrucciones para los usuarios o administradores sobre acciones necesarias después de actualizar a esta versión, si las hay.]

### Notas Adicionales:
- [Cualquier otra información relevante sobre esta versión, como advertencias o limitaciones conocidas.]

Para obtener más detalles sobre los cambios realizados, consulte el registro de cambios completo en el repositorio del proyecto.
```

<details><summary>Ejemplo:</summary>
  
Versión 2.0.0 - "Lanzamiento de la Funcionalidad de Pagos"
-------------------------------------------------------------

Esta versión marca un hito importante en el desarrollo del proyecto, con un enfoque principal en la implementación de la funcionalidad de pagos. A continuación, se detallan los cambios realizados en esta versión:

- Se ha agregado una nueva página de pago que permite a los usuarios realizar transacciones seguras en línea.
- Se han mejorado los sistemas de seguridad y encriptación para proteger la información financiera de los usuarios.
- Se ha optimizado el rendimiento del sistema para manejar grandes volúmenes de transacciones de manera eficiente.
- Se han corregido varios errores menores relacionados con la interfaz de usuario y la lógica de negocios.

Se recomienda encarecidamente a todos los usuarios que actualicen a esta versión para disfrutar de las últimas características y mejoras en la plataforma de pagos.

Para obtener más detalles sobre los cambios realizados, consulte el registro de cambios completo en el repositorio del proyecto.

</details>











