# 🌋 vulcano-api-grupo-1
**Plataforma de gamificación educativa para fortalecer la lógica de programación mediante desafíos interactivos.**

---

## 📌 Introducción / Contexto

* **Descripción del problema:** Los estudiantes de desarrollo de software enfrentan dificultades para consolidar conocimientos teóricos de forma motivadora, existiendo una brecha significativa entre la teoría impartida y su aplicación práctica creativa.
* **Justificación:** VULCANO API surge para promover la interacción y motivación mediante dinámicas lúdicas que reducen esa brecha, integrando el aprendizaje con experiencias gamificadas.
* **Contexto:** Proyecto académico desarrollado para la Carrera Técnica en Desarrollo de Software.

## 🎯 Objetivos

**Objetivo General** Desarrollar e implementar una plataforma web de gamificación académica que fortalezca el aprendizaje de contenidos teóricos mediante una arquitectura cliente–servidor, utilizando React y Java Spring Boot.

**Objetivos Específicos** 
* **OE1:** Diseñar actividades lúdicas grupales e individuales integradas en una interfaz web dinámica y responsiva.
* **OE2:** Aplicar metodologías ágiles durante el desarrollo para garantizar la adaptación continua a los requerimientos.
* **OE3:** Evaluar y ajustar continuamente el funcionamiento de la plataforma mediante pruebas funcionales y retroalimentación de usuarios.
* **OE4:** Implementar funcionalidades interactivas para gestión de reseñas, desafíos académicos y ejecución de código en tiempo real con una API REST.

## 📐 Alcance del Proyecto (Scope)

**Qué se va a desarrollar:**
* Plataforma web interactiva construida con React, JavaScript y Tailwind CSS.
* Arquitectura cliente–servidor con API REST desarrollada en Java Spring Boot y JPA.
* Gestión de datos con Prisma para modelado de usuarios, reseñas y desafíos.
* Sistema CRUD académico completo para contenidos y retos.
* Módulo de desafíos interactivos con editor de código en el navegador.
* Sistema de autenticación y validación de usuarios.

**Qué NO se va a desarrollar (Fuera de alcance):**
* Entorno de ejecución de código en servidor con sandbox seguro.
* Evaluación automática con inteligencia artificial.
* Aplicación móvil nativa.
* Despliegue en infraestructura de alta disponibilidad.

## 🛠️ Tecnologías y Herramientas (Tech Stack)

* **Backend:** Java Spring Boot, JPA, Maven.
* **Frontend:** React, JavaScript (ES6+), Tailwind CSS.
* **Base de Datos:** PostgreSQL (Prisma) para producción y H2 para desarrollo inicial.
* **Control de Versiones:** Git y GitHub.

## 👥 Integrantes del Equipo

| Nombre | Rol principal | Usuario GitHub |
| :--- | :--- | :--- |
| Mario Múnera | Líder / Backend | [@MarioMunera1993](https://github.com/MarioMunera1993) |
| [Nombre 2] | Frontend Lead | @[usuario] |
| [Nombre 3] | Backend / DB Specialist | @[usuario] |
| [Nombre 4] | QA / Tester | @[usuario] |
| [Nombre 5] | UI/UX Designer | @[usuario] |

## 📊 Diagrama de Clases del Dominio (v1)

```mermaid
classDiagram
    class User {
        +Long id
        +String username
        +String email
        +String password
        +register()
        +login()
    }
    class Challenge {
        +Long id
        +String title
        +String description
        +String difficulty
        +String baseCode
        +validateSolution()
    }
    class Review {
        +Long id
        +String comment
        +int rating
        +createReview()
    }
    class AcademicProgress {
        +Long id
        +String status
        +Double score
        +Date completionDate
        +updateProgress()
    }
    User "1" -- "*" Review : writes
    User "1" -- "*" AcademicProgress : tracks
    Challenge "1" -- "*" AcademicProgress : involves
```


*Diagrama inicial que contempla las entidades: Usuario, Reseña, Desafío y Progreso Académico.*

## 🚀 Instrucciones de Instalación y Ejecución

### 1. Clonar el repositorio
```bash
git clone https://github.com/MarioMunera1993/vulcano-api-grupo-1.git
```

### 2. Entrar al directorio
```bash
cd vulcano-api-grupo-1
```

### 3. Configurar base de datos

Configura el archivo `src/main/resources/application-dev.properties` con los siguientes datos:

**Opción PostgreSQL (Prisma Cloud):**
```properties
spring.datasource.url=jdbc:postgresql://db.prisma.io:5432/postgres?sslmode=require
spring.datasource.username=961bb5fffbad150fbf36b6fd78def9bfb9acdfdd978a31c4bbe2a16ccb555781
spring.datasource.password=sk_KdSlYnC95TUP4M9P3IV8n
spring.jpa.hibernate.ddl-auto=update
```

**Opción H2 (Pruebas locales):**
```properties
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver
spring.datasource.username=sa
spring.datasource.password=
spring.h2.console.enabled=true
spring.jpa.hibernate.ddl-auto=update
```

### 4. Ejecutar la aplicación

Desde la terminal:
```bash
./mvnw spring-boot:run
```

O desde su IDE ejecutando: **Run → VulcanoApiApplication**.

---

## 📄 Licencia

MIT License *(Recomendada para proyectos académicos).*