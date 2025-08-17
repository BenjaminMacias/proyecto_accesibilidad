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

bash
Copiar
Editar
npx http-server -p 5173
# abre http://localhost:5173
Python 3:

bash
Copiar
Editar
python -m http.server 5173
# abre http://localhost:5173
Si este repo es React/Vite:

bash
Copiar
Editar
npm install
npm run dev
# o npm start según tu tooling
🧪 Ejemplos de uso (snippets útiles)
1) Enlace “Saltar al contenido”
html
Copiar
Editar
<a class="skip-link" href="#contenido">Saltar al contenido</a>

<header>…</header>
<nav aria-label="Principal">…</nav>
<main id="contenido" tabindex="-1">…</main>
css
Copiar
Editar
.skip-link{
  position:absolute; left:-9999px; top:auto;
  width:1px; height:1px; overflow:hidden;
}
.skip-link:focus{
  position:static; width:auto; height:auto; padding:.5rem .75rem;
  background:#000; color:#fff; border-radius:.5rem;
}
2) Landmarks semánticos + roles/labels cuando aplica
html
Copiar
Editar
<header role="banner">…</header>
<nav aria-label="Navegación principal">…</nav>
<main role="main">…</main>
<footer role="contentinfo">…</footer>
3) Formularios con etiquetas y feedback accesible
html
Copiar
Editar
<form novalidate>
  <div>
    <label for="email">Correo electrónico</label>
    <input id="email" name="email" type="email" autocomplete="email"
           aria-describedby="email-ayuda">
    <small id="email-ayuda">No compartiremos tu correo.</small>
  </div>

  <div aria-live="polite" id="mensaje-form"></div>

  <button type="submit">Enviar</button>
</form>
4) Foco visible y suficiente contraste
css
Copiar
Editar
:root{
  --c-foco: #66FCF1;
}
:where(a, button, input, textarea, select):focus{
  outline: 3px solid var(--c-foco);
  outline-offset: 2px;
}
5) Reducir animaciones si el usuario lo prefiere
css
Copiar
Editar
@media (prefers-reduced-motion: reduce){
  * {
    animation-duration: 0.001ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.001ms !important;
    scroll-behavior: auto !important;
  }
}
✅ Checklist rápida (WCAG 2.1 AA)
 Teclado: todo es alcanzable y usable con Tab/Shift+Tab/Enter/Espacio/Escape.

 Foco: indicador visible (no lo ocultes).

 Semántica: HTML correcto; usa ARIA solo cuando sea necesario.

 Contraste: texto normal ≥ 4.5:1; grande (≥ 18px bold / 24px normal) ≥ 3:1.

 Imágenes: alt significativo o alt="" si son decorativas.

 Formularios: label asociado, errores anunciados (p.ej. aria-live).

 Estructura: jerarquía de h1…h6 coherente, landmarks claros.

 Movimiento: respeta prefers-reduced-motion.

Herramientas de verificación (sugeridas)
Lighthouse (Chrome DevTools) → pestaña Accessibility.

axe DevTools (extensión).

NVDA (Windows) / VoiceOver (macOS/iOS) para pruebas con lector de pantalla.

Prueba manual con teclado (sin mouse).

makefile
Copiar
Editar
::contentReference[oaicite:0]{index=0}
