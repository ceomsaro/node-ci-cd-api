[![Node.js CI/CD with Docker](https://github.com/ceomsaro/node-ci-cd-api/actions/workflows/ci.yml/badge.svg)](https://github.com/ceomsaro/node-ci-cd-api/actions/workflows/ci.yml)


---



# Node CI/CD API

API simple en Node.js creada para demostrar **pipelines de CI/CD**, **contenedorización con Docker** y **buenas prácticas DevOps** usando GitHub Actions y Docker Hub.

El enfoque del proyecto está en la **automatización, reproducibilidad y entrega**, no en la complejidad de la aplicación.

---

## 🚀 Características

- API en Node.js usando Express
- Endpoint de health check
- Pruebas automatizadas con Jest y Supertest
- Aplicación dockerizada
- Pipeline de CI con GitHub Actions
- Pipeline de CD que publica imágenes en Docker Hub
- Versionado de imágenes Docker usando el hash del commit

---

## 🧱 Tecnologías usadas

- **Node.js 20**
- **Express**
- **Docker**
- **GitHub Actions**
- **Docker Hub**
- **Jest / Supertest**

---

## 📂 Estructura del proyecto

```

node-ci-cd-api/
├── src/
│   ├── app.js
│   └── index.js
├── tests/
│   └── health.test.js
├── .github/
│   └── workflows/
│       └── ci.yml
├── Dockerfile
├── .dockerignore
├── package.json
├── package-lock.json
└── README.md

```

---

## 🩺 Endpoints de la API

### Health Check

```

GET /health

````

**Respuesta**
```json
{
  "status": "ok"
}
````

Este endpoint se utiliza para:

* pruebas automatizadas
* validación en CI
* verificación del estado del contenedor

---

## 🐳 Ejecutar con Docker

### Construir la imagen

```bash
docker build -t node-ci-cd-api .
```

### Ejecutar el contenedor

```bash
docker run -p 3001:3000 node-ci-cd-api
```

Acceso:

```
http://localhost:3001/health
```

---

## 🔄 Pipeline CI/CD

El pipeline se ejecuta automáticamente en cada push a la rama `main`.

### CI (Integración Continua)

* Instalación de dependencias
* Ejecución de pruebas automatizadas
* Validación del Dockerfile mediante build

### CD (Entrega Continua)

* Construcción de la imagen Docker
* Etiquetado de la imagen con:

  * `latest`
  * hash del commit (ej. `a1b2c3d`)
* Publicación de la imagen en Docker Hub

Esto permite:

* builds reproducibles
* trazabilidad entre código e imagen
* rollback sencillo

---

## 🧠 Conceptos DevOps demostrados

* Integración Continua (CI)
* Entrega Continua (CD)
* Infraestructura como código
* Contenedorización
* Versionado de artefactos
* Pruebas automatizadas
* Consistencia entre entornos

---

## 📌 Propósito del proyecto

Este proyecto fue creado como **proyecto de portafolio DevOps**, con el objetivo de demostrar flujos reales de CI/CD utilizando una aplicación sencilla en Node.js.

---

## 📜 Licencia

MIT


