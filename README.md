API REST desarrollada en Node.js + Express + TypeScript + MongoDB, como parte del
Trabajo Práctico: Desarrollo y Deploy de una API REST en TypeScript (UTN).

Este repositorio contiene **exclusivamente el backend** del proyecto.

---

## 👤 Datos del Autor

- **Nombre:** María Soledad Donnet  
- **Proyecto:** Backend UTN – API REST  
- **Rol:** Estudiante de Programación Web Full Stack  
- **GitHub:** https://github.com/MariaDonnet  

---

## 🎯 Objetivo del Proyecto 

Desarrollar una API REST funcional que permita:

- Registro y login de usuarios
- Autenticación y autorización con JWT
- Gestión de productos (CRUD)
- Filtrado mediante query params
- Subida de imágenes
- Uso de variables de entorno
- Deploy en un servicio cloud

---

## 🛠️ Tecnologías Utilizadas

- Node.js
- Express
- TypeScript
- MongoDB + Mongoose
- JWT (jsonwebtoken)
- bcryptjs
- multer
- zod
- morgan
- dotenv

---

## 📁 Estructura del Proyecto


---

## 🔐 Variables de Entorno

Crear un archivo `.env` a partir de `.env.example`:

```env
PORT=
JWT_SECRET=
URI_DB=
EMAIL_USER=
EMAIL_PASS=

▶️ Scripts Disponibles

Instalar dependencias:

npm install

Ejecutar en desarrollo:

npm run dev

Compilar Proyecto:

npm run build

Ejecutar en produccion: 

npm start

🌐 Deploy

El backend se encuentra desplegado en Render y disponible públicamente.

URL base:

https://backend-utn-u8mm.onrender.com

📌 Endpoints Principales
🔐 Autenticación

POST /auth/register

{
  "email": "usuario@mail.com",
  "password": "password123"
}

POST /auth/login

{
  "email": "usuario@mail.com",
  "password": "password123"
}

📦 Productos

GET /products
Permite filtros mediante query params:

name

category

minPrice

maxPrice

stock

POST /products 🔒
Ruta protegida con JWT.
Permite crear un producto y subir una imagen (multipart/form-data).

PATCH /products/:id 🔒
Actualizar producto.

DELETE /products/:id 🔒
Eliminar producto.

🔒 Seguridad

Autenticación con JWT

Middleware de autorización

Rutas protegidas para crear, actualizar y eliminar

Rate limit aplicado en rutas de autenticación

📸 Subida de Archivos

Implementada con multer

Archivos almacenados en /uploads

Servidos de forma estática

🧪 Pruebas

Las rutas fueron probadas utilizando Bruno / Postman, verificando:

Registro

Login

Token JWT

CRUD de productos

Filtros

Autorización

✅ Cumplimiento de la Consigna

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

📝 Observaciones

Este backend fue desarrollado como parte del trabajo final integrador de la diplomatura, aplicando los contenidos vistos durante la cursada.

