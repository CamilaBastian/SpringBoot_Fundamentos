# 📋 Sistema de Gestión de Tareas (Spring Boot)

![Java](https://img.shields.io/badge/Java-17-orange?style=flat-square&logo=java)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-green?style=flat-square&logo=springboot)
![Maven](https://img.shields.io/badge/Maven-Build-blue?style=flat-square&logo=apachemaven)

> **Trabajo Práctico - Fundamentos de Spring Boot**
> Ingeniería en Sistemas de Información (UTN)

## 📝 Descripción del Proyecto

Este proyecto es una aplicación de consola desarrollada con **Spring Boot** que implementa un sistema de gestión de tareas (To-Do List). El objetivo principal es demostrar la aplicación práctica de los conceptos fundamentales del framework, incluyendo **Inyección de Dependencias**, **Inversión de Control (IoC)**, configuración externa y gestión de entornos mediante **Profiles**.

La aplicación permite realizar operaciones básicas sobre tareas (crear, listar, completar, eliminar) y adapta su comportamiento y mensajes según el entorno de ejecución (Desarrollo o Producción).

## ⚙️ Tecnologías Utilizadas

* **Lenguaje:** Java 17+
* **Framework:** Spring Boot 3.x
* **Gestor de Dependencias:** Maven
* **Librerías Adicionales:**
    * *Lombok:* Para reducir el código boilerplate (Getters, Setters, etc).
    * *Spring Boot DevTools:* Para facilitar el desarrollo.

## 📂 Estructura del Proyecto

El proyecto sigue una arquitectura en capas profesional bajo el paquete `com.utn.tareas`:

* `model`: Definición de la entidad `Tarea` y el enum `Prioridad`.
* `repository`: Simulación de persistencia en memoria (`TareaRepository`).
* `service`: Lógica de negocio (`TareaService`) y servicios de mensajería condicionales (`MensajeService`).
* `TareasApplication`: Clase principal que implementa `CommandLineRunner` para la ejecución del flujo.

## 🚀 Instrucciones de Instalación y Ejecución

1.  **Clonar el repositorio:**
    ```bash
    git https://github.com/CamilaBastian/SpringBoot_Fundamentos.git
    cd SpringBoot_Fundamentos
    ```

2.  **Compilar el proyecto:**
    ```bash
    mvn clean install
    ```

3.  **Ejecutar la aplicación:**
    ```bash
    mvn spring-boot:run
    ```

---

## 🔧 Gestión de Perfiles (Profiles)

Una de las características clave de este TP es el uso de **Spring Profiles** para modificar el comportamiento de la aplicación sin cambiar el código.

Para cambiar el perfil, edita el archivo `src/main/resources/application.properties`:

```properties
# Cambiar a 'dev' o 'prod' según se requiera
spring.profiles.active=dev

```

### 🛠 Perfil de Desarrollo (`dev`)

* **Configuración:** `application-dev.properties`
* **Comportamiento:**
* Límite de tareas bajo (10).
* Mensajes de bienvenida/despedida amigables y detallados via `MensajeDevService`.
* Logs en nivel `DEBUG`.
* Estadísticas activadas.



### 🏭 Perfil de Producción (`prod`)

* **Configuración:** `application-prod.properties`
* **Comportamiento:**
* Alto límite de tareas (1000).
* Mensajes concisos y formales via `MensajeProdService`.
* Logs restringidos a `ERROR`.
* Estadísticas desactivadas (por defecto).



---

## 📸 Capturas de Pantalla

### Ejecución en entorno DEV

> *Se observan mensajes detallados y logs de depuración.*

  ![MensajeDev](https://github.com/user-attachments/assets/4b91d434-a157-489a-9773-a295546268c6)

### Ejecución en entorno PROD

> *Se observan mensajes simplificados y ausencia de logs de debug.*

  ![MensajeProd](https://github.com/user-attachments/assets/7ef39bde-df1f-4057-9928-f9164ca83aaf)

---

## 💭 Conclusiones y Aprendizaje

Durante el desarrollo de este trabajo práctico se aplicaron los siguientes conceptos:

1. **Inyección de Dependencias:** Se utilizó inyección por constructor en `TareaService` y la clase principal, promoviendo el desacoplamiento y facilitando el testing.
2. **Estereotipos:** Uso correcto de `@Repository` para la persistencia, `@Service` para la lógica de negocio y `@Component` (implícito) para beans gestionados.
3. **Configuración Flexible:** Uso de `@Value` para inyectar valores desde `application.properties`, permitiendo cambiar límites y flags sin recompilar.
4. **Polimorfismo con Profiles:** Implementación de la interfaz `MensajeService` con dos implementaciones distintas (`Dev` y `Prod`) que se instancian condicionalmente usando `@Profile`.

---

## 👤 Autor

**Nombre:** Camila Bastian
**Legajo:** 50795
**Materia:** Desarrollo de Software - Ingeniería en Sistemas de Información

```


