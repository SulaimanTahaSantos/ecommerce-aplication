# Issues del Proyecto E-commerce

## 🏗️ FASE 1: Configuración Inicial del Proyecto

### Issue #1: Configurar estructura base del proyecto
**Prioridad:** Alta  
**Etiquetas:** setup, infrastructure

**Descripción:**
- Crear carpeta `frontend/` con Next.js + TypeScript
- Crear carpeta `backend/` con Express.js + TypeScript
- Configurar estructura de monorepo o workspaces
- Configurar ESLint y Prettier
- Crear `.gitignore` adecuado

**Criterios de aceptación:**
- [ ] Proyecto Next.js inicializado correctamente
- [ ] Proyecto Express inicializado correctamente
- [ ] Ambos proyectos con TypeScript configurado
- [ ] Scripts de desarrollo funcionando

---

### Issue #2: Configurar Tailwind CSS y Framer Motion
**Prioridad:** Alta  
**Etiquetas:** frontend, setup, styling

**Descripción:**
- Instalar y configurar Tailwind CSS
- Configurar tema personalizado (colores tipo PC Componentes)
- Instalar Framer Motion
- Crear archivo de configuración de animaciones reutilizables
- Configurar variables CSS para colores de marca

**Criterios de aceptación:**
- [ ] Tailwind CSS funcionando correctamente
- [ ] Tema personalizado configurado
- [ ] Framer Motion instalado
- [ ] Documento con paleta de colores definida

---

### Issue #3: Configurar Base de Datos MySQL
**Prioridad:** Alta  
**Etiquetas:** backend, database, setup

**Descripción:**
- Instalar y configurar Prisma o TypeORM
- Crear conexión a MySQL
- Configurar variables de entorno
- Crear script de inicialización de base de datos
- Configurar migraciones

**Criterios de aceptación:**
- [ ] Conexión a MySQL funcional
- [ ] ORM configurado correctamente
- [ ] Scripts de migración creados
- [ ] Variables de entorno documentadas

---

## 📊 FASE 2: Diseño de Base de Datos

### Issue #4: Diseñar y crear modelo de datos User
**Prioridad:** Alta  
**Etiquetas:** backend, database, model

**Descripción:**
Crear tabla/modelo de usuarios con:
- id, email, password (hasheada), nombre, apellidos
- dirección, teléfono, fecha registro
- rol (admin, user)
- Relaciones con pedidos y direcciones

**Criterios de aceptación:**
- [ ] Modelo User creado
- [ ] Migración ejecutada
- [ ] Relaciones definidas
- [ ] Índices apropiados en email

---

### Issue #5: Diseñar y crear modelos de Productos y Categorías
**Prioridad:** Alta  
**Etiquetas:** backend, database, model

**Descripción:**
Crear tablas/modelos:
- **Category:** id, nombre, slug, descripción, parent_id (subcategorías), imagen
- **Product:** id, nombre, descripción, precio, stock, sku, marca, imágenes[], categoría_id, especificaciones (JSON), activo, destacado
- Relaciones entre productos y categorías

**Criterios de aceptación:**
- [ ] Modelo Category con soporte para subcategorías
- [ ] Modelo Product con todos los campos
- [ ] Relaciones correctas
- [ ] Índices en campos de búsqueda

---

### Issue #6: Diseñar modelos de Carrito y Pedidos
**Prioridad:** Alta  
**Etiquetas:** backend, database, model

**Descripción:**
Crear tablas/modelos:
- **Cart:** id, user_id, session_id (para usuarios no logueados)
- **CartItem:** id, cart_id, product_id, cantidad
- **Order:** id, user_id, estado, total, dirección_envío, fecha_pedido, método_pago
- **OrderItem:** id, order_id, product_id, cantidad, precio_unitario

**Criterios de aceptación:**
- [ ] Modelo Cart y CartItem creados
- [ ] Modelo Order y OrderItem creados
- [ ] Estados de pedido definidos (pendiente, pagado, enviado, entregado)
- [ ] Relaciones correctas entre modelos

---

### Issue #7: Crear modelo de Direcciones y Métodos de Pago
**Prioridad:** Media  
**Etiquetas:** backend, database, model

**Descripción:**
- **Address:** id, user_id, nombre_completo, dirección, ciudad, código_postal, país, teléfono, predeterminada
- **PaymentMethod:** id, nombre, activo (Tarjeta, PayPal, Transferencia)

**Criterios de aceptación:**
- [ ] Modelo Address creado
- [ ] Modelo PaymentMethod creado
- [ ] Usuario puede tener múltiples direcciones

---

## 🔐 FASE 3: Autenticación y Autorización

### Issue #8: Implementar sistema de registro de usuarios
**Prioridad:** Alta  
**Etiquetas:** backend, auth, API

