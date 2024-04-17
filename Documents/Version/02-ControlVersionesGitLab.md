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
      
   :one: **Clonar el repositorio desde GitLab a tu máquina local:**
   
     
      git clone <URL_del_repositorio_en_GitLab>
      
   
   :two: **Navegar al directorio del repositorio clonado:**
   
   
      cd app-proyecto
   
   
   :three: **Asegurarse de estar en la rama develop:**
   
      
      git checkout develop
      
   
   :four: **Crear una nueva rama de características desde develop:**
   
      
      git checkout -b feature/01
      
   
   :five: **Desarrollar la funcionalidad y hacer commits según sea necesario:**
   
      
      # Realizar cambios y agregar archivos
      git add .
      # Hacer commit de los cambios
      git commit -m "Implementar nueva funcionalidad"
      
   
   :six: **Subir la rama de características al repositorio en GitLab:**
   
      
      git push origin feature/01

   Con estos pasos, has creado correctamente la rama feature/01 a partir de la rama develop en el repositorio en GitLab llamado "app-proyecto" y has comenzado a desarrollar la nueva funcionalidad en esa rama.
   
   </details>

Despúes de haber terminado la tarea y hacer el push, se pasa a la integración de la rama feature/01 con la rama develop, ambas ramas del GitLab, ver el Escenario 3. 
<br><br>

#### 3.2 Escenario 2: Corrección de un Error en Producción

Partiendo del repositorio en GitLab llamado "app-proyecto" y creando la rama hotfix/error a partir de la rama main/master que está en GitLab:

<details><summary>Pasos:</summary>
<br>
   
 :one: **Clonar el repositorio desde GitLab a tu máquina local si aún no lo has hecho:**
   
   ```bash
   git clone <URL_del_repositorio_en_GitLab>
   ```

:two: **Navegar al directorio del repositorio clonado:**

   ```bash
   cd app-proyecto
   ```

:three: **Asegurarse de estar en la rama main:**

   ```bash
   git checkout main
   ```

:four: **Crear una nueva rama de corrección de errores desde main:**

   ```bash
   git checkout -b hotfix/error
   ```

:five: **Realizar la corrección del error en tu código.**

   ```bash
   # Realizar correcciones según sea necesario
   ```

:six: **Hacer commit de los cambios:**

   ```bash
   git add .
   git commit -m "Corregir error crítico en producción"
   ```

:seven: **Subir la rama de corrección de errores al repositorio en GitLab:**

   ```bash
   git push origin hotfix/error
   ```

Con estos pasos, has creado correctamente la rama hotfix/error a partir de la rama develop en el repositorio en GitLab llamado "app-proyecto" y has comenzado a corregir el error crítico en esa rama.


</details>

<br><br>
#### 3.2 Escenario 3: Solicitar un pull request para hacer un merget request

Una vez que has realizado el push a la rama de feature/01 en GitLab, el proceso de solicitud de pull request y la fusión del código por parte del responsable del repositorio se pueden realizar de la siguiente manera:

<details><summary>Pasos:</summary>
<br>
   
:one: **Navega al Repositorio en GitLab:**

   - Abre el navegador web y accede al repositorio en GitLab donde has realizado la solicitud de cambios.

:two: **Abre la Página de Merge Requests:**

   - En la página principal del repositorio, busca y haz clic en la pestaña "Merge Requests" o "Solicitudes de Fusión".

:three: **Crea un Nuevo Merge Request:**

   - Haz clic en el botón "New merge request" o "Nueva solicitud de fusión".

:four: **Selecciona las Ramas:**

   - En la página de creación de la solicitud de fusión, selecciona la rama de destino (generalmente la rama `develop` o `master`) como "Target branch".
   - Selecciona la rama de características (en este caso, `feature/01`) como "Source branch".

:five: **Completa los Detalles del Merge Request:**

   - Proporciona un título descriptivo para la solicitud de fusión y una descripción detallada de los cambios realizados.
   - Puedes etiquetar a los revisores apropiados y asignarles tareas si es necesario.

:six: **Crea la Solicitud de Fusión:**

   - Haz clic en el botón "Submit merge request" o "Enviar solicitud de fusión" para crear la solicitud de fusión.

