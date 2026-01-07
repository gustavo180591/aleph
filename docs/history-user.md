# 📘 Historia de Usuario – Plataforma Educativa ALEPH

## Nombre del sistema
**ALEPH**

Plataforma educativa orientada a **Matemática** y **Programación de Sistemas** para alumnos de **nivel secundario**, con acceso controlado por institución y validación por padrón de DNI.

---

## 👤 Usuario principal
**Alumno de nivel secundario**

---

## 👨‍🏫 Usuario administrador
**Profe Eber**  
Responsable de:
- Cargar instituciones educativas
- Cargar padrones de DNIs por institución
- Habilitar el acceso de los alumnos

---

## 🎯 Historia de Usuario (principal)

> **Como** alumno de nivel secundario  
> **quiero** acceder a la plataforma educativa **ALEPH**  
> **para** estudiar Matemática y Programación de Sistemas desde una plataforma moderna, clara y personalizada, siempre que pertenezca a una institución habilitada.

---

## 🏫 Instituciones educativas

### Regla institucional
- Cada **instituto donde trabaja el profe Eber** proporciona el **listado de DNIs de sus alumnos**.
- El profe Eber **carga manualmente** esos DNIs en el sistema.
- Solo los alumnos cuyo DNI esté **precargado** pueden registrarse.

---

## 🧭 Navegación principal (Navbar)

La plataforma cuenta con una **barra de navegación** con las siguientes secciones:

- **Home**
- **Quiénes somos**
- **Docentes**
- **Contacto**
- **Alumno**

### Perfil
- Si el alumno **no inició sesión**: se muestra opción para acceder.
- Si el alumno **inició sesión**: se muestra el **perfil del alumno** en la esquina superior derecha, con acceso a:
  - Mi perfil
  - Configuración
  - Cerrar sesión

---

## 🏠 Inicio de la aplicación (Splash)

Al iniciar la aplicación:
1. Se muestra el **logo de ALEPH**
2. Luego aparece el **nombre “ALEPH”**, inspirado en el comportamiento visual de aplicaciones educativas modernas
3. Se redirige automáticamente a la **Home** o a **Login**, según el estado de sesión

---

## 🏠 Home

La página **Home** muestra información general e introductoria sobre:

### 📐 Matemática
- Qué se trabaja
- Importancia de la matemática
- Relación con la lógica y la programación

### 💻 Programación de Sistemas
- Introducción a la programación
- Lenguajes y herramientas que se utilizan:
  - PHP
  - SQL
  - MySQL
  - HTML
  - Lenguaje C
  - PSeInt
  - otros contenidos introductorios

---

## 🎓 Sección Alumno

### Grilla de instituciones
- Al ingresar a **Alumno**, se muestra una **grilla de cards** con las instituciones educativas.
- Cada card contiene:
  - **Logo/Escudo** de la institución
  - **Nombre** de la institución
- Solo se muestran instituciones **activas**.

### Selección de institución
- Al hacer click en una card:
  - Se selecciona la institución
  - Se abre el **Login del alumno**
  - La institución queda **persistida como contexto**

---

## 🔐 Login del alumno

- El login está **siempre asociado a una institución**.
- El alumno puede iniciar sesión usando:
  - **DNI o Alias**
  - **Contraseña**

---

## 📝 Registro del alumno

Si el alumno **no está registrado**, desde el login puede acceder al **registro**.

### Campos del registro
- **Nombre**
- **Apellido**
- **DNI**
- **Usuario/Alias**  
  > Este alias será utilizado por la IA para dirigirse al alumno
- **Contraseña**

### Reglas del registro
- El **DNI debe existir previamente** en el padrón de la institución seleccionada.
- Si el DNI **no existe**, se bloquea el registro y se muestra el mensaje:

> **“Ese DNI no corresponde a esta institución.  
> Si creés que es un error, comunicate con el profe Eber.”**

- No se permite:
  - Registrar el mismo DNI dos veces en una institución
  - Repetir alias dentro de la misma institución

---

## ⚙️ Configuración del alumno

El alumno puede personalizar su experiencia:

### 🎨 Modo visual
- **Light mode**
- **Dark mode**
- Persistencia en `localStorage`

### 🔠 Tamaño de fuente
- El alumno puede aumentar o disminuir el tamaño de la fuente
- Se implementa con **CSS variables**
- Persistencia en `localStorage`

---

## 👨‍🏫 Panel del Profe Eber (Administrador)

### Alta de instituciones (manual)

Las instituciones se cargan **a mano desde el panel**, directamente en base de datos.

#### Campos de la institución
- **Nombre de la institución** (obligatorio)
- Provincia
- Ciudad
- Dirección
- Teléfono
- Email institucional
- Sitio web
- Estado (Activa / No activa)
- **Nivel educativo**: fijo a **Secundario**

#### Logo de la institución
- Se permite subir **solo imágenes**:
  - PNG
  - JPG / JPEG
  - WEBP
- Tamaño máximo: **2 MB**
- El archivo se guarda y se asocia a la institución

---

## 📋 Padrón de alumnos (DNIs)

- El profe Eber carga los DNIs **por institución**.
- La carga es:
  - Manual
  - Directa a base de datos
- El padrón es la **única fuente válida** para permitir el registro.

---

## 🔒 Seguridad y control

- Acceso controlado por:
  - Institución
  - DNI precargado
- No existen registros libres
- El alumno no puede cambiar de institución
- Los errores de padrón se resuelven **fuera del sistema**, con el profe Eber

---

## 💎 Valor del sistema

- Acceso educativo seguro y controlado
- Experiencia moderna para alumnos
- Gestión clara para el administrador
- Escalabilidad para sumar nuevas instituciones
- Base sólida para integrar IA educativa personalizada

---

## 🧱 Stack tecnológica definida

### Frontend
- **Astro 4+**
- **TailwindCSS**
- Dark/Light mode con `<html class>`
- Tamaño de fuente con CSS variables
- Persistencia en `localStorage`
- UI en Tailwind o shadcn/ui (React dentro de Astro)

### Backend
- **NestJS**
- **JWT (access + refresh opcional)**
- **Prisma ORM**
- **RBAC**: `ADMIN_EBER`, `ALUMNO`
- **class-validator**

### Base de datos
- **PostgreSQL**
- Tablas:
  - instituciones
  - padron_alumnos
  - alumnos
  - admin_users
  - auditoría_importaciones

---

## ✅ Estado
**Historia de usuario cerrada y lista para implementación.**
