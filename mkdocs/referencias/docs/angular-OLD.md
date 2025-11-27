
## 6. CSS en Angular: ViewEncapsulation y arquitectura

### Cómo Angular maneja los estilos

Angular ofrece tres modos de encapsulación de estilos:

**Emulated (por defecto)**: Angular añade atributos únicos a tus elementos y reescribe tus selectores para que sean específicos del componente.

```typescript
@Component({
  selector: 'app-card',
  templateUrl: './card.component.html',
  styleUrls: ['./card.component.scss'],
  encapsulation: ViewEncapsulation.Emulated // Por defecto
})
```

Genera HTML como:
```html
<app-card _ngcontent-abc123>
  <h2 _ngcontent-abc123>Título</h2>
</app-card>
```

Y CSS como:
```css
h2[_ngcontent-abc123] {
  color: blue;
}
```

**ShadowDOM**: Usa Shadow DOM nativo del navegador.

```typescript
encapsulation: ViewEncapsulation.ShadowDom
```

**None**: Sin encapsulación, los estilos son globales.

```typescript
encapsulation: ViewEncapsulation.None
```

### Arquitectura de estilos en Angular

**Opción 1: Estilos globales + tokens**

```scss
// styles.scss (global)
@import 'abstracts/variables';
@import 'base/reset';
@import 'base/typography';

:root {
  --color-primary: #3b82f6;
  --spacing-unit: 0.5rem;
}

// card.component.scss
.card {
  padding: var(--spacing-unit);
  background: var(--color-primary);
}
```

**Opción 2: Biblioteca de utilidades compartidas**

```scss
// _shared.scss
@mixin card-shadow {
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
}

// card.component.scss
@import 'shared';

.card {
  @include card-shadow;
}
```

**Opción 3: Cascade Layers con Angular**

```scss
// styles.scss
@layer reset, tokens, base, components;

@layer tokens {
  :root {
    --color-primary: #3b82f6;
  }
}

// card.component.scss
@layer components {
  .card {
    background: var(--color-primary);
  }
}
```

### Selectores especiales de Angular

```scss
// :host - El elemento anfitrión del componente
:host {
  display: block;
  padding: 1rem;
}

:host(.compact) {
  padding: 0.5rem;
}

// :host-context - Cuando el componente está dentro de algo
:host-context(.dark-theme) {
  background: black;
  color: white;
}

// ::ng-deep - Penetrar encapsulación (usar con precaución)
:host ::ng-deep .external-library-class {
  color: red;
}
```

### Patrones recomendados para Angular

1. **Usa variables CSS para theming**, no SCSS variables
2. **Define tokens globales**, estilos de componente locales
3. **Evita `::ng-deep`** siempre que sea posible
4. **Usa `@layer` para organizar prioridades**
5. **Considera ViewEncapsulation.None para componentes de librería**

## 7. CSS en React: Estrategias de maquetación

### CSS tradicional en React

React no impone ninguna metodología específica para CSS. Puedes usar CSS tradicional exactamente igual que en HTML puro:

```jsx
// Card.jsx
function Card({ title, highlighted }) {
  return (
    <div className={`card ${highlighted ? 'card--highlighted' : ''}`}>
      <h2 className="card__title">{title}</h2>
    </div>
  );
}
```

```css
/* styles.css */
.card {
  padding: 1rem;
  background: white;
  border-radius: 8px;
}

.card--highlighted {
  border: 2px solid blue;
  background: lightblue;
}

.card__title {
  font-size: 1.5rem;
  margin: 0;
}
```

**Ventajas:**
- CSS estándar, sin curva de aprendizaje
- Compatible con todas las herramientas CSS
- Fácil de migrar de HTML tradicional

**Desventajas:**
- Estilos globales (riesgo de colisiones)
- Necesitas disciplina con nomenclatura (BEM, SMACSS, etc.)

### CSS Modules: Scope local automático

CSS Modules viene integrado en Create React App, Vite y la mayoría de bundlers modernos. **No es un framework**, es una transformación en tiempo de compilación que convierte tus clases en identificadores únicos:

```css
/* Card.module.css */
.card {
  padding: 1rem;
  background: white;
}

.title {
  font-size: 1.5rem;
}

.isHighlighted {
  border: 2px solid blue;
}
```

