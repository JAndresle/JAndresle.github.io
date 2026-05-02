# CLAUDE.md — andresle.com

## Descripción del sitio
Portafolio personal de Jose Andres Espinoza (Data Engineer).
Dominio: andresle.com | Repo: JAndresle.github.io (GitHub Pages)

Secciones: About, Resume, Certifications, Portfolio.

## Stack
- HTML/CSS/JS vanilla — sin frameworks ni bundlers
- Ionicons (CDN, ES module) para íconos
- Google Fonts: Poppins (300, 400, 500, 600)
- GitHub Pages para hosting (rama master, deploy automático)

## Estructura de archivos
index.html          → único HTML, todo el contenido
assets/css/style.css → todos los estilos (~1,882 líneas)
assets/js/script.js  → JS principal (parcialmente reemplazado por inline script en el HTML)
assets/images/       → imágenes, íconos SVG, badges de certificaciones

## Convenciones detectadas

### HTML
- Navegación de tabs: elementos `<li data-page="...">` con clase `active` para mostrar sección
- Cada sección es un `<article data-page="...">` oculto por defecto, visible con clase `active`
- Sidebar expandible: `.sidebar` con clase `active` en mobile
- Filtros de certificaciones: botones con `data-filter-btn` + items con `data-category`

### CSS
- Variables en `:root` para colores, tipografía y sombras
- Convención de color: `--vegas-gold` para acento principal, escala de grises `--jet`/`--onyx`/`--eerie-black`
- Mobile-first: breakpoints en 450px, 580px, 768px, 1024px, 1250px
- Animaciones: `@keyframes scaleUp` para entrada de elementos filtrados

### JavaScript
- Funciones del template en `script.js` (algunas sin uso activo)
- Lógica de navegación y filtros en inline `<script>` al final de `index.html`
- Sin módulos, sin bundler — scope global

## Cómo previsualizar localmente
1. Instalar extensión **Live Server** en VS Code
2. Click derecho en `index.html` → "Open with Live Server"
3. Puerto configurado: `5501` (ver `.vscode/settings.json`)
4. URL local: http://localhost:5501

Alternativa sin VS Code:
```bash
python -m http.server 5501
# luego abrir http://localhost:5501
```

## Notas de mantenimiento
- Las imágenes de perfil tienen nombres con espacios ("WhatsApp Image 2025-06-26...") — no renombrar sin actualizar el HTML
- El archivo `index.txt` es la plantilla original — no borrar sin respaldar, sirve de referencia
- `assets/images/` contiene ~88 archivos; limpiar los no referenciados eventualmente
