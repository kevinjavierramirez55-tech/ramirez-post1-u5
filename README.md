# Gestion de Tareas con Servlets y JSP

## Autor

- **Nombre:** Kevin Ramirez
- **Código:** 02220131008
- **Programa:** Ingeniería de Sistemas
- **Unidad:** 5 Fundamentos de Java Web
- **Actividad:** Post-Contenido 1
- **Fecha:** 19/04/2026

Aplicacion web desarrollada en Java Web para la Unidad 5 de Programacion Web. El proyecto implementa un `Servlet` que procesa solicitudes HTTP `GET` y `POST`, valida formularios en el servidor, reenvia informacion a una vista JSP mediante `RequestDispatcher` y aplica el patron Post/Redirect/Get.

## Datos del proyecto

- `groupId`: `com.ejemplo`
- `artifactId`: `gestion-tareas`
- Java: `17`
- Empaquetado: `war`
- Servidor recomendado: `Apache Tomcat 10.x`

## Funcionalidades implementadas

- Listado de tareas existentes mediante `GET /tareas`
- Registro de nuevas tareas mediante `POST /tareas`
- Validacion del titulo en el servidor
- Eliminacion de tareas por `id` mediante `POST /tareas`
- Vista JSP ubicada en `WEB-INF/views/tareas.jsp`
- Redireccion posterior al `POST` con el patron PRG

## Estructura principal

```text
src/main/java/com/ejemplo/model/Tarea.java
src/main/java/com/ejemplo/servlet/TareasServlet.java
src/main/webapp/index.jsp
src/main/webapp/WEB-INF/web.xml
src/main/webapp/WEB-INF/views/tareas.jsp
```

## Requisitos

- JDK 17 o superior
- Maven 3.8 o superior
- Apache Tomcat 10.x
- IntelliJ IDEA o Eclipse

## Ejecucion del proyecto

1. Clonar el repositorio.
2. Abrir el proyecto en IntelliJ IDEA como proyecto Maven.
3. Verificar que el SDK del proyecto este configurado en Java 17.
4. Ejecutar el comando:

```bash
mvn clean package
```

5. Configurar un servidor Tomcat local en el IDE.
6. Desplegar el artefacto `gestion-tareas.war exploded`.
7. Abrir en el navegador:

```text
http://localhost:8080/gestion-tareas/tareas
```

## Flujo esperado

- Al ingresar a `/tareas`, se muestran 2 tareas de ejemplo cargadas en `init()`.
- Al agregar una tarea valida, el sistema redirige nuevamente a `/tareas`.
- Al enviar el formulario sin titulo, se muestra el mensaje `El titulo no puede estar vacio`.
- Al eliminar una tarea, esta desaparece de la tabla y se mantiene la URL `/tareas`.

## Evidencias

### Compilacion del proyecto

![Compilacion Maven](evidencias/captura_app_compilando.png)

### Lista inicial de tareas

![Lista de tareas](evidencias/captura_lista_tareas.png)

### Registro de nueva tarea

![Nueva tarea](evidencias/captura_nueva_tarea.png)

### Validacion de titulo vacio

![Mensaje de error](evidencias/captura_mensaje_error.png)

### Eliminacion de tarea

![Eliminar tarea](evidencias/captura_eliminar_tarea.png)

## Checkpoint de verificacion

- La aplicacion compila sin errores con `mvn clean package`.
- La pagina muestra las dos tareas iniciales.
- El formulario agrega tareas correctamente y aplica PRG.
- La validacion en servidor muestra el mensaje de error cuando el titulo esta vacio.
- La eliminacion de tareas funciona correctamente.

## Recomendacion para la entrega

Para cumplir con el enunciado del curso, en GitHub el repositorio debe publicarse con el nombre `apellido-post1-u5`.
