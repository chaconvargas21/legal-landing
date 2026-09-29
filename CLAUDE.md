# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Qué es este repositorio

Tres propuestas alternativas de landing page para el estudio jurídico **Asesores Legales JC** (abogado Juan Carlos Chacón Farfán, Wanchaq, Cusco). Cada `propuesta-N.html` es un archivo único y autocontenido: HTML + `<style>` + `<script>` inline, sin build, sin dependencias, sin tests. Para verlas, basta con abrir el archivo en el navegador.

Todo el contenido visible está en español (`lang="es"`), con ortografía y tildes correctas.

## Las tres propuestas

Comparten el mismo contenido y estructura de secciones (`#inicio`, `#servicios`, `#casos`, `#oficina`, `#contacto`), pero difieren en dirección visual:

- `propuesta-1.html` — "Clásico/Institucional": verde bosque y bronce, Cormorant Garamond + Mulish, hero partido texto/retrato, secciones en dos columnas con filete.
- `propuesta-2.html` — "Andino/Comunidad": añil, cochinilla y maíz, Alegreya + Alegreya Sans, franja de *tocapu* (CSS gradients) como separador, banner panorámico.
- `propuesta-3.html` — "Moderno/Directo": cobalto sobre blanco, Archivo (ancho variable) + Figtree, pensado para móvil, número de WhatsApp como titular y barra fija inferior (`.dock`).

Segunda ronda (hecha con el skill impeccable, ver `PRODUCT.md` y los contratos de dirección en `.impeccable/surfaces/`):

- `propuesta-4.html` — "Plano": lámina de plano catastral; curvas de nivel generadas por JS, lindero con hitos como navegación, rótulo como ficha de contacto. Rojo de lindero reservado a acciones.
- `propuesta-5.html` — "Expediente": carpeta manila, carátula con campos mecanografiados, folios, sello violeta "RECIBIDO" con la fecha real que se estampa al hacer scroll.
- `propuesta-6.html` — "Cartel chicha": fondo negro, tintas fluorescentes, número de WhatsApp gigante, muro de carteles que se pegan al entrar.

Si se cambia un dato de negocio, hay que actualizarlo en todas las propuestas.

Imágenes de las propuestas 4–6: cada `<img src="img/…">` se elimina sola si el archivo no existe (`onerror`) y entonces se ve el prompt de Higgsfield; al existir, la clase `has-img` oculta el prompt. La lista de archivos y prompts está en `img/PROMPTS.md`. Higgsfield no está conectado como herramienta: el usuario genera las imágenes.

## Datos del negocio (fuente de verdad)

- Celular/WhatsApp: 984 208 032 (`tel:+51984208032`, `https://wa.me/51984208032`)
- Correo: asesoreslegalesjc@hotmail.com
- Dirección: Ofic. 209, 2.º piso, Inmueble N.º 1115-C, Av. Tomasa Tito Condemayta, Wanchaq, Cusco, Perú
- Servicio: asesoría legal general. Casos de éxito: comunidades campesinas, municipalidades, personas naturales y jurídicas.

## Convenciones comunes

- **Tokens de color en `:root`** con modo oscuro duplicado en dos lugares: `@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){…}}` y `:root[data-theme="dark"]{…}`. Al añadir o cambiar un token, actualizar los tres bloques.
- Fuentes solo desde Google Fonts; nada de otros CDNs.
- Responsive con un único breakpoint (~780–820px) que colapsa las grillas a una columna; gutter lateral `1.25rem` en `.wrap`.
- **Placeholders de imagen**: las imágenes reales aún no existen. Cada hueco es un `<figure class="ph">` (o `.img`/`.phnote`) con fondo en gradiente CSS y un `figcaption` con la etiqueta "Imagen Higgsfield · …" y el prompt descriptivo para generarla. Al sustituir por imágenes reales, conservar la proporción (`aspect-ratio`) indicada.
- Botones "Copiar" usan `data-copy="…"`; el script al final de cada archivo intenta `navigator.clipboard` y, si falla, selecciona el texto del enlace hermano.
