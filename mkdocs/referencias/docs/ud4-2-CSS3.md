---
hide:
  - navigation
---
---
## Tabla de contenido

* [1 HTML5](ud4-1-HTML5.md)
* [2 CSS3](ud4-2-CSS3.md)
* [3 SASS](ud4-3-SASS.md)
---

# **4.2 Guía completa de CSS3**.
## 1. Introducción a CSS3

**CSS3** (Cascading Style Sheets Level 3) es la última versión de CSS, utilizada para describir la presentación de documentos HTML y XML. CSS3 introduce nuevas características y mejoras que facilitan la creación de diseños web más atractivos y funcionales.

### 1.2 ¿Por qué usar CSS3?

- **Modularidad:** CSS3 se divide en módulos, lo que facilita su uso y comprensión.
- **Nuevas propiedades:** Permite efectos visuales avanzados como sombras, transiciones y animaciones.
- **Responsive Design:** Facilita la creación de sitios web que se adaptan a diferentes tamaños de pantalla.
- **Mejoras en el diseño:** Nuevas herramientas como Flexbox y Grid Layout para layouts más complejos y flexibles.

---

## 2. Estructura Básica de CSS

Un archivo CSS está compuesto por reglas que definen cómo se deben mostrar los elementos HTML.

### 2.2 Sintaxis Básica

```css
selector {
    propiedad: valor;
}
```

### 2.3 Ejemplo de sintaxis

```css
body {
    background-color: #f0f0f0;
    font-family: Arial, sans-serif;
}

h1 {
    color: #333333;
    text-align: center;
}
```

---

## 3. Selectores CSS

Los **selectores** son patrones utilizados para seleccionar los elementos HTML que deseas estilizar.

### 3.1 Selectores Básicos

- **Selector de Tipo:** Selecciona todos los elementos de un tipo específico.

    ```css
    p {
        color: blue;
    }
    ```

- **Selector Universal:** Selecciona todos los elementos.

    ```css
    * {
        margin: 0;
        padding: 0;
    }
    ```

### 3.2 Selectores de Clase y ID

- **Clase:** Selecciona elementos con una clase específica.

    ```css
    .mi-clase {
        background-color: yellow;
    }
    ```

- **ID:** Selecciona un elemento con un ID específico (debe ser único).

    ```css
    **#**mi-id {
        border: 1px solid black;
    }
    ```

### 3.3 Selectores de Atributo

Seleccionan elementos basados en atributos o valores de atributos.

```css
input[type="text"] {
    width: 200px;
    padding: 5px;
}
```
### 3.4 Selectores de Pseudo-clases y Pseudo-elementos

- **Pseudo-clases:** Seleccionan elementos en un estado específico.

    ```css
    a:hover {
        color: red;
    }
    ```

- **Pseudo-elementos:** Seleccionan una parte específica de un elemento.

    ```css
    p::first-line {
        font-weight: bold;
    }
    ```
---

## 4. Modelo de Caja (Box Model)

El **Box Model** de CSS describe cómo se calculan las dimensiones y el espacio alrededor de los elementos.

### 4.1 Componentes del Box Model

1. **Contenido:** Área donde se muestra el contenido (texto, imágenes, etc.).
2. **Padding (Relleno):** Espacio entre el contenido y el borde.
3. **Border (Borde):** Línea que rodea el padding y el contenido.
4. **Margin (Margen):** Espacio fuera del borde.

### 4.2 Ejemplo del Box Model

```css
div {
    width: 300px;
    padding: 20px;
    border: 5px solid #333;
    margin: 15px;
}
```

### 4.3 Visualización

```
+-----------------------------+
|          Margin             |
|  +-----------------------+  |
|  |        Border         |  |
|  |  +-----------------+  |  |
|  |  |     Padding     |  |  |
|  |  |  +-----------+  |  |  |
|  |  |  |  Content  |  |  |  |
|  |  |  +-----------+  |  |  |
|  |  +-----------------+  |  |
|  +-----------------------+  |
+-----------------------------+
```

---

## 5. Propiedades de Texto y Fuente

CSS3 ofrece una amplia gama de propiedades para estilizar el texto.