**Descripción:**
- Endpoint POST `/api/auth/register`
- Validación de datos con Zod
- Hash de contraseñas con bcrypt
- Validación de email único
- Respuesta con token JWT

**Criterios de aceptación:**
- [ ] Endpoint funcional
- [ ] Validación de datos correcta
- [ ] Contraseñas hasheadas
- [ ] Tests unitarios

---

### Issue #9: Implementar sistema de login
**Prioridad:** Alta  
**Etiquetas:** backend, auth, API

**Descripción:**
- Endpoint POST `/api/auth/login`
- Autenticación con email y password
- Generación de JWT token
- Refresh token
- Manejo de errores

**Criterios de aceptación:**
- [ ] Endpoint funcional
- [ ] JWT token generado correctamente
- [ ] Refresh token implementado
- [ ] Tests unitarios

---

### Issue #10: Configurar NextAuth.js en frontend
**Prioridad:** Alta  
**Etiquetas:** frontend, auth

**Descripción:**
- Instalar y configurar NextAuth.js
- Configurar provider credentials
- Crear páginas de login y registro
- Implementar protección de rutas
- Manejo de sesión en cliente

**Criterios de aceptación:**
- [ ] NextAuth configurado
- [ ] Páginas de login/registro funcionales
- [ ] Rutas protegidas
- [ ] Estado de sesión global

---

### Issue #11: Implementar middleware de autenticación
**Prioridad:** Alta  
**Etiquetas:** backend, auth, middleware

**Descripción:**
- Middleware para verificar JWT
- Middleware para roles (admin/user)
- Proteger rutas del backend
- Manejo de tokens expirados

**Criterios de aceptación:**
- [ ] Middleware de autenticación funcional
- [ ] Middleware de autorización por roles
- [ ] Rutas protegidas correctamente

---

## 🛍️ FASE 4: API de Productos

### Issue #12: Crear endpoints CRUD de Categorías
**Prioridad:** Alta  
**Etiquetas:** backend, API, products

**Descripción:**
- GET `/api/categories` - Listar todas (con subcategorías)
- GET `/api/categories/:slug` - Obtener una categoría
- POST `/api/categories` - Crear (admin)
- PUT `/api/categories/:id` - Actualizar (admin)
- DELETE `/api/categories/:id` - Eliminar (admin)

**Criterios de aceptación:**
- [ ] Todos los endpoints funcionando
- [ ] Validaciones implementadas
- [ ] Solo admin puede crear/editar/eliminar
- [ ] Tests de integración

---

### Issue #13: Crear endpoints CRUD de Productos
**Prioridad:** Alta  
**Etiquetas:** backend, API, products

**Descripción:**
- GET `/api/products` - Listar con paginación, filtros y ordenamiento
- GET `/api/products/:slug` - Obtener detalle
- POST `/api/products` - Crear (admin)
- PUT `/api/products/:id` - Actualizar (admin)
- DELETE `/api/products/:id` - Eliminar (admin)
- GET `/api/products/featured` - Productos destacados

**Criterios de aceptación:**
- [ ] Endpoints con paginación (limit, offset)
- [ ] Filtros: categoría, precio min/max, marca, disponibilidad
- [ ] Ordenamiento: precio, nombre, destacados, novedades
- [ ] Búsqueda por texto
- [ ] Tests de integración

---

### Issue #14: Implementar búsqueda de productos
**Prioridad:** Media  
**Etiquetas:** backend, API, search

**Descripción:**
- GET `/api/products/search?q=query`
- Búsqueda por nombre, descripción, marca
- Autocompletado
- Búsqueda con filtros combinados
- Optimización con índices FULLTEXT

**Criterios de aceptación:**
- [ ] Búsqueda funcionando correctamente
- [ ] Resultados relevantes
- [ ] Performance optimizada
- [ ] Tests de búsqueda

---

### Issue #15: Crear sistema de imágenes de productos
**Prioridad:** Media  
**Etiquetas:** backend, API, media

**Descripción:**
- Endpoint para subir imágenes
- Integración con Cloudinary o similar
- Múltiples imágenes por producto
- Optimización automática
- Generación de thumbnails

**Criterios de aceptación:**
- [ ] Upload de imágenes funcional
- [ ] Múltiples imágenes por producto
- [ ] Imágenes optimizadas
- [ ] URL de imágenes guardadas en BD

---

## 🛒 FASE 5: Carrito de Compras

### Issue #16: Crear API de gestión de carrito
**Prioridad:** Alta  
**Etiquetas:** backend, API, cart

**Descripción:**
- GET `/api/cart` - Obtener carrito del usuario
- POST `/api/cart/items` - Añadir producto
- PUT `/api/cart/items/:id` - Actualizar cantidad
- DELETE `/api/cart/items/:id` - Eliminar producto
- DELETE `/api/cart` - Vaciar carrito
- Gestión de stock en tiempo real

