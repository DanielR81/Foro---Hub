# API REST con Spring Boot y Spring Security

## Descripción
Una API REST (Representational State Transfer) es un estilo de arquitectura que permite la comunicación entre aplicaciones a través de peticiones HTTP. Este proyecto es un ejemplo de una API REST desarrollada con Spring Boot y Spring Security, que simula un foro donde los usuarios deben autenticarse para registrar sus dudas.

---

## Características
- **JDK 17:** La aplicación utiliza la versión 17 del JDK.
- **Maven:** Herramienta de gestión de dependencias y construcción del proyecto.
- **IntelliJ IDEA:** IDE utilizado para el desarrollo.
- **MySQL:** Base de datos predeterminada. También es compatible con PostgreSQL (requiere configuración adicional).
- **Insomnia:** Utilizado para emular peticiones de cliente, ya que este proyecto no cuenta con frontend.
- **Dependencias:** Todas las dependencias necesarias están especificadas en el archivo `pom.xml`.

---

## Funcionamiento

### 1. Configuración Inicial
Antes de comenzar, conecta tu aplicación a un servidor de base de datos (MySQL o PostgreSQL). Una vez conectada, registra manualmente un usuario con un correo y una contraseña encriptada en la base de datos. Para encriptar la contraseña, puedes usar herramientas como [Browserling BCrypt](https://www.browserling.com/tools/bcrypt).

### 2. Ejemplo de Usuario
Crea un usuario en la base de datos con las siguientes características:
- **Correo:** `daniel@hotmail.com`
- **Contraseña cifrada:** Contraseña generada utilizando el algoritmo BCrypt.

### 3. Rutas Principales
Revisa los endpoints implementados en los controladores para conocer las funcionalidades disponibles. El endpoint principal es `/auth/login`, el cual devuelve un token JWT necesario para acceder a las demás funciones protegidas de la API.

### 4. Ejemplo de Autenticación
1. Abre Insomnia (o cualquier herramienta similar).
2. Realiza una petición `POST` al endpoint `http://localhost:8080/auth/login` con el siguiente JSON:

```json
{
  "login": "daniel@hotmail.com",
  "clave": "12345"
}
```

### 5. Obtención del Token
- Si las credenciales son válidas, el servidor devolverá un token JWT.
- Este token debe incluirse en las cabeceras de las peticiones subsiguientes como `Authorization: Bearer <token>`.

### 6. Probar las Demás Funciones
Con el token obtenido, podrás realizar pruebas en los demás endpoints protegidos de la API. Asegúrate de revisar la documentación o los controladores para conocer las rutas disponibles.

---

## Nota
Este proyecto es solo un ejemplo para aprender y probar conceptos básicos de autenticación y autorización con Spring Security. Puedes extenderlo para adaptarlo a tus necesidades o integrarlo con un frontend para una experiencia completa.

