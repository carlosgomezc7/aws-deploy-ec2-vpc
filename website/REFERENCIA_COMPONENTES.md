/* ========================================================================
   REFERENCIA RÁPIDA - COMPONENTES Y FUNCIONALIDAD
   ========================================================================
   Guía de referencia rápida para entender qué hace cada componente
   del sitio web Solid Template
======================================================================== */

═══════════════════════════════════════════════════════════════════════════════
📄 ARCHIVOS HTML
═══════════════════════════════════════════════════════════════════════════════

index.html
──────────
Página principal (landing page) del sitio. Primera página que ven los usuarios.

Secciones principales:
  • Header: Encabezado con logo
  • Hero: Sección de bienvenida con título, descripción y botones
  • Features: 6 características principales con iconos
  • Pricing: Información de precios y planes
  • CTA: Llamada a acción final para contacto
  • Footer: Pie de página con enlaces y copyright

Función: Convertir visitantes en leads/clientes


contacto.html
─────────────
Página dedicada a formulario de contacto.

Campos del formulario:
  • Nombre (obligatorio)
  • Email (obligatorio)
  • Teléfono
  • Asunto
  • Mensaje

Función: Capturar información de contacto de interesados


nosotros.html
──────────────
Página de información de la empresa.

Contenido:
  • Descripción general de la empresa
  • 6 características/fortalezas
  • Estadísticas (clientes, proyectos, profesionales, años)

Función: Contar la historia de la empresa y generar confianza


preguntas-frecuentes.html
───────────────────────────
Página con respuestas a preguntas frecuentes (FAQ).

Temas cubiertos:
  • Precios y planes
  • Cambio de planes
  • Período de prueba
  • Tiempo de respuesta de soporte
  • Cancelación de servicios
  • Seguridad de datos

Función: Reducir dudas y eliminar objeciones


soporte.html
─────────────
Página de opciones de soporte y planes de asistencia.

Opciones de soporte:
  • Centro de documentación
  • Comunidad de usuarios
  • Webinars y tutoriales
  • Sistema de tickets
  • Chat en vivo
  • Base de conocimiento

Planes de soporte:
  • Basic: Gratuito, soporte por email
  • Professional: €49/mes, soporte prioritario
  • Enterprise: Personalizado, dedicado

Función: Ayudar a usuarios y mantener satisfacción


═══════════════════════════════════════════════════════════════════════════════
🎨 ESTRUCTURA SCSS (ESTILOS)
═══════════════════════════════════════════════════════════════════════════════

ABSTRACTS/ (Configuración - Sin salida CSS)
────────────────────────────────────────────

_variables.scss
  Contenido: Definiciones centralizadas
  Variables:
    • Colores (primario, tipografía, fondos)
    • Tipografía (familias, pesos)
    • Tamaños (contenedor, padding, márgenes)
    • Escalas responsivas
  Función: Punto único de verdad para valores reutilizables


_functions.scss
  Contenido: Funciones SCSS personalizadas
  Funciones:
    • get-font-size(): Obtener tamaño de fuente de escala
    • get-line-height(): Obtener alto de línea
    • get-kerning(): Obtener espaciado de letra
    • get-font-family(): Obtener familia de fuente
    • get-font-weight(): Obtener peso de fuente
    • get-content-padding(): Obtener padding responsivo
    • color(): Obtener color de la paleta
  Función: Reutilizar valores complejos de forma sencilla


_mixins.scss
  Contenido: Mixins reutilizables
  Mixins:
    • font-size(): Aplicar tamaño + alto de línea + kerning
    • font-family(): Aplicar familia de fuente
    • font-weight(): Aplicar peso de fuente
    • anchor-aspect(): Estilos para enlaces (main/header/footer)
    • shadow(): Sombra profunda
    • shadow-sm(): Sombra pequeña
    • divider(): Líneas divisorias (antes/después)
  Función: Reducir repetición de CSS


_include-media.scss
  Contenido: Sistema de media queries
  Función: Breakpoints responsivos predefinidos


BASE/ (Estilos Fundamentales)
─────────────────────────────

_base.scss
  Aplica a: Elementos HTML puros (html, body, ul, ol, dl, hr)
  Configura: Box-sizing, fondos, suavizado de fuentes
  Función: Estilos base para elementos HTML sin clases


_typography.scss
  Aplica a: Encabezados (h1-h6), párrafos, enlaces
  Configura: Tamaños responsivos, colores, pesos
  Función: Dar estilo a todo el texto del sitio


_helpers.scss
  Clases: .container, .container-sm, .screen-reader-text
  Clases: .text-left, .text-center, .text-right
  Clases: .text-primary, .list-reset
  Clases: .m-0, .mt-0, .mb-0, .pt-0, .pb-0, .pb-8, .pb-24, .pb-48
  Función: Utilidades reutilizables para espaciado y alineación


COMPONENTS/ (Componentes Reutilizables)
────────────────────────────────────────

