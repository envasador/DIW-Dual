---
hide:
  * navigation
---

## **Fases del proyecto**

# **FASE 1: FUNDAMENTOS Y ARQUITECTURA CSS**

Criterios: RA1.a, RA2.a, RA2.c, RA1.f Entrega: 18 de diciembre

## **OBJETIVOS DE LA FASE**

En esta fase establecerás los cimientos técnicos de todo tu sistema de estilos. No se trata solo de escribir CSS, sino de crear una arquitectura escalable que permita mantener y hacer crecer tu proyecto sin que se convierta en caos.

Definirás un sistema de design tokens (variables SCSS) que sean la única fuente de verdad para colores, tipografías, espaciados y demás propiedades visuales. Organizarás tus archivos siguiendo una metodología profesional (ITCSS), crearás mixins reutilizables que te ahorren código repetitivo, y documentarás todo para que cualquiera entienda cómo funciona el sistema.

## **TAREAS**

### ***1\. Sistema de Design Tokens en SCSS***

Crea la carpeta `src/styles/00-settings/` y dentro el archivo `_variables.scss` con todas tus variables:

**Variables de color:** Define tu paleta completa. Necesitas colores primarios (el color principal de tu marca), secundarios (color de apoyo), neutrales (grises del 50 al 900 para textos y fondos), y semánticos (success verde, error rojo, warning naranja, info azul).

Ejemplo de estructura:

color-primary: tu-color-principal

color-primary-light: versión más clara

color-primary-dark: versión más oscura

color-secondary: tu-color-secundario

color-neutral-50: casi blanco

color-neutral-100: gris muy claro

...hasta...

color-neutral-900: casi negro

color-success: verde

color-error: rojo

color-warning: naranja

color-info: azul

**Escala tipográfica:** Define las fuentes que usarás y los tamaños. La escala debe ser coherente (usa una escala modular, por ejemplo con ratio 1.25). Necesitas definir familias (font-primary para texto, font-secondary si usas otra para títulos), tamaños desde xs hasta 5xl, pesos (light, regular, medium, semibold, bold), y line-heights (tight para títulos, normal para párrafos, relaxed para textos largos).

**Sistema de espaciado:** Crea una escala basada en 4px u 8px. Define spacing-1 (4px), spacing-2 (8px), spacing-3 (12px), spacing-4 (16px), spacing-5 (20px), y así hasta spacing-24 (96px). Esto te permite mantener consistencia en márgenes y paddings.

**Breakpoints:** Define los puntos de quiebre para responsive. Usa al menos: sm (640px para móvil grande), md (768px para tablet), lg (1024px para desktop), xl (1280px para desktop grande).

**Elevaciones (sombras):** Define sombras de diferentes intensidades: shadow-sm (sombra sutil), shadow-md (sombra media), shadow-lg (sombra grande), shadow-xl (sombra muy grande). Usa rgba con transparencia para que funcionen en cualquier fondo.

**Bordes y radios:** Define grosores de borde (thin 1px, medium 2px, thick 4px) y radios de borde (desde sm 2px hasta full 9999px para círculos).

**Transiciones:** Define duraciones estándar: fast (150ms para cambios rápidos), base (300ms para la mayoría), slow (500ms para transiciones complejas). Usa ease-in-out para transiciones suaves.

### ***2\. Mixins y funciones útiles***

Crea la carpeta `src/styles/01-tools/` y dentro el archivo `_mixins.scss`:

**Mixin responsive:** Crea un mixin que te permita escribir media queries fácilmente. La idea es que en lugar de escribir "@media (min-width: 768px)" cada vez, puedas escribir "@include respond-to('md')" que es más legible. El mixin debe aceptar 'sm', 'md', 'lg', 'xl' y aplicar el breakpoint correspondiente.

**Mixin truncar texto:** Crea dos mixins útiles. Uno llamado "truncate" que corta texto en una línea con puntos suspensivos (usa overflow hidden, text-overflow ellipsis, white-space nowrap). Otro llamado "line-clamp" que acepta un número de líneas y corta el texto después de esas líneas (usa display \-webkit-box, \-webkit-line-clamp, \-webkit-box-orient vertical).

**Mixin aspect-ratio:** Crea un mixin para mantener proporciones de elementos (útil para imágenes y videos). Debe aceptar ancho y alto, y calcular el padding-top correcto para mantener la proporción.

**Mixin centrar:** Crea mixins para centrar elementos. Uno con position absolute (center-absolute) y otro con flexbox (center-flex).

### ***3\. Organización de archivos ITCSS***

Crea la estructura completa de carpetas en `src/styles/`:

styles/