### 5.1 Tipografía

- **font-family:** Define la familia de fuentes.

    ```css
    body {
        font-family: 'Helvetica Neue', sans-serif;
    }
    ```

- **font-size:** Tamaño de la fuente.

     ```css
    h1 {
        font-size: 2em;
    }
    ```

- **font-weight:** Grosor de la fuente.

     ```css
    p {
        font-weight: bold;
    }
    ```

- **font-style:** Estilo de la fuente (normal, italic, oblique).

    ```css
    em {
        font-style: italic;
    }
    ```

### 5.2 Propiedades de Texto

- **color:** Color del texto.

     ```css
    span {
        color: #ff5733;
    }
    ```

- **text-align:** Alineación del texto.

    ```css
    .centrado {
        text-align: center;
    }
    ```

- **text-decoration:** Decoraciones del texto (subrayado, tachado, etc.).

    ```css
    a {
        text-decoration: none;
    }
    a:hover {
        text-decoration: underline;
    }
    ```

- **line-height:** Altura de la línea.

    ```css
    p {
        line-height: 1.6;
    }
    ```

---

## 6. Colores y Fondos

### 6.1 Colores

Puedes definir colores usando nombres, códigos hexadecimales, RGB, RGBA, HSL y HSLA.

```css
h2 {
    color: #3498db; /* Hexadecimal */
}

p {
    color: rgb(52, 152, 219); /* RGB */
}

div {
    background-color: rgba(52, 152, 219, 0.5); /* RGBA */
}
```

### 6.2 Fondos

- **background-color:** Color de fondo.
- **background-image:** Imagen de fondo.
- **background-repeat:** Repetición de la imagen.
- **background-size:** Tamaño de la imagen de fondo.
- **background-position:** Posición de la imagen de fondo.


```css
body {
    background-color: #ecf0f1;
    background-image: url('fondo.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center;
}
```

---

## 7. Diseño de Layout

### 7.1 Flexbox

**Flexbox** es un modelo de diseño unidimensional que facilita la alineación y distribución de elementos dentro de un contenedor.

#### Contenedor Flex

```css
.container {
    display: flex;
    flex-direction: row; /* column, row-reverse, column-reverse */
    justify-content: space-between; /* flex-start, flex-end, center, space-around, space-evenly */
    align-items: center; /* stretch, flex-start, flex-end, center, baseline */
}
```

#### Elementos Flex

```css
.item {
    flex: 1; /* grow, shrink, basis */
    margin: 10px;
}
```

#### Ejemplo Completo

```html
<div class="container">
    <div class="item">Elemento 1</div>
    <div class="item">Elemento 2</div>
    <div class="item">Elemento 3</div>
</div>
```

```css
.container {
    display: flex;
    justify-content: space-around;
    align-items: center;
    height: 200px;
    background-color: #f8f9fa;
}

.item {
    background-color: #007bff;
    color: white;
    padding: 20px;
    border-radius: 5px;
}
```

### 7.2 Grid Layout

**Grid Layout** es un sistema de diseño bidimensional que permite crear estructuras complejas con filas y columnas.

#### Contenedor Grid

```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr); /* 3 columnas de igual tamaño */
    grid-gap: 10px; /* Espacio entre filas y columnas */
}
```

#### Elementos Grid

```css
.grid-item {
    background-color: #28a745;
    color: white;
    padding: 20px;
    text-align: center;
}
```

#### Ejemplo Completo

```html
<div class="grid-container">
    <div class="grid-item">1</div>
    <div class="grid-item">2</div>
    <div class="grid-item">3</div>
    <div class="grid-item">4</div>
    <div class="grid-item">5</div>
    <div class="grid-item">6</div>
</div>
```

```css
.grid-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 15px;
    background-color: #f1f1f1;
    padding: 10px;
}

.grid-item {
    background-color: #28a745;
    color: white;
    padding: 30px 0;
    font-size: 30px;
    text-align: center;
}
```

---

## 8. Transiciones y Animaciones

### Transiciones

Las **transiciones** permiten cambiar las propiedades CSS de un elemento de manera suave durante un período de tiempo.

