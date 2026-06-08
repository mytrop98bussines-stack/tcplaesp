# 📋 DOCUMENTACIÓN COMPLETA DEL PROYECTO

## TCP "La Esperanza" – Segundo Frente
### Catálogo Digital con Integración WhatsApp

---

## 📑 ÍNDICE

1. [Resumen Ejecutivo](#1-resumen-ejecutivo)
2. [Características Principales](#2-características-principales)
3. [Guía de Uso – Vista del Cliente](#3-guía-de-uso--vista-del-cliente)
4. [Guía de Uso – Panel de Administración](#4-guía-de-uso--panel-de-administración)
5. [Arquitectura Técnica](#5-arquitectura-técnica)
6. [Seguridad](#6-seguridad)
7. [Personalización](#7-personalización)
8. [Preguntas Frecuentes](#8-preguntas-frecuentes)
9. [Soporte](#9-soporte)

---

## 1. RESUMEN EJECUTIVO

**TCP "La Esperanza"** es una aplicación web tipo catálogo digital diseñada para operar como tienda online a través de WhatsApp. Permite mostrar productos organizados por categorías, y cada pedido se envía directamente al WhatsApp del negocio con todos los detalles del producto seleccionado.

### ¿Qué problema resuelve?
- Elimina la necesidad de publicar productos manualmente en estados o grupos.
- Los clientes ven un catálogo profesional, ordenado y siempre actualizado.
- Cada pedido llega al WhatsApp del administrador con información completa y lista para gestionar.

### ¿Qué lo hace especial?
- **Cero servidores** – Funciona 100% en el navegador. No necesita hosting backend, bases de datos ni pagos mensuales de servidor.
- **Un solo archivo** – Toda la aplicación vive en un único archivo `index.html`.
- **Funciona sin internet constante** – Una vez cargada, los datos se guardan localmente en el navegador.
- **Diseño mobile-first** – Optimizado para verse perfecto en teléfonos móviles.

---

## 2. CARACTERÍSTICAS PRINCIPALES

### 🛍️ Para el Cliente (Tienda Pública)
| Función | Descripción |
|---------|-------------|
| Catálogo visual | Grid de productos con imagen, título, descripción y precio |
| 5 categorías | Electrodomésticos, Pasajes Internacionales, Productos Alimenticios, Remesas y "Todos" |
| Buscador | Busca por nombre, descripción o categoría en tiempo real |
| Filtros por categoría | Chips deslizables para filtrar rápidamente |
| Vista detallada | Modal a pantalla completa al tocar un producto |
| Pedido por WhatsApp | Botón verde en cada tarjeta que abre WhatsApp con el pedido completo |
| Consultar producto | Desde el modal, envía una pregunta específica por WhatsApp |
| Botón flotante WhatsApp | Acceso directo al WhatsApp del negocio siempre visible |
| Links de Canal/Grupo | Botones en el hero para unirse al canal o grupo de WhatsApp |
| Logo personalizable | Muestra el logo del negocio en navbar y hero |

### ⚙️ Para el Administrador (Panel Privado)
| Función | Descripción |
|---------|-------------|
| Login con contraseña | Acceso protegido con cifrado SHA-256 |
| Agregar productos | Formulario completo: título, descripción, precio, moneda, categoría, imagen |
| Editar productos | Modificar cualquier dato de un producto existente |
| Eliminar productos | Borrar productos con confirmación |
| Subir imágenes | Desde la galería del teléfono, se convierte a Base64 |
| Cambiar logo | Subir o quitar el logotipo del negocio |
| Configurar WhatsApp | Cambiar el número de teléfono para pedidos |
| Links de canal/grupo | Agregar enlaces de canal y grupo de WhatsApp |
| Nombre y descripción | Modificar el nombre y la descripción del negocio |
| Cambiar contraseña | Actualizar la contraseña del panel admin |

---

## 3. GUÍA DE USO – VISTA DEL CLIENTE

### 3.1 Navegación
Al abrir la página, el cliente ve:
- **Barra superior (navbar):** Logo del negocio, nombre y botón de búsqueda.
- **Sección hero:** Bienvenida con el nombre del negocio, descripción, botones de acción y estadísticas.
- **Filtros de categoría:** Chips horizontales deslizables.
- **Grid de productos:** Tarjetas con imagen, título, precio y botón de WhatsApp.

### 3.2 Buscar un Producto
1. Tocar el icono de lupa (🔍) en la barra superior.
2. Escribir el nombre o categoría del producto.
3. Los resultados se filtran en tiempo real.
4. Tocar de nuevo la lupa para cerrar la búsqueda.

### 3.3 Filtrar por Categoría
- Tocar uno de los chips: **Todos**, **Pasajes**, **Electrodomésticos**, **Alimentos** o **Remesas**.
- Los productos se filtran instantáneamente.

### 3.4 Ver Detalles de un Producto
- Tocar la imagen o el título de cualquier producto.
- Se abre un modal a pantalla completa con:
  - Imagen ampliada del producto
  - Título y precio destacado
  - Descripción completa
  - Categoría y disponibilidad
  - Botones de acción

### 3.5 Hacer un Pedido
**Opción rápida (desde la tarjeta):**
1. Tocar el botón verde de WhatsApp (📱) en la tarjeta del producto.
2. Se abre WhatsApp automáticamente con un mensaje que incluye:
   - Nombre del producto
   - Descripción
   - Categoría
   - Precio y moneda
   - Fecha y hora del pedido

**Opción desde el modal de detalles:**
1. Tocar "Ver más" en un producto.
2. Revisar los detalles completos.
3. Tocar **"Pedir por WhatsApp"** para hacer el pedido.
4. Tocar **"Consultar"** para hacer una pregunta sobre el producto.

### 3.6 Unirse al Canal o Grupo
- Si el administrador configuró los enlaces, aparecerán botones "Canal" y "Grupo" en la sección hero.
- Al tocarlos, se abre el enlace correspondiente de WhatsApp.

---

## 4. GUÍA DE USO – PANEL DE ADMINISTRACIÓN

### 4.1 Acceder al Panel
1. Tocar el botón **"Admin"** en la esquina inferior izquierda.
2. Ingresar la contraseña (por defecto: `admin123`).
3. Tocar **"Acceder"**.

> ⚠️ **IMPORTANTE:** Cambiar la contraseña por defecto en el primer acceso.

### 4.2 Pestañas del Panel
El panel tiene 3 pestañas:

#### 📦 Productos
- Lista todos los productos del catálogo.
- Cada producto muestra: imagen miniatura, título, categoría, precio.
- Botones de acción:
  - 🔵 **Editar** – Abre el formulario con los datos del producto.
  - 🔴 **Eliminar** – Borra el producto (pide confirmación).

#### ➕ Añadir
Formulario para crear un nuevo producto:

| Campo | Obligatorio | Descripción |
|-------|:-----------:|-------------|
| Título | ✅ | Nombre del producto |
| Descripción | ❌ | Texto descriptivo breve |
| Precio | ✅ | Valor numérico |
| Moneda | ✅ | Zelle, USD, CUP o MLC |
| Categoría | ✅ | Electrodomésticos, Pasajes, Alimentos, Remesas |
| Imagen | ❌ | Foto desde la galería (se usa imagen por defecto si se omite) |

**Pasos para agregar un producto:**
1. Ir a la pestaña **"➕ Añadir"**.
2. Llenar el título y el precio (mínimo obligatorio).
3. Seleccionar moneda y categoría.
4. Opcionalmente subir una foto tocando **"Subir foto"**.
5. Tocar **"Guardar Producto"**.
6. El producto aparece inmediatamente en la tienda.

**Para editar un producto:**
1. Ir a **"📦 Productos"**.
2. Tocar el botón azul de editar (✏️).
3. Modificar los campos deseados.
4. Tocar **"Actualizar"**.

#### ⚙️ Ajustes
Dividido en 4 secciones:

**🎨 Logotipo**
- Muestra el logo actual o la inicial del negocio.
- **"Subir"** – Seleccionar una imagen cuadrada (JPG/PNG).
- **"Quitar"** – Volver al logo SVG predeterminado.
- El logo se refleja instantáneamente en la navbar y el hero.

**📱 Información del Negocio**
- **Nombre:** Aparece en navbar, hero y mensajes de WhatsApp.
- **Descripción:** Texto mostrado debajo del título en el hero.
- **WhatsApp (pedidos):** Número de teléfono al que llegan todos los pedidos. Formato: código de país + número, sin espacios ni signos (ejemplo: `5350000000`).

**🔗 Enlaces WhatsApp**
- **Link del Canal:** URL del canal de WhatsApp (aparece como botón "Canal" en el hero).
- **Link del Grupo:** URL del grupo de WhatsApp (aparece como botón "Grupo" en el hero).
- Dejar vacío para ocultar los botones.

**🔐 Seguridad**
- Cambiar la contraseña del panel de administración.
- Mínimo 4 caracteres.
- Se almacena cifrada con SHA-256 (no se puede leer ni recuperar).

### 4.3 Volver a la Tienda
- Tocar **"← Tienda"** en la barra superior del panel admin.
- Los cambios se reflejan instantáneamente.

---

## 5. ARQUITECTURA TÉCNICA

### 5.1 Tecnologías Utilizadas

| Tecnología | Uso | Versión |
|------------|-----|---------|
| HTML5 | Estructura de la página | - |
| Tailwind CSS | Diseño visual y responsive | v4 (CDN) |
| JavaScript (Vanilla) | Lógica de la aplicación | ES2020+ |
| Web Crypto API | Cifrado SHA-256 de contraseñas | Nativa |
| FileReader API | Conversión de imágenes a Base64 | Nativa |
| localStorage | Persistencia de datos en el navegador | Nativa |
| Google Fonts | Tipografía Inter | - |

### 5.2 Estructura de Datos

**Producto (objeto):**
```json
{
  "id": "1717000000000",
  "title": "Congelador 5 Pies",
  "description": "Congelador horizontal...",
  "price": 280,
  "currency": "Zelle",
  "category": "Electrodomésticos",
  "image": "data:image/jpeg;base64,/9j/4AAQ..."
}
```

**Configuración (objeto):**
```json
{
  "phone": "5350000000",
  "name": "TCP La Esperanza",
  "desc": "Tu tienda de confianza...",
  "logo": "data:image/png;base64,...",
  "channel": "https://whatsapp.com/channel/...",
  "group": "https://chat.whatsapp.com/..."
}
```

### 5.3 Almacenamiento (localStorage)

| Clave | Contenido |
|-------|-----------|
| `tcp_prods` | Array de productos (JSON) |
| `tcp_set` | Configuración del negocio (JSON) |
| `tcp_ph` | Hash SHA-256 de la contraseña |

### 5.4 Categorías Disponibles

| Categoría | Emoji | Imagen por defecto |
|-----------|:-----:|-------------------|
| Electrodomésticos | 🔌 | Cocina/electrodomésticos |
| Pasajes Internacionales | ✈️ | Avión en aeropuerto |
| Productos Alimenticios | 🍎 | Aceite/productos |
| Remesas | 💸 | Dinero/transferencia |

### 5.5 Monedas Soportadas

| Moneda | Símbolo | Uso típico |
|--------|:-------:|------------|
| Zelle | $ | Pagos electrónicos USA |
| USD | $ | Dólar estadounidense |
| CUP | $ | Peso cubano |
| MLC | $ | Moneda libremente convertible |

---

## 6. SEGURIDAD

### 6.1 Cifrado de Contraseña
- La contraseña **nunca** se guarda en texto plano.
- Se utiliza el algoritmo **SHA-256** (estándar criptográfico) a través de la Web Crypto API del navegador.
- Al iniciar sesión, la contraseña ingresada se hashea y se compara con el hash almacenado.
- **No es posible recuperar la contraseña** desde el hash. Si se olvida, se debe limpiar el localStorage del navegador.

### 6.2 Almacenamiento Local
- Todos los datos se guardan en el **localStorage del navegador**.
- Son accesibles únicamente desde el dispositivo donde se configuró la tienda.
- No se envían datos a ningún servidor externo.
- Los datos persisten al cerrar y reabrir el navegador.

### 6.3 Imágenes
- Las imágenes se convierten a **Base64** y se almacenan directamente en localStorage.
- No se suben a ningún servidor.
- Límite de tamaño: **5MB por imagen**.
- Formatos aceptados: JPG, PNG, WebP.

### 6.4 Contraseña por Defecto
```
admin123
```
> ⚠️ Se recomienda cambiarla inmediatamente después del primer acceso en Ajustes → Seguridad.

---

## 7. PERSONALIZACIÓN

### 7.1 Identidad Visual
El diseño está basado en una paleta de colores verde esmeralda que transmite:
- 🟢 **Frescura** y naturaleza
- 🤝 **Confianza** y profesionalismo
- 🌿 **Ecología** (logotipo con manos y hojas)

### 7.2 Logotipo SVG Nativo
La aplicación incluye un logotipo SVG vectorial integrado directamente en el código con:
- Dos manos abiertas orientadas hacia arriba
- Hojas estilizadas creciendo desde el centro
- Círculos y burbujas flotantes
- Paleta de verdes (#22c55e, #4ade80, #86efac, #34d399)

Este logo se muestra por defecto si el administrador no sube uno personalizado.

### 7.3 Elementos Personalizables desde el Panel

| Elemento | Dónde se cambia | Dónde se refleja |
|----------|----------------|-----------------|
| Logo | Ajustes → Logotipo | Navbar + Hero |
| Nombre del negocio | Ajustes → Info | Navbar + Hero + Mensajes WhatsApp |
| Descripción | Ajustes → Info | Hero |
| Teléfono WhatsApp | Ajustes → Info | Todos los pedidos y consultas |
| Link del Canal | Ajustes → Enlaces | Botón "Canal" en hero |
| Link del Grupo | Ajustes → Enlaces | Botón "Grupo" en hero |
| Contraseña | Ajustes → Seguridad | Login del panel admin |
| Productos | Pestañas Productos/Añadir | Grid de la tienda |

---

## 8. PREGUNTAS FRECUENTES

### ¿Necesito un servidor o hosting?
**No para uso personal.** Puedes abrir el archivo `index.html` directamente en cualquier navegador. Si quieres que sea accesible por un link público, puedes subirlo gratis a servicios como GitHub Pages, Netlify o Vercel.

### ¿Los datos se pierden si cierro el navegador?
**No.** Todo se guarda en el localStorage del navegador y persiste al cerrarlo. Solo se pierden si:
- Limpias los datos del navegador manualmente.
- Usas el modo incógnito/privado.
- Cambias de navegador o dispositivo.

### ¿Puedo usarlo en varios dispositivos?
Cada dispositivo tiene su propia copia independiente de los datos. Si configuras la tienda en tu teléfono, esos datos no se sincronizan automáticamente con una tablet u otra computadora.

### ¿Cuántos productos puedo agregar?
No hay un límite fijo impuesto por la app. El límite práctico depende del almacenamiento del navegador (generalmente 5-10MB para localStorage). Se recomienda:
- Mantener las imágenes lo más pequeñas posible.
- No exceder los ~50-100 productos con imágenes Base64.
- Usar imágenes por defecto cuando sea posible.

### ¿Qué pasa si olvido la contraseña?
La contraseña se almacena como hash SHA-256 y no se puede recuperar. Para restablecerla:
1. Abrir las herramientas de desarrollador del navegador (F12).
2. Ir a la pestaña "Application" → "Local Storage".
3. Eliminar la clave `tcp_ph`.
4. Recargar la página. La contraseña volverá a ser `admin123`.

### ¿El comprador recibe una notificación del pedido?
No automáticamente. Cuando el cliente toca "Pedir por WhatsApp", se abre la app de WhatsApp con un mensaje prellenado. El cliente debe **enviar el mensaje** para que el administrador lo reciba.

### ¿Puedo cambiar los colores del diseño?
Sí, modificando las clases de Tailwind CSS y los valores en la sección `<style>` del archivo. Requiere conocimientos básicos de CSS.

### ¿Funciona sin internet?
- **Primera carga:** Necesita internet para descargar Tailwind CSS y Google Fonts.
- **Después:** Los datos del catálogo y la configuración funcionan sin internet, pero los pedidos por WhatsApp sí necesitan conexión.

---

## 9. SOPORTE

### Datos de Contacto del Desarrollador
Para soporte técnico, actualizaciones o nuevas funcionalidades, contactar al desarrollador.

### Formato de Mensaje de WhatsApp Generado
Cuando un cliente hace un pedido, el mensaje tiene este formato:

```
🛍️ *PEDIDO*
━━━━━━━━━━━━━━━

Hola, quiero pedir:

🔌 *Congelador 5 Pies*
📝 Congelador horizontal de 5 pies cúbicos. Bajo consumo.
📌 Electrodomésticos
💵 *$280 Zelle*

📅 15 de enero de 2026
⏰ 14:30

¿Está disponible?

_TCP "La Esperanza"_
```

### Requisitos del Sistema

| Requisito | Mínimo |
|-----------|--------|
| Navegador | Chrome 80+, Safari 14+, Firefox 78+, Edge 80+ |
| Conexión | Solo para carga inicial y envío de WhatsApp |
| Almacenamiento | ~5MB disponibles en localStorage |
| Pantalla | Cualquier tamaño (responsive) |

---

## 📄 LICENCIA Y ENTREGA

- **Tipo de entrega:** Archivo único `index.html`
- **Propiedad:** El comprador obtiene todos los derechos de uso del código.
- **Modificaciones:** Libre de modificar y adaptar según sus necesidades.
- **Dependencias externas:** Tailwind CSS (CDN gratuito), Google Fonts (gratuito).

---

*Documentación generada para TCP "La Esperanza" – Segundo Frente*
*Versión 1.0 – 2026*
