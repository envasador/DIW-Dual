---
hide:
  - navigation
---

# Unidad de Trabajo 6: **"Accesibilidad Web"**

## **Introducción**.
La accesibilidad web es un componente clave del diseño inclusivo. Su objetivo es garantizar que todas las personas, independientemente de sus capacidades físicas, sensoriales, cognitivas o tecnológicas, puedan interactuar con los sitios web y aplicaciones de manera equitativa. En España, la accesibilidad web está regulada por normativas como el Real Decreto 1112/2018, que adapta las directrices europeas al contexto nacional. Sin embargo, más allá de las obligaciones legales, la accesibilidad es un compromiso ético con la igualdad de oportunidades en el entorno digital.

En este contexto, el término *diversidad funcional* se utiliza como una alternativa al concepto de discapacidad, promoviendo una visión más inclusiva y positiva sobre las capacidades humanas. Además, la accesibilidad no solo beneficia a personas con diversidad funcional, sino también a otros grupos como:
- Personas mayores que pueden tener dificultades para usar tecnologías modernas.
- Usuarios con limitaciones temporales (por ejemplo, una lesión en la mano).
- Personas con conexiones lentas a internet o dispositivos antiguos.
- Usuarios en entornos ruidosos o silenciosos que necesitan subtítulos o transcripciones.

Este tema busca proporcionar una guía estructurada para diseñadores y desarrolladores interesados en crear experiencias digitales accesibles para todos.

---

## **Objetivos del Tema**
1. **Concienciar:** Sensibilizar sobre la importancia de la accesibilidad web como un derecho fundamental.
2. **Educar:** Proporcionar conocimientos prácticos sobre las pautas WCAG (Web Content Accessibility Guidelines).
3. **Empoderar:** Ofrecer herramientas y recursos para implementar mejoras de accesibilidad en proyectos digitales.
4. **Fomentar la colaboración:** Promover comunidades inclusivas donde se compartan experiencias y buenas prácticas.

---

## **Contenidos**

### **1. ¿Qué es la Accesibilidad Web?**
La accesibilidad web se refiere al diseño y desarrollo de sitios web, aplicaciones y herramientas digitales que puedan ser utilizados por todas las personas, incluidas aquellas con diversidad funcional (visual, auditiva, motora o cognitiva). También beneficia a otros grupos que pueden enfrentarse a barreras tecnológicas o contextuales.

**Casos donde la accesibilidad es beneficiosa:**

- Personas mayores con disminución en habilidades motoras o sensoriales.
- Usuarios con discapacidades temporales (fracturas, lesiones).
- Personas en situaciones específicas (por ejemplo, leer bajo luz solar intensa).
- Usuarios con dispositivos antiguos o conexiones lentas.
- Personas no nativas del idioma que necesitan contenido claro y comprensible.

**Importancia:**

- **Social:** Promueve la inclusión digital y reduce la brecha tecnológica.
- **Legal:** Cumple con normativas como el Real Decreto 1112/2018 en España.
- **Económica:** Amplía el alcance del público objetivo, mejorando la experiencia del usuario para todos.

---

### **2. Principios Fundamentales de Accesibilidad**
Los principios WCAG 2.1 son esenciales para garantizar que el contenido sea accesible:

#### **Perceptible**
La información debe ser presentada de forma que todos los usuarios puedan percibirla:

- *Ejemplo:* Proporcionar texto alternativo (`alt`) para imágenes.
- *Buenas prácticas:*
    - Asegurar un contraste adecuado entre texto y fondo (mínimo 4.5:1).
    - Ofrecer alternativas textuales a contenido multimedia.

#### **Operable**
Los componentes de la interfaz deben ser utilizables mediante diferentes dispositivos o tecnologías:

- *Ejemplo:* Permitir la navegación mediante teclado.
- *Buenas prácticas:*
    - Evitar tiempos límite estrictos en formularios.
    - Diseñar menús claros y estructurados.

#### **Comprensible**
El contenido debe ser claro y fácil de entender:

- *Ejemplo:* Uso de lenguaje sencillo y directo.
- *Buenas prácticas:*
    - Proporcionar instrucciones claras en formularios.
    - Evitar jerga técnica innecesaria.

#### **Robusto**
El contenido debe ser compatible con tecnologías actuales y futuras:

- *Ejemplo:* Uso correcto de etiquetas semánticas HTML5.
- *Buenas prácticas:*
    - Validar el código para garantizar su correcta interpretación por lectores de pantalla.

---

### **3. Pautas Principales de Accesibilidad**

A continuación se presentan pautas clave organizadas por casos específicos:

1. **Color:**
    - Garantizar un contraste adecuado entre texto y fondo (mínimo 4.5:1).
    - No usar el color como único medio para transmitir información (por ejemplo, errores en formularios).

2. **Contenido:**
    - Usar lenguaje claro y directo.
    - Dividir el contenido en bloques lógicos con encabezados jerárquicos (`<h1>`, `<h2>`).

