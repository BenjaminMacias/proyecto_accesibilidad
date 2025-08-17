# Proyecto Accesibilidad

Sitio de ejemplo centrado en **buenas prácticas de accesibilidad web (a11y)**: navegación por teclado, uso de HTML semántico, roles/atributos ARIA cuando aplica, contraste de color, estados de foco visibles, textos alternativos y soporte a *prefers-reduced-motion*. La meta es orientarse a **WCAG 2.1 AA**.

---

## 🧠 Descripción del proyecto

- Estructura semántica con landmarks (`header`, `nav`, `main`, `footer`).
- **Navegación por teclado**: orden lógico, foco visible, sin trampas de teclado.
- Compatibilidad con **lectores de pantalla** (etiquetas, `aria-*` y relaciones).
- **Contraste** suficiente y tipografía legible.
- Soporte para **reducción de movimiento** (`prefers-reduced-motion`).
- Patrones accesibles en formularios y componentes comunes.

---

## 🧰 Tecnologías utilizadas

- **HTML5** semántico
- **CSS3** (variables, media queries, `prefers-reduced-motion`)
- **JavaScript** (vanilla) para pequeñas mejoras progresivas  
  *(Si usas React en este repo, aplica los mismos patrones en JSX y componentes.)*

---

## ⚙️ Instrucciones de instalación y uso

> Es un proyecto estático. Puedes abrir `index.html` directo o servirlo con un servidor local.

**Opción A — Abrir directo**
```bash
git clone https://github.com/BenjaminMacias/proyecto_accesibilidad.git
cd proyecto_accesibilidad
# Doble clic en index.html o arrástralo al navegador
Opción B — Servidor local (recomendado)

VS Code + Live Server → click derecho en index.html → Open with Live Server.

Node.js:


::contentReference[oaicite:0]{index=0}
