---
hide:
  - navigation
---

# Unidad de Trabajo 7: **"Implantación del SEO en una Aplicación Web"**
## 1. Introducción al SEO
**Qué es el SEO:**
Search Engine Optimization (SEO) es el conjunto de técnicas y estrategias que permiten mejorar la visibilidad de una página web en los motores de búsqueda como Google. El objetivo principal es posicionar una web entre los primeros resultados, incrementando el tráfico orgánico.

**Tipos de SEO:**

- **SEO On-page:** Optimización de contenido y estructura del sitio web.
- **SEO Off-page:** Estrategias externas, como backlinks y redes sociales.
- **SEO Técnico:** Optimizaciones que afectan al rastreo y rendimiento del sitio web.

## 2. SEO On-page con HTML
**Buenas prácticas:**

- Utilizar etiquetas semánticas como `<header>`, `<main>`, `<footer>`, `<article>`, para estructurar el contenido.
- Incluir un `<title>` descriptivo en cada página.
- Configurar `<meta>` con descripciones claras y precisas es crucial para el SEO. Estas etiquetas ayudan a los motores de búsqueda a entender el propósito y el contenido de la página. Por ejemplo:

- **`<meta name="description">`**: Proporciona un resumen breve del contenido de la página, que puede aparecer como fragmento en los resultados de búsqueda. Ejemplo:
  ```html
  <meta name="description" content="Tienda online con las mejores ofertas en tecnología y gadgets." />
  ```

- **`<meta name="keywords">`** (aunque en desuso en muchos motores de búsqueda): Permite incluir palabras clave relacionadas con el contenido.

- **`<meta charset>`**: Define la codificación de caracteres para garantizar una correcta visualización del texto.
  ```html
  <meta charset="UTF-8" />
  ```

Incluir estas etiquetas correctamente puede mejorar tanto la visibilidad como la relevancia de la página en los resultados de búsqueda.
- Usar `<h1>` para el título principal y `<h2>`, `<h3>` para subsecciones.

**Ejemplo:**
```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Aplicación web para gestionar tareas de manera eficiente">
  <title>Gestor de Tareas</title>
</head>
<body>
  <header>
    <h1>Bienvenido a Gestor de Tareas</h1>
  </header>
  <main>
    <article>
      <h2>Organiza tu día</h2>
      <p>Con nuestra aplicación podrás priorizar y gestionar tus tareas fácilmente.</p>
    </article>
  </main>
</body>
</html>
```

**URLs amigables:**

- Evitar URLs como `/productos?id=123`.
- Usar URLs claras y descriptivas como `/productos/zapatillas-deportivas`.

**Canonical tags:** Son etiquetas utilizadas para evitar problemas de contenido duplicado en un sitio web. Indican a los motores de búsqueda cuál es la URL preferida para una página específica, asegurando que el tráfico y la autoridad de SEO no se dividan entre múltiples URLs similares o idénticas. Por ejemplo, si un producto está disponible en varias URLs debido a parámetros de seguimiento o filtros, se puede usar una etiqueta canonical para consolidar la autoridad SEO en una sola URL.
```html
<link rel="canonical" href="https://miweb.com/productos/zapatillas-deportivas">
```

### 3. SEO On-page con CSS
**Optimizaciones clave:**

- Reducir el tamaño de los archivos CSS usando minificación.
- Asegurarse de que los diseños sean **responsive**.
- Utilizar la propiedad `font-display: swap` en fuentes externas para mejorar la carga.

**Ejemplo de fuentes externas:**
```css
@font-face {
  font-family: 'Roboto';
  font-style: normal;
  font-weight: 400;
  src: url('roboto.woff2') format('woff2');
  font-display: swap;
}
```

### 4. SEO On-page con JavaScript
**Precauciones:**

- Evitar bloquear el renderizado con scripts pesados.
- Garantizar que el contenido crítico sea accesible aunque el JavaScript no se ejecute.

**Renderizado en el cliente vs servidor:**

