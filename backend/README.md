# Backend - E-commerce API

Backend API para la aplicación de e-commerce construida con Express.js y TypeScript.

## 🚀 Tecnologías

- **Express.js** - Framework web
- **TypeScript** - Tipado estático
- **Node.js** - Runtime
- **MySQL** - Base de datos (configurar posteriormente con Prisma/TypeORM)

## 📦 Instalación

Desde la raíz del proyecto:

```bash
npm install
```

O desde la carpeta backend:

```bash
cd backend
npm install
```

## 🛠️ Scripts Disponibles

- `npm run dev` - Inicia el servidor en modo desarrollo con hot-reload
- `npm run build` - Compila TypeScript a JavaScript
- `npm start` - Inicia el servidor en producción
- `npm run lint` - Ejecuta ESLint
- `npm run lint:fix` - Ejecuta ESLint y corrige errores automáticamente

## ⚙️ Configuración

1. Copia el archivo `.env.example` a `.env`:
   ```bash
   cp .env.example .env
   ```

2. Configura las variables de entorno en `.env`

## 🌐 Endpoints

### Health Check
```
GET /health
```
Verifica el estado del servidor

### Root
```
GET /
```
Información básica de la API

## 📁 Estructura del Proyecto

```
backend/
├── src/
│   ├── index.ts          # Punto de entrada
│   ├── routes/           # Rutas de la API (próximamente)
│   ├── controllers/      # Controladores (próximamente)
│   ├── models/           # Modelos de datos (próximamente)
│   ├── middlewares/      # Middlewares (próximamente)
│   ├── services/         # Lógica de negocio (próximamente)
│   ├── utils/            # Utilidades (próximamente)
│   └── config/           # Configuraciones (próximamente)
├── dist/                 # Código compilado
├── package.json
├── tsconfig.json
├── nodemon.json
└── .env.example
```

## 🔐 Variables de Entorno

Ver `.env.example` para la lista completa de variables requeridas.

## 📝 Notas

- El servidor por defecto corre en el puerto 5000
- Usa `nodemon` para hot-reload durante el desarrollo
- TypeScript está configurado con strict mode habilitado