```jsx
// Card.jsx
import styles from './Card.module.css';

function Card({ title, highlighted }) {
  return (
    <div className={`${styles.card} ${highlighted ? styles.isHighlighted : ''}`}>
      <h2 className={styles.title}>{title}</h2>
    </div>
  );
}
```

El navegador verá algo como:
```html
<div class="Card_card__a8f3k Card_isHighlighted__x7j2p">
  <h2 class="Card_title__k3m9n">Mi título</h2>
</div>
```

**Ventajas:**
- Scope local sin conflictos
- CSS estándar (no aprende sintaxis nueva)
- Sin overhead en runtime
- Composición con `composes`:

```css
/* Button.module.css */
.base {
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 4px;
}

.primary {
  composes: base;
  background: blue;
  color: white;
}

.secondary {
  composes: base;
  background: gray;
  color: black;
}
```

### Variables CSS + React: Valores dinámicos

La mejor forma de pasar valores dinámicos desde React a CSS es usando custom properties:


```
function Card({ title, spacing, accentColor }) {
  return (
    <div 
      className={styles.card}
      style={{ 
        '--card-spacing': `${spacing}rem`,
        '--accent-color': accentColor
      }}
      
    >
      <h2 className={styles.title}>{title}</h2>
    </div>
  );
}
```


```css
/* Card.module.css */
.card {
  padding: var(--card-spacing, 1rem);
  border-left: 4px solid var(--accent-color, blue);
  /* Fallback values si no se pasan las variables */
}

.card:hover {
  padding: calc(var(--card-spacing) * 1.2);
}

.title {
  color: var(--accent-color);
}
```

**Ventajas de este enfoque:**
- Estilos dinámicos sin mezclar CSS en JavaScript
- Puedes usar pseudo-clases (`:hover`, `:focus`) y media queries
- CSS puede hacer cálculos con las variables
- Transiciones y animaciones funcionan perfectamente
- El CSS mantiene toda la lógica de presentación

### Organización de estilos en proyectos React

**Opción 1: Archivo CSS global + CSS Modules para componentes**
```
src/
├── styles/
│   ├── reset.css
│   ├── variables.css
│   └── global.css
├── components/
│   ├── Card/
│   │   ├── Card.jsx
│   │   └── Card.module.css
│   └── Button/
│       ├── Button.jsx
│       └── Button.module.css
└── App.jsx
```

```jsx
// App.jsx
import './styles/reset.css';
import './styles/variables.css';
import './styles/global.css';
```

**Opción 2: Todo con CSS Modules**
```
src/
├── styles/
│   ├── tokens.module.css  /* Variables compartidas */
│   └── utils.module.css   /* Utilidades */
└── components/
    └── Card/
        ├── Card.jsx
        └── Card.module.css
```

```css
/* tokens.module.css */
:root {
  --color-primary: #3b82f6;
  --spacing-unit: 0.5rem;
}
```

```css
/* Card.module.css */
@import '../../styles/tokens.module.css';

.card {
  padding: calc(var(--spacing-unit) * 2);
  background: var(--color-primary);
}
```

### Patrones recomendados para React

1. **CSS Modules para componentes**, CSS global para reset y tokens
2. **Variables CSS para theming**, no valores hardcodeados
3. **Inline styles solo para valores calculados dinámicamente**
4. **Nomenclatura consistente** (BEM dentro de módulos si quieres)
5. **Co-locación**: CSS junto al componente que lo usa

### Errores comunes en React

❌ **No aprovechar las variables CSS para valores dinámicos**
```jsx
// Evitar: lógica de estilos mezclada con JSX
<div className={props.isDark ? styles.darkText : styles.lightText}>
```

✅ **Usar variables CSS y data attributes**
```jsx
// Mejor: CSS maneja la lógica visual
<div 
  className={styles.text}
  data-theme={props.isDark ? 'dark' : 'light'}
>
```

```css
.text {
  color: var(--text-color);
}

.text[data-theme="dark"] {
  --text-color: #ffffff;
}

.text[data-theme="light"] {
  --text-color: #000000;
}
```