_buttons.scss
  Clases: .button (genérico), .button-primary (destacado)
  Clases: .button-sm (pequeño)
  Estilos: Colores, padding, transiciones, hover
  Función: Dar consistencia a todos los botones del sitio


_forms.scss
  Clases: .input, .textarea
  Estilos: Bordes, colores, placeholders, estados
  Estados: Normal, hover, focus, disabled
  Función: Dar estilo a campos de formularios


LAYOUT/ (Secciones Grandes)
────────────────────────────

_main.scss
  Aplica a: Contenedores principales (.container, .section)
  Configura: Ancho máximo, centrado, padding responsivo
  Función: Estructura general del layout


_header.scss
  Aplica a: Navegación principal (.site-header, .site-header-inner)
  Configura: Padding, flex layout, fondos, enlaces
  Función: Encabezado y navegación del sitio


_hero.scss
  Aplica a: Sección héroe (.hero, .hero-copy, .hero-figure)
  Configura: Padding aumentado, gradiente de fondo, botones
  Función: Sección de bienvenida impactante


_features.scss
  Aplica a: Grid de características (.features, .feature)
  Configura: Layout flexbox 6 columnas, iconos 80-96px, efectos hover
  Función: Mostrar 6 características principales


_pricing.scss
  Aplica a: Tarjeta de precios (.pricing-table)
  Configura: Centrado, sombras, hover effects, border-radius
  Función: Mostrar información de precios


_cta.scss
  Aplica a: Sección de llamada a acción (.cta, .cta-inner)
  Configura: Fondo oscuro, sombras profundas, efectos hover
  Función: Incentivar conversión final


_footer.scss
  Aplica a: Pie de página (.site-footer, .footer-links)
  Configura: Tipografía pequeña, links, disposición flex
  Función: Información legal y enlaces secundarios


═══════════════════════════════════════════════════════════════════════════════
🎯 FLUJO DE USUARIO
═══════════════════════════════════════════════════════════════════════════════

Visitante nuevo
    ↓
Llega a index.html
    ↓
Ve Hero section (atractiva)
    ↓
Lee Features (ventajas)
    ↓
Mira Pricing (costo)
    ↓
Tiene dudas → Va a preguntas-frecuentes.html
    ↓
Quiere saber más → Va a nosotros.html
    ↓
Necesita soporte → Va a soporte.html
    ↓
Listo para actuar → Va a contacto.html (formulario)
    ↓
Envía información de contacto


═══════════════════════════════════════════════════════════════════════════════
📱 RESPONSIVIDAD
═══════════════════════════════════════════════════════════════════════════════

Móvil (320px-575px)
  • Ancho completo
  • Una columna para características (stack vertical)
  • Fuentes más pequeñas
  • Padding reducido
  • Botones grandes y fáciles de tocar

Tablet (576px-1023px)
  • Ancho adaptable
  • 2-3 columnas para características
  • Fuentes medianas
  • Padding normal
  • Layout optimizado

Desktop (1024px+)
  • Ancho máximo 1200px
  • 6 columnas para características
  • Fuentes grandes
  • Padding amplio
  • Layout completo con márgenes


═══════════════════════════════════════════════════════════════════════════════
🎨 PALETA DE COLORES
═══════════════════════════════════════════════════════════════════════════════

Primary (Azul)
  #0270D7  ← Color principal (botones, enlaces)
  #004CC3  ← Azul oscuro (hover)
  #0256B0  ← Azul intermedio

Background (Oscuro)
  #0B1629  ← Negro (fondo principal)
  #1A2332  ← Gris oscuro
  #2D3E52  ← Gris medio
  #3D4F63  ← Gris claro

Typography (Texto)
  #FFFFFF  ← Blanco (títulos)
  #B8C9D9  ← Gris claro (texto)
  #8E96A1  ← Gris oscuro (muted)


═══════════════════════════════════════════════════════════════════════════════
🔤 TIPOGRAFÍA
═══════════════════════════════════════════════════════════════════════════════

Familia: IBM Plex Sans
Pesos:
  400 (normal) ← Para texto regular
  600 (bold)   ← Para títulos y énfasis

Escala (Móvil → Desktop):
  h1: 16px → 32px (Títulos principales)
  h2: 14px → 28px (Subtítulos)
  h3: 13px → 24px (Encabezados de sección)
  h4: 12px → 20px (Encabezados menores)
  p:  13px → 16px (Párrafos)
  small: 10px → 12px (Texto pequeño)


═══════════════════════════════════════════════════════════════════════════════
📊 CARACTERÍSTICAS IMPLEMENTADAS
═══════════════════════════════════════════════════════════════════════════════

✅ HTML Semántico
  • <section>, <article>, <nav>, <header>, <footer>
  • <h1>, <h2>, <h3> en orden jerárquico
  • <img> con atributos alt descriptivos

✅ Accesibilidad
  • Colores con contraste suficiente
  • .screen-reader-text para lectores de pantalla
  • Atributos ARIA cuando es necesario

✅ Performance
  • Archivo CSS único compilado
  • Sin JavaScript (carga instantánea)
  • Imágenes optimizadas
  • Fuentes de Google (CDN rápido)

