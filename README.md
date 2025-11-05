# TP_SpringBootFundamentos
Desarrollo de Software: trabajo de fundamentos de Spring Boot

## Descripción

Proyecto en Spring Boot para practicar la estructura de una aplicación backend: controladores, servicios, configuración, perfiles y ejecución del proyecto con Maven.

## Tecnologías utilizadas

* Java
* Spring Boot
* Maven

## Cómo clonar y ejecutar

```bash
git clone https://github.com/CamilaBastian/TP_SpringBootFundamentos.git
cd TP_SpringBootFundamentos
mvn clean install
mvn spring-boot:run
```

O ejecutar el JAR en `/target/`.

## Cambiar entre perfiles (dev/prod)

* Editar `spring.profiles.active` en `application.properties`.
* O ejecutarlo con:

  ```bash
  mvn spring-boot:run -Dspring-boot.run.profiles=prod
  ```

  ```bash
  java -jar app.jar --spring.profiles.active=prod
  ```

### Camila Bastian - 50795
