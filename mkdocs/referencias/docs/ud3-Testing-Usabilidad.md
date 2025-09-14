---
hide:
  - navigation
---

# Unidad de trabajo 3: **Pruebas de Usabilidad en Prototipos de Productos Digitales**

Las pruebas de usabilidad en prototipos permiten evaluar cómo interactúan los usuarios con un producto digital en su fase de diseño, antes de ser completamente desarrollado. Estas pruebas buscan identificar problemas de usabilidad y mejorar la experiencia de usuario, asegurando que la interfaz sea intuitiva, clara y fácil de usar. Al realizar estas pruebas, el equipo de desarrollo puede hacer ajustes en los diseños con base en el feedback y las métricas obtenidas, lo que ahorra tiempo y recursos en etapas posteriores.

Maze, una herramienta de testing de usabilidad, permite realizar distintos tipos de pruebas directamente en prototipos creados en Figma, brindando métricas y análisis detallados que ayudan a optimizar los diseños. A continuación, se describen los principales tipos de pruebas de usabilidad que se pueden realizar en Maze.

### 1. **Test de Misiones (Mission Test)**
- **Objetivo:** Evaluar si los usuarios pueden completar tareas específicas, como encontrar un botón o finalizar un proceso.
- **Configuración:**
    1. En Figma, asegúrate de que el prototipo esté conectado y listo para ser exportado a Maze.
    2. Importa el prototipo desde Figma a Maze.
    3. Crea una "Misión" en Maze e introduce instrucciones claras para cada tarea que quieres que los usuarios realicen.
    4. Puedes definir una ruta ideal que los usuarios deben seguir para completar la misión, lo que permite a Maze detectar dónde se equivocan.
- **Resultados:** Podrás ver el tiempo que los usuarios tardaron en completar la misión, el porcentaje de éxito, y dónde hicieron clics incorrectos, lo cual es útil para identificar posibles puntos de fricción en la interfaz.

### 2. **Test de Rutas (Path Test)**
- **Objetivo:** Verificar la navegación del usuario y entender cómo interactúan con la interfaz para realizar determinadas acciones.
- **Configuración:**
    1. Al crear una nueva prueba en Maze, selecciona "Path Test" y define un objetivo claro (por ejemplo, “encontrar la sección de contacto”).
    2. Define la ruta o flujo de pantallas que los usuarios deben seguir para cumplir con el objetivo.
    3. Importa el prototipo y selecciona las pantallas específicas que forman parte de esta ruta.
- **Resultados:** Maze mostrará qué ruta tomó cada usuario, si se desviaron del flujo ideal, y cuánto tiempo pasaron en cada pantalla, lo cual permite ajustar el diseño para que la navegación sea más intuitiva.

### 3. **Test de Cuestionarios (Survey Test)**
- **Objetivo:** Recoger la percepción del usuario sobre ciertos elementos de la interfaz o sobre su experiencia general.
- **Configuración:**
    1. Crea un nuevo cuestionario en Maze y añade preguntas sobre la experiencia del usuario en áreas como diseño, claridad de navegación y accesibilidad.
    2. Puedes utilizar preguntas de opción múltiple, respuestas abiertas, o incluso calificaciones (por ejemplo, una escala del 1 al 5).
- **Resultados:** Los cuestionarios brindan datos cualitativos que permiten obtener feedback directo de los usuarios sobre su experiencia y percepción del diseño.

### 4. **Prueba de Primer Clic (First Click Test)**
- **Objetivo:** Evaluar dónde hacen clic primero los usuarios al ver una pantalla específica para medir si la interfaz es intuitiva.
- **Configuración:**
    1. Selecciona el tipo de test "First Click" en Maze y carga la pantalla que quieres analizar.
    2. Define el área donde deberían hacer clic según el flujo ideal de la aplicación.
- **Resultados:** Maze proporciona un mapa de calor y un análisis de cuánto tiempo tardaron los usuarios en hacer su primer clic, ayudando a identificar problemas de diseño que pueden afectar la intuición de la interfaz.

### 5. **Test de los 5 Segundos (5-Second Test)**
- **Objetivo:** Evaluar la claridad y la comprensión inicial de una pantalla en solo 5 segundos, viendo qué información retiene el usuario y si entiende su propósito principal.
- **Configuración:**
    1. Importa el prototipo de Figma a Maze y selecciona la pantalla que quieres probar.
    2. En Maze, crea una prueba nueva y selecciona "5-Second Test".
    3. Configura el test para mostrar la pantalla durante exactamente 5 segundos.
    4. Define preguntas específicas para el test, como:
        - "¿Cuál era el propósito principal de la página?"
        - "¿Qué elementos recuerdas haber visto?"
    5. Puedes personalizar el tipo de preguntas para obtener respuestas específicas sobre la percepción inicial de la interfaz.
- **Resultados:** El test de los 5 segundos recopila respuestas cualitativas que indican si los usuarios comprenden los elementos clave de la pantalla en un primer vistazo, ayudando a mejorar la comunicación visual.

### 6. **Test de Expectativa Visual (Heatmap Test)**
- **Objetivo:** Ver qué áreas de la pantalla llaman más la atención de los usuarios.
- **Configuración:**
    1. Maze genera automáticamente mapas de calor al realizar otros test, como el de Misiones o Primer Clic.
    2. Configura las áreas de interés en las que quieres ver la interacción.
- **Resultados:** Un mapa visual donde se observa el interés del usuario en diferentes partes de la pantalla, lo cual es útil para optimizar la interfaz en función de la atención.

### Consejos para la Configuración de los Test
- **Prepara instrucciones claras** en cada misión para evitar malentendidos.
- **Revisa las rutas ideales** antes de importar el prototipo en Maze para asegurarte de que los objetivos estén bien definidos.
- **Añade preguntas de seguimiento** después de cada misión para obtener feedback adicional.

---

Cada uno de estos tests proporciona datos únicos y valiosos para comprender cómo interactúan los usuarios con el diseño. Al realizar diferentes tipos de pruebas, los diseñadores y desarrolladores pueden obtener una visión detallada del rendimiento de la interfaz y tomar decisiones fundamentadas para mejorar la experiencia de usuario antes de pasar a desarrollo.
