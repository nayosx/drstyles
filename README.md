# drstyles

Librería de estilos SCSS utilitaria + componentes, orientada a proyectos web rápidos con clases predefinidas para:

- layout
- grid
- flex
- tipografía
- colores
- spacing
- botones
- tablas
- formularios
- dialog
- sidebar/navbar

## Instalación

```bash
npm install drstyles
```

## Uso rápido

### Opción 1: usar el CSS compilado

```html
<link rel="stylesheet" href="node_modules/drstyles/dist/styles.min.css" />
```

### Opción 2: usar SCSS y compilar en tu proyecto

```scss
@use "drstyles/src/main";
```

## Desarrollo local

```bash
npm install
npm run build
```

Esto compila:

- `src/main.scss` -> `dist/styles.min.css`

## Convenciones de clases

- `u-`: utilities (ejemplo `u-text-center`, `u-bg-blue`, `u-btn`)
- `l-`: layout objects de página (ejemplo `l-general`, `l-panel`)
- `o-`: object reusable de estructura (ejemplo `o-grid`, `o-grid__item`)

## Breakpoints

Configurados en `src/settings/_settings.scss`:

- `sm: 576px`
- `md: 768px`
- `lg: 992px`
- `xl: 1200px`

## Grid System

La librería tiene 2 sistemas de grid:

- grid clásico (`.container`, `.row`, `.col-*`) para compatibilidad existente
- grid BEMIT (`.o-grid`) basado en `display: grid`

### 1) Grid clásico

```html
<div class="container">
  <div class="row">
    <div class="col-12 col-md-8">Contenido principal</div>
    <div class="col-12 col-md-4">Sidebar</div>
  </div>
</div>
```

Clases disponibles:

- `.container`, `.container-fluid`
- `.row`
- `.col-1` ... `.col-12`
- `.col-sm-1` ... `.col-sm-12`
- `.col-md-1` ... `.col-md-12`
- `.col-lg-1` ... `.col-lg-12`
- `.col-xl-1` ... `.col-xl-12`

### 2) Grid BEMIT (`o-grid`)

Objeto base:

```html
<div class="o-grid">
  <div class="o-grid__item">A</div>
  <div class="o-grid__item">B</div>
  <div class="o-grid__item">C</div>
</div>
```

Control de columnas:

```html
<div class="o-grid o-grid--cols-1 o-grid--md-cols-2 o-grid--lg-cols-4">
  <article class="o-grid__item">1</article>
  <article class="o-grid__item">2</article>
  <article class="o-grid__item">3</article>
  <article class="o-grid__item">4</article>
</div>
```

Control de span/start/end:

```html
<div class="o-grid o-grid--cols-12 o-grid--gap-3">
  <aside class="o-grid__item o-grid__item--span-12 o-grid__item--lg-span-3">
    Sidebar
  </aside>
  <main class="o-grid__item o-grid__item--span-12 o-grid__item--lg-span-9">
    Main
  </main>
</div>
```

```html
<div class="o-grid o-grid--cols-12">
  <div class="o-grid__item o-grid__item--start-2 o-grid__item--end-8">
    Bloque posicionado por líneas de grid
  </div>
</div>
```

Modificadores disponibles:

- `.o-grid--dense`
- `.o-grid--cols-1` ... `.o-grid--cols-12`
- `.o-grid--gap-1` ... `.o-grid--gap-16`
- `.o-grid--gap-x-1` ... `.o-grid--gap-x-16`
- `.o-grid--gap-y-1` ... `.o-grid--gap-y-16`
- `.o-grid--sm-cols-*`, `.o-grid--md-cols-*`, `.o-grid--lg-cols-*`, `.o-grid--xl-cols-*`

Items disponibles:

- `.o-grid__item`
- `.o-grid__item--span-1` ... `.o-grid__item--span-12`
- `.o-grid__item--start-1` ... `.o-grid__item--start-12`
- `.o-grid__item--end-2` ... `.o-grid__item--end-13`
- versión responsive: `--sm-*`, `--md-*`, `--lg-*`, `--xl-*`

