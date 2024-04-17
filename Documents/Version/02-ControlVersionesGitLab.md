# Política de Ramas y Flujo de Trabajo en GitLab utilizando Gitflow

### 1. Objetivo:
El objetivo de esta política es establecer un flujo de trabajo claro y consistente para el equipo de desarrollo de software, utilizando GitLab y la metodología Gitflow, al tiempo que se integra con el marco de trabajo Scrum.
<br><br>

### 2. Lineamientos Generales:

#### 2.1  Ramas Permanentes:

![image](https://github.com/crodrigr/E3Creatic-TechDoc/assets/31961588/87099c14-5db4-4926-baac-c4a48ee9c77d)


:small_blue_diamond: **master:** Representa la rama principal de producción y solo contiene versiones estables y listas para producción.

:small_blue_diamond:**develop:** Rama de desarrollo principal donde se integran todas las características nuevas y se realizan las pruebas de integración.

#### 2.2 Ramas de Funcionalidades:

![image](https://github.com/crodrigr/E3Creatic-TechDoc/assets/31961588/9c13690c-5f4d-40f7-98f6-e0cbc59728bf)


:small_blue_diamond: Cada nueva funcionalidad, tarea o historia de usuario debe desarrollarse en una rama de características separada desde la rama develop.

:small_blue_diamond: El nombre de la rama debe ser descriptivo y seguir el formato: `feature/nombre-de-la-funcionalidad`.

:small_blue_diamond: Después de completar la funcionalidad, se fusiona con la rama develop a través de una solicitud de extracción (pull request).

#### 2.3 Ramas de Publicación:

![image](https://github.com/crodrigr/E3Creatic-TechDoc/assets/31961588/d9b4af73-f01e-4add-b58a-698e894d164b)


:small_blue_diamond: Las ramas de publicación se crean para preparar lanzamientos específicos.

:small_blue_diamond: Se derivan de la rama develop y se nombran con el formato: `release/version-del-lanzamiento`.

:small_blue_diamond: Se utilizan para realizar pruebas finales y ajustes antes de lanzar una nueva versión al entorno de producción.

:small_blue_diamond: Después de la finalización, se fusionan con `master` y `develop` y se etiqueta con la versión correspondiente.

#### 2.4 Ramas de Corrección de Errores:


![image](https://github.com/crodrigr/E3Creatic-TechDoc/assets/31961588/33144100-e146-4865-bbe0-d8b420c0b0a9)



:small_blue_diamond: Las ramas de corrección de errores (hotfix) se utilizan para abordar problemas críticos en producción.

:small_blue_diamond: Se derivan de la rama master y se nombran con el formato: hotfix/nombre-del-error.

:small_blue_diamond: Se fusionan con master y develop después de la corrección y se etiquetan con la versión correspondiente.

<br><br>

### 3. Escenarios 

#### 3.1 Escenario 1: Desarrollo de una Nueva Funcionalidad

Partiendo del repositorio en GitLab llamado **app-proyecto**, creando la rama **feature/01** a partir de la rama develop que está en **GitLab**:

   <details><summary>Pasos:</summary>
   <br>   
   :one: Clonar el repositorio desde GitLab a tu máquina local:
      ```bash
      git clone <URL_del_repositorio_en_GitLab>
      ```
   
   :two: Navegar al directorio del repositorio clonado:
      ```bash
      cd app-proyecto
      ```
   
   :three: Asegurarse de estar en la rama develop:
      ```bash
      git checkout develop
      ```
   
   :four: Crear una nueva rama de características desde develop:
      ```bash
      git checkout -b feature/01
      ```
   
   :five: Desarrollar la funcionalidad y hacer commits según sea necesario:
      ```bash
      # Realizar cambios y agregar archivos
      git add .
      # Hacer commit de los cambios
      git commit -m "Implementar nueva funcionalidad"
      ```
   
   :six: Subir la rama de características al repositorio en GitLab:
      ```bash
      git push origin feature/01
      ```
   </details>