├── 00-settings/     (Variables globales)
│   └── \_variables.scss
├── 01-tools/        (Mixins y funciones)
│   └── \_mixins.scss
├── 02-generic/      (Reset CSS y normalize)
│   └── \_reset.scss
├── 03-elements/     (Estilos base de HTML)
│   ├── \_html.scss
│   ├── \_typography.scss
│   └── \_links.scss
├── 04-layout/       (Estructura de página)
│   ├── \_grid.scss
│   ├── \_container.scss
│   └── \_spacing.scss
├── 05-components/   (Componentes UI \* aquí irán tus componentes)
│   └── (vacío por ahora, lo llenas en Fase 3\)
├── 06-utilities/    (Clases utilitarias)
│   └── \_utilities.scss
└── styles.scss      (Archivo principal que importa todo)

En `styles.scss` importa todo en orden:

```css
@import '00-settings/variables';

@import '01-tools/mixins';

@import '02-generic/reset';

@import '03-elements/html';

@import '03-elements/typography';

@import '03-elements/links';

@import '04-layout/grid';

@import '04-layout/container';

@import '04-layout/spacing';

@import '06-utilities/utilities';
```

**Importante:** Este orden es crítico. Las variables primero, luego mixins, luego reset, y así sucesivamente aumentando la especificidad.

### ***4\. Reset CSS***

En `02-generic/_reset.scss` crea un reset básico. Como mínimo:

* Box-sizing border-box para todos los elementos
* Margin y padding 0 por defecto
* List-style none para listas
* Quitar estilos por defecto de botones

Puedes usar un reset existente como Normalize.css o crear el tuyo propio.

### ***5\. Estilos base de elementos***

En `03-elements/` define estilos base para elementos HTML sin clases:

**\_html.scss:** Define html con font-size base (generalmente 16px o 100%), y body con font-family, line-height, color de texto, y color de fondo.

**\_typography.scss:** Define estilos para h1 a h6, párrafos, strong, em. Usa tus variables de tamaño y peso tipográfico.

**\_links.scss:** Define estilos para enlaces (a) con color, text-decoration, y estados hover/focus.

### ***6\. Sistema de Grid***

En `04-layout/_grid.scss` crea un sistema de grid básico usando CSS Grid:

* Un contenedor .container con max-width y padding lateral
* Un grid .grid con display grid y gap entre elementos
* Modificadores para número de columnas (.grid--2, .grid--3, .grid--4)

### ***7\. Documentación en DOCUMENTACION.md***

Crea el archivo `docs/DOCUMENTACION.md` y escribe la **Sección 1: Arquitectura CSS y comunicación visual**.

Esta sección debe incluir:

**1.1 Principios de comunicación visual:** Explica los 5 principios básicos y cómo los aplicas en tu proyecto:

* Jerarquía: Cómo usas tamaños, pesos y espaciado para crear importancia visual
* Contraste: Cómo usas color, tamaño y peso para diferenciar elementos
* Alineación: Tu estrategia de alineación (izquierda, centro, grid)
* Proximidad: Cómo agrupas elementos relacionados con espaciado
* Repetición: Cómo creas coherencia repitiendo patrones visuales

Incluye capturas de pantalla de tu diseño de Figma señalando dónde aplicas cada principio.

**1.2 Metodología CSS:** Explica qué metodología usas (BEM recomendado) y por qué. Muestra ejemplos de tu nomenclatura. Si usas BEM, explica que usarás bloques (.card), elementos (.card\_\_title), y modificadores (.card--featured).

**1.3 Organización de archivos:** Documenta tu estructura ITCSS. Explica por qué cada carpeta está en ese orden (de menor a mayor especificidad). Muestra el árbol de carpetas completo.

**1.4 Sistema de Design Tokens:** Documenta todas tus variables. Para cada grupo (colores, tipografía, espaciado, etc.) explica las decisiones:

* Por qué elegiste esos colores
* Por qué esa escala tipográfica
* Por qué esos breakpoints

**1.5 Mixins y funciones:** Documenta cada mixin que creaste, para qué sirve, y muestra un ejemplo de uso.

**1.6 ViewEncapsulation en Angular:** Explica qué estrategia de encapsulación usarás. Angular por defecto usa Emulated (estilos encapsulados por componente). Documenta si mantendrás esto o usarás None (estilos globales). Justifica tu decisión.

## **ENTREGABLES FASE 1**

* Carpeta `src/styles/` con estructura ITCSS completa
* Archivo `_variables.scss` con todos los design tokens
* Archivo `_mixins.scss` con mixins reutilizables
* Reset CSS implementado
* Estilos base de elementos HTML
* Sistema de grid básico
* Sección 1 del `docs/DOCUMENTACION.md` completada con capturas