## Display y Flex Utilities

### Flex base

```html
<div class="u-d-flex u-d-flex-row u-d-flex-align-center u-d-flex-justify-between">
  <span>Izquierda</span>
  <span>Derecha</span>
</div>
```

Dirección:

- `.u-d-flex-column`
- `.u-d-flex-row`
- `.u-d-flex-row-reverse`
- `.u-d-flex-column-reverse`

Alineación:

- `.u-d-flex-justify-start|end|center|between|around`
- `.u-d-flex-align-start|end|center|stretch|baseline`

Otros:

- `.u-d-flex-wrap`, `.u-d-flex-nowrap`
- `.u-d-flex-gap-1` ... `.u-d-flex-gap-5`
- `.u-d-flex-inline`
- `.u-d-flex-spacer`

### Flex responsive de dirección

```html
<div class="u-d-flex u-d-flex-row-responsive u-d-flex-gap-3">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>
```

Comportamiento:

- `.u-d-flex-row-responsive`: mobile `column`, desktop `row`
- `.u-d-flex-column-responsive`: mobile `row`, desktop `column`

### Display mobile / desktop helpers

```html
<div class="u-d-block-mobile u-d-none-desktop">Solo mobile</div>
<div class="u-d-none-mobile u-d-block-desktop">Solo desktop</div>
```

También existen:

- `.u-d-flex-mobile`, `.u-d-grid-mobile`
- `.u-d-flex-desktop`, `.u-d-grid-desktop`

## Botones

Clase base:

```html
<button class="u-btn u-btn-primary">Primary</button>
```

### Variantes principales

```html
<button class="u-btn u-btn-primary">Primary</button>
<button class="u-btn u-btn-secondary">Secondary</button>
<button class="u-btn u-btn-ghost">Ghost</button>
<button class="u-btn u-btn-success">Success</button>
<button class="u-btn u-btn-danger">Danger</button>
<button class="u-btn u-btn-info">Info</button>
```

### Botones de redes sociales

```html
<button class="u-btn u-btn-facebook">Facebook</button>
<button class="u-btn u-btn-instagram">Instagram</button>
<button class="u-btn u-btn-x">X</button>
<button class="u-btn u-btn-youtube">YouTube</button>
<button class="u-btn u-btn-linkedin">LinkedIn</button>
<button class="u-btn u-btn-tiktok">TikTok</button>
<button class="u-btn u-btn-whatsapp">WhatsApp</button>
```

### Multicolor automático

Estas variantes se generan a partir del mapa de colores:

```html
<button class="u-btn u-btn-primary-blue">Primary blue</button>
<button class="u-btn u-btn-primary-green">Primary green</button>
<button class="u-btn u-btn-secondary-red-20">Secondary red-20</button>
```

### Modificadores de tamaño y forma

```html
<button class="u-btn u-btn-primary u-btn--large">Ancho completo</button>
<button class="u-btn u-btn-primary u-btn--no-width">Auto width</button>
<button class="u-btn u-btn-primary u-btn--no-height">Auto height</button>
<button class="u-btn u-btn-primary u-btn--big">Big</button>
<button class="u-btn u-btn-primary u-btn--mid">Mid</button>
<button class="u-btn u-btn-primary u-btn--text-left">Text left</button>
<button class="u-btn u-btn-primary u-btn--text-right">Text right</button>
<button class="u-btn u-btn-primary u-btn--circle u-btn--x48">Circle</button>
```

Tamaños de círculo disponibles:

- `u-btn--x8`, `u-btn--x16`, `u-btn--x24`, `u-btn--x32`, `u-btn--x40`
- `u-btn--x48`, `u-btn--x64`, `u-btn--x72`, `u-btn--x80`, `u-btn--x96`, `u-btn--x128`

## Tipografía

### Tamaños