:seven: **Revisión y Comentarios:**

   - El responsable del repositorio y otros colaboradores pueden revisar la solicitud de fusión, realizar comentarios y solicitar modificaciones si es necesario.
   - Puede haber discusiones adicionales sobre los cambios propuestos antes de que se apruebe la solicitud de fusión.

:eight: **Aprobación de la Solicitud de Fusión:**

   - Una vez que se hayan realizado las revisiones y se hayan abordado todos los comentarios, el responsable del repositorio puede aprobar la solicitud de fusión.

:nine: **Fusión del Código:**

   - Después de la aprobación, el responsable del repositorio puede fusionar la rama de características (`feature/01`) en la rama de destino (`develop` o `master`) utilizando la interfaz de GitLab.
   - Se pueden agregar etiquetas de versión y otros metadatos relevantes antes de completar la fusión.

:one: **Confirmación de Fusión:**
   - Una vez completada la fusión, GitLab proporcionará una confirmación de que la fusión se ha realizado con éxito.    
   - Los cambios ahora estarán disponibles en la rama de destino y se reflejarán en el historial de cambios del repositorio.
   - Elminar la rama feature/01 del repositorio de gitLab. 



</details>

Este proceso garantiza que los cambios propuestos sean revisados y aprobados por el responsable del repositorio antes de fusionarse en la rama principal, lo que ayuda a mantener la integridad y la calidad del código base.

  
<br><br>

#### 3.4 Escenario 4: Release de una nueva versión 

<details><summary>Pasos</summary>
Aquí tienes los pasos detallados para hacer un release basado en la metodología Gitflow:

1. **Asegúrate de estar en la rama `develop`:**
   - Antes de crear un release, asegúrate de estar en la rama `develop` para garantizar que la nueva versión se base en el código más reciente de desarrollo.
   ```bash
   git checkout develop
   ```

2. **Crea una nueva rama de release desde `develop`:**
   - Utiliza el prefijo `release/` seguido del número de versión para nombrar la rama de release.
   ```bash
   git checkout -b release/1.0.0
   ```

3. **Actualiza el número de versión en tu código:**
   - Actualiza el número de versión en tu código según el estándar de versionamiento de tu proyecto. Esto podría incluir actualizar el archivo `package.json`, `composer.json`, o cualquier otro archivo donde se especifique la versión del software.
   - Asegúrate de hacer un commit con este cambio.
   ```bash
   git add <archivos modificados>
   git commit -m "Actualizar número de versión para el release 1.0.0"
   ```

4. **Realiza pruebas finales en la rama de release:**
   - Realiza pruebas de integración y pruebas de usuario final en la rama de release para garantizar que la versión esté lista para su despliegue.

5. **Fusiona la rama de release con `master`:**
   - Una vez que el release esté listo, fusiona la rama de release con la rama `master`.
   ```bash
   git checkout master
   git merge --no-ff release/1.0.0
   ```

6. **Etiqueta el release en `master`:**
   - Etiqueta la fusión en la rama `master` con el número de versión para marcar el lanzamiento oficial.
   ```bash
   git tag -a v1.0.0 -m "Versión 1.0.0"
   ```

7. **Fusiona la rama de release con `develop`:**
   - Fusiona la rama de release con la rama `develop` para asegurarte de que los cambios en el release también se reflejen en la rama de desarrollo.
   ```bash
   git checkout develop
   git merge --no-ff release/1.0.0
   ```

8. **Elimina la rama de release (opcional):**
   - Si ya no se necesita, puedes eliminar la rama de release.
   ```bash
   git branch -d release/1.0.0
   ```

9. **Empuja los cambios y las etiquetas al repositorio remoto:**
   - Finalmente, asegúrate de empujar los cambios y las etiquetas al repositorio remoto para compartir la nueva versión con otros colaboradores y desencadenar los despliegues correspondientes.
   ```bash
   git push origin master
   git push origin develop
   git push --tags
   ```

Estos pasos te permitirán seguir la metodología Gitflow para realizar un release de manera ordenada y controlada, asegurando que cada versión sea probada y etiquetada adecuadamente antes de su lanzamiento.

</details>


<br><br>
