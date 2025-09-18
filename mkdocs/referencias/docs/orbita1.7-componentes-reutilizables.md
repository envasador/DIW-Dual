---
hide:
  - navigation
---
# **Órbita 1: Diseñar para que funcione** **Introducción**

![](assets/referencias.jpg)

# **7\. Componentes funcionales (Atomic Design): construir piezas reutilizables**

Una vez que tenemos claro el MVP, los flujos funcionales y los wireframes que estructuran la aplicación, es el momento de identificar qué partes se repiten y pueden convertirse en componentes reutilizables. Este es un paso crucial en cualquier sistema de diseño moderno, ya que permite crear una interfaz coherente, mantenible y escalable.

Aquí es donde entra en juego la metodología **Atomic Design**, propuesta por Brad Frost. Esta técnica nos ayuda a organizar los elementos de la interfaz como si fueran piezas de un sistema: desde los más simples a los más complejos, con el objetivo de que puedan reutilizarse de forma lógica y eficiente.

## **¿Qué es exactamente Atomic Design?**

Atomic Design propone una jerarquía de cinco niveles que nos permite dividir y estructurar cualquier interfaz de manera modular:

1. **Átomos**: son los elementos más básicos e indivisibles de la interfaz, como un botón, un campo de texto o una etiqueta.

2. **Moléculas**: combinaciones simples de átomos que trabajan juntas para cumplir una función. Un buen ejemplo sería un formulario de búsqueda compuesto por un input y un botón.

3. **Organismos**: conjuntos complejos y funcionales de moléculas y átomos. Por ejemplo, una cabecera con logo, menú de navegación y buscador.

4. **Templates**: estructuras de páginas con componentes distribuidos según una jerarquía definida. Sirven de base para organizar contenido.

5. **Pages**: instancias reales del diseño con contenido definitivo, que permiten verificar cómo se comporta todo en conjunto.

Este enfoque no sólo aporta orden, sino que también permite detectar inconsistencias, reducir el número de elementos redundantes y facilitar la colaboración entre diseñadores y desarrolladores.

### **¿Por qué es útil aplicar Atomic Design incluso antes de tener los estilos visuales definidos?**

Puede parecer extraño construir una librería de componentes sin haber definido todavía los colores, tipografías o espaciados. Sin embargo, este enfoque funcional tiene varias ventajas:

* **Permite iterar antes de definir estilos**, centrándonos en cómo funciona la interfaz y no en cómo se ve.

* **Ayuda a validar interacciones y estructuras** de forma rápida, sin necesidad de cerrar detalles estéticos.

* **Fomenta una mentalidad de diseño sistemático**, que facilita el trabajo colaborativo y reduce errores futuros.

Más adelante, cuando se definan los estilos globales (en la siguiente órbita), bastará con aplicar esas decisiones al sistema ya creado, en lugar de rediseñar cada pantalla desde cero.

### **Construir una librería funcional en Figma**

Figma permite trabajar con componentes y variantes de forma nativa. Podemos crear, nombrar, organizar y reutilizar elementos con facilidad, agrupándolos según la jerarquía de Atomic Design. Por ejemplo, un botón puede tener varias variantes: normal, con icono, desactivado…

A medida que los grupos trabajan en sus apps, pueden ir creando una página de componentes dentro de su archivo. Esta página servirá como inventario funcional y como base para el diseño visual futuro.

Es importante que cada componente tenga un nombre claro, una función definida y, si es posible, una pequeña documentación de uso. Esto hace que el sistema sea comprensible para cualquiera que lo revise.

### **Herramientas y extensiones útiles**

Para organizar y mantener bien estructurado el sistema de componentes en Figma, existen algunas herramientas y plugins recomendables:

* **Instance Finder**: permite localizar todas las instancias de un componente, útil para evitar duplicidades.

* **Design System Organizer**: ayuda a categorizar los componentes y mantener una jerarquía clara.

* **Themer**: aunque más avanzado, permite gestionar tokens de diseño como colores o espaciados, incluso antes de definirlos.

* **Styler**: útil para auditar estilos y preparar la transición a diseño visual.

* **Figma Tokens**: para quienes quieran trabajar con variables desde fases tempranas del proyecto.

Estos recursos no son obligatorios, pero pueden facilitar mucho la tarea de mantener un diseño funcional coherente.

## **Ejemplo práctico: identificar componentes en una app de recetas**

Supongamos que hemos diseñado las primeras pantallas de una app de recetas. Podemos observar que hay varios elementos que se repiten: botones, campos de búsqueda, tarjetas con imagen y texto, menús flotantes…

El primer paso sería crear un inventario con estos elementos, clasificarlos por nivel (átomo, molécula, organismo) y construirlos como componentes reutilizables en Figma. Por ejemplo:

* **Átomos**: botón, campo de texto, etiqueta
* **Moléculas**: buscador, tarjeta de receta
* **Organismos**: cabecera, listado de recetas, menú inferior

Estos elementos se pueden usar en múltiples pantallas, garantizando coherencia funcional.

## **Actividad práctica en clase: “Construcción del sistema de componentes”**

Cada grupo revisará su prototipo funcional e identificará al menos cinco componentes reutilizables. En una nueva página de su archivo de Figma:

* Construirán esos componentes y los clasificarán según Atomic Design.
* Añadirán etiquetas y una breve descripción funcional.
* Definirán al menos una variante para cada uno (por ejemplo: activo / inactivo).

Esta actividad no requiere todavía aplicar estilo visual. Su objetivo es estructurar la interfaz funcional como un sistema reutilizable. Además, este sistema servirá de base directa para la siguiente órbita, donde sí aplicaremos colores, tipografías y guías de estilo.