```html
<p class="u-text-xs">XS</p>
<p class="u-text-base">Base</p>
<p class="u-text-3xl">3XL</p>
```

### Pesos

```html
<p class="u-font-regular">Regular</p>
<p class="u-font-medium">Medium</p>
<p class="u-font-semibold">Semibold</p>
<p class="u-font-bold">Bold</p>
```

### Tamaño + peso combinados

```html
<p class="u-text-lg-semibold">Texto combinado</p>
<p class="u-text-2xl-bold">Título</p>
```

### Alineación y line-height

```html
<p class="u-text-center u-leading-relaxed">Texto centrado y relajado</p>
```

Clases:

- `.u-text-left|center|right|justify`
- `.u-leading-tight|normal|relaxed|loose`

## Colores y bordes

Colores disponibles:

- `white`, `white-pure`, `black`, `grey-black`, `yellow`
- `green-v1`, `green`, `red`, `blue`, `blue-v2`, `blue-cyan`
- `grey-v1`, `grey-v2`, `hover-blue`
- `green-10`, `green-20`, `green-30`
- `yellow-10`, `yellow-20`, `yellow-30`
- `red-10`, `red-20`, `red-30`
- `cyan-10`, `cyan-20`, `cyan-30`
- `grey-10`, `grey-20`, `grey-30`, `grey-40`, `grey-50`, `grey-60`, `grey-70`, `grey-80`, `grey-90`

Ejemplos:

```html
<p class="u-text-blue-v2">Texto azul</p>
<div class="u-bg-hover-blue u-p-all-3">Fondo</div>
<div class="u-border-grey-40 u-p-all-2">Borde</div>
<div class="u-border-bottom-red-20">Borde inferior</div>
<button class="u-border-blue-hover">Hover border</button>
```

Patrones:

- texto: `.u-text-{color}`
- fondo: `.u-bg-{color}`
- hover texto/fondo: `.u-text-{color}-hover`, `.u-bg-{color}-hover`
- bordes: `.u-border-{color}`, `.u-border-top-{color}`, `.u-border-right-{color}`, `.u-border-bottom-{color}`, `.u-border-left-{color}`
- hover bordes: mismo patrón + `-hover`

## Spacing

Escala: `1` a `16`.

```html
<div class="u-p-all-4 u-mb-3">Bloque con spacing</div>
<div class="u-pl-2 u-pr-2">Padding horizontal</div>
```

Patrones:

- padding: `.u-pl-*`, `.u-pr-*`, `.u-pt-*`, `.u-pb-*`, `.u-p-all-*`
- margin: `.u-ml-*`, `.u-mr-*`, `.u-mt-*`, `.u-mb-*`, `.u-m-all-*`
- reset: `.u-p-all-none`, `.u-m-all-none`

## Icon sizes

Se generan tamaños de `8px` a `128px` en pasos de `4`.

```html
<i class="u-icon-x16">★</i>
<i class="u-icon-x48">★</i>
```

## Layouts (`l-*`)

### `l-general`

```html
<div class="l-general">
  <header class="l-general__navbar">Navbar</header>
  <main class="l-general__content">
    <section class="l-general__body">Contenido</section>
  </main>
  <footer class="l-general__footer">Footer</footer>
</div>
```

### `l-panel`

```html
<div class="l-panel">
  <header class="l-panel__navbar">Navbar</header>
  <div class="l-panel__content">
    <aside class="l-panel__sidebar">Sidebar</aside>
    <main class="l-panel__body">Body</main>
  </div>
</div>
```

También existe `l-panel-sticky`.

Modificador de padding:

- `__header--no-padding`
- `__navbar--no-padding`
- `__content--no-padding`
- `__body--no-padding`
- `__footer--no-padding`
- `__sidebar--no-padding`

## Cards

```html
<article class="u-card u-card--shadow u-card--hover">
  <h3 class="u-card__title">Título</h3>
  <div class="u-card__content">Contenido de tarjeta</div>
  <button class="u-btn u-btn-primary u-btn--no-width">Acción</button>
</article>
```

