# Política de Ramas y Flujo de Trabajo en GitLab utilizando Gitflow

### 1. Objetivo:
El objetivo de esta política es establecer un flujo de trabajo claro y consistente para el equipo de desarrollo de software, utilizando GitLab y la metodología Gitflow, al tiempo que se integra con el marco de trabajo Scrum.
<br><br>

### 2. Lineamientos Generales:

#### 2.1  Ramas Permanentes:

:small_blue_diamond: **master:** Representa la rama principal de producción y solo contiene versiones estables y listas para producción.

:small_blue_diamond:**develop:** Rama de desarrollo principal donde se integran todas las características nuevas y se realizan las pruebas de integración.

#### 2.2 Ramas de Funcionalidades:

:small_blue_diamond: Cada nueva funcionalidad, tarea o historia de usuario debe desarrollarse en una rama de características separada desde la rama develop.

:small_blue_diamond: El nombre de la rama debe ser descriptivo y seguir el formato: `feature/nombre-de-la-funcionalidad`.

:small_blue_diamond: Después de completar la funcionalidad, se fusiona con la rama develop a través de una solicitud de extracción (pull request).

#### 2.3 Ramas de Publicación:

:small_blue_diamond: Las ramas de publicación se crean para preparar lanzamientos específicos.

:small_blue_diamond: Se derivan de la rama develop y se nombran con el formato: `release/version-del-lanzamiento`.

:small_blue_diamond: Se utilizan para realizar pruebas finales y ajustes antes de lanzar una nueva versión al entorno de producción.

:small_blue_diamond: Después de la finalización, se fusionan con `master` y `develop` y se etiqueta con la versión correspondiente.

#### 2.4 Ramas de Corrección de Errores:

:small_blue_diamond: Las ramas de corrección de errores (hotfix) se utilizan para abordar problemas críticos en producción.

:small_blue_diamond: Se derivan de la rama master y se nombran con el formato: hotfix/nombre-del-error.

:small_blue_diamond: Se fusionan con master y develop después de la corrección y se etiquetan con la versión correspondiente.
