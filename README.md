# Perfumeria Lavanda

Lavanda es una aplicación web de perfumeres desarrollada con **Angular** en el frontend y **Spring Boot** con **MongoDB Atlas** en el backend. La plataforma permite visualizar productos por categoría o marca, realizar búsquedas, ver detalles de productos y realizar pagos a través de **Stripe**.

## 🚀 Funcionalidades principales

- Visualización de productos por categoría y marca.
- Sistema de autenticación y autorización con roles.
- Registro e inicio de sesión de usuarios.
- Subida y visualización de imágenes para productos.
- Carrito de compra e integración con pasarela de pago Stripe.
- Manejo robusto de errores y validaciones.
- Interfaz amigable y moderna (Angular + Bootstrap).

---

## 🛠️ Tecnologías utilizadas

### Backend
- **Java 17**
- **Spring Boot**
  - Spring Web
  - Spring Security
  - Spring Data MongoDB
- **MongoDB Atlas**
- **Stripe SDK**
- **Gradle** como herramienta de construcción

### Frontend
- **Angular**
- **Bootstrap**
- **TypeScript**
- **SweetAlert2** (alertas elegantes)
- **Angular Router** (navegación entre vistas)

---

## 📁 Estructura del Backend (Spring Boot)

| Carpeta / Archivo                   | Descripción                                                  |
|------------------------------------|--------------------------------------------------------------|
| `CRUD/controller`                  | Controladores REST (Producto, Usuario, etc.)                 |
| `CRUD/entity`                      | Entidades principales del sistema                            |
| `CRUD/repository`                  | Interfaces de acceso a MongoDB                               |
| `CRUD/service`                     | Lógica de negocio                                            |
| `CRUD/Stripe`                      | Controlador y servicio para integración con Stripe           |
| `security/config`                  | Configuración de seguridad con JWT                           |
| `security/entity`                  | Entidades relacionadas con la seguridad (Usuario, Roles)     |
| `security/jwt`                     | Utilidades JWT para autenticación                            |
| `security/service`                 | Servicios de autenticación y autorización                    |
| `Global/dto`                       | Estructura de respuesta estándar (`MessageDTO`)              |
| `Global/entity`                    | Clase base `EntityId` con ID autoincremental                |
| `Global/Exceptions`                | Manejadores globales de errores                              |
| `Global/utils`                     | Utilidades comunes (autoIncrement, limpieza de mensajes)     |
| `WebConfig`                        | Configuración CORS y recursos estáticos                      |
| `LavandaProyectoApplication.java` | Clase principal del backend                                  |

---

## 📁 Estructura del Frontend (Angular)

| Carpeta / Archivo                   | Descripción                                                  |
|------------------------------------|--------------------------------------------------------------|
| `src/app/components`               | Componentes reutilizables como cards, carrusel, etc.         |
| `src/app/pages/home`               | Página principal con carrusel y búsqueda por categoría       |
| `src/app/pages/productos`          | Página para mostrar lista de productos                       |
| `src/app/pages/detalle-producto`   | Página de detalle de un producto y productos relacionados    |
| `src/app/pages/auth`               | Componentes de login y registro                              |
| `src/app/services`                 | Servicios para consumir la API del backend                   |
| `src/app/guards`                   | Guards de autenticación (AuthGuard, AdminGuard, etc.)        |
| `src/app/models`                   | Interfaces y modelos (Producto, Usuario, etc.)               |
| `src/environments`                 | Configuración de entornos (API URL, Stripe Key, etc.)        |
| `src/assets`                       | Recursos estáticos como imágenes, íconos, etc.               |
| `app.module.ts`                    | Módulo raíz que declara y configura toda la app              |
| `app-routing.module.ts`           | Configuración de rutas de la aplicación                      |

---
## ⚙️ Instalación y configuración

### Requisitos
- JDK 17
- Node.js y Angular CLI
- MongoDB Atlas (o local si se desea)
- Stripe Account

### Backend
1. Clona el repositorio.
2. Configura las variables en `application.properties`:
    ```properties
    spring.data.mongodb.uri=mongodb+srv://<usuario>:<password>@<cluster>.mongodb.net/lavanda
    stripe.api.secret.key=sk_test_XXXXXXXXXXXXXXXX
    ```
3. Ejecuta el backend:
    ```bash
    ./gradlew bootRun
    ```

### Frontend
1. Ve a la carpeta del frontend Angular:
    ```bash
    cd lavanda-frontend
    ```
2. Instala las dependencias:
    ```bash
    npm install
    ```
3. Ejecuta la aplicación:
    ```bash
    ng serve
    ```

4. Abre tu navegador en [http://localhost:4200](http://localhost:4200)

---

## 🧪 Pruebas

- Las pruebas unitarias y de integración pueden realizarse usando `JUnit` y `Mockito` en el backend.
- El frontend puede probarse con `Cypress`.

---

## 📦 API REST (Resumen)

### Productos
| Método | Endpoint                     | Descripción                  |
|--------|------------------------------|------------------------------|
| GET    | `/api/productos`             | Obtener todos los productos |
| GET    | `/api/productos/categoria/{cat}` | Filtrar por categoría |
| GET    | `/api/productos/marca/{mar}` | Filtrar por marca |
| POST   | `/api/productos`             | Crear un nuevo producto      |
| PUT    | `/api/productos/{id}`        | Editar producto              |
| DELETE | `/api/productos/{id}`        | Eliminar producto            |

### Autenticación
| Método | Endpoint             | Descripción             |
|--------|----------------------|-------------------------|
| POST   | `/auth/login`        | Iniciar sesión          |
| POST   | `/auth/register`     | Registrar nuevo usuario |

### Pagos con Stripe
| Método | Endpoint                        | Descripción                |
|--------|----------------------------------|----------------------------|
| POST   | `/api/payment/create-checkout-session` | Crear sesión de pago  |

---

## 🛡️ Seguridad

- Los endpoints protegidos requieren token JWT.
- Roles diferenciados para acceso (por ejemplo: `ADMIN`, `USER`).
- Manejadores personalizados para errores de autorización/autenticación.

---

## 📸 Gestión de Imágenes

- Las imágenes de los productos se guardan en la carpeta `uploads/` del backend.
- Se acceden desde el frontend mediante rutas públicas definidas en `WebConfig`.

---

## 💬 Contacto

Para dudas o sugerencias, contacta con el desarrollador del proyecto.

---

## ✅ Estado del Proyecto

✔️ Funcionalidades principales completas  

---

## Licencia

Este proyecto se distribuye bajo licencia Creative Commons.
Hecho por Laura Garrido Arredondo