Modificadores:

- `u-card--shadow`
- `u-card--shadow-sm`
- `u-card--shadow-lg`
- `u-card--hover`
- `u-card--selected`
- `u-card--disabled`

## Formularios

```html
<form class="form">
  <div class="form-group">
    <label class="form-label" for="email">Email</label>
    <input id="email" class="form-control" type="email" />
  </div>

  <div class="form-group">
    <label class="form-label" for="role">Rol</label>
    <select id="role" class="form-select">
      <option>Admin</option>
      <option>User</option>
    </select>
  </div>

  <div class="form-group">
    <label class="form-label" for="notes">Notas</label>
    <textarea id="notes" class="form-textarea"></textarea>
  </div>

  <p class="form-feedback form-feedback--info">Mensaje informativo</p>
  <p class="form-feedback form-feedback--error">Mensaje de error</p>

  <button class="u-btn u-btn-primary">Enviar</button>
</form>
```

## Tablas

```html
<div class="table-responsive">
  <table class="table-striped table-hover table-hover-blue-v2">
    <thead>
      <tr>
        <th>Nombre</th>
        <th>Email</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Ana</td>
        <td>ana@mail.com</td>
      </tr>
      <tr>
        <td>Luis</td>
        <td>luis@mail.com</td>
      </tr>
    </tbody>
  </table>
</div>
```

Variantes:

- `.table-normal`
- `.table-striped`
- `.table-interlaced`
- `.table-hover`
- `.table-hover-{color}`
- `.table-responsive`

## Dialog

```html
<div class="dialog dialog--active">
  <div class="dialog__overlay"></div>
  <div class="dialog__content dialog__content--mid">
    <div class="dialog__header">
      <h3 class="dialog__title">Confirmación</h3>
      <button class="dialog__close" type="button">×</button>
    </div>
    <div class="dialog__body">
      ¿Deseas continuar?
    </div>
    <div class="dialog__footer">
      <button class="u-btn u-btn-ghost u-btn--no-width">Cancelar</button>
      <button class="u-btn u-btn-primary u-btn--no-width">Aceptar</button>
    </div>
  </div>
</div>
```

Tamaños de contenido:

- `dialog__content--small`
- `dialog__content--mid`
- `dialog__content--large`

## Sidebar y Navbar

```html
<button class="menu-button" type="button">☰</button>
<h1 class="navbar-title">Dashboard</h1>

<div class="sidebar-container open">
  <aside class="sidebar u-bg-white-pure">
    <button class="close-btn" type="button">×</button>
    <nav class="sidebar-menu">
      <ul>
        <li><a class="active" href="#">Inicio</a></li>
        <li><a href="#">Reportes</a></li>
      </ul>
    </nav>
  </aside>
</div>
```

## Círculos y avatares

```html
<img class="u-circle-md" src="avatar.jpg" alt="Avatar" />
<img class="u-circle-lg-shadow" src="avatar.jpg" alt="Avatar" />
```

Clases:

- tamaños: `u-circle-xs|sm|md|lg|xl|xxl`
- sombras: `u-circle-xs-shadow` ... `u-circle-xxl-shadow`
- helpers: `u-circle`, `u-circle-shadow`, `u-circle-ratio`

## HR por color

```html
<hr />
<hr class="blue-v2" />
<hr class="green-20" />
```

## Ejemplo completo