#### Sintaxis

```css
.selector {
    transition: propiedad duración timing-función retraso;
}
```

#### Ejemplo

```css
button {
    background-color: #3498db;
    color: white;
    padding: 10px 20px;
    border: none;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #2980b9;
}
```

### Animaciones

Las **animaciones** permiten definir una serie de estilos que cambian a lo largo del tiempo.

#### Sintaxis

```css
@keyframes nombre-animación {
    desde { /* estilos iniciales */ }
    hasta { /* estilos finales */ }
}

.selector {
    animation: nombre-animación duración timing-función retraso iteraciones dirección relleno;
}
```

#### Ejemplo

```css
@keyframes girar {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(360deg);
    }
}

.icono {
    display: inline-block;
    animation: girar 2s linear infinite;
}
```

```html
<div class="icono">🔄</div>
```

---

## 9. Responsive y Media Queries

Las **Media Queries** permiten aplicar estilos CSS específicos según las características del dispositivo, como el ancho de la pantalla.

### Ejemplo Básico

```css
/* Estilos por defecto */
body {
    font-size: 16px;
}

/* Para pantallas con un ancho máximo de 768px */
@media (max-width: 768px) {
    body {
        font-size: 14px;
    }
}

/* Para pantallas con un ancho máximo de 480px */
@media (max-width: 480px) {
    body {
        font-size: 12px;
    }
}
```

### Diseño Responsive con Flexbox

```css
.container {
    display: flex;
    flex-wrap: wrap;
}

.item {
    flex: 1 1 300px; /* grow, shrink, basis */
    margin: 10px;
}

/* Ajuste para pantallas pequeñas */
@media (max-width: 600px) {
    .container {
        flex-direction: column;
    }
}
```

---

## 10. Nuevas Características de CSS3

### La Regla `@scope`

La regla `@scope` es una **propuesta avanzada** en CSS que permite definir un ámbito específico dentro del cual se aplican ciertas reglas de estilo. Esto facilita el encapsulamiento de estilos, evitando conflictos globales y mejorando la mantenibilidad del código CSS.

#### Sintaxis Básica

```css
@scope .mi-contenedor {
    /* Reglas CSS aquí solo aplicarán dentro de .mi-contenedor */
    h1 {
        color: blue;
    }

    .boton {
        background-color: green;
    }
}
```

#### Estado Actual de la Regla `@scope`

Hasta la fecha de mi conocimiento (octubre de 2023), la regla `@scope` aún está en etapa de propuesta y **no es soportada de manera nativa** por la mayoría de los navegadores. Por lo tanto, su uso directo en proyectos web estándar **no es factible**. Sin embargo, entender su funcionamiento es beneficioso para futuros desarrollos y para aprovechar otras técnicas de encapsulamiento de estilos disponibles en frameworks modernos como React y Vue.

#### Ejemplo (Propuesta)

```css
@scope .mi-contenedor {
    h1 {
        color: blue;
    }

    .boton {
        background-color: green;
    }
}
```

En este ejemplo, las reglas dentro de `@scope .mi-contenedor` solo se aplicarán a los elementos que estén dentro del contenedor con la clase `mi-contenedor`.

### Otras Nuevas Características

Además de la regla `@scope`, CSS3 ha introducido múltiples nuevas características que mejoran la capacidad de diseño y estilización de las páginas web:

- **Variables CSS (`--variable`):** Permiten definir variables reutilizables para colores, tamaños, etc.

```css
    :root {
        --color-primario: #3498db;
        --padding-base: 10px;
    }

    .boton {
        background-color: var(--color-primario);
        padding: var(--padding-base);
    }
```

- **Propiedades de Sombra (`box-shadow`, `text-shadow`):** Para agregar sombras a elementos y textos.

```css
    .caja {
        box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }

    h1 {
        text-shadow: 2px 2px #ff0000;
    }
```

- **Transformaciones 2D y 3D (`transform`):** Para rotaciones, escalados, traslaciones y más.

```css
    .elemento {
        transform: rotate(45deg) scale(1.2);
    }
```

- **Filtros CSS (`filter`):** Para aplicar efectos visuales como desenfoques y cambios de color.

