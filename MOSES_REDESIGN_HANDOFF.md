# Moses Executive Studio — Rediseño Dirección A · Handoff (sin publicar)

Fecha: 2026-10-13 · Integrado por The303. **No se ha publicado nada (sin `git push`).**

## Qué quedó hecho (listo para revisar)

Integración del prototipo de Claude Design (Dirección A "estudio de autor") en el repo real, con las **fotos reales optimizadas** (no las miniaturas de referencia):

- **`index.html`** — Home nueva: portada dividida con el retrato de Moses (P02), tres tarjetas de servicio (Haircuts / Beard & Detail / Personal), Experience Attention/Craft/Finish, About con P01 (sin bio de prueba), "Craft, in Detail" (4 fotos) y Journal fotográfico. Conserva marca, Bodoni Moda + Instrument Sans, datos del negocio y la reserva Vagaro.
- **`blog.html`** — Journal fotográfico (desde `Journal.dc.html`).
- **`blog-beard-boardroom.html`** — artículo destacado con el nuevo diseño (desde `Journal Article.dc.html`).
- **`support.js`** — runtime DC actualizado (el que usan los prototipos). Solo `index.html` lo usa.
- **`photos/studio/`** — 17 fotos seleccionadas, exportadas desde los originales en AVIF + WebP + JPEG a 640/1024/1600 px, con `srcset`/`sizes`, nombres descriptivos y las monocromas (P01, C01, C03, D04, B05) en blanco y negro como pide el brief. Portada con `fetchpriority`, resto `lazy`.

## Cómo verlo (el panel de preview no renderiza DC)

El framework DC necesita ejecutar `support.js` en un navegador real. Para revisarlo:
- Ábrelo con un servidor local desde la carpeta del repo, p. ej.: `python -m http.server 8080` y entra a `http://localhost:8080/index.html` (así cargan `support.js`, las fuentes y las fotos con rutas relativas).
- O súbelo a un preview de Vercel (no producción).

## Pendiente dentro del diseño (fase siguiente)

- **Re-pielar los 4 artículos restantes** a la nueva plantilla (`blog-beard-boardroom.html`), conservando su texto aprobado y con estas fotos asignadas por el brief:
  - `blog-executive-haircut.html` → C05, D02, C06, C08 (scissor-work, scissor-detail, hair-texture, haircut-finish).
  - `blog-private-studio.html` → C02, C01, B02, P01 (studio-mirror-work, at-work-bw, personal-attention, founder-portrait).
  - `blog-royal-shave.html` → B02/B03 (atmósfera; **no** afirmar pasos de toalla caliente, que la sesión no documenta).
  - `blog-executive-routine.html` → C08, C06, P02 (haircut-finish, hair-texture, profile-scissors).
- Tras aprobar, retirar las fotos antiguas `photos/1.jpg`…`8.jpg` (legacy, ya no se usan en la home).

## Pendiente fuera del diseño (datos/terceros, del brief)

- **Hours:** conectar el bloque de horario al dato existente del sitio (hoy muestra un marcador "Connected to the site's existing hours data").
- **Reviews:** la nav/footer enlazan a `reviews.html`; dentro de esa página falta sustituir `#GBP_REVIEW_LINK` por la URL real de Google o retirar el enlace.
- **Black Mask (Vagaro):** corregir en Vagaro la descripción (hoy muestra texto de arreglo de barba). No se arregla desde la web.
- **Biografía de Moses:** el About usa un párrafo de filosofía sin datos inventados; falta formación/trayectoria aprobadas por Moses.
- **Autorización de uso comercial** de las personas fotografiadas antes de publicar.

## Limpieza

Borrar estos 3 archivos temporales de QA (el sandbox no los dejó borrar por permisos): `_qa_preview.html`, `_mini_test.html`, `_contact_sheet.html`.

## Rutas (mapa del prototipo → real)

`Home.dc.html` → `index.html` · `Journal.dc.html` → `blog.html` · `Journal Article.dc.html` → `blog-beard-boardroom.html`. Todos los CTA → `book.html` (Vagaro). Reviews / Privacy / Terms / SMS sin cambios.

## Cambio solicitado por Moses (2026-10-14)

- **Portada:** Moses prefirió el retrato **de frente, sonriendo, con las tijeras** (archivo `WhatsAppImage...PMs.jpeg`, 1261×1935) en lugar del perfil original (P02). Ya está puesto en el héroe de `index.html` como `moses-portrait-front` (AVIF/WebP/JPEG 640/1024/1261, `object-position:35% 35%` para mantener la cara a la izquierda y las tijeras). Nota: es una foto de buena resolución pero no de la sesión profesional completa; suficiente para el tamaño del héroe.
- **Selfie** (secador + trimmer dorado, mandil FACON, `WhatsAppImage...PM.jpeg`, 1290×1577): exportado como `moses-selfie-tools` (640/1024/1290) y **a la espera de decidir dónde va** (no colocado aún; es un selfie informal, no encaja en el About sobrio tal cual).
- Temporales de QA a borrar: `_qa_preview.html`, `_mini_test.html`, `_contact_sheet.html`, `_hero_preview.html`.