```html
<section class="container u-mt-4">
  <div class="o-grid o-grid--cols-1 o-grid--lg-cols-3 o-grid--gap-4">
    <article class="o-grid__item o-grid__item--lg-span-2 u-card u-card--shadow">
      <h2 class="u-card__title u-text-2xl-semibold">Resumen</h2>
      <p class="u-text-grey-70 u-leading-relaxed">
        Vista general del dashboard.
      </p>
      <div class="u-d-flex u-d-flex-row-responsive u-d-flex-gap-2 u-mt-3">
        <button class="u-btn u-btn-primary u-btn--no-width">Guardar</button>
        <button class="u-btn u-btn-whatsapp u-btn--no-width">Compartir</button>
      </div>
    </article>

    <aside class="o-grid__item u-card u-card--shadow-sm">
      <h3 class="u-card__title">Contacto</h3>
      <p class="u-text-sm">Síguenos en redes:</p>
      <div class="u-d-flex u-d-flex-wrap u-d-flex-gap-2 u-mt-2">
        <button class="u-btn u-btn-facebook u-btn--circle u-btn--x40">f</button>
        <button class="u-btn u-btn-instagram u-btn--circle u-btn--x40">i</button>
        <button class="u-btn u-btn-x u-btn--circle u-btn--x40">x</button>
      </div>
    </aside>
  </div>
</section>
```

## Personalización

Edita los mapas de `src/settings/_settings.scss` y `src/settings/_buttons.scss` para:

- cambiar paleta
- tipografía
- spacing scale
- breakpoints
- estilos de botones y estados

Luego recompila:

```bash
npm run build
```

## Licencia

ISC

---

## Índice rápido de referencia

### Prefijo `u-` (utilities)

- `u-d-*`: display/flex utilities
- `u-text-*`, `u-font-*`, `u-leading-*`: tipografía
- `u-bg-*`, `u-border-*`: color y bordes
- `u-p*`, `u-m*`: spacing
- `u-btn*`: botones
- `u-icon-*`: tamaños de íconos
- `u-circle*`: avatares y círculos

### Prefijo `l-` (layouts)

- `l-general`
- `l-panel`
- `l-panel-sticky`

### Prefijo `o-` (objetos estructurales)

- `o-grid`
- `o-grid__item`

## Matriz de clases clave (cheat sheet)

### Display/Flex

```txt
u-d-flex
u-d-flex-inline
u-d-flex-row | u-d-flex-column | u-d-flex-row-reverse | u-d-flex-column-reverse
u-d-flex-row-responsive | u-d-flex-column-responsive
u-d-flex-justify-start|end|center|between|around
u-d-flex-align-start|end|center|stretch|baseline
u-d-flex-wrap | u-d-flex-nowrap
u-d-flex-gap-1..5
u-d-flex-spacer
u-d-none-mobile | u-d-block-mobile | u-d-flex-mobile | u-d-grid-mobile
u-d-none-desktop | u-d-block-desktop | u-d-flex-desktop | u-d-grid-desktop
```

### Grid BEMIT

```txt
o-grid
o-grid--dense
o-grid--cols-1..12
o-grid--gap-1..16
o-grid--gap-x-1..16
o-grid--gap-y-1..16
o-grid--sm-cols-* | o-grid--md-cols-* | o-grid--lg-cols-* | o-grid--xl-cols-*
o-grid__item
o-grid__item--span-1..12
o-grid__item--start-1..12
o-grid__item--end-2..13
o-grid__item--{breakpoint}-span-*
o-grid__item--{breakpoint}-start-*
o-grid__item--{breakpoint}-end-*
```

### Botones

```txt
u-btn + u-btn-primary|secondary|ghost|success|danger|info
u-btn + u-btn-facebook|instagram|x|youtube|linkedin|tiktok|whatsapp
u-btn + u-btn-primary-{color}
u-btn + u-btn-secondary-{color}
u-btn--large|no-width|no-height|big|mid|text-left|text-right|circle
u-btn--x8|x16|x24|x32|x40|x48|x64|x72|x80|x96|x128
```

## Recetas de implementación (copy/paste)

### 1) Hero responsive con CTA y grid

