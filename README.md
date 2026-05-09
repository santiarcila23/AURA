# AURA — Landing Page

Catálogo de lociones de autor con selección de preferencia (Hombre / Unisex / Mujer), construido únicamente con **HTML y CSS** aplicando la metodología **BEM (Block Element Modifier)**.

---

## Estructura del proyecto

```
aura/
├── index.html    ← Toda la estructura HTML de la página
├── styles.css    ← Todos los estilos organizados por bloques BEM
└── README.md     ← Este archivo
```

---

## Secciones de la página

| Sección | Bloque BEM principal |
|---|---|
| Navegación | `.nav` |
| Selector de género | `.selector` |
| Hero | `.hero` |
| Encabezado de sección | `.section-header` |
| Características | `.feature-card` |
| Catálogo de productos | `.product-card` |
| Testimonios | `.testimonial` |
| Planes de membresía | `.pricing-card` |
| Formulario de contacto | `.contact-form` |
| Pie de página | `.footer` |

---

## Tecnologías usadas

- **HTML5** — estructura semántica, sin JavaScript
- **CSS3** — variables personalizadas (`--color-*`), Grid, Flexbox, transiciones, `scroll-behavior: smooth`
- **Google Fonts** — Cormorant Garamond (display) + Jost (cuerpo)

No se usó JavaScript. Toda la interactividad se resuelve con:
- `href="#id"` para navegación interna y scroll suave
- `:hover` en CSS para efectos visuales
- `scroll-behavior: smooth` en el `body` para desplazamiento animado

---

## Cómo funcionan los botones

Todos los botones son etiquetas `<a>` con `href` interno, no elementos `<button>` con JavaScript:

```html
<!-- Botón de plan de precios → lleva al formulario -->
<a href="#contacto" class="pricing-card__btn">Elegir Noir</a>

<!-- Tarjeta de producto → lleva al formulario -->
<a href="#contacto" class="product-card product-card--featured">
  ...
</a>

<!-- Botones del selector → llevan al catálogo -->
<a href="#catalogo" class="selector__btn selector__btn--active">
  Unisex
</a>
```

---

## Metodología BEM aplicada

La nomenclatura sigue esta convención:

```
.bloque
.bloque__elemento
.bloque--modificador
.bloque__elemento--modificador
```

### Ejemplo real del proyecto

```html
<!-- Bloque base -->
<article class="pricing-card">
  <p class="pricing-card__plan">Noir</p>
  <p class="pricing-card__price">$49<span>/mes</span></p>
  <ul class="pricing-card__features">
    <li class="pricing-card__feature-item">Envío prioritario gratis</li>
  </ul>
  <a href="#contacto" class="pricing-card__btn">Elegir Noir</a>
</article>

<!-- Modificador: plan destacado (siempre con la clase base) -->
<article class="pricing-card pricing-card--featured">
  ...
</article>
```

### Todos los modificadores usados

| Bloque | Modificadores |
|---|---|
| `.nav__link` | `--active` |
| `.selector__btn` | `--active` |
| `.hero__btn` | `--outline` |
| `.feature-card` | `--featured` |
| `.product-card` | `--featured` |
| `.testimonial` | `--featured`, `--accent` |
| `.pricing-card` | `--featured` |
| `.contact-form__field` | `--error` |
| `.contact-form__submit` | `--disabled` |
| `.footer__link` | `--active` |

### Reglas BEM respetadas

- **Solo minúsculas.** Palabras compuestas con guión simple: `product-card`, `contact-form`.
- **Sin anidar elementos.** Se evitó `.testimonial__profile__avatar`. `.testimonial__avatar` es elemento directo del bloque.
- **Nombres por propósito.** Se usó `--featured`, `--active`, `--outline`, no `--dorado` ni `--grande`.
- **Modificadores siempre con la clase base.** Nunca solo `pricing-card--featured`, siempre `pricing-card pricing-card--featured`.
- **Especificidad baja.** No hay `div.card` ni `nav > ul > li`. Solo clases BEM.
- **Bloque reutilizable.** `.section-header` se usa en 5 secciones distintas sin modificar nada.

---

## Cómo ver el proyecto localmente

Abre `index.html` directamente en el navegador. No requiere servidor, instalación ni conexión a internet (excepto para cargar las fuentes de Google Fonts).

```
Con VS Code y la extensión Live Server:
clic derecho en index.html → Open with Live Server
```

---

## Cómo publicarlo en Vercel

Vercel es la forma más rápida de poner una página en vivo — sin configuración, sin FTP, sin comandos.

**Paso 1 — Crea una cuenta**
Entra a [vercel.com](https://vercel.com) y regístrate. Puedes usar tu cuenta de GitHub o solo un correo.

**Paso 2 — Sube el proyecto**
En el dashboard de Vercel busca el botón **"Add New Project"** y luego selecciona **"Deploy from your computer"** o simplemente arrastra la carpeta del proyecto a la pantalla.

**Paso 3 — Despliega**
Vercel detecta automáticamente que es un proyecto HTML estático y lo publica en segundos. Te entrega una URL pública como:

```

**URL DE LA PAG 
https://aura-ten-woad.vercel.app/**


```

**Paso 4 — Actualizar la página**
Si necesitas cambiar algo en el código, vuelve al dashboard, sube los archivos nuevamente y Vercel actualiza la URL automáticamente.

> No necesitas instalar nada en tu computador. Todo se hace desde el navegador.

---

## Información académica

| Campo | Detalle |
|---|---|
| Institución | CEFIT Barrio Mesa |
| Materia | Desarrollo de Aplicaciones Web |
| Docente | James Mosquera Rentería |
| Actividad | Taller práctico — Metodología BEM |
| Año | 2026 |
