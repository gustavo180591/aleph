
# 🚀 Plan de Implementación - Plataforma ALEPH

## 📋 Fase 1: Configuración Inicial (Semana 1)
- [x] Estructura del monorepo
  - [x] Configuración de pnpm workspace
  - [x] Estructura de carpetas básica
  - [x] Configuración de entornos (.env)
- [ ] Configuración base de datos
  - [ ] Docker Compose para PostgreSQL
  - [ ] Esquema inicial de Prisma
  - [ ] Migraciones iniciales

## 🏗️ Fase 2: Backend - NestJS (Semana 2-3)
- [ ] Módulo de Autenticación
  - [ ] Registro de alumnos con validación DNI
  - [ ] Login con JWT
  - [ ] Refresh tokens
- [ ] Módulo de Instituciones
  - [ ] CRUD de instituciones
  - [ ] Carga de padrones de DNI
  - [ ] Validación de alumnos por DNI
- [ ] Módulo de Alumnos
  - [ ] Perfil de alumno
  - [ ] Configuración de preferencias

## 🎨 Fase 3: Frontend - Astro (Semana 4-5)
- [ ] Layout base
  - [ ] Tema claro/oscuro
  - [ ] Barra de navegación
  - [ ] Footer
- [ ] Páginas principales
  - [ ] Home
  - [ ] Login/Registro
  - [ ] Dashboard alumno
- [ ] Componentes compartidos
  - [ ] Formularios
  - [ ] Tarjetas
  - [ ] Modales

## 🔄 Fase 4: Integración (Semana 6)
- [ ] Conexión frontend-backend
- [ ] Manejo de estados (Zustand/Context)
- [ ] Validación de formularios
- [ ] Manejo de errores

## 🧪 Fase 5: Testing (Semana 7)
- [ ] Pruebas unitarias
- [ ] Pruebas de integración
- [ ] Pruebas E2E

## 🚀 Despliegue (Semana 8)
- [ ] Configuración de producción
- [ ] CI/CD
- [ ] Monitoreo

## 📊 Estructura de Base de Datos
```prisma
model Institucion {
  id          Int      @id @default(autoincrement())
  nombre      String
  activa      Boolean  @default(true)
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt
  alumnos     Alumno[]
  padronDnis  String[]
  // otros campos según la historia de usuario
}

model Alumno {
  id           Int        @id @default(autoincrement())
  dni          String     @unique
  nombre       String
  apellido     String
  alias        String     @unique
  password     String
  institucion  Institucion @relation(fields: [institucionId], references: [id])
  institucionId Int
  // otros campos según la historia de usuario
}
