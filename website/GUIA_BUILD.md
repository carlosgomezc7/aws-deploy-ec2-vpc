# 🛠️ GUÍA DE COMPILACIÓN Y BUILD

## Tabla de Contenidos
1. [Configuración Inicial](#configuración-inicial)
2. [Compilación SCSS](#compilación-scss)
3. [Scripts Disponibles](#scripts-disponibles)
4. [Flujo de Trabajo](#flujo-de-trabajo)
5. [Troubleshooting](#troubleshooting)

---

## 🚀 Configuración Inicial

### Paso 1: Instalar Node.js y npm
Descargar e instalar desde: https://nodejs.org/

Verificar instalación:
```bash
node --version
npm --version
```

### Paso 2: Instalar Dependencias del Proyecto
```bash
npm install
```

Esto instala todas las herramientas en `node_modules/`:
- **node-sass**: Compila SCSS a CSS
- **autoprefixer**: Añade prefijos para navegadores antiguos
- **browser-sync**: Servidor local con recarga automática
- **imagemin**: Optimiza imágenes
- **npm-run-all**: Ejecuta múltiples scripts
- **onchange**: Vigila cambios en archivos
- **stylelint**: Valida sintaxis SCSS

### Paso 3: Verificar Instalación
```bash
npm run build
# Debe generar:
# - dist/css/style.css
# - dist/images/
```

---

## 📝 Compilación SCSS

### ¿Qué es SCSS?
SCSS es un preprocesador de CSS que añade características:
- Variables (reutilizar valores)
- Mixins (reutilizar bloques de código)
- Funciones (lógica personalizada)
- Nesting (anidar selectores)
- Importaciones (dividir en archivos)

### ¿Por qué compilar?
Los navegadores NO entienden SCSS, solo CSS. Necesitamos compilar:

```
SCSS (src/scss/)
    ↓ Compilación con node-sass
CSS (dist/css/style.css)
    ↓ Navegador entiende y renderiza
```

### Flujo de Compilación SCSS

```
1. node-sass lee src/scss/style.scss
2. Sigue las importaciones:
   @import './abstracts/variables'
   @import './abstracts/functions'
   @import './abstracts/mixins'
   @import './base/normalize'
   @import './base/base'
   @import './base/typography'
   @import './base/helpers'
   @import './components/buttons'
   @import './components/forms'
   @import './layout/main'
   @import './layout/header'
   @import './layout/hero'
   @import './layout/features'
   @import './layout/pricing'
   @import './layout/cta'
   @import './layout/footer'

3. Compila TODO a un único archivo CSS minificado
4. Guarda en dist/css/style.css
```

### Ejemplo de Compilación Paso a Paso

**Entrada (src/scss/abstracts/_variables.scss):**
```scss
$color-primary: #0270D7;
$spacing-medium: 24px;

.button {
    background-color: $color-primary;
    padding: $spacing-medium;
}
```

**Salida (dist/css/style.css):**
```css
.button{background-color:#0270D7;padding:24px}
```

---

## 📜 Scripts Disponibles

### Desarrollo (Recomendado)

#### `npm run watch`
**Propósito**: Desarrollar de forma cómoda con recarga automática

**Qué hace**:
1. Inicia servidor local en http://localhost:3000
2. Vigila cambios en `src/scss/`
3. Vigila cambios en `src/images/`
4. Compila automáticamente
5. Recarga página en navegador

**Cuándo usarlo**: Siempre durante desarrollo

**Comando**:
```bash
npm run watch
# Output: Abre navegador automáticamente
```

---

### Construcción (Build)

#### `npm run build`
**Propósito**: Generar archivos finales para producción

**Qué hace**:
1. Limpia archivos anteriores (rimraf)
2. Compila CSS final
3. Optimiza imágenes
4. Genera dist/ completo

**Cuándo usarlo**: Antes de deploy a producción

**Comando**:
```bash
npm run build
# Output: 
# dist/css/style.css ✓
# dist/images/* ✓
```

---

#### `npm run build:css`
**Propósito**: Compilar solo CSS (sin imágenes)

**Qué hace**:
1. Valida SCSS (lint-scss)
2. Compila SCSS a CSS
3. Añade prefijos de navegadores (autoprefixer)

**Cuándo usarlo**: Cuando cambias SCSS

**Comando**:
```bash
npm run build:css
# Output:
# ✓ SCSS válido
# ✓ CSS compilado
# ✓ Prefijos añadidos
```

---

#### `npm run build:images`
**Propósito**: Optimizar imágenes

**Qué hace**:
1. Comprime PNG/JPG
2. Mantiene formato SVG
3. Guarda en dist/images/

**Cuándo usarlo**: Cuando añades imágenes nuevas

**Comando**:
```bash
npm run build:images
# Output: Imágenes optimizadas en dist/images/
```

---

### Utilidades

#### `npm run serve`
**Propósito**: Iniciar servidor local sin vigilancia

**Comando**:
```bash
npm run serve
# Abre: http://localhost:3000
```

---

#### `npm run lint-scss`
**Propósito**: Validar sintaxis SCSS

**Comando**:
```bash
npm run lint-scss
# Output: Lista errores/warnings en SCSS
```

---

#### `npm run clean`
**Propósito**: Limpiar archivos compilados

**Comando**:
```bash
npm run clean
# Elimina:
# - dist/css/*
# - dist/images/*
```

---

#### `npm run watch:css`
**Propósito**: Vigilar solo SCSS (sin servidor)

**Comando**:
```bash
npm run watch:css
# Vigila cambios en src/scss/
# Compila automáticamente
```

---

#### `npm run watch:images`
**Propósito**: Vigilar solo imágenes

**Comando**:
```bash
npm run watch:images
# Vigila cambios en src/images/
# Optimiza automáticamente
```

---

## 🔄 Flujo de Trabajo

### Workflow Típico de Desarrollo

#### 1. Iniciar sesión de desarrollo
```bash
npm run watch
# Abre navegador automáticamente
```

#### 2. Editar archivo SCSS
```bash
# Editar: src/scss/layout/_features.scss
# Cambiar: .feature { gap: 24px; }
```

#### 3. Guardar (Ctrl+S)
```
OnChange detecta cambio
    ↓
npm run build:css ejecuta
    ↓
Valida SCSS
    ↓
Compila a CSS
    ↓
Autoprefixer añade prefijos
    ↓
dist/css/style.css actualizado
    ↓
Browser-sync recarga página
    ↓
Ves cambios en tiempo real
```

#### 4. Verificar resultado
- Abre DevTools (F12)
- Inspecciona elementos
- Verifica estilos se aplican

#### 5. Iterar hasta satisfecho

---

### Workflow de Producción

#### 1. Terminar desarrollo
```bash
# Presionar Ctrl+C para salir de npm run watch
```

#### 2. Build final
```bash
npm run build
# Compila todo
# Optimiza imágenes
# Limpia archivos
```

#### 3. Verificar archivos generados
```bash
# dist/css/style.css existe
# dist/images/ tiene imágenes
# Tamaño de style.css ~20KB
```

#### 4. Deploy a servidor
```bash
# Subir archivos a AWS/servidor
# Asegurar que index.html carga dist/css/style.css
```

---

## 📊 Estructura de Compilación

### Archivos ENTRADA (src/)
```
src/scss/
├── style.scss           ← Archivo principal (importa todo)
├── _normalize.scss      ← Reset CSS
├── abstracts/
│   ├── _variables.scss
│   ├── _functions.scss
│   ├── _mixins.scss
│   └── _include-media.scss
├── base/
│   ├── _base.scss
│   ├── _typography.scss
│   ├── _helpers.scss
│   └── _normalize.scss
├── components/
│   ├── _buttons.scss
│   └── _forms.scss
└── layout/
    ├── _main.scss
    ├── _header.scss
    ├── _hero.scss
    ├── _features.scss
    ├── _pricing.scss
    ├── _cta.scss
    └── _footer.scss

src/images/
├── logo.svg
├── feature-icon-01.svg
├── feature-icon-02.svg
└── ...
```

### Archivos SALIDA (dist/) - Auto-generado
```
dist/
├── css/
│   └── style.css        ← 1 archivo compilado (~20KB minificado)
└── images/
    ├── logo.svg
    ├── feature-icon-01.svg
    └── ...              ← Optimizadas
```

---

## 🎯 Qué Significa Cada Paso

### `npm run lint-scss`
Valida que SCSS está bien escrito:
```scss
// ✓ Correcto
.button {
    padding: 16px;
}

// ✗ Error (falta punto y coma)
.button {
    padding: 16px
}
```

### `npm run scss`
Compila SCSS a CSS:
```scss
// Entrada
$color: #0270D7;
.button { color: $color; }

// Salida
.button { color: #0270D7; }
```

### `npm run autoprefixer`
Añade prefijos para navegadores antiguos:
```css
/* Entrada */
.button { display: flex; }

/* Salida */
.button {
    display: -webkit-flex;  /* Safari, Chrome viejo */
    display: -moz-flex;     /* Firefox viejo */
    display: flex;          /* Estándar */
}
```

### `npm run imagemin`
Comprime imágenes:
```
logo.svg (original): 2.5 KB
logo.svg (optimizado): 1.8 KB ✓
```

---

## 🔍 Verificar Compilación

### Ver archivo compilado
```bash
# Windows
type dist/css/style.css | more

# Mac/Linux
cat dist/css/style.css
```

### Verificar tamaño
```bash
# Windows
dir dist/css/style.css

# Mac/Linux
ls -lh dist/css/style.css
```

### Contar líneas
```bash
# Windows
find dist/css -name "*.css" | xargs wc -l

# Mac/Linux
wc -l dist/css/style.css
```

---

## ⚙️ Configuración de Scripts (package-sample.json)

```json
{
  "scripts": {
    "clean": "rimraf dist/{css/*,images/*}",
    // Borra archivos compilados anteriores
    
    "autoprefixer": "postcss -u autoprefixer -r dist/css/*",
    // Añade prefijos de navegadores
    
    "scss": "node-sass --output-style compressed -o dist/css src/scss",
    // Compila SCSS minificado
    
    "lint-scss": "stylelint src/scss/*.scss --syntax scss || true",
    // Valida SCSS (no falla si hay errores)
    
    "imagemin": "imagemin src/images/* -o dist/images",
    // Optimiza imágenes
    
    "serve": "browser-sync start --server --files",
    // Servidor local con recarga automática
    
    "build:css": "run-s lint-scss scss autoprefixer",
    // Secuencia: valida → compila → prefijos
    
    "build:images": "run-s imagemin",
    // Optimiza imágenes
    
    "build": "run-s build:css build:images",
    // Build completo CSS + imágenes
    
    "watch:css": "onchange \"src/scss\" -- run-s build:css",
    // Vigila SCSS y compila
    
    "watch:images": "onchange \"src/images\" -- run-s build:images",
    // Vigila imágenes y optimiza
    
    "watch": "run-p serve watch:css watch:images",
    // Paralelo: servidor + vigila SCSS + vigila imágenes
    
    "postinstall": "run-s build watch"
    // Auto-ejecuta después de instalar
  }
}
```

---

## 🐛 Troubleshooting

### Problema: "Command not found: npm"
**Solución**: Instalar Node.js desde https://nodejs.org/

---

### Problema: Dependencias no instalan
**Solución**:
```bash
# Limpiar caché
npm cache clean --force

# Reinstalar
npm install
```

---

### Problema: SCSS no compila
**Solución**:
```bash
# Verificar errores
npm run lint-scss

# Ver mensajes de error
npm run scss

# Ejemplo: Falta punto y coma
// Error: Unexpected token }
.button {
    padding: 16px  // ← Falta ;
}
```

---

### Problema: CSS no se ve en navegador
**Solución**:
1. Verificar HTML incluye CSS: `<link rel="stylesheet" href="dist/css/style.css">`
2. Vaciar caché: Ctrl+Shift+Delete
3. Recargar página: Ctrl+F5
4. Verificar dist/css/style.css existe

---

### Problema: Cambios SCSS no aparecen
**Solución**:
```bash
# Parar npm run watch (Ctrl+C)
# Reiniciar
npm run watch

# O compilar manual
npm run build:css
```

---

### Problema: Browser-sync no abre navegador
**Solución**:
```bash
# Abrir manualmente
http://localhost:3000
```

---

## 📈 Performance Tips

### Monitorear tamaño de CSS
```bash
# Ver tamaño del archivo compilado
ls -lh dist/css/style.css

# Debe ser ~20KB minificado
```

### Optimizar imágenes
```bash
# Usar formatos modernos (WebP)
# Comprimir antes de subir
# Usar responsive images (<picture>)
```

### Monitorear build time
```bash
# time npm run build:css
# Debe tardar < 2 segundos
```

---

## ✅ Checklist de Build

Antes de deploy:
- [ ] `npm run build` sin errores
- [ ] `dist/css/style.css` existe y tiene contenido
- [ ] `dist/images/` tiene todas las imágenes
- [ ] Tamaño CSS < 50KB
- [ ] Verificar en navegador (F12)
- [ ] Verificar responsive (F12 > Device Toggle)
- [ ] Verificar enlaces funcionan
- [ ] Verificar formularios funcionan

---

## 📞 Recursos

- Node.js: https://nodejs.org/
- npm: https://www.npmjs.com/
- SASS: https://sass-lang.com/
- PostCSS: https://postcss.org/
- Browser-Sync: https://browsersync.io/

---

**Última actualización**: 9 de junio de 2026