**Criterios de aceptación:**
- [ ] Todos los endpoints funcionando
- [ ] Validación de stock disponible
- [ ] Cálculo de totales correcto
- [ ] Tests de integración

---

### Issue #17: Implementar carrito en frontend con Zustand
**Prioridad:** Alta  
**Etiquetas:** frontend, state, cart

**Descripción:**
- Configurar Zustand para estado del carrito
- Persistencia en localStorage
- Sincronización con backend
- Contador de items en navbar
- Cálculo de totales en tiempo real

**Criterios de aceptación:**
- [ ] Estado global del carrito funcional
- [ ] Persistencia entre sesiones
- [ ] Sincronización con backend
- [ ] UI actualizada en tiempo real

---

### Issue #18: Crear página de carrito de compras
**Prioridad:** Alta  
**Etiquetas:** frontend, UI, cart

**Descripción:**
- Diseño de página de carrito
- Lista de productos con imagen, precio, cantidad
- Botones para aumentar/disminuir cantidad
- Eliminar productos
- Resumen de pedido con subtotal, envío, total
- Botón para proceder al checkout
- Animaciones con Framer Motion

**Criterios de aceptación:**
- [ ] Página responsive y atractiva
- [ ] Todas las funcionalidades del carrito
- [ ] Animaciones fluidas
- [ ] Validaciones de stock

---

## 💳 FASE 6: Proceso de Checkout

### Issue #19: Crear flujo de checkout - Dirección de envío
**Prioridad:** Alta  
**Etiquetas:** frontend, checkout

**Descripción:**
- Página para seleccionar/crear dirección de envío
- Formulario de nueva dirección
- Listado de direcciones guardadas
- Validación de campos
- Navegación al siguiente paso

**Criterios de aceptación:**
- [ ] Formulario de dirección funcional
- [ ] Validación completa
- [ ] Guardar dirección para futuras compras
- [ ] UI intuitiva

---

### Issue #20: Crear flujo de checkout - Método de pago
**Prioridad:** Alta  
**Etiquetas:** frontend, checkout

**Descripción:**
- Página de selección de método de pago
- Opciones: tarjeta, PayPal, transferencia
- Formulario de tarjeta (si aplica)
- Resumen del pedido
- Botón de confirmar pedido

**Criterios de aceptación:**
- [ ] Métodos de pago disponibles
- [ ] Formulario de tarjeta con validación
- [ ] Resumen completo del pedido
- [ ] Diseño seguro y profesional

---

### Issue #21: Implementar integración de pagos (Stripe)
**Prioridad:** Alta  
**Etiquetas:** backend, payments, API

**Descripción:**
- Instalar Stripe SDK
- Crear endpoint para crear Payment Intent
- Webhook para confirmación de pago
- Actualización de estado del pedido
- Manejo de errores de pago

**Criterios de aceptación:**
- [ ] Integración con Stripe funcional
- [ ] Pagos procesados correctamente
- [ ] Webhooks configurados
- [ ] Tests con datos de prueba

---

### Issue #22: Crear API de gestión de pedidos
**Prioridad:** Alta  
**Etiquetas:** backend, API, orders

**Descripción:**
- POST `/api/orders` - Crear pedido
- GET `/api/orders` - Listar pedidos del usuario
- GET `/api/orders/:id` - Detalle del pedido
- PUT `/api/orders/:id/status` - Actualizar estado (admin)
- Validación de stock al crear pedido
- Reducción de stock automática

**Criterios de aceptación:**
- [ ] Creación de pedidos funcional
- [ ] Validación de stock correcta
- [ ] Stock reducido al confirmar pedido
- [ ] Estados de pedido gestionados
- [ ] Tests de integración

---

## 📱 FASE 7: Páginas Principales del Frontend

### Issue #23: Crear página de inicio (Home)
**Prioridad:** Alta  
**Etiquetas:** frontend, UI

**Descripción:**
- Hero section con banner principal
- Carrusel de categorías destacadas
- Grid de productos destacados
- Sección de ofertas/promociones
- Newsletter signup
- Animaciones con Framer Motion
- Diseño responsive estilo PC Componentes

**Criterios de aceptación:**
- [ ] Diseño atractivo y moderno
- [ ] Totalmente responsive
- [ ] Animaciones fluidas
- [ ] Carga rápida de imágenes optimizadas
- [ ] SEO optimizado

---

### Issue #24: Crear página de listado de productos
**Prioridad:** Alta  
**Etiquetas:** frontend, UI, products

**Descripción:**
- Grid de productos con cards
- Sidebar con filtros (categoría, precio, marca, disponibilidad)
- Ordenamiento (precio, nombre, destacados)
- Paginación
- Breadcrumbs de navegación
- Contador de resultados
- Loading states