```html
<section class="container u-pt-6 u-pb-6">
  <div class="o-grid o-grid--cols-1 o-grid--lg-cols-2 o-grid--gap-6">
    <div class="o-grid__item u-d-flex u-d-flex-column u-d-flex-gap-3">
      <h1 class="u-text-4xl-bold u-leading-tight">Acelera tu UI</h1>
      <p class="u-text-lg u-text-grey-70">
        Librería utilitaria para construir interfaces limpias y rápidas.
      </p>
      <div class="u-d-flex u-d-flex-row-responsive u-d-flex-gap-2">
        <button class="u-btn u-btn-primary u-btn--no-width">Comenzar</button>
        <button class="u-btn u-btn-ghost u-btn--no-width">Ver docs</button>
      </div>
    </div>
    <div class="o-grid__item u-card u-card--shadow-lg u-p-all-5">
      <p class="u-text-2xl-semibold">Preview panel</p>
      <hr class="grey-40" />
      <p class="u-text-grey-70">Contenido visual de ejemplo.</p>
    </div>
  </div>
</section>
```

### 2) Barra de acciones para tabla

```html
<div class="u-d-flex u-d-flex-row-responsive u-d-flex-justify-between u-d-flex-align-center u-d-flex-gap-2 u-mb-3">
  <input class="form-control u-m-all-none" placeholder="Buscar..." />
  <div class="u-d-flex u-d-flex-gap-2">
    <button class="u-btn u-btn-secondary u-btn--no-width">Exportar</button>
    <button class="u-btn u-btn-primary u-btn--no-width">Crear</button>
  </div>
</div>

<div class="table-responsive">
  <table class="table-normal table-hover">
    <thead>
      <tr><th>ID</th><th>Nombre</th><th>Estado</th></tr>
    </thead>
    <tbody>
      <tr><td>1</td><td>Pedido 001</td><td><span class="u-text-green">OK</span></td></tr>
      <tr><td>2</td><td>Pedido 002</td><td><span class="u-text-red-20">Pendiente</span></td></tr>
    </tbody>
  </table>
</div>
```

### 3) Card de perfil social

```html
<article class="u-card u-card--shadow u-p-all-4">
  <div class="u-d-flex u-d-flex-align-center u-d-flex-gap-3">
    <img class="u-circle-md-shadow" src="avatar.jpg" alt="Avatar" />
    <div>
      <p class="u-text-lg-semibold">María López</p>
      <p class="u-text-sm u-text-grey-70">@marialopez</p>
    </div>
  </div>

  <p class="u-mt-3 u-mb-3">Diseñadora UI y frontend engineer.</p>

  <div class="u-d-flex u-d-flex-wrap u-d-flex-gap-2">
    <button class="u-btn u-btn-linkedin u-btn--circle u-btn--x40">in</button>
    <button class="u-btn u-btn-x u-btn--circle u-btn--x40">x</button>
    <button class="u-btn u-btn-instagram u-btn--circle u-btn--x40">ig</button>
  </div>
</article>
```

### 4) Dialog de confirmación destructiva

```html
<div class="dialog dialog--active">
  <div class="dialog__overlay"></div>
  <div class="dialog__content dialog__content--small">
    <div class="dialog__header">
      <h3 class="dialog__title">Eliminar registro</h3>
      <button class="dialog__close">×</button>
    </div>
    <div class="dialog__body">
      Esta acción no se puede deshacer.
    </div>
    <div class="dialog__footer">
      <button class="u-btn u-btn-ghost u-btn--no-width">Cancelar</button>
      <button class="u-btn u-btn-danger u-btn--no-width">Eliminar</button>
    </div>
  </div>
</div>
```

### 5) Sidebar lateral tipo app

```html
<div class="l-panel">
  <header class="l-panel__navbar u-d-flex u-d-flex-align-center u-d-flex-justify-between">
    <button class="menu-button">☰</button>
    <h2 class="navbar-title">Admin</h2>
  </header>

  <div class="l-panel__content">
    <aside class="l-panel__sidebar sidebar u-bg-white-pure">
      <nav class="sidebar-menu">
        <ul>
          <li><a class="active" href="#">Dashboard</a></li>
          <li><a href="#">Users</a></li>
          <li><a href="#">Billing</a></li>
        </ul>
      </nav>
    </aside>

    <main class="l-panel__body">
      <div class="u-card u-card--shadow-sm">Contenido principal</div>
    </main>
  </div>
</div>
```

