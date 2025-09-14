---
hide:
  - navigation
---

## Tabla de contenido

* [1 HTML5](ud4-1-HTML5.md)
* [2 CSS3](ud4-2-CSS3.md)
* [2 SASS](ud4-3-SASS.md)
---

# 4.3 **Guía completa de SASS**.
### **1. ¿Qué es SASS?**
SASS (Syntactically Awesome Style Sheets) es un preprocesador de CSS que extiende las capacidades de CSS, permitiendo una escritura más eficiente y estructurada de estilos para proyectos web. Es una herramienta que facilita la creación de hojas de estilo complejas y manejables a largo plazo.

### **2. Ventajas de SASS**

#### **2.1 Variables**
SASS permite definir variables para almacenar valores reutilizables a lo largo de todo el archivo CSS, como colores y tamaños. Sin embargo, es importante señalar que las **variables nativas de CSS** (`var()`) pueden ser una mejor opción en algunos casos, como la creación de un **Dark Mode** dinámico, ya que las variables CSS permiten cambiar temas en tiempo real sin necesidad de recompilar los estilos.

```scss
// Variables en SASS
$primary-color: #3498db;
$font-size-large: 18px;

body {
  color: $primary-color;
  font-size: $font-size-large;
}
```

#### **2.2 Anidación**
SASS permite la anidación de selectores, lo que facilita la organización y lectura del código, especialmente en proyectos complejos:

```scss
.navbar {
  background: $primary-color;

  ul {
    list-style: none;

    li {
      display: inline-block;
      margin: 0 10px;

      a {
        text-decoration: none;
        color: white;
      }
    }
  }
}
```

#### **2.3 Mixins**
Los mixins son bloques reutilizables de código CSS que aceptan parámetros, lo que permite la reutilización y reducción del código duplicado:

```scss
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
  -moz-border-radius: $radius;
  border-radius: $radius;
}

.button {
  @include border-radius(5px);
}
```

#### **2.4 Herencia**
SASS permite la herencia para extender estilos de otros selectores, lo que facilita mantener un diseño consistente:

```scss
%button-style {
  padding: 10px 20px;
  color: white;
  background-color: $primary-color;
  border: none;
}

.primary-button {
  @extend %button-style;
  background-color: darken($primary-color, 10%);
}

.secondary-button {
  @extend %button-style;
  background-color: lighten($primary-color, 10%);
}
```

#### **2.5 Partials**
Los **partials** son archivos `.scss` parciales que contienen fragmentos de código reutilizable. Estos archivos suelen empezar con un guion bajo (`_`) en su nombre, indicando que son archivos auxiliares que no deberían compilarse directamente en CSS. Utilizar partials permite dividir el CSS en módulos pequeños y gestionables, mejorando la organización del proyecto.

Ejemplo de partial:

```scss
// _variables.scss
$primary-color: #3498db;
$font-size-large: 18px;
```

Estos archivos se importan en un archivo principal usando `@import`:

```scss
// main.scss
@import 'variables';
@import 'mixins';
@import 'base';
```

### **3. Variables en SASS vs. Variables en CSS para Dark Mode**
Mientras que las variables en SASS son útiles para definir estilos consistentes, las **variables en CSS** tienen la ventaja de ser dinámicas y ajustables a través de JavaScript. Esto las hace ideales para implementar un **Dark Mode**, donde se puede cambiar el tema sin necesidad de recompilar el CSS.

Ejemplo de uso de variables CSS para Dark Mode:

```css
:root {
  --primary-color: #3498db;
  --background-color: white;
}

body {
  background-color: var(--background-color);
  color: var(--primary-color);
}

/* Modo oscuro */
body.dark-mode {
  --primary-color: #f39c12;
  --background-color: #2c3e50;
}
```

### **4. Integración de SASS en Proyectos Frontend con React y Vue**

#### **4.1 En proyectos con React**
Integrar SASS en un proyecto de React es sencillo. Puedes seguir estos pasos:

1. **Instalación**: Instala `node-sass` (o `sass`) en el proyecto para habilitar la compilación de archivos `.scss`.

   ```bash
   npm install node-sass
   ```

2. **Estructura del proyecto**: Organiza el proyecto utilizando una estructura de carpetas para los archivos `.scss`. Por ejemplo, podrías tener una carpeta `styles` con un archivo `main.scss` que importe todos los partials.

3. **Uso en componentes**: Importa los archivos `.scss` directamente en los componentes de React:

   ```javascript
   import './styles/button.scss';

   const Button = () => {
     return (
       <button className="primary-button">
         Click Me
       </button>
     );
   };

   export default Button;
   ```

#### **4.2 En proyectos con Vue**
Vue tiene una integración excelente con SASS, gracias a la posibilidad de utilizar estilos en el ámbito de cada componente:

1. **Instalación**: Instala `node-sass` o `sass`.

   ```bash
   npm install node-sass sass-loader
   ```

2. **Uso en componentes Vue**: En los componentes Vue, se pueden utilizar estilos en `<style lang="scss">` con la posibilidad de usar partials y mixins:

   ```vue
   <template>
     <div class="card">
       <h1>{{ title }}</h1>
       <button class="primary-button">Click Me</button>
     </div>
   </template>

   <script>
   export default {
     data() {
       return {
         title: 'Tarjeta de Ejemplo'
       };
     }
   };
   </script>

   <style lang="scss">
   @import './variables.scss';

   .card {
     padding: 20px;
     background-color: $primary-color;
     border-radius: 10px;

     .primary-button {
       @include button-style;
     }
   }
   </style>
   ```

### **5. Buenas prácticas en el uso de SASS en proyectos Frontend**

#### **5.1 Estructura de Carpetas**
Organiza los archivos `.scss` en carpetas según su funcionalidad: `base`, `components`, `layout`, `themes`, `mixins`, `utils`, etc. Esto facilita el mantenimiento a medida que el proyecto crece.

#### **5.2 Uso de Variables Globales**
Centraliza las variables en un archivo dedicado (`_variables.scss`) para mantener una coherencia en los colores, fuentes y tamaños. Para temas dinámicos, considera combinar SASS con variables CSS.

#### **5.3 Modularización**
Usa partials, mixins, funciones y módulos para crear estilos reutilizables y evitar la repetición de código.

#### **5.4 SASS Linting**
Utiliza herramientas de linting para mantener el código limpio y consistente según las buenas prácticas.