**Criterios de aceptación:**
- [ ] Filtros funcionales
- [ ] Ordenamiento funcional
- [ ] Paginación correcta
- [ ] Responsive design
- [ ] Loading states apropiados

---

### Issue #25: Crear componente ProductCard
**Prioridad:** Alta  
**Etiquetas:** frontend, component, products

**Descripción:**
- Card de producto reutilizable
- Imagen del producto
- Nombre, precio, valoración
- Badge de descuento/oferta
- Badge de disponibilidad
- Botón "Añadir al carrito"
- Hover effects con Framer Motion
- Quick view modal

**Criterios de aceptación:**
- [ ] Componente reutilizable
- [ ] Diseño atractivo
- [ ] Animaciones smooth
- [ ] Funcionalidad completa

---

### Issue #26: Crear página de detalle de producto
**Prioridad:** Alta  
**Etiquetas:** frontend, UI, products

**Descripción:**
- Galería de imágenes con zoom
- Información detallada del producto
- Precio y disponibilidad
- Selector de cantidad
- Botón "Añadir al carrito"
- Tabs: descripción, especificaciones, reseñas
- Productos relacionados
- Breadcrumbs
- Animaciones de transición

**Criterios de aceptación:**
- [ ] Galería de imágenes funcional
- [ ] Toda la información visible
- [ ] Tabs funcionando
- [ ] SEO optimizado
- [ ] Responsive

---

### Issue #27: Crear sistema de reseñas de productos
**Prioridad:** Media  
**Etiquetas:** fullstack, reviews

**Backend:**
- Modelo Review (user_id, product_id, rating, comentario, fecha)
- GET `/api/products/:id/reviews` - Listar reseñas
- POST `/api/products/:id/reviews` - Crear reseña (usuario autenticado)

**Frontend:**
- Mostrar reseñas en detalle de producto
- Formulario para nueva reseña
- Sistema de valoración con estrellas
- Promedio de valoraciones

**Criterios de aceptación:**
- [ ] API de reseñas funcional
- [ ] UI de reseñas completa
- [ ] Validación: un usuario una reseña por producto
- [ ] Cálculo de promedio correcto

---

### Issue #28: Crear página de perfil de usuario
**Prioridad:** Media  
**Etiquetas:** frontend, UI, user

**Descripción:**
- Información del usuario
- Editar datos personales
- Historial de pedidos
- Gestión de direcciones
- Cambio de contraseña
- Tabs para organizar secciones

**Criterios de aceptación:**
- [ ] Vista de perfil completa
- [ ] Edición de datos funcional
- [ ] Historial de pedidos visible
- [ ] Gestión de direcciones
- [ ] Validaciones correctas

---

### Issue #29: Crear página de historial de pedidos
**Prioridad:** Media  
**Etiquetas:** frontend, UI, orders

**Descripción:**
- Lista de todos los pedidos del usuario
- Card por pedido con: número, fecha, estado, total
- Vista de detalle del pedido
- Estado del envío con tracking
- Posibilidad de repetir pedido
- Filtros por estado

**Criterios de aceptación:**
- [ ] Lista completa de pedidos
- [ ] Detalle de cada pedido
- [ ] Estados visuales claros
- [ ] Responsive

---

## 🔍 FASE 8: Búsqueda y Filtros Avanzados

### Issue #30: Crear barra de búsqueda global con autocompletado
**Prioridad:** Alta  
**Etiquetas:** frontend, search

**Descripción:**
- Input de búsqueda en navbar
- Autocompletado mientras se escribe
- Sugerencias de productos y categorías
- Búsqueda por Enter o click
- Animaciones de apertura/cierre
- Debounce para optimizar peticiones

**Criterios de aceptación:**
- [ ] Autocompletado funcional
- [ ] Sugerencias relevantes
- [ ] Performance optimizada
- [ ] UI intuitiva

---

### Issue #31: Implementar filtros avanzados de productos
**Prioridad:** Media  
**Etiquetas:** frontend, backend, filters

**Backend:**
- Soporte para filtros combinados
- Rangos de precio dinámicos
- Filtro por especificaciones técnicas

**Frontend:**
- Sidebar de filtros colapsable
- Checkboxes para múltiples selecciones
- Range slider para precio
- Chips de filtros aplicados
- Botón limpiar filtros

**Criterios de aceptación:**
- [ ] Filtros combinados funcionando
- [ ] URL con parámetros de filtros (compartible)
- [ ] UI intuitiva y responsive
- [ ] Performance optimizada

---

## 👨‍💼 FASE 9: Panel de Administración

### Issue #32: Crear layout del panel de admin
**Prioridad:** Alta  
**Etiquetas:** frontend, admin, UI

**Descripción:**
- Ruta `/admin` protegida
- Sidebar con navegación
- Header con usuario admin
- Dashboard con estadísticas generales
- Responsive (tabla/móvil)

