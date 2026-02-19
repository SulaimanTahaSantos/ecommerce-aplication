# 🛒 E-commerce Application

Aplicación de e-commerce full-stack construida con Next.js, TypeScript, Express.js y MySQL.

## 📁 Estructura del Proyecto

Este es un monorepo que contiene:

- **Frontend (Raíz):** Next.js + TypeScript + Tailwind CSS + Framer Motion
- **Backend:** Express.js + TypeScript + MySQL

```
aplicacion-ecommerce/
├── src/                    # Frontend Next.js
│   ├── app/               # App Router
│   └── ...
├── backend/               # Backend API
│   ├── src/
│   │   └── index.ts
│   ├── package.json
│   └── tsconfig.json
├── public/               # Assets estáticos
├── objetivos/           # Documentación del proyecto
├── package.json         # Configuración del workspace
└── README.md
```

## 🚀 Tecnologías

### Frontend
- **Next.js 16** - Framework React con App Router
- **TypeScript** - Tipado estático
- **Tailwind CSS** - Estilos utility-first
- **Framer Motion** - Animaciones (próximamente)

### Backend
- **Express.js** - Framework web Node.js
- **TypeScript** - Tipado estático
- **MySQL** - Base de datos relacional
- **Prisma/TypeORM** - ORM (próximamente)

## 📦 Instalación

1. Clona el repositorio:
```bash
git clone <repository-url>
cd aplicacion-ecommerce
```

2. Instala todas las dependencias (monorepo):
```bash
npm install
```

Esto instalará las dependencias tanto del frontend como del backend gracias a npm workspaces.

## 🛠️ Scripts Disponibles

### Frontend (Next.js)
```bash
npm run dev              # Inicia el servidor de desarrollo en http://localhost:3000
npm run build            # Crea el build de producción
npm run start            # Inicia el servidor de producción
npm run lint             # Ejecuta ESLint
```

### Backend (Express)
```bash
npm run dev:backend      # Inicia el servidor backend en http://localhost:5000
npm run build:backend    # Compila TypeScript del backend
npm run start:backend    # Inicia el servidor backend en producción
npm run lint:backend     # Ejecuta ESLint en el backend
```

### Ambos (Desarrollo Simultáneo)
```bash
npm run dev:all          # Inicia frontend y backend simultáneamente
npm run build:all        # Construye ambos proyectos
npm run lint:all         # Ejecuta ESLint en todo el monorepo
```

### Formateo de Código
```bash
npm run format           # Formatea todo el código con Prettier
npm run format:check     # Verifica el formato sin modificar archivos
```

## ⚙️ Configuración

### Frontend
El frontend ya está configurado y funcional. Puedes comenzar a editar:
- `src/app/page.tsx` - Página principal
- `src/app/layout.tsx` - Layout principal

### Backend
1. Navega a la carpeta backend:
```bash
cd backend
```

2. Copia el archivo de ejemplo de variables de entorno:
```bash
cp .env.example .env
```

3. Configura las variables de entorno en `.env`

Ver [backend/README.md](backend/README.md) para más detalles.

## 🎯 Roadmap

El proyecto está organizado en issues/fases. Ver [objetivos/issues.md](objetivos/issues.md) para:
- 65 issues organizados en 15 fases
- Prioridades (MVP, Post-MVP, Mejoras)
- Estimaciones de tiempo
- Criterios de aceptación

### Estado Actual: ✅ Issue #1 - Configuración Base
- [x] Proyecto Next.js + TypeScript configurado
- [x] Backend Express + TypeScript creado
- [x] Estructura de monorepo con npm workspaces
- [x] ESLint y Prettier configurados
- [x] .gitignore apropiado

### Próximos Pasos:
- **Issue #2:** Configurar Tailwind CSS (tema personalizado) y Framer Motion
- **Issue #3:** Configurar Base de Datos MySQL con Prisma/TypeORM
- **Issue #4-7:** Diseñar modelos de base de datos

## 📝 Comandos Útiles

```bash
# Instalar una dependencia en el frontend (raíz)
npm install <package>

# Instalar una dependencia en el backend
npm install <package> --workspace=backend

# Ejecutar un script específico del backend
npm run <script> --workspace=backend
```

## 🧪 Testing

(Por configurar en Issue #49-52)

## 🚀 Deployment

(Por configurar en Issue #53-58)

## 📚 Documentación

- [Objetivos del Proyecto](objetivos/issues.md)
- [Backend README](backend/README.md)

## 🤝 Contribución

Este es un proyecto de aprendizaje/desarrollo personal. Para contribuir:
1. Revisa los issues en [objetivos/issues.md](objetivos/issues.md)
2. Sigue las convenciones de código (ESLint + Prettier)
3. Asegúrate de que todos los tests pasen

## 📄 Licencia

[Especificar licencia]

## 👨‍💻 Autor

[Tu nombre/información]

---

**Nota:** Este proyecto está en desarrollo activo. Consulta [objetivos/issues.md](objetivos/issues.md) para ver el estado actual y próximos pasos.