- **Cliente:** React renderiza la aplicación en el navegador, lo que significa que el HTML y el contenido se generan dinámicamente en el dispositivo del usuario. Aunque esta técnica puede ofrecer una experiencia interactiva más rápida, no siempre es ideal para el SEO, ya que los motores de búsqueda podrían tener dificultades para interpretar el contenido generado dinámicamente.

- **Servidor (SSR):** React genera HTML en el servidor y envía un documento completamente renderizado al cliente. Esto mejora significativamente el SEO, ya que el contenido completo está disponible para los motores de búsqueda al momento del rastreo. Una implementación común es el uso de frameworks como Next.js, que facilita el SSR y permite manejar tanto el rendimiento como el SEO de forma eficiente. Por ejemplo:
```javascript
import React from 'react';
import Head from 'next/head';

export default function Home() {
  return (
    <div>
      <Head>
        <title>Página SSR Optimizada</title>
        <meta name="description" content="Página web con renderizado del lado del servidor para mejorar el SEO." />
      </Head>
      <h1>Bienvenido a una página con SSR</h1>
      <p>Esta página está optimizada para buscadores.</p>
    </div>
  );
}
```
**Ejemplo con React Helmet:**
```jsx
import { Helmet } from 'react-helmet';

function HomePage() {
  return (
    <div>
      <Helmet>
        <title>Gestor de Tareas</title>
        <meta name="description" content="Aplicación web para gestionar tareas de manera eficiente" />
      </Helmet>
      <h1>Bienvenido a Gestor de Tareas</h1>
    </div>
  );
}
```

### 5. SEO Técnico
**Archivo robots.txt:**

El archivo `robots.txt` es esencial para informar a los motores de búsqueda qué páginas o secciones de un sitio web pueden rastrear. Es particularmente útil para evitar que áreas como `/admin/` o páginas de prueba sean indexadas.

Ejemplo de archivo básico:
```txt
User-agent: *
Disallow: /admin/
Sitemap: https://miweb.com/sitemap.xml
```

- `User-agent: *` permite definir reglas para todos los rastreadores.
- `Disallow: /admin/` restringe el acceso al directorio `/admin/`.
- `Sitemap:` proporciona la ubicación del sitemap del sitio, facilitando el rastreo.

**Sitemap XML:**

Un sitemap es un archivo que enumera todas las URLs de un sitio web, ayudando a los motores de búsqueda a identificar y rastrear su contenido.

Ejemplo básico de sitemap:
```xml
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://miweb.com/</loc>
    <lastmod>2025-01-01</lastmod>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://miweb.com/about</loc>
    <lastmod>2025-01-02</lastmod>
    <priority>0.8</priority>
  </url>
</urlset>
```

- `<loc>` define la URL de la página.
- `<lastmod>` indica la última fecha de modificación.
- `<priority>` establece la prioridad relativa de la URL para el rastreo.

**Optimización de velocidad:**

- **Compresión de imágenes:** Usar formatos como WebP que reducen el tamaño de las imágenes sin sacrificar calidad.
- **Habilitar Gzip:** Comprimir respuestas HTTP desde el servidor para acelerar la transferencia de datos.
- **Minificar archivos:** Reducir el tamaño de archivos CSS y JavaScript eliminando espacios y comentarios innecesarios.

### 6. SEO Off-page
**Backlinks:**

- Crear contenido valioso, como guías, tutoriales o estudios originales, para atraer enlaces de otras webs. Por ejemplo, un artículo detallado sobre "Mejores prácticas de SEO para desarrolladores MERN" puede ser enlazado por blogs del sector.
- Participar en comunidades relacionadas con el sector, como foros especializados o plataformas como Reddit, respondiendo preguntas y compartiendo contenido útil que enlace a tu página.
- Colaborar con otras páginas o blogs en publicaciones conjuntas, donde se intercambien enlaces de manera natural y relevante.
- Publicar contenido en plataformas externas como Medium o LinkedIn, incluyendo enlaces estratégicos hacia tu sitio principal.