**Criterios de aceptación:**
- [ ] Layout completo y funcional
- [ ] Solo accesible por admin
- [ ] Navegación clara
- [ ] Responsive

---

### Issue #33: Crear dashboard de administración
**Prioridad:** Media  
**Etiquetas:** frontend, admin, analytics

**Descripción:**
- Resumen de ventas (día/semana/mes)
- Gráficas de ventas (Chart.js o Recharts)
- Pedidos recientes
- Productos más vendidos
- Estadísticas de usuarios
- Stock bajo/agotado

**Criterios de aceptación:**
- [ ] Dashboard informativo
- [ ] Gráficas funcionando
- [ ] Datos en tiempo real
- [ ] Diseño claro

---

### Issue #34: Crear panel de gestión de productos (Admin)
**Prioridad:** Alta  
**Etiquetas:** frontend, admin, products

**Descripción:**
- Tabla de productos con paginación
- Búsqueda y filtros
- Botones: crear, editar, eliminar
- Formulario de crear/editar producto
- Upload de múltiples imágenes
- Validaciones

**Criterios de aceptación:**
- [ ] CRUD completo funcional
- [ ] Tabla con datos correctos
- [ ] Formularios con validación
- [ ] Upload de imágenes funcional

---

### Issue #35: Crear panel de gestión de categorías (Admin)
**Prioridad:** Media  
**Etiquetas:** frontend, admin, categories

**Descripción:**
- Lista de categorías con jerarquía
- Crear/editar/eliminar categorías
- Soporte para subcategorías
- Drag & drop para reordenar (opcional)

**Criterios de aceptación:**
- [ ] CRUD de categorías funcional
- [ ] Jerarquía visual clara
- [ ] Validaciones correctas

---

### Issue #36: Crear panel de gestión de pedidos (Admin)
**Prioridad:** Alta  
**Etiquetas:** frontend, admin, orders

**Descripción:**
- Tabla de todos los pedidos
- Filtros por estado, fecha, cliente
- Vista detallada del pedido
- Cambiar estado del pedido
- Exportar pedidos a CSV/PDF
- Notificaciones al cambiar estado

**Criterios de aceptación:**
- [ ] Lista completa de pedidos
- [ ] Cambio de estado funcional
- [ ] Filtros y búsqueda
- [ ] Exportación funcional

---

### Issue #37: Crear panel de gestión de usuarios (Admin)
**Prioridad:** Baja  
**Etiquetas:** frontend, admin, users

**Descripción:**
- Lista de usuarios registrados
- Información: nombre, email, fecha registro, pedidos
- Buscar usuarios
- Cambiar rol (admin/user)
- Desactivar/activar usuario

**Criterios de aceptación:**
- [ ] Lista de usuarios completa
- [ ] Búsqueda funcional
- [ ] Gestión de roles
- [ ] Acciones sobre usuarios

---

## 📧 FASE 10: Notificaciones y Emails

### Issue #38: Configurar sistema de envío de emails
**Prioridad:** Media  
**Etiquetas:** backend, email

**Descripción:**
- Configurar nodemailer o servicio (SendGrid, Mailgun)
- Templates de emails HTML
- Email de bienvenida
- Email de confirmación de registro
- Email de confirmación de pedido
- Email de cambio de estado de pedido
- Email de recuperación de contraseña

**Criterios de aceptación:**
- [ ] Sistema de emails configurado
- [ ] Templates profesionales
- [ ] Emails enviados correctamente
- [ ] Tests con emails de prueba

---

### Issue #39: Implementar sistema de recuperación de contraseña
**Prioridad:** Media  
**Etiquetas:** fullstack, auth

**Backend:**
- POST `/api/auth/forgot-password` - Solicitar reset
- POST `/api/auth/reset-password` - Cambiar contraseña
- Tokens de reset con expiración

**Frontend:**
- Página "Olvidé mi contraseña"
- Página para establecer nueva contraseña
- Validaciones

**Criterios de aceptación:**
- [ ] Flujo completo funcional
- [ ] Email con link de reset enviado
- [ ] Token con expiración
- [ ] Nueva contraseña guardada

---

### Issue #40: Implementar notificaciones en tiempo real
**Prioridad:** Baja  
**Etiquetas:** fullstack, notifications

**Descripción:**
- Configurar Socket.io o SSE
- Notificar al admin de nuevos pedidos
- Notificar al usuario de cambios de estado
- Badge de notificaciones no leídas
- Panel de notificaciones

**Criterios de aceptación:**
- [ ] Sistema en tiempo real funcional
- [ ] Notificaciones recibidas correctamente
- [ ] UI de notificaciones
- [ ] Marcar como leídas

---

## 🎨 FASE 11: UX y Optimizaciones