3. **Encabezados:**
    - Usar etiquetas `<h1>` a `<h6>` correctamente jerarquizadas para estructurar el contenido.
    - Evitar saltos innecesarios en los niveles (por ejemplo, pasar directamente de `<h1>` a `<h4>`).

4. **Enlaces:**
    - Proporcionar textos descriptivos en los enlaces ("Leer más sobre accesibilidad" en lugar de "Haz clic aquí").
    - Evitar enlaces vacíos o redundantes.

5. **Estructura:**
    - Usar etiquetas semánticas HTML (`<header>`, `<main>`, `<footer>`) para definir áreas clave del sitio web.
    - Incluir "enlaces para saltar al contenido" (`skip links`).

6. **Foco:**
    - Asegurar que los elementos interactivos sean claramente visibles cuando reciben foco mediante teclado.
    - No eliminar los estilos predeterminados del foco del navegador.

7. **Formularios:**
    - Añadir etiquetas (`<label>`) descriptivas a cada campo.
    - Proporcionar mensajes claros en caso de error e instrucciones específicas.

8. **Imágenes:**
    - Incluir texto alternativo (`alt`) descriptivo para todas las imágenes relevantes.
    - Usar `aria-hidden="true"` para imágenes decorativas.

9. **Modales:**
    - Asegurarse de que sean navegables mediante teclado.
    - Utilizar `aria-hidden="true"` para ocultar contenido detrás del modal cuando esté activo.

10. **Multimedia:**
    - Incluir subtítulos en vídeos y transcripciones para contenido únicamente en audio.
    - Ofrecer descripciones auditivas para vídeos si contienen información visual importante.

11. **Navegación:**
    - Diseñar menús consistentes e intuitivos.
    - Permitir navegación mediante teclado.

12. **PDF:**
    - Crear documentos PDF etiquetados correctamente para lectores de pantalla.
    - Añadir texto alternativo a imágenes dentro del PDF.

13. **SVG:**
    - Incluir descripciones mediante `title` o `desc` dentro del archivo SVG cuando sea relevante.
    - Usar `role="img"` si se usa SVG como imagen decorativa.

14. **Tablas:**
    - Usar encabezados (`<th>`) correctamente definidos dentro de tablas.
    - Añadir descripciones adicionales mediante `aria-describedby` si es necesario.

---

### **4. Introducción Ampliada a WAI-ARIA**

**WAI-ARIA** (*Web Accessibility Initiative – Accessible Rich Internet Applications*) es un conjunto de especificaciones desarrollado por el W3C para mejorar la accesibilidad de aplicaciones web dinámicas e interactivas.

#### ¿Qué problemas resuelve?
En aplicaciones modernas basadas en JavaScript o frameworks como React o Angular:
1. Los elementos dinámicos no siempre son reconocidos correctamente por tecnologías asistivas (lectores de pantalla).
2. Los cambios dinámicos no se comunican adecuadamente a los usuarios con diversidad funcional.

#### Componentes Clave:

1. **Roles ARIA:**
   Definen el propósito o función de un elemento:
    - Ejemplo: `role="alert"` indica un mensaje importante que debe ser anunciado inmediatamente por lectores de pantalla.
      Roles comunes:
        - `role="button"` (botón interactivo).
        - `role="navigation"` (área destinada a navegación).

2. **Propiedades ARIA:**
   Describen características adicionales del elemento:
    - Ejemplo: `aria-required="true"` señala que un campo es obligatorio.
      Propiedades comunes:
        - `aria-label`: Proporciona una etiqueta personalizada para elementos interactivos.
        - `aria-labelledby`: Relaciona un elemento con su etiqueta visible.

3. **Estados ARIA:**
   Comunican cambios dinámicos en tiempo real:
    - Ejemplo: `aria-expanded="true"` indica si un menú desplegable está abierto o cerrado.
      Estados comunes:
        - `aria-hidden`: Oculta elementos visualmente e informativamente.
        - `aria-busy`: Indica si una sección está cargando contenido dinámico.

#### Ejemplo Completo:

```html
<div role="dialog" aria-labelledby="modal-title" aria-describedby="modal-desc">
  <h2 id="modal-title">Confirmación</h2>
  <p id="modal-desc">¿Estás seguro de que deseas continuar?</p>
  <button role="button" aria-label="Aceptar">Aceptar</button>
  <button role="button" aria-label="Cancelar">Cancelar</button>
</div>
```

**Explicación del código**:
1. El contenedor tiene el rol `dialog` para indicar que es un modal.
2. Se usan `aria-labelledby` y `aria-describedby` para asociar títulos y descripciones al modal.
3. Los botones tienen etiquetas personalizadas (`aria-label`).

#### Buenas Prácticas:
1. Priorizar etiquetas HTML semánticas antes que roles ARIA personalizados siempre que sea posible (`<button>` mejor que `role="button"`).
2. Validar el uso correcto con herramientas como WAVE o Axe Accessibility Checker.
3. Evitar sobrecargar elementos con demasiadas propiedades ARIA innecesarias.