```css
    img {
        filter: grayscale(50%);
    }
```

- **Clipping y Masking (`clip-path`, `mask`):** Para crear formas complejas y máscaras en elementos.

```css
    .caja {
        clip-path: circle(50%);
    }
```

---

## Buenas Prácticas en CSS

1. **Organización del Código:**
    - Utiliza comentarios para separar secciones.
    - Agrupa selectores relacionados.
    - Sigue una estructura lógica (por ejemplo, de lo general a lo específico).

2. **Nomenclatura Consistente:**
    - Sigue convenciones como **BEM** (Block Element Modifier) para nombrar clases.

```css
    /* BEM Example */
    .tarjeta {
        /* Block */
    }

    .tarjeta__titulo {
        /* Element */
    }

    .tarjeta__titulo--destacado {
        /* Modifier */
    }
```

3. **Evita el Uso Excesivo de `!important`:**
    - No se debe usar porque añade mucha especificidad.

4. **Optimización de Selectores:**
    - Utiliza selectores específicos para mejorar el rendimiento.
    - Evita selectores demasiado generales que puedan afectar a muchos elementos innecesariamente.

5. **Uso de Variables CSS:**
    - Define variables para colores, tamaños y otros valores repetitivos.

```css
    :root {
        --color-primario: #3498db;
        --padding-base: 8px;
    }

    .boton {
        background-color: var(--color-primario);
        padding: var(--padding-base);
    }
```

6. **Compatibilidad entre Navegadores:**
    - Utiliza prefijos de proveedores cuando sea necesario para asegurar la compatibilidad.

```css
    .caja {
        -webkit-border-radius: 8px;
        -moz-border-radius: 8px;
        border-radius: 8px;
    }
```

7. **Minimización y Compresión:**
    - Minimiza los archivos CSS para reducir el tamaño y mejorar la carga.
    - Utiliza herramientas de compresión como **CSSNano** o **UglifyCSS**.

8. **Evita el CSS Innecesario:**
    - Elimina estilos no utilizados para mantener el código limpio y eficiente.

---

## ¿Cómo implemento un Dark mode?

Para implementar un modo oscuro en un proyecto utilizando CSS, puedes seguir estos pasos:

## Definición de Variables CSS

1. **Define las variables para ambos temas**: Utiliza el selector `:root` para establecer las variables CSS globales para el tema claro y oscuro.

```css
   :root {
     /* Tema claro */
     --background-color: #ffffff;
     --text-color: #000000;
     --accent-color: #007BFF;
   }

   [data-theme="dark"] {
     /* Tema oscuro */
     --background-color: #121212;
     --text-color: #E0E0E0;
     --accent-color: #BB86FC;
   }
```

## Aplicación de Variables en el CSS

2. **Utiliza las variables en tus estilos**: Aplica estas variables a los elementos de tu página para que los estilos cambien dinámicamente según el tema seleccionado.

```css
   body {
     background-color: var(--background-color);
     color: var(--text-color);
   }

   a, button {
     color: var(--accent-color);
   }
```

## Cambio de Tema con JavaScript

3. **Implementa un botón de toggle para cambiar el tema**: Usa JavaScript para alternar entre los temas claro y oscuro.

```html
   <button id="toggle-button">Cambiar Tema</button>
```

```javascript
   const toggleButton = document.getElementById("toggle-button");

   toggleButton.addEventListener("click", function() {
     const body = document.body;
     const currentTheme = body.getAttribute("data-theme");
     const newTheme = currentTheme === "dark" ? "light" : "dark";
     body.setAttribute("data-theme", newTheme);
   });
```

## Detección de Preferencias del Usuario

4. **Detecta la preferencia del sistema operativo**: Utiliza la media query `prefers-color-scheme` para aplicar automáticamente el tema según la preferencia del usuario.

```javascript
   const prefersDarkScheme = window.matchMedia("(prefers-color-scheme: dark)");

   if (prefersDarkScheme.matches) {
     document.body.setAttribute("data-theme", "dark");
   } else {
     document.body.setAttribute("data-theme", "light");
   }
```