### Issue #41: Implementar animaciones con Framer Motion
**Prioridad:** Media  
**Etiquetas:** frontend, animations

**Descripción:**
- Transiciones de página
- Animaciones de entrada en scroll
- Animaciones en hover de productos
- Animaciones de carrito (añadir producto)
- Loading skeletons
- Modal animations
- Micro-interacciones

**Criterios de aceptación:**
- [ ] Animaciones fluidas en toda la app
- [ ] No afecta performance
- [ ] Experiencia de usuario mejorada

---

### Issue #42: Optimizar imágenes y performance
**Prioridad:** Alta  
**Etiquetas:** frontend, performance

**Descripción:**
- Usar next/image para optimización automática
- Lazy loading de imágenes
- Placeholders de imágenes
- Código splitting
- Dynamic imports para componentes pesados
- Preload de recursos críticos

**Criterios de aceptación:**
- [ ] Lighthouse score > 90
- [ ] Imágenes optimizadas
- [ ] Lazy loading implementado
- [ ] Bundle size reducido

---

### Issue #43: Implementar SEO y metadatos
**Prioridad:** Alta  
**Etiquetas:** frontend, SEO

**Descripción:**
- Configurar metadata en todas las páginas
- Open Graph tags
- Twitter cards
- Sitemap.xml generado
- Robots.txt configurado
- Schema markup para productos
- URLs amigables

**Criterios de aceptación:**
- [ ] Metadata en todas las páginas
- [ ] Sitemap generado
- [ ] Schema markup implementado
- [ ] SEO audit aprobado

---

### Issue #44: Implementar modo responsive completo
**Prioridad:** Alta  
**Etiquetas:** frontend, responsive

**Descripción:**
- Revisar todas las páginas en móvil
- Menú hamburguesa en móvil
- Filtros en drawer/modal en móvil
- Tablas responsive
- Optimizar touch interactions
- Testing en diferentes dispositivos

**Criterios de aceptación:**
- [ ] Todas las páginas responsive
- [ ] UX optimizada para móvil
- [ ] Tests en múltiples resoluciones
- [ ] No horizontal scroll

---

### Issue #45: Implementar estados de loading y error
**Prioridad:** Media  
**Etiquetas:** frontend, UX

**Descripción:**
- Loading states en todas las peticiones
- Skeleton loaders
- Mensajes de error user-friendly
- Toast notifications para acciones
- Empty states cuando no hay datos
- Retry mechanisms

**Criterios de aceptación:**
- [ ] Loading states en toda la app
- [ ] Manejo de errores consistente
- [ ] Empty states diseñados
- [ ] UX fluida

---

## 🔒 FASE 12: Seguridad

### Issue #46: Implementar validaciones y sanitización
**Prioridad:** Alta  
**Etiquetas:** backend, security

**Descripción:**
- Validación de inputs con Zod en backend
- Sanitización de datos
- Protección contra XSS
- Protección contra SQL Injection (usando ORM)
- Rate limiting en endpoints críticos
- CORS configurado correctamente

**Criterios de aceptación:**
- [ ] Todas las rutas con validación
- [ ] Datos sanitizados
- [ ] Rate limiting implementado
- [ ] Tests de seguridad

---

### Issue #47: Implementar protección CSRF
**Prioridad:** Media  
**Etiquetas:** backend, security

**Descripción:**
- Tokens CSRF en formularios
- Validación de tokens en backend
- Configuración de cookies seguras
- SameSite cookies

**Criterios de aceptación:**
- [ ] CSRF protection implementada
- [ ] Cookies configuradas correctamente
- [ ] Tests de seguridad pasando

---

### Issue #48: Configurar HTTPS y variables de entorno
**Prioridad:** Alta  
**Etiquetas:** infrastructure, security

**Descripción:**
- Archivo .env.example documentado
- Validación de variables de entorno en startup
- Configurar HTTPS en producción
- Secrets management (API keys, JWT secret, etc.)
- Documentar variables requeridas

**Criterios de aceptación:**
- [ ] .env.example completo
- [ ] Validación de env vars
- [ ] Documentación clara
- [ ] Secrets no committeados

---

## 🧪 FASE 13: Testing

### Issue #49: Configurar testing framework
**Prioridad:** Media  
**Etiquetas:** testing, setup

**Descripción:**
- Configurar Jest + React Testing Library (frontend)
- Configurar Jest + Supertest (backend)
- Scripts de testing
- Coverage reports
- CI/CD hooks

**Criterios de aceptación:**
- [ ] Testing frameworks configurados
- [ ] Scripts funcionando
- [ ] Coverage reports generando

---

### Issue #50: Crear tests unitarios del backend
**Prioridad:** Media  
**Etiquetas:** backend, testing

**Descripción:**
- Tests de modelos
- Tests de controllers
- Tests de middlewares
- Tests de servicios
- Mocks de base de datos
- Coverage > 70%

