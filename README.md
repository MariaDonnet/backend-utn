API REST desarrollada en Node.js + Express + TypeScript + MongoDB, como parte del
Trabajo Práctico: Desarrollo y Deploy de una API REST en TypeScript (UTN).

Este repositorio contiene solo **el backend** del proyecto.

---

## 👤 Datos del Autor

- **Nombre:** María Soledad Donnet  
- **Proyecto:** Backend UTN – API REST  
- **Rol:** Estudiante de Programación Web Full Stack  
- **GitHub:** https://github.com/MariaDonnet  
- **Linkedin:**[Maria Soledad Donnet] (https://www.linkedin.com/in/maría-soledad-donnet/)

---

## 🎯 Objetivo del Proyecto 

Desarrollar una API REST funcional que permita:

- Registro y login de usuarios
- Autenticación y autorización con JWT
- Gestión de productos (CRUD)
- Filtrado mediante query params
- Subida de imágenes
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
Permite filtros mediante query params:

Ejemplos: 
name
category
minPrice
maxPrice
stock

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

- Registro

- Login

- Token JWT

- CRUD de productos

- Filtros

- Autorización

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

## 📝 Observaciones

Este backend fue desarrollado como parte del trabajo final integrador de la diplomatura, aplicando los contenidos vistos durante la cursada.

