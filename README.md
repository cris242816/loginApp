README - Proyecto de Login con Spring Boot y Google OAuth 2.0
📘 Descripción del Proyecto
Este proyecto es una aplicación web de inicio de sesión realizada con Spring Boot, Spring Security, Thymeleaf y autenticación mediante formulario clásico y Google OAuth 2.0. Al autenticar correctamente, el usuario es redirigido a una pantalla de éxito; si falla, a una pantalla de error. También cuenta con un botón para regresar al inicio desde ambas pantallas.
📦 Tecnologías Usadas
•	• Java 17+
•	• Spring Boot 3.x
•	• Spring Security
•	• Thymeleaf
•	• Google OAuth 2.0
•	• Gradle o Maven
•	• IntelliJ IDEA
📁 Estructura del Proyecto

src
├── main
│   ├── java
│   │   └── com.login.loginapp
│   │       ├── LoginAppApplication.java
│   │       ├── config
│   │       │   └── SecurityConfig.java
│   │       └── controller
│   │           └── LoginController.java
│   └── resources
│       ├── static
│       │   └── css
│       │       └── styles.css
│       ├── templates
│       │   ├── index.html
│       │   ├── success.html
│       │   └── error.html
│       └── application.yml

⚙️ Configuración
Agrega el siguiente bloque en tu archivo application.yml:

spring:
  security:
    oauth2:
      client:
        registration:
          google:
            client-id: 434684851588-o500kam6d1p9v7j0a4t247timomkr42u.apps.googleusercontent.com
            client-secret: TU_CLIENT_SECRET
            scope:
              - openid
              - profile
              - email
        provider:
          google:
            authorization-uri: https://accounts.google.com/o/oauth2/v2/auth
            token-uri: https://oauth2.googleapis.com/token
            user-info-uri: https://www.googleapis.com/oauth2/v3/userinfo
            user-name-attribute: sub

🔐 Importante: Asegúrate de registrar tu proyecto en Google Cloud Console y configurar el URI de redirección: http://localhost:8080/login/oauth2/code/google
💡 Funcionalidades
•	• Autenticación por nombre de usuario y contraseña (formulario clásico).
•	• Autenticación con Google OAuth 2.0.
•	• Redirección a pantalla de éxito o error.
•	• Botones para regresar al inicio desde pantallas de éxito y error.
•	• Interfaz simple y amigable con estilos CSS.
▶️ Cómo Ejecutar
1. Clona el repositorio: git clone https://github.com/tu-usuario/nombre-del-repo.git
2. Abre el proyecto en IntelliJ IDEA.
3. Asegúrate de tener Java 17 y Gradle/Maven configurado.
4. Ejecuta la clase LoginAppApplication.java.
5. Abre tu navegador en: http://localhost:8080
✍️ Autor
Cristhian Andrés Aguirre
Estudiante de desarrollo de software
Colombia
📃 Licencia
MIT License – libre uso con fines educativos y profesionales.