**Criterios de aceptación:**
- [ ] Tests escritos para lógica crítica
- [ ] Mocks apropiados
- [ ] Coverage > 70%
- [ ] Todos los tests pasando

---

### Issue #51: Crear tests de integración de API
**Prioridad:** Media  
**Etiquetas:** backend, testing, integration

**Descripción:**
- Tests de endpoints de autenticación
- Tests de endpoints de productos
- Tests de endpoints de carrito
- Tests de endpoints de pedidos
- Tests de flujo completo de compra
- Base de datos de testing

**Criterios de aceptación:**
- [ ] Tests de integración completos
- [ ] DB de testing configurada
- [ ] Flujos críticos testeados
- [ ] Tests pasando

---

### Issue #52: Crear tests E2E con Playwright o Cypress
**Prioridad:** Baja  
**Etiquetas:** frontend, testing, e2e

**Descripción:**
- Configurar Playwright o Cypress
- Test: registro y login
- Test: búsqueda de productos
- Test: añadir al carrito
- Test: proceso de checkout completo
- Test: panel de admin

**Criterios de aceptación:**
- [ ] Framework E2E configurado
- [ ] Tests de flujos críticos
- [ ] Tests ejecutándose en CI

---

## 📦 FASE 14: Despliegue

### Issue #53: Configurar Docker para desarrollo
**Prioridad:** Media  
**Etiquetas:** devops, docker

**Descripción:**
- Dockerfile para frontend
- Dockerfile para backend
- docker-compose.yml con todos los servicios
- MySQL en container
- Variables de entorno para containers
- Documentación de comandos

**Criterios de aceptación:**
- [ ] Dockerfiles creados
- [ ] docker-compose funcional
- [ ] App levanta con un comando
- [ ] Documentación clara

---

### Issue #54: Preparar aplicación para producción
**Prioridad:** Alta  
**Etiquetas:** devops, production

**Descripción:**
- Build de producción optimizado
- Variables de entorno de producción
- Configurar PM2 o similar para backend
- Configurar logs
- Health check endpoints
- Error tracking (Sentry o similar)

**Criterios de aceptación:**
- [ ] Build de producción funcional
- [ ] Logs configurados
- [ ] Health checks implementados
- [ ] Error tracking activo

---

### Issue #55: Deploy de base de datos MySQL
**Prioridad:** Alta  
**Etiquetas:** devops, database

**Descripción:**
- Elegir hosting (AWS RDS, PlanetScale, etc.)
- Migrar schema
- Configurar backups automáticos
- Configurar conexión segura
- Scripts de migración

**Criterios de aceptación:**
- [ ] Base de datos en producción
- [ ] Backups configurados
- [ ] Conexión segura
- [ ] Documentación de acceso

---

### Issue #56: Deploy del backend
**Prioridad:** Alta  
**Etiquetas:** devops, backend

**Descripción:**
- Elegir hosting (Railway, Render, AWS, DigitalOcean, etc.)
- Configurar deploy automático
- Variables de entorno en producción
- Configurar dominio
- Monitoreo de servidor

**Criterios de aceptación:**
- [ ] Backend desplegado
- [ ] Deploy automático configurado
- [ ] Dominio configurado
- [ ] Monitoreo activo

---

### Issue #57: Deploy del frontend
**Prioridad:** Alta  
**Etiquetas:** devops, frontend

**Descripción:**
- Deploy en Vercel (recomendado para Next.js)
- Configurar variables de entorno
- Configurar dominio custom
- Configurar analytics
- CDN verificado

**Criterios de aceptación:**
- [ ] Frontend desplegado en Vercel
- [ ] Dominio configurado
- [ ] Analytics configurado
- [ ] Performance optimizado

---

### Issue #58: Configurar CI/CD Pipeline
**Prioridad:** Media  
**Etiquetas:** devops, CI/CD

**Descripción:**
- GitHub Actions o similar
- Pipeline de testing automático
- Deploy automático en merge a main
- Linting automático
- Build verification

**Criterios de aceptación:**
- [ ] Pipeline configurado
- [ ] Tests corriendo automáticamente
- [ ] Deploy automático funcional
- [ ] Notificaciones de fallos

---

## 📚 FASE 15: Documentación y Pulido Final

### Issue #59: Crear documentación técnica
**Prioridad:** Media  
**Etiquetas:** documentation

**Descripción:**
- README.md completo
- Documentación de API (Swagger/OpenAPI)
- Guía de instalación
- Guía de despliegue
- Arquitectura del proyecto
- Diagramas de base de datos
- Convenciones de código

**Criterios de aceptación:**
- [ ] README completo y claro
- [ ] API documentada
- [ ] Guías de instalación y deploy
- [ ] Diagramas visuales

---