## Guía de combinación de clases

Reglas prácticas para evitar conflicto de estilos:

- primero define estructura: `container`/`o-grid`/`l-*`
- luego layout interno: `u-d-flex*`, `o-grid__item*`
- después tipografía y color: `u-text-*`, `u-bg-*`
- por último spacing y ajustes finos: `u-p*`, `u-m*`, `u-btn--*`

Ejemplo recomendado:

```html
<button class="u-btn u-btn-primary u-btn--no-width u-mt-2">Guardar</button>
```

## Integración con frameworks

### React

```jsx
import "drstyles/dist/styles.min.css";

export function SaveButton() {
  return (
    <button className="u-btn u-btn-success u-btn--no-width">
      Guardar cambios
    </button>
  );
}
```

### Vue

```vue
<template>
  <button class="u-btn u-btn-whatsapp u-btn--no-width">
    Compartir
  </button>
</template>

<style>
@import "drstyles/dist/styles.min.css";
</style>
```

### Blade / Laravel

```blade
<button class="u-btn u-btn-primary u-btn--no-width">
  {{ __("Continuar") }}
</button>
```

## Personalización avanzada

### Cambiar escala de spacing

En `src/settings/_settings.scss`:

```scss
$spacing-scale: (
  1: 4px,
  2: 8px,
  3: 12px,
  4: 16px,
  5: 20px,
);
```

### Crear un botón temático nuevo

En `src/settings/_buttons.scss` agrega una entrada al mapa `$buttons` con:

- `background`
- `border`
- `text`
- `states.hover`
- `states.focus`
- `states.disabled`

Luego en `src/utils/_buttons.scss` enlázalo:

```scss
&.u-btn-tu-tipo {
  @include funcs.btn-action("tu-tipo");
}
```

## Accesibilidad recomendada

- usa texto descriptivo en botones (`Guardar`, `Eliminar`, `Continuar`)
- no dependas solo del color para estados críticos
- en botones circulares incluye `aria-label`
- mantén contraste AA en combinaciones `u-text-*` + `u-bg-*`
- en dialogs gestiona foco con JavaScript (focus trap)

Ejemplo:

```html
<button class="u-btn u-btn-facebook u-btn--circle u-btn--x40" aria-label="Abrir Facebook">
  f
</button>
```

## FAQ

### ¿Puedo usar solo una parte de la librería?

Sí. Puedes importar módulos SCSS específicos en lugar de `main.scss`.

### ¿Cómo cambio breakpoints?

Edita `$breakpoints` en `src/settings/_settings.scss` y recompila.

### ¿Cómo agrego colores nuevos?

Edita `$colors` en `src/settings/_settings.scss`. Automáticamente se generarán utilidades de texto, fondo y bordes.

### ¿El sistema soporta dark mode?

No hay modo dark automático por defecto. Se puede construir creando un tema con variables y clases envolventes.

## Troubleshooting

### No veo estilos aplicados

- verifica que el CSS compilado esté cargado
- revisa orden de importación (drstyles después de reset externo si quieres prioridad)
- inspecciona conflictos de especificidad en el navegador

### Las clases responsive no cambian como esperaba

- confirma tamaño de viewport
- verifica breakpoints actuales en settings
- revisa que hayas aplicado la clase responsive correcta

### Los botones no cambian de color

- asegúrate de incluir la clase base `u-btn`
- agrega la variante después: `u-btn-primary`, `u-btn-facebook`, etc.

## Roadmap sugerido para el proyecto

Si quieres evolucionar la librería:

- tokens CSS custom properties para tema dinámico
- dark mode con wrapper `.theme-dark`
- utilidades de width/height y overflow
- variantes de boton `outline-*` por red social
- documentación en sitio estático (VitePress/Docusaurus)