❌ **Estilos globales que colisionan**
```css
/* styles.css - riesgo de conflictos */
.card { padding: 1rem; }
.title { font-size: 1.5rem; }
```

✅ **CSS Modules para scope local**
```css
/* Card.module.css - sin conflictos */
.card { padding: 1rem; }
.title { font-size: 1.5rem; }
```

## 8. Multimedia para web: Optimización y rendimiento

### Formatos de imagen modernos

**WebP**: 25-35% más pequeño que JPEG con igual calidad
```html
<picture>
  <source srcset="imagen.webp" type="image/webp">
  <img src="imagen.jpg" alt="Descripción">
</picture>
```

**AVIF**: 50% más pequeño que JPEG, pero soporte limitado
```html
<picture>
  <source srcset="imagen.avif" type="image/avif">
  <source srcset="imagen.webp" type="image/webp">
  <img src="imagen.jpg" alt="Descripción">
</picture>
```

**SVG**: Para iconos, logos, ilustraciones
```html
<svg class="icon" aria-hidden="true">
  <use href="/icons.svg#icon-name"></use>
</svg>
```

### Lazy loading y performance

```html
<!-- Imágenes que no están en el viewport inicial -->
<img src="imagen.jpg" loading="lazy" alt="Descripción">

<!-- Imágenes críticas (above the fold) -->
<img src="hero.jpg" loading="eager" fetchpriority="high" alt="Hero">

<!-- Iframes -->
<iframe src="video.html" loading="lazy"></iframe>
```

### Responsive images: Srcset y Sizes

```html
<img
  srcset="
    small.jpg 400w,
    medium.jpg 800w,
    large.jpg 1200w
  "
  sizes="
    (max-width: 600px) 100vw,
    (max-width: 1200px) 50vw,
    33vw
  "
  src="medium.jpg"
  alt="Descripción"
>
```

**Traducción**:
- En pantallas ≤600px: imagen ocupa 100% del viewport
- En pantallas ≤1200px: imagen ocupa 50% del viewport
- En pantallas >1200px: imagen ocupa 33% del viewport

El navegador elige automáticamente el tamaño más apropiado.

### Video optimizado

```html
<video 
  controls 
  preload="metadata"
  poster="thumbnail.jpg"
>
  <source src="video.webm" type="video/webm">
  <source src="video.mp4" type="video/mp4">
  <track kind="subtitles" src="subs.vtt" srclang="es" label="Español">
</video>
```

**Reglas de oro:**
- `preload="none"` para videos no críticos
- `preload="metadata"` para videos probablemente vistos
- `poster` siempre
- Incluye subtítulos (`<track>`) para accesibilidad

## 9. Errores comunes y cómo evitarlos

### ❌ Especificidad fuera de control

```css
/* Mal */
#header .nav ul li a.active { }

/* Bien */
.nav-link.is-active { }
```

**Solución**: Usa clases, evita IDs para estilos, aprovecha `@layer`.

### ❌ Unidades absolutas cuando necesitas fluidez

```css
/* Mal */
.container {
  width: 1200px;
  padding: 20px;
}

/* Bien */
.container {
  max-width: 75rem; /* 1200px con font base 16px */
  padding: clamp(1rem, 3%, 2rem);
}
```

### ❌ No pensar en componentes

```css
/* Mal: Estilos demasiado específicos */
.homepage .section .card .title { }

/* Bien: Componente independiente */
.card__title { }
```

**Mentalidad**: Si lo estás copiando y pegando, debería ser un componente.

### ❌ Ignorar cascada y herencia

```css
/* Mal: Repitiendo font-family en cada elemento */
.button { font-family: sans-serif; }
.card { font-family: sans-serif; }
.input { font-family: sans-serif; }

/* Bien: Definir en la raíz */
:root {
  font-family: system-ui, sans-serif;
}
```

### ❌ Media queries que miran el dispositivo, no el contenido

```css
/* Mal */
@media (min-width: 768px) { /* "tablet" */ }

/* Bien */
@media (min-width: 600px) { /* "cuando el contenido lo necesite" */ }
```

**Regla**: Los breakpoints deben estar determinados por tu diseño, no por dispositivos específicos.

---