### Issue #60: Crear datos de seed/demo
**Prioridad:** Baja  
**Etiquetas:** database, data

**Descripción:**
- Script de seed con datos de ejemplo
- Categorías de ejemplo
- Productos de ejemplo (mínimo 50)
- Usuarios de prueba
- Pedidos de ejemplo
- Imágenes de placeholder

**Criterios de aceptación:**
- [ ] Script de seed funcional
- [ ] Datos coherentes y realistas
- [ ] Documentado cómo ejecutar

---

### Issue #61: Auditoría de accesibilidad (a11y)
**Prioridad:** Media  
**Etiquetas:** frontend, accessibility

**Descripción:**
- Revisar contraste de colores
- Navegación por teclado
- Screen reader compatibility
- Alt text en imágenes
- ARIA labels donde corresponda
- Formularios accesibles
- Test con Lighthouse

**Criterios de aceptación:**
- [ ] Lighthouse accessibility > 90
- [ ] Navegación por teclado funcional
- [ ] Screen reader compatible
- [ ] WCAG 2.1 AA compliance

---

### Issue #62: Testing de compatibilidad cross-browser
**Prioridad:** Media  
**Etiquetas:** frontend, testing

**Descripción:**
- Testing en Chrome
- Testing en Firefox
- Testing en Safari
- Testing en Edge
- Testing en dispositivos móviles
- Polyfills si es necesario

**Criterios de aceptación:**
- [ ] Funcional en todos los navegadores modernos
- [ ] UI consistente
- [ ] Bugs críticos resueltos

---

### Issue #63: Optimización final de performance
**Prioridad:** Alta  
**Etiquetas:** frontend, backend, performance

**Descripción:**
- Auditoría de Lighthouse
- Optimizar consultas SQL
- Implementar caché donde corresponda
- Comprimir assets
- Lazy loading de componentes
- Reducir bundle size
- CDN para assets estáticos

**Criterios de aceptación:**
- [ ] Lighthouse score > 90 en todas las categorías
- [ ] Tiempos de respuesta < 200ms
- [ ] First Contentful Paint < 1.5s
- [ ] Bundle size optimizado

---

### Issue #64: Crear política de privacidad y términos de uso
**Prioridad:** Media  
**Etiquetas:** legal, content

**Descripción:**
- Página de política de privacidad
- Página de términos y condiciones
- Cookie consent banner
- GDPR compliance básico
- Aviso legal

**Criterios de aceptación:**
- [ ] Páginas legales creadas
- [ ] Cookie banner implementado
- [ ] Enlaces en footer

---

### Issue #65: Review final y testing de usuario
**Prioridad:** Alta  
**Etiquetas:** testing, QA

**Descripción:**
- Testing manual completo
- Revisar todos los flujos críticos
- Testing con usuarios reales
- Recopilar feedback
- Arreglar bugs encontrados
- Verificar responsive en dispositivos reales

**Criterios de aceptación:**
- [ ] Todos los flujos funcionando
- [ ] Bugs críticos resueltos
- [ ] Feedback de usuarios incorporado
- [ ] Lista para producción

---

## 🚀 RESUMEN DE PRIORIDADES

### 🔴 Prioridad Crítica (Para MVP):
1. Configuración inicial (#1-3)
2. Base de datos (#4-7)
3. Autenticación (#8-11)
4. API de productos (#12-15)
5. Carrito (#16-18)
6. Checkout básico (#19-22)
7. Páginas principales (#23-29)
8. Despliegue (#55-57)

### 🟡 Prioridad Alta (Post-MVP):
- Panel de administración (#32-36)
- SEO y performance (#42-43)
- Seguridad (#46-48)
- Búsqueda avanzada (#30-31)

### 🟢 Prioridad Media (Mejoras):
- Reseñas (#27)
- Emails (#38-39)
- Testing (#49-52)
- Documentación (#59)

### 🔵 Prioridad Baja (Nice to have):
- Notificaciones en tiempo real (#40)
- Tests E2E (#52)
- Gestión de usuarios admin (#37)
- Datos de seed (#60)

---

## 📊 ESTIMACIÓN TOTAL:
- **65 issues** en total
- **MVP:** ~25-30 issues (8-12 semanas para 1 desarrollador)
- **Versión completa:** ~45-50 issues (15-20 semanas para 1 desarrollador)
- **Pulido y extras:** Restantes issues (4-6 semanas)

## 🎯 ROADMAP SUGERIDO:

**Mes 1-2:** Issues #1-22 (Infraestructura + Backend + Checkout básico)  
**Mes 3:** Issues #23-31 (Frontend principal + Búsqueda)  
**Mes 4:** Issues #32-40 (Admin panel + Notificaciones)  
**Mes 5:** Issues #41-52 (Optimizaciones + Testing)  
**Mes 6:** Issues #53-65 (Deploy + Documentación + Pulido final)
