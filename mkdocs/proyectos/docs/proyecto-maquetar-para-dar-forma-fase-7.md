---
hide:
  - navigation
---

## **Fases del proyecto**

### **Fase 7: Accesibilidad web**

**Criterios:** RA5.a, RA5.b, RA5.c, RA5.g

#### **Tareas:**

1. **Implementar requisitos WCAG 2.1 nivel A**

   * Contraste de color mínimo 4.5:1 (texto normal) y 3:1 (texto grande)
   * Navegación por teclado funcional en todos los elementos interactivos
   * Estados :focus visibles y claros
   * Textos alternativos descriptivos en imágenes
   * Estructura de headings lógica sin saltos
2. **Atributos ARIA donde sea necesario**

   * aria-label, aria-labelledby, aria-describedby
   * aria-live para contenido dinámico
   * aria-expanded, aria-controls en elementos interactivos
   * roles ARIA cuando los landmarks no sean suficientes
3. **Testear con herramientas de accesibilidad**

   * Lighthouse Accessibility (mínimo 90\)
   * WAVE o axe DevTools
   * Navegación solo con teclado
   * Lector de pantalla (NVDA/VoiceOver) en página principal
4. **Sección en DOCUMENTACION.md: "7. Informe de accesibilidad"**

   * Importancia de la accesibilidad web
   * Principios WCAG implementados (Perceptible, Operable, Comprensible, Robusto)
   * Criterios de nivel A cubiertos
   * Capturas de tests (Lighthouse, WAVE)
   * Problemas encontrados y soluciones aplicadas
   * Test de navegación por teclado
   * Test con lector de pantalla
   * Verificación en diferentes navegadores
   * Checklist de verificación completada

#### **Entregables:**

* \[ \] Contraste verificado y corregido
* \[ \] Navegación por teclado funcional
* \[ \] ARIA implementado apropiadamente
* \[ \] Tests con mínimo 2 herramientas
* \[ \] Sección 7 del DOCUMENTACION.md completada
