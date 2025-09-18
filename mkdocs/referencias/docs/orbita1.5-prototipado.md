---
hide:
  - navigation
---
# **Órbita 1: Diseñar para que funcione** **Introducción**

![](assets/referencias.jpg)

# **5\. Prototipado navegable lo-fi: simular antes de construir**

Una vez tenemos los wireframes de baja fidelidad que representan la estructura funcional de nuestra app, el siguiente paso es **hacerlos interactivos**. Es decir, convertir esos bocetos estáticos en un **prototipo navegable**, que permita simular cómo sería la experiencia real del usuario al moverse entre pantallas.

Este tipo de prototipos no son todavía productos terminados ni tienen estilos visuales definitivos. Son maquetas funcionales que ayudan a comprobar si los flujos tienen sentido, si las acciones están claras y si la navegación es intuitiva.

Antes de escribir una sola línea de código, debemos tener claro que la estructura de la app funciona. Y la mejor forma de comprobarlo es navegándola.

## **¿Qué es un prototipo navegable?**

Un prototipo navegable es una simulación interactiva de una aplicación o sitio web, en la que se pueden realizar acciones como hacer clic en botones, cambiar de pantalla o simular una interacción básica.

No se trata de una app real, pero **se comporta como si lo fuera**, permitiendo recorrer sus pantallas como lo haría un usuario final.

## **¿Para qué sirve un prototipo navegable?**

* **Validar la experiencia de usuario** sin necesidad de desarrollo.
* **Detectar errores en el flujo** o confusiones en la interacción.
* **Testear con usuarios reales o con otros grupos**.
* **Comunicar la propuesta de forma clara** a personas no técnicas.

## **¿Cómo se construye?**

En herramientas como **Figma**, el proceso es sencillo:

1. Crear un archivo con los **frames** de cada pantalla (por ejemplo, los wireframes).
2. Ir a la pestaña **Prototype** y enlazar elementos interactivos:
  * Botones que llevan a otras pantallas
  * Íconos que abren menús
  * Áreas clicables que simulan navegación
3. Ajustar transiciones, animaciones básicas o efectos simples si es necesario.
4. Compartir el prototipo mediante un **link interactivo** para que otros puedan probarlo.

### ***Buenas prácticas para prototipos navegables***

* No añadas estilos visuales si aún no están definidos: céntrate en **la lógica funcional**.
* Usa nombres claros para las pantallas: “Login”, “Home”, “Carrito”, etc.
* Asegúrate de que **todas las acciones posibles** estén conectadas a algún resultado visible.
* Simula solo lo necesario para validar el flujo: **menos es más** en esta fase.
* Si algo no funciona aún, indícalo como “pantalla en desarrollo” o “interacción no implementada”.

## **Ejemplo práctico: app de recetas**

Supongamos que ya tenemos wireframes para estas pantallas:

* Pantalla de inicio (buscar recetas)
* Ficha de receta
* Registro de usuario
* Crear receta

Ahora en Figma enlazamos:

* El botón de “Buscar” lleva a una lista de resultados.
* Cada resultado lleva a la ficha de receta.
* Desde cualquier pantalla se puede ir al registro.
* El botón de “Crear receta” abre un formulario básico.

El resultado es un flujo de navegación funcional que podemos **probar, enseñar y corregir** antes de empezar a programar.

## **Recursos de referencia**

* [Figma: cómo crear prototipos](https://help.figma.com/hc/en-us/articles/360040451373-Create-interactive-prototypes)
---

## **Actividad práctica en clase**

**Título**: *“Prototipa tu idea”*

Cada persona partirá de los **wireframes creados en el punto anterior** y los transformará en un **prototipo navegable**.

**Instrucciones:**

1. Usaréis Figma para montar sus pantallas.
2. Enlazaréis botones y elementos interactivos para simular al menos **tres flujos completos de usuario** (por ejemplo: buscar \> ver \> añadir, o registro \> login \> inicio).
3. Compartiréis el enlace del prototipo con otros grupos.
4. Cada grupo hará una **prueba cruzada**: usar el prototipo de otro grupo y dejar comentarios sobre la claridad del flujo.

**Objetivo de la actividad:**

* Comprobar si el diseño funciona sin explicaciones externas.
* Detectar puntos de confusión o pantallas innecesarias.
* Preparar la validación del diseño antes del desarrollo.

Este prototipo es el entregable funcional previo al desarrollo. Su validación es parte del proceso iterativo del proyecto conjunto.
