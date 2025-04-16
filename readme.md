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