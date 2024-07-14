# API ForoHub

Bienvenido a la documentación de la API ForoHub, una aplicación RESTful creada con Spring que ofrece funciones completas para la gestión de un foro educativo.

## Descripción

ForoHub es una API diseñada para facilitar la administración de temas, respuestas, usuarios y cursos en un entorno educativo. Utiliza Spring Security para la autenticación mediante tokens JWT y sigue las mejores prácticas de REST en la organización de sus endpoints.

## Servidores

La API se puede acceder localmente en:

- URL Base: `http://localhost:8080`
- Swagger: `http://localhost:8080/swagger-ui/index.html`

## Autorización

Para acceder a ciertos endpoints, la API requiere autorización mediante tokens JWT. Revisa la sección de Autenticación para obtener más información.

## Tecnologías Utilizadas

- **Spring Boot**: Framework para el desarrollo de aplicaciones en Java.
- **Spring Security**: Gestión de seguridad y autenticación.
- **JWT (JSON Web Tokens)**: Para la creación y validación de tokens de acceso.
- **Spring Data JPA**: Persistencia de datos utilizando Hibernate.
- **MySql**: Base de datos utilizada para desarrollo y pruebas.
- **Swagger/OpenAPI**: Documentación de la API.
- **Maven**: Gestión de dependencias y construcción del proyecto.
- **Java 17**: Versión del lenguaje utilizada.

## Endpoints

### Tópicos (`topico-controller`)

- **Actualizar un tópico**
  - `PUT /topico/actualizar`
  - Cuerpo: `DatosActualizarTopico`

- **Crear un nuevo tópico**
  - `POST /topico`
  - Cuerpo: `DatosRegistroTopico`

- **Listar todos los tópicos**
  - `GET /topico/listar`
  - Respuesta: `List<PageDatosListadoTopico>`

- **Listar tópicos por curso**
  - `GET /topico/listarPorCurso`
  - Parámetros: `cursoId`
  - Respuesta: `List<PageDatosListadoTopico>`

- **Obtener detalles de un tópico por ID**
  - `GET /topico/detalle/{id}`
  - Respuesta: `Topico`

- **Dar de alta un tópico**
  - `GET /topico/alta/{id}`

- **Eliminar un tópico (lógico)**
  - `DELETE /topico/eliminar/{id}`

- **Eliminar un tópico permanentemente**
  - `DELETE /topico/baja/{id}`

### Respuestas (`respuesta-controller`)

- **Actualizar una respuesta**
  - `PUT /respuesta/actualizar`
  - Cuerpo: `DatosActualizarRespuestas`

- **Registrar una nueva respuesta**
  - `POST /respuesta/registrar`
  - Cuerpo: `DatosRegistroRespuestas`

- **Obtener la solución de una respuesta por ID**
  - `GET /respuesta/solucion/{id}`
  - Respuesta: `Respuesta`

- **Listar todas las respuestas**
  - `GET /respuesta/listar`
  - Respuesta: `List<PageDatosRespuestaRespuestas>`

- **Listar respuestas por tópico**
  - `GET /respuesta/listarPorTopico/{topicoId}`
  - Respuesta: `List<PageDatosRespuestaRespuestas>`

- **Obtener detalles de una respuesta por ID**
  - `GET /respuesta/detalle/{id}`
  - Respuesta: `Respuesta`

- **Eliminar una respuesta (lógico)**
  - `DELETE /respuesta/eliminar/{id}`

- **Eliminar permanentemente una respuesta**
  - `DELETE /respuesta/baja/{id}`

### Usuarios (`usuario-controller`)

- **Registrar un nuevo usuario**
  - `POST /usuario/registrar`
  - Cuerpo: `DatosRegistroUsuario`

### Autenticación (`autenticacion-controller`)

- **Iniciar sesión (login)**
  - `POST /login`
  - Cuerpo: `DatosAutenticacionUsuario`
  - Respuesta: `DatosJWTtoken`

- **Redirigir después del login**
  - `GET /login/redirect`

### Cursos (`curso-controller`)

- **Registrar un nuevo curso**
  - `POST /curso/registrar`
  - Cuerpo: `DatosRegistroCurso`

## Seguridad y Autenticación

La API emplea Spring Security para la autenticación y autorización. Los endpoints protegidos requieren un token JWT válido en el encabezado de autorización.

## Documentación Adicional

Para una descripción más detallada sobre los parámetros, cuerpos de las peticiones y respuestas de cada endpoint, puedes explorar la documentación Swagger de la API accediendo a `/v3/api-docs`.

## Desarrollador

Este proyecto fue creado por Brian Alberto Moreno Ortega.
