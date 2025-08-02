# 👗 Anahui – Tienda de Ropa "Old Money" Online

![Anahui Logo](./frontend/src/assets/Anahui.png)

**Anahui** es una tienda de ropa en línea especializada en el estilo **Old Money**, ofreciendo piezas atemporales con diseño clásico y elegancia moderna. Desarrollada con arquitectura modular y tecnología de vanguardia (Backend + Frontend + CRM), Anahui combina moda, tecnología y experiencia de usuario en un solo sistema.

> 🛍️ **Versión actual**: `v1.0.0`  
> ![Licencia](https://img.shields.io/badge/Licencia-MIT-green)

---

## 📝 Descripción General

**Anahui** es una plataforma que permite a usuarios comprar prendas de estilo clásico, elegante y sobrio, con una experiencia de navegación fluida y segura. Su sistema está dividido en tres módulos:

- 🧾 **Frontend**: Tienda pública para explorar catálogos, comprar y gestionar pedidos.
- 🔐 **Backend**: API REST con Spring Boot y JWT para gestionar productos, usuarios y transacciones.
- 📊 **CRM**: Panel administrativo para gestionar inventario, ventas y análisis de clientes.

---

## 🌟 Visión

**"Vestir bien es un arte; hacerlo con sobriedad es elegancia."**

**Anahui** ofrece:

- ✔️ Ropa de alta calidad con estética Old Money.
- ✔️ Imágenes detalladas, descripciones cuidadas y stock en tiempo real.
- ✔️ Gestión personalizada de pedidos, seguimiento y contacto postventa.

---

## 📐 Arquitectura del Sistema

### Diagrama de Componentes

![Arquitectura Anahui](./frontend/src/assets/Diagrama%20de%20Arquitectura.svg)

- **Frontend**: Aplicación React + Vite
- **Backend**: Spring Boot REST API
- **Base de datos**: MySQL (modular y escalable)
- **Seguridad**: JWT + Roles (`CLIENTE`, `ADMIN`)
- **Integraciones futuras**: Stripe, Cloudinary, Email

---

## 🛠️ Stack Tecnológico

### Backend
| Categoría       | Tecnología                          | Uso                                |
|-----------------|-------------------------------------|------------------------------------|
| Lenguaje        | Java 21                             | Lógica del negocio                 |
| Framework       | Spring Boot, Spring Security        | API REST, seguridad JWT            |
| Base de datos   | MySQL + JPA (Hibernate)             | Gestión de productos y pedidos     |
| Documentación   | Swagger / OpenAPI                   | Visualización de endpoints         |
| Build Tool      | Maven                               | Gestión de dependencias            |

### Frontend (Tienda)
| Categoría       | Tecnología                          | Uso                                |
|-----------------|-------------------------------------|------------------------------------|
| Core            | React 18 + Vite                     | Interfaz rápida y ligera           |
| Tipado          | TypeScript                          | Seguridad de tipos                 |
| Estilos         | Tailwind CSS                        | Diseño limpio, responsive          |
| Formularios     | React Hook Form + Zod               | Validación                         |
| Notificaciones  | Toastify, SweetAlert2               | Experiencia del usuario            |

### CRM Admin
| Categoría       | Tecnología                          | Uso                                |
|-----------------|-------------------------------------|------------------------------------|
| Core            | React + Vite                        | Panel administrativo               |
| Seguridad       | JWT + Context API                   | Rutas protegidas                   |
| Gráficas        | Recharts                            | Visualización de ventas            |
| Gestión         | Roles, productos, usuarios          | Control total del sistema          |

---

## 🎯 Funcionalidades Clave

### Para Clientes
- 🧥 **Catálogo filtrable**: Por categoría (hombre, mujer), tipo, precio y tallas.
- 👛 **Carrito de compras** con resumen y totales dinámicos.
- 📦 **Seguimiento de pedidos** y perfil de cliente.
- 🛡️ **Autenticación segura** con JWT.

### Para Administradores
- 📋 **Gestión de productos** (CRUD con imágenes y variantes).
- 👥 **Gestión de usuarios** y permisos.
- 📈 **Dashboard de ventas** con gráficas y KPIs.
- 🛍️ **Gestión de pedidos** y estados (nuevo, enviado, entregado).

---

## 🧱 Estructura del Proyecto

```

   anahui-wed/
    ├── backend/                     # API REST con Spring Boot
    │   ├── src/
    │   │   ├── main/
    │   │   │   ├── java/com/anahui/backend/
    │   │   │   │   ├── BackendApplication.java  # Clase principal de Spring Boot
    │   │   │   │   ├── config/          # Configuraciones (CORS, Swagger, JWT)
    │   │   │   │   ├── controller/      # Endpoints REST (Productos, Usuarios, Pedidos)
    |   |   |   |   |     ├──auth/          # Autenticación y autorización
    |   |   |   |   |     ├──product/       # Productos
    |   |   |   |   |     └──user/          # Usuarios
    │   │   │   │   ├── dto/             # Objetos de transferencia de datos
    │   │   │   │   ├── exception/       # Manejo global de errores
    │   │   │   │   ├── model/           # Entidades JPA (Producto, Usuario, Pedido)
    │   │   │   │   ├── repository/      # Repositorios JPA para acceso a datos
    │   │   │   │   ├── security/        # Configuración de JWT y filtros de seguridad
    │   │   │   │   └── service/         # Lógica de negocio
    │   │   │   │       └── impl/        # Implementaciones de servicios
    │   │   │   └── resources/
    │   │   │       ├── application.properties      # Configuración de la aplicación
    │   │   │       └── application-example.properties  # Ejemplo de configuración
    │   │   └── test/
    │   │       └── java/com/anahui/backend/  # Pruebas unitarias y de integración
    │   |── Dockerfile        # Dockerfile para el backend
    │   └── pom.xml                   # Dependencias y configuración de Maven
    ├── frontend/                     # Tienda pública con React + Vite
    │   ├── public/                   # Recursos estáticos (favicon, imágenes)
    │   ├── src/
    │   │   ├── assets/               # Imágenes, fuentes y otros recursos
    │   │   ├── components/           # Componentes reutilizables de React
    │   │   ├── pages/                # Páginas de la aplicación (Home, Producto, Carrito)
    │   │   ├── services/             # Llamadas a la API REST
    │   │   ├── context/              # Gestión de estado global con Context API
    │   │   ├── routes/               # Configuración de rutas con React Router
    │   │   ├── hooks/                # Hooks personalizados
    │   │   ├── tests/                # Pruebas unitarias con Jest
    │   │   ├── App.tsx               # Componente principal de la aplicación
    │   │   └── main.tsx              # Punto de entrada de React
    │   ├── Dockerfile                # Dockerfile para el frontend
    │   ├── .env.example              # Ejemplo de variables de entorno
    │   ├── tailwind.config.js        # Configuración de Tailwind CSS
    │   └── package.json              # Dependencias y scripts de npm
    ├── crm/                          # Panel administrativo con React + Vite
    │   ├── public/                   # Recursos estáticos (favicon, imágenes)
    │   ├── src/
    │   │   ├── components/           # Componentes del panel (Dashboard, Tablas)
    │   │   ├── pages/                # Páginas (Dashboard, Gestión de Productos)
    │   │   ├── services/             # Llamadas a la API REST
    │   │   ├── context/              # Gestión de estado y autenticación
    │   │   ├── routes/               # Rutas protegidas para administradores
    │   │   ├── hooks/                # Hooks personalizados
    │   │   ├── tests/                # Pruebas unitarias con Jest
    │   │   ├── App.tsx               # Componente principal del CRM
    │   │   └── main.tsx              # Punto de entrada de React
    │   ├── .env.example              # Ejemplo de variables de entorno
    │   ├── tailwind.config.js        # Configuración de Tailwind CSS
    │   └── package.json              # Dependencias y scripts de npm
    ├── docker/
    │   ├── backend.Dockerfile
    │   ├── frontend.Dockerfile
    │   ├── crm.Dockerfile
    │   └── docker-compose.yml
    ├── .gitignore                    # Archivos y carpetas ignorados por Git
    ├── CONTRIBUTING.md               # Guía para colaboradores
    ├── LICENSE                       # Licencia MIT
    └── README.md                     # Documentación principal del proyecto

````

---

## ⚙️ Instalación Rápida

1. **Backend**:
```bash
cd backend
mvn spring-boot:run
````

2. **Frontend**:

```bash
cd frontend
npm install
npm run dev
```

3. **CRM (Admin)**:

```bash
cd crm
npm install
npm run dev -- --port 5174
```

---

## 📸 Capturas de Pantalla

> *Próximamente*
> Se incluirán capturas de la tienda, detalle de producto, panel de administración, etc.

---

## 🧭 Roadmap

| Versión | Objetivo                        | Estado         |
| ------- | ------------------------------- | -------------- |
| `v1.0`  | Catálogo + carrito + pedidos    | ✅ Listo        |
| `v1.1`  | Pasarela de pago Stripe         | ⏳ En curso     |
| `v2.0`  | Wishlist + sistema de puntos    | ⏳              |
| `v3.0`  | Aplicación móvil (React Native) | 🧪 Planificada |

---

## 📄 Licencia

MIT License © 2025
**Cristhian Paul Calloquispe Cusi** – Fundador de Anahui
📧 [contacto@anahui.com](mailto:contacto@anahui.com)

---

## 🤍 Inspirado en la estética Old Money

> "La elegancia no grita, susurra."
> – Anahui, estilo sin tiempo.

