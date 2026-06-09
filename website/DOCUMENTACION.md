# 📚 DOCUMENTACIÓN DEL PROYECTO - Solid Template

## 📋 Tabla de Contenidos
1. [Descripción General](#descripción-general)
2. [Estructura del Proyecto](#estructura-del-proyecto)
3. [Tecnologías Utilizadas](#tecnologías-utilizadas)
4. [Componentes Principales](#componentes-principales)
5. [Arquitectura SCSS](#arquitectura-scss)
6. [Cómo Funciona Todo](#cómo-funciona-todo)
7. [Compilación y Construcción](#compilación-y-construcción)

---

## 🎯 Descripción General

**Solid Template** es una plantilla de desembarque (landing page) moderna y responsiva diseñada para startups. Está construida con HTML5 semántico, CSS/SCSS modular y está completamente libre de JavaScript, lo que la hace extremadamente ligera y eficiente.

### Características Principales:
- ✅ HTML5 semántico y accesible
- ✅ Diseño responsivo (mobile-first)
- ✅ Sin dependencias de JavaScript
- ✅ Arquitectura SCSS modular (SMACSS)
- ✅ Optimizado para SEO
- ✅ Compilación automática con npm
- ✅ 100% compatible con AWS EC2/VPC

---

## 📁 Estructura del Proyecto

```
website/
├── index.html                 # Página principal (landing page)
├── contacto.html              # Página de contacto
├── nosotros.html              # Página "Sobre Nosotros"
├── preguntas-frecuentes.html  # Página de FAQ
├── soporte.html               # Página de soporte
├── package-sample.json        # Configuración de NPM y scripts
├── README.md                  # Documentación en inglés
├── CHANGELOG.md               # Historial de cambios
├── LICENSE                    # Licencia (GPLv3)
│
├── src/
│   ├── images/               # Imágenes y assets (SVG)
│   ├── js/
│   │   └── main.js           # Archivo JS (vacío - deprecated)
│   └── scss/                 # Hojas de estilo (SCSS)
│       ├── style.scss        # Archivo principal (importa todos)
│       ├── _normalize.scss   # Normalizacion de estilos
│       │
│       ├── abstracts/        # Variables, funciones, mixins
│       │   ├── _variables.scss      # Colores, tipografía, tamaños
│       │   ├── _functions.scss      # Funciones SCSS reutilizables
│       │   ├── _mixins.scss         # Mixins reutilizables
│       │   └── _include-media.scss  # Media queries
│       │
│       ├── base/             # Estilos fundamentales
│       │   ├── _base.scss    # Estilos HTML básicos
│       │   ├── _typography.scss    # Tipografía (h1-h6, p, etc)
│       │   ├── _normalize.scss     # Normalización de navegadores
│       │   └── _helpers.scss       # Clases de utilidad
│       │
│       ├── components/       # Componentes reutilizables
│       │   ├── _buttons.scss       # Estilos de botones
│       │   └── _forms.scss         # Estilos de formularios
│       │
│       └── layout/           # Secciones del layout
│           ├── _main.scss         # Layout principal
│           ├── _header.scss       # Encabezado/Navegación
│           ├── _hero.scss         # Sección héroe
│           ├── _features.scss     # Sección de características
│           ├── _pricing.scss      # Sección de precios
│           ├── _cta.scss          # Call To Action
│           └── _footer.scss       # Pie de página
│
└── dist/
    ├── css/
    │   └── style.css         # CSS compilado (auto-generado)
    └── images/               # Imágenes optimizadas (auto-generadas)
```

---

## 🛠️ Tecnologías Utilizadas

### Frontend:
- **HTML5**: Marcado semántico y accesible
- **SCSS/SASS**: Preprocesador CSS modular
- **CSS3**: Flexbox, Grid, Gradientes, Transiciones
- **Google Fonts**: IBM Plex Sans (pesos 400 y 600)

### Herramientas de Construcción:
- **node-sass**: Compilación de SCSS a CSS
- **autoprefixer**: Añade prefijos de navegadores (-webkit-, -moz-)
- **browser-sync**: Servidor local y recarga automática
- **imagemin**: Optimización de imágenes
- **npm-run-all**: Ejecución de scripts en paralelo/secuencia
- **stylelint**: Validación y linting de SCSS

### Despliegue:
- **AWS EC2**: Servidor virtual
- **AWS VPC**: Red privada virtual
- **HTML Estático**: No requiere servidor backend

---

## 🎨 Componentes Principales

### 1. **index.html** - Página Principal
Contiene todas las secciones principales del sitio:

#### Estructura:
```
Header (Encabezado)
├── Logo
└── Navegación (oculta en mobile)

Hero (Portada)
├── Título Principal
├── Descripción
├── Botones CTA
└── Figuras Decorativas

Features (Características)
├── 6 Tarjetas de características
├── Iconos SVG
└── Descripciones

Pricing (Precios)
├── Plan único (€49/mes)
└── Lista de características

CTA (Llamada a Acción)
├── Pregunta provocativa
└── Botón de Contacto

Footer (Pie de Página)
├── Logo
├── Enlaces de navegación
├── Enlaces a redes sociales
└── Copyright
```

### 2. **contacto.html** - Página de Contacto
Formulario de contacto con campos:
- Nombre
- Email
- Teléfono
- Asunto
- Mensaje

### 3. **nosotros.html** - Sobre Nosotros
Información de la empresa:
- Descripción
- 6 características principales
- Estadísticas (clientes, proyectos, profesionales, años)

### 4. **preguntas-frecuentes.html** - FAQ
6 Preguntas frecuentes cubriendo:
- Precios
- Cambio de planes
- Período de prueba
- Tiempo de respuesta
- Cancelación
- Seguridad de datos

### 5. **soporte.html** - Soporte
Opciones de soporte:
- 6 opciones de soporte (docs, comunidad, webinars, etc)
- 3 planes de soporte (Basic, Professional, Enterprise)

---

## 🎨 Arquitectura SCSS

La arquitectura sigue el patrón **SMACSS** (Scalable and Modular Architecture for CSS):

### 1. **Abstracts** - (Sin salida CSS)
Configuraciones y herramientas reutilizables:
- `_variables.scss`: Colores, tipografía, tamaños
- `_functions.scss`: Funciones SCSS
- `_mixins.scss`: Mixins reutilizables
- `_include-media.scss`: Media queries

### 2. **Base** - (Estilos fundamentales)
Estilos para elementos HTML puros:
- `_normalize.scss`: Normalización cross-navegador
- `_base.scss`: Estilos HTML base (html, body, listas, etc)
- `_typography.scss`: Tipografía (h1-h6, p, a)
- `_helpers.scss`: Clases de utilidad (.container, .text-center, etc)

### 3. **Components** - (Componentes reutilizables)
Componentes específicos:
- `_buttons.scss`: .button, .button-primary, .button-sm
- `_forms.scss`: .input, .textarea

### 4. **Layout** - (Secciones del layout)
Secciones grandes del layout:
- `_main.scss`: Layout general y contenedores
- `_header.scss`: Encabezado y navegación
- `_hero.scss`: Sección héroe
- `_features.scss`: Grid de características (6 columnas)
- `_pricing.scss`: Sección de precios
- `_cta.scss`: Call to action
- `_footer.scss`: Pie de página

### Paleta de Colores:
```scss
// Colores de tipografía
$color-typography-1: #FFFFFF    // Blanco (títulos)
$color-typography-2: #B8C9D9    // Gris claro (texto)
$color-typography-3: #8E96A1    // Gris oscuro (muted)

// Colores de fondo
$color-bg-1: #0B1629            // Negro (principal)
$color-bg-2: #1A2332            // Gris oscuro
$color-bg-3: #2D3E52            // Gris medio
$color-bg-4: #3D4F63            // Gris claro

// Colores primarios (Azul)
$color-primary-1: #0270D7       // Azul principal
$color-primary-2: #004CC3       // Azul oscuro
$color-primary-3: #0256B0       // Azul intermedio
```

### Escala Tipográfica (Móvil a Desktop):
```
Tamaño 1 (Títulos):   16px → 32px
Tamaño 2:             14px → 28px
Tamaño 3:             13px → 24px
Tamaño 4:             12px → 20px
Tamaño 5 (Base):      13px → 16px
Tamaño 6:             12px → 14px
Tamaño 7:             11px → 13px
Tamaño 8 (Pequeño):   10px → 12px
```

---

## 🔄 Cómo Funciona Todo

### 1. **Flujo de Renderizado de Página**

```
Usuario accede a index.html
        ↓
Navegador carga HTML
        ↓
Descarga Google Fonts (IBM Plex Sans)
        ↓
Descarga dist/css/style.css (compilado)
        ↓
Renderiza página con estilos
        ↓
Página completamente visible
```

### 2. **Compilación de SCSS a CSS**

```
src/scss/
    ├── style.scss (importa todos)
    │   ├── abstracts/
    │   ├── base/
    │   ├── components/
    │   └── layout/
        ↓
   node-sass compila
        ↓
  dist/css/style.css (1 archivo)
        ↓
autoprefixer añade prefijos
        ↓
CSS listo para navegadores antiguos
```

### 3. **Responsive Design (Mobile-First)**

El sitio se construye primero para móvil y se mejora progresivamente:

```
320px (Mobile)
    ↓ @media (>small: 576px)
576px (Tablet Small)
    ↓ @media (>medium: 768px)
768px (Tablet)
    ↓ @media (>large: 1024px)
1024px+ (Desktop)
```

**Breakpoints clave:**
- `small`: 576px
- `medium`: 768px
- `large`: 1024px
- `xlarge`: 1200px+

### 4. **Flujo de Estilos para una Sección (Ejemplo: Features)**

```
1. HTML: <section class="features">
2. SCSS busca: src/scss/layout/_features.scss
3. Aplica variables: color(primary, 1), $container__width
4. Aplica mixins: @include font-size(), @include media()
5. Compila a CSS
6. Navegador renderiza con estilos finales
```

---

## 🏗️ Compilación y Construcción

### Instalación
```bash
npm install
```

### Scripts Disponibles

#### Desarrollo (Recomendado):
```bash
npm run watch
# Inicia:
# - Servidor local (browser-sync)
# - Vigilancia de SCSS
# - Vigilancia de imágenes
# - Recarga automática del navegador
```

#### Construcción
```bash
npm run build
# Ejecuta:
# - npm run build:css  (compila SCSS + autoprefixer)
# - npm run build:images (optimiza imágenes)
```

#### Compilar solo CSS:
```bash
npm run build:css
# Ejecuta:
# - Linting de SCSS
# - Compilación a CSS
# - Autoprefixer
```

#### Limpiar archivos compilados:
```bash
npm run clean
# Elimina dist/css/* y dist/images/*
```

#### Servir localmente:
```bash
npm run serve
# Abre servidor en http://localhost:3000
```

### Flujo de Trabajo Típico

1. **Editar SCSS**:
   ```bash
   # Editamos src/scss/layout/_features.scss
   ```

2. **Guardamos el archivo** (Ctrl+S)

3. **Compilación automática**:
   ```
   Onchange detecta cambio
        ↓
   Ejecuta: npm run build:css
        ↓
   SCSS compila a CSS
        ↓
   Autoprefixer añade prefijos
        ↓
   dist/css/style.css actualizado
   ```

4. **Navegador actualiza automáticamente** (browser-sync)

---

## 📄 Variables y Configuración

### Paleta de Colores (en _variables.scss)
```scss
$color: (
    typography: (1: #FFFFFF, 2: #B8C9D9, 3: #8E96A1),
    bg: (1: #0B1629, 2: #1A2332, 3: #2D3E52, 4: #3D4F63),
    primary: (1: #0270D7, 2: #004CC3, 3: #0256B0)
);
```

### Familias de Fuente
```scss
$font__family: (
    base: 'IBM Plex Sans',
    heading: 'IBM Plex Sans'
);
```

### Contenedor Max-Width
```scss
$container__width: 1200px;      // Ancho máximo normal
$container__width-sm: 640px;    // Ancho máximo pequeño
```

---

## 🎯 Casos de Uso Comunes

### Cambiar colores primarios
```scss
// src/scss/abstracts/_variables.scss
$color: (
    primary: (
        1: #FF6B6B,    // Rojo en lugar de azul
        2: #FF0000,
        3: #DD0000
    )
);
```

### Agregar nueva sección
```html
<!-- En index.html -->
<section class="mi-seccion">
    <div class="container">
        <h2>Nueva Sección</h2>
    </div>
</section>
```

```scss
// Crear src/scss/layout/_mi-seccion.scss
.mi-seccion {
    padding: 56px 16px;
    
    h2 {
        @include font-size(2, mobile, true, true, true);
    }
}
```

```scss
// Importar en src/scss/style.scss
@import './layout/mi-seccion';
```

### Cambiar tipografía responsiva
```scss
// _variables.scss
// Cambiar tamaño móvil a desktop para h1
$font__scale: (
    mobile: (1: (16px, 24px, 0.5px)),
    desktop: (1: (64px, 72px, 1px))  // Aumenta de 32px a 64px
);
```

---

## ✨ Característica Especiales

### 1. **Accesibilidad**
- HTML semántico (section, article, nav, etc)
- Atributos alt en imágenes
- Contraste de colores suficiente
- `.screen-reader-text` para lectores de pantalla

### 2. **Performance**
- CSS compilado a un solo archivo
- Sin JavaScript = carga más rápida
- Imágenes optimizadas con imagemin
- Minificación de CSS

### 3. **Flexibilidad**
- Arquitectura modular (SMACSS)
- Fácil de mantener y escalar
- Variables centralizadas
- Mixins reutilizables

### 4. **Compatibilidad**
- Cross-navegador (autoprefixer)
- Mobile-first responsive
- Compatible con navegadores antiguos (IE10+)

---

## 📱 Responsive Breakpoints

```scss
// Mobile (por defecto)
// 320px - 575px

// @include media( '>small' )
// 576px - 767px

// @include media( '>medium' )
// 768px - 1023px

// @include media( '>large' )
// 1024px+
```

---

## 🚀 Despliegue en AWS

1. **Generar archivos compilados**:
   ```bash
   npm run build
   ```

2. **Copiar a servidor EC2**:
   ```bash
   scp -r ./* usuario@servidor:/var/www/html/
   ```

3. **Configurar Nginx** (o Apache):
   ```nginx
   server {
       listen 80;
       server_name example.com;
       root /var/www/html;
       index index.html;
   }
   ```

4. **Servir contenido estático** (sin servidor backend)

---

## 📞 Soporte

Para consultas o problemas:
- 📧 Email: support@example.com
- 🌐 Web: https://example.com/soporte
- 💬 Chat: En vivo en el sitio

---

## 📄 Licencia

Este proyecto está bajo licencia GPLv3. Ver archivo LICENSE para más detalles.

---

**Última actualización**: 9 de junio de 2026
**Versión**: 1.0.0
