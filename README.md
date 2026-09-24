# FAQ del Call Center — Lunas y Mecánica

Página de consulta rápida para los agentes del Call Center: qué responder al cliente,
con buscador y dos pestañas.

- **CC Lunas** — 33 preguntas del servicio de lunas, revisadas con el propio Call Center.
- **CC Mecánica** — 82 entradas de mecánica rápida (Aurgi / Motortown), con la ruta del IVR
  y los criterios de actuación de cada servicio.

## Cómo se usa

Se abre la página y se escribe lo que está diciendo el cliente. El buscador ignora tildes
y mayúsculas, busca dentro de la pregunta y de la respuesta, y acepta varias palabras.
`/` salta al buscador, `Esc` lo borra.

## Cómo se edita

Todo vive en `index.html`: un único fichero, sin dependencias ni proceso de build.
Cada pregunta es un bloque de esta forma:

```html
<div class="faq">
  <h3>La pregunta del cliente</h3>
  <div class="say"><span class="say-label">Qué decir</span><p>«La frase que se le dice.»</p></div>
</div>
```

Para añadir una pregunta basta con copiar ese bloque dentro de la sección que toque.
El buscador y los contadores se actualizan solos.

Las preguntas marcadas con `<span class="tag validar">Pendiente de confirmar</span>` aún no
están validadas por Negocio o Prestaciones: **no deben darse como respuesta oficial.**

## Publicación

GitHub Pages sirve el `index.html` de la rama principal. El fichero `.nojekyll` evita que
Jekyll procese el contenido.

La página lleva `<meta name="robots" content="noindex, nofollow">` para no aparecer en
buscadores. Sigue siendo accesible para cualquiera que tenga el enlace: si se quiere que
Google la indexe, se quita esa línea del `<head>`.
