# 🎓 ALEPH - Plataforma Educativa

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![pnpm](https://img.shields.io/badge/pnpm-workspace-%234a90e2)](https://pnpm.io/workspaces)

Plataforma educativa orientada a **Matemática** y **Programación de Sistemas** para alumnos de **nivel secundario**, con acceso controlado por institución y validación mediante padrón de DNI.

---

## 🚀 Características Principales

- 🔐 **Acceso controlado** por institución educativa  
- 🪪 **Validación de alumnos** mediante padrón de DNI  
- 🎨 **Temas personalizables** (claro / oscuro)  
- 🔠 **Tamaño de fuente ajustable**  
- 📱 **Interfaz moderna, accesible y responsive**

---

## 🏗️ Estructura del Proyecto

```text
aleph/
├── apps/
│   ├── web/        # Frontend con Astro (alumnos + sitio público)
│   └── api/        # Backend con NestJS
├── packages/
│   └── database/  # Esquemas y migraciones Prisma
├── docker/
│   └── docker-compose.yml
├── docs/           # Documentación del proyecto
├── .env.example
├── pnpm-workspace.yaml
└── README.md
```

---

## 🛠️ Requisitos

- **Node.js** 18+
- **pnpm** 8+
- **Docker** (para base de datos)
- **PostgreSQL** 14+

---

## 🚀 Empezando

### 1️⃣ Clonar el repositorio

```bash
git clone [URL_DEL_REPOSITORIO]
cd aleph
```

---

### 2️⃣ Instalar dependencias

```bash
pnpm install
```

---

### 3️⃣ Configuración del entorno

Copiar el archivo de variables de entorno de ejemplo:

```bash
cp .env.example .env
```

Editar las variables según el entorno local.

---

### 4️⃣ Iniciar servicios

```bash
# Iniciar base de datos (Docker)
docker-compose up -d
```

```bash
# Iniciar backend (NestJS)
pnpm --filter api dev
```

```bash
# En otra terminal, iniciar frontend (Astro)
pnpm --filter web dev
```

---

## 🌐 Puertos

| Servicio              | Puerto |
|----------------------|--------|
| Frontend (Astro)     | 4321   |
| Backend (NestJS)     | 3001   |
| PostgreSQL (Docker)  | 5433   |

---

## 📄 Documentación

- 📘 **Historia de Usuario**
- 🗺️ **Plan de Implementación**
- 🔌 **Documentación de la API** *(próximamente)*

Toda la documentación se encuentra en la carpeta `/docs`.

---

## 🤝 Contribución

1. Hacé un **Fork** del proyecto  
2. Creá una rama:
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. Commit de tus cambios:
   ```bash
   git commit -m "Add AmazingFeature"
   ```
4. Push a la rama:
   ```bash
   git push origin feature/AmazingFeature
   ```
5. Abrí un **Pull Request**

---

## 📝 Licencia

Este proyecto está bajo la **Licencia MIT**.  
Ver el archivo `LICENSE` para más detalles.

---

## ✨ Agradecimientos

- [Astro](https://astro.build)
- [NestJS](https://nestjs.com)
- [Prisma](https://www.prisma.io)
- [Tailwind CSS](https://tailwindcss.com)

---