# Backend UTN – API REST en TypeScript

> API REST desarrollada en Node.js + Express + TypeScript + MongoDB, como parte del
> Trabajo Práctico: Desarrollo y Deploy de una API REST en TypeScript (UTN).

Este repositorio contiene solo **el backend** del proyecto.

---

## 👤 Datos del Autor

- **Nombre:** María Soledad Donnet  
- **Proyecto:** Backend UTN – API REST  
- **Rol:** Estudiante de Programación Web Full Stack  
- **GitHub:** https://github.com/MariaDonnet  
- - **LinkedIn:** [Maria Soledad Donnet](https://www.linkedin.com/in/maría-soledad-donnet/)

---

## 🎯 Objetivo del Proyecto 

Desarrollar una API REST funcional que permita:

- Registro y login de usuarios
- Autenticación y autorización con JWT
- Gestión de productos (CRUD)
- Filtrado mediante query params
- Uso de variables de entorno
- Deploy del backend en un servicio cloud (Render)

---

## 🛠️ Tecnologías Utilizadas

- **Node.js**
- **Express**
- **TypeScript**
- **MongoDB + Mongoose**
- **JWT (jsonwebtoken)** – Autenticación
- **bcryptjs** – Hash de contraseñas
- **Multer** – Subida de imágenes
- **Zod** – Validación de datos
- **Morgan** – Logger de requests
- **dotenv** – Variables de entorno

---

## 📁 Estructura del Proyecto

```bash
backend-utn/
├── dist/                # Código compilado (producción)
├── logs/                # Logs del servidor
├── uploads/             # Imágenes de productos
├── src/
│   ├── config/
│   ├── controllers/
│   ├── interfaces/
│   ├── middleware/
│   ├── model/
│   ├── routes/
│   ├── services/
│   ├── templates/
│   ├── validators/
│   └── index.ts
├── .env
├── .env.example
├── .gitignore
├── package-lock.json
├── package.json
├── products.json
├── tsconfig.json
└── README.md
```
---

## 🔐 Variables de Entorno

Crear un archivo `.env` a partir de `.env.example`:

```env
PORT=
JWT_SECRET=
URI_DB=
EMAIL_USER=
EMAIL_PASS=
```
Ejemplo:

```bash
# Puerto del servidor
PORT=3000

# Base de datos (MongoDB Atlas)
URI_DB=mongodb+srv://usuario:password@cluster.mongodb.net/mi-base-de-datos

# JWT
JWT_SECRET=super_clave_secreta

# Email (envío de correos)
EMAIL_USER=tu_correo@ejemplo.com
EMAIL_PASS=tu_password_o_app_password
```
⚠️ Nota: estos valores son solo de ejemplo.
El archivo .env no debe subirse al repositorio por motivos de seguridad.

---

## ▶️ Scripts Disponibles

 - Instalar dependencias:
```bash
npm install
```

- Ejecutar en desarrollo:
```bash
npm run dev
```
El servidor se levanta en (por ejemplo):

```text
http://localhost:3000
```

- Compilar Proyecto:
```bash
npm run build
```

- Ejecutar en produccion: 
```bash
npm start
```
---

## 🌐 Deploy

El backend se encuentra desplegado en **Render** y disponible públicamente.

URL base:

```text
https://backend-utn-u8mm.onrender.com
```
---

## 📌 Endpoints Principales
### 🔐 Autenticación

- POST /auth/register
Registra un nuevo usuario.

```json
{
  "email": "usuario@mail.com",
  "password": "password123"
}
```

- POST /auth/login
Inicia sesión.

```json
{
  "email": "usuario@mail.com",
  "password": "password123"
}
```
---

## 📦 Productos

- GET /products
Obtiene el listado de productos. 
Permite filtros mediante query params:

Ejemplos: 
- - name: filtra por nombre (búsqueda parcial)

```bash
{
GET /products?name=hamburguesa
}
```

- - category: filtra por categoría

```bash
{
GET /products?category=veg
}
```

- - minPrice:filtra por mínimo precio 

```bash
{
GET /products?minPrice=500
}
```

- - maxPrice: filtra por máximo precio

```bash
{
GET /products?maxPrice=2000
} 
```

- - stock:filtra por stock exacto

```bash
{
GET /products?category=hogar&minPrice=1000
}
```

- POST /products 🔒
Ruta protegida con JWT.
Permite crear un producto y subir una imagen (multipart/form-data).

- PATCH /products/:id 🔒
Actualizar un producto.

- DELETE /products/:id 🔒
Eliminar un producto.

---

## 🔒 Seguridad

Autenticación con JWT

Middleware de autorización

Rutas protegidas para crear, actualizar y eliminar

Rate limit aplicado en rutas de autenticación

---

## 📸 Subida de Archivos

Implementada con multer

Archivos almacenados en /uploads

Servidos de forma estática

---

## 🧪 Pruebas

Las rutas fueron probadas utilizando Bruno, verificando:

- Registro de usuarios

- Login y generación de JWT

- Acceso a rutas protegidas

- CRUD completo de productos

- Funcionamiento de filtros

- Manejo de errores y validaciones

Las imágenes se encuentran en `/docs/bruno-tests`. 

Las capturas se incluyen en el repositorio para facilitar la corrección.

---

## ✅ Cumplimiento de la Consigna

✔ API REST en TypeScript

✔ Arquitectura organizada

✔ MongoDB

✔ JWT

✔ Validaciones

✔ Query Params

✔ Subida de archivos

✔ Logger

✔ Deploy en Render

✔ Variables de entorno

---

## 🚀 Mejoras Futuras

Algunas funcionalidades fueron planificadas pero no implementadas en esta entrega:

- Implementación completa y estable de actualización de imágenes en productos.

- Envío real de correos electrónicos desde el formulario de contacto (usando Resend)

- Paginación de resultados en el endpoint de productos.

- Roles de usuario (admin / user).

- Tests automatizados.

Estas mejoras quedan como posibles extensiones del proyecto.

---

## 📝 Observaciones

Este backend fue desarrollado como parte del trabajo final integrador de la diplomatura full stack, aplicando los contenidos vistos durante la cursada.

