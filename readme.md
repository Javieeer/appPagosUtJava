# Curso Full Stack Backend

Este proyecto es una aplicación backend desarrollada con **Spring Boot** que gestiona estudiantes y pagos. Incluye funcionalidades para registrar, listar y actualizar información de estudiantes y pagos, además de manejar archivos adjuntos como comprobantes de pago.

## Características

- Gestión de estudiantes:
  - Registro de estudiantes.
  - Listado de estudiantes por programa académico.
  - Búsqueda de estudiantes por código.

- Gestión de pagos:
  - Registro de pagos con archivo adjunto (PDF).
  - Listado de pagos por estudiante, estado o tipo.
  - Actualización del estado de un pago.
  - Descarga de archivos adjuntos de pagos.

- Base de datos en memoria **H2** para pruebas y desarrollo.
- Documentación automática de la API con **Swagger**.

## Tecnologías utilizadas

- **Java 21**
- **Spring Boot 3.4.4**
- **H2 Database**
- **Lombok**
- **Spring Data JPA**
- **Springdoc OpenAPI**

## Requisitos previos

- **Java 21** o superior.
- **Maven** (opcional, ya que el proyecto incluye el Maven Wrapper).

## Configuración

### Base de datos

El proyecto utiliza una base de datos en memoria **H2**. La configuración se encuentra en el archivo [`application.properties`](src/main/resources/application.properties):

```properties
spring.datasource.url=jdbc:h2:mem:estudiantes
spring.datasource.username=sa
spring.datasource.password=sa
spring.h2.console.enabled=true
```
Puedes acceder a la consola H2 en la siguiente ruta después de iniciar la aplicación.
http://localhost:8080/h2-console 

Swagger
La documentación de la API está disponible en http://localhost:8080/swagger-ui.html.

## Ejecución
- Usando Maven Wrapper
En la raíz del proyecto, ejecuta:
```
mvn spring-boot:run
```

- Usando un IDE

Importa el proyecto como un proyecto Maven.

Ejecuta la clase principal: CursoFullStackBackendApplication.

## Endpoints principales
Estudiantes\
GET /estudiantes: Lista todos los estudiantes.\
GET /estudiantes/{codigo}: Obtiene un estudiante por su código.\
GET /estudiantesPorPorgrama?programaId={programaId}: Lista estudiantes por programa académico.

Pagos\
GET /pagos: Lista todos los pagos.\
GET /pagos/{id}: Obtiene un pago por su ID.\
GET /estudiantes/{codigo}/pagos: Lista pagos de un estudiante por su código.\
GET /pagosPorStatus?status={CREADO|VALIDADO|RECHAZADO}: Lista pagos por estado.\
GET /pagos/PorTipo?type={EFECTIVO|CHEQUE|TRANSFERENCIA|DEPOSITO}: Lista pagos por tipo.\
POST /pagos: Registra un pago con archivo adjunto.\
PUT /pagos/{id}/actualizarPago: Actualiza el estado de un pago.\
GET /pagoFile/{pagoId}: Descarga el archivo adjunto de un pago.

## Estructura del proyecto
src/\
├── main/\
│   ├── java/\
│   │   └── com.systempaymentut.CursoFullStackBackend/\
│   │       ├── entities/\
│   │       ├── enums/\
│   │       ├── repository/\
│   │       ├── services/\
│   │       └── web/\
│   └── resources/\
│       ├── META-INF/\
│       ├── static/\
│       ├── templates/\
│       ├── application.properties\
└── test/

## Contribuciones
¡Las contribuciones son bienvenidas! Si deseas contribuir, por favor abre un issue o envía un pull request.