✅ SEO-Friendly
  • Meta tags (charset, viewport)
  • Estructura semántica
  • Títulos descriptivos
  • URLs amigables

✅ Responsive
  • Mobile-first
  • Media queries múltiples
  • Flexbox moderno
  • Imágenes adaptables

✅ Mantenibilidad
  • Arquitectura modular (SMACSS)
  • Comentarios exhaustivos en español
  • Variables centralizadas
  • Fácil de escalar


═══════════════════════════════════════════════════════════════════════════════
🚀 OPTIMIZACIONES
═══════════════════════════════════════════════════════════════════════════════

CSS Minificado
  • Reducción ~70% de tamaño
  • Descarga más rápida

Autoprefixer
  • -webkit- para Chrome/Safari
  • -moz- para Firefox
  • Compatible con navegadores antiguos

Image Optimization
  • Compresión de PNG/JPG
  • Conversión a formatos modernos
  • Reducción de tamaño

Lazy Loading (Futuro)
  • Cargar imágenes bajo demanda
  • Mejorar performance

CDN
  • Google Fonts vía CDN
  • Descarga rápida en todo mundo


═══════════════════════════════════════════════════════════════════════════════
📋 CHECKLIST DE MANTENIMIENTO
═══════════════════════════════════════════════════════════════════════════════

Antes de deploying:
  ☐ npm run build (compilar todo)
  ☐ Verificar dist/css/style.css existe
  ☐ Verificar dist/images/ tiene imágenes
  ☐ Revisar en navegador (Chrome, Firefox, Safari, Edge)
  ☐ Revisar en mobile (iPhone, Android)
  ☐ Verificar enlaces internos funcionan
  ☐ Revisar formularios
  ☐ Comprobar speeds de página (PageSpeed Insights)

Mensualmente:
  ☐ Revisar analytics
  ☐ Verificar enlaces externos
  ☐ Revisar typos y ortografía
  ☐ Actualizar información de contacto si cambió

Trimestralmente:
  ☐ Actualizar dependencias (npm update)
  ☐ Revisar seguridad (npm audit)
  ☐ Optimizar imágenes nuevas
  ☐ Revisar performance


═══════════════════════════════════════════════════════════════════════════════
💡 TIPS Y TRUCOS
═══════════════════════════════════════════════════════════════════════════════

Cambiar colores rápidamente:
  1. Editar src/scss/abstracts/_variables.scss
  2. Cambiar valores en $color map
  3. Guardar archivo
  4. npm run build:css compila automáticamente

Agregar clase de utilidad:
  1. Editar src/scss/base/_helpers.scss
  2. Agregar nuevo selector y estilos
  3. Usar en HTML: class="mi-clase"

Cambiar tipografía:
  1. Editar src/scss/abstracts/_variables.scss
  2. Cambiar $font__family o tamaños en $font__scale
  3. Guardar y compilar

Hacer sitio responsive:
  ✓ Usar @include media( '>medium' ) para cambios
  ✓ Mobile-first (estilos base son mobile)
  ✓ Desktop mejora (más padding, fuentes grandes)


═══════════════════════════════════════════════════════════════════════════════
🆘 TROUBLESHOOTING
═══════════════════════════════════════════════════════════════════════════════

Los estilos no se aplican:
  1. Verificar que npm run build:css ejecutó sin errores
  2. Vaciar caché del navegador (Ctrl+Shift+Delete)
  3. Verificar que dist/css/style.css existe
  4. Verificar el HTML incluye <link rel="stylesheet" href="dist/css/style.css">

Las imágenes no se muestran:
  1. Verificar que src/images/ tiene los archivos
  2. Ejecutar npm run build:images
  3. Verificar rutas en HTML (dist/images/archivo.svg)

Cambios no compilan:
  1. Verificar sintaxis SCSS (falta de puntos y comas, llaves)
  2. Ejecutar npm run lint-scss para detectar errores
  3. Revisar console del navegador (F12)
  4. Reiniciar: npm run watch

Botones no alineados:
  1. Revisar _buttons.scss
  2. Verificar padding y height
  3. Usar align-items: center en contenedor padre


═══════════════════════════════════════════════════════════════════════════════
📞 CONTACTO Y RECURSOS
═══════════════════════════════════════════════════════════════════════════════

Documentación:
  📄 DOCUMENTACION.md - Guía completa del proyecto
  📄 README.md - Información general (inglés)
  📄 CHANGELOG.md - Historial de cambios

Recursos Externos:
  🌐 SCSS Documentation: https://sass-lang.com/documentation
  🌐 CSS-Tricks Flexbox: https://css-tricks.com/snippets/css/a-guide-to-flexbox/
  🌐 MDN Web Docs: https://developer.mozilla.org/
  🌐 Google Fonts: https://fonts.google.com/

Licencia:
  📄 LICENSE (GPLv3) - Este proyecto es código abierto


═══════════════════════════════════════════════════════════════════════════════
