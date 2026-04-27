# Design System — SEP Chubut

Guía visual del mockup. Documenta los colores, tipografías y componentes que se usan en el sitio. Pensada para mantener coherencia durante el diseño y servir de referencia cuando se implemente en WordPress.

---

## 🎨 Paleta de colores

Todos los colores están definidos como variables CSS en `:root` dentro de `index.html`. Si querés cambiar un color en todo el sitio, modificalo ahí una sola vez.

| Variable | Hex | Uso | Proporción sugerida |
|---|---|---|---|
| `--color-principal` | `#597B9E` | Color institucional dominante. Navegación, títulos, logo. | 45% |
| `--color-secundario-azul` | `#a4b7ca` | Fondos de secciones destacadas (ej: bloque SIREPPAR). | 20% |
| `--color-oscuro` | `#0f1a30` | Footer, botones primarios, texto sobre fondos claros. | 20% |
| `--color-acento-azul` | `#5b9bd5` | Detalles, bordes de cards, acentos visuales. | 10% |
| `--color-dorado` | `#c2b59b` | Detalles institucionales (borde overlay, subrayado nav activo). | 10% |
| `--color-tierra` | `#9b8579` | Bordes de notificaciones, subtítulos secundarios. | 5% |
| `--blanco` | `#ffffff` | Fondo de cards y header. | — |
| Fondo general | `#f4f7f9` | Fondo del `body`. | — |

### Vista rápida

```
█ #597B9E  Principal
█ #a4b7ca  Secundario azul
█ #0f1a30  Oscuro
█ #5b9bd5  Acento azul
█ #c2b59b  Dorado
█ #9b8579  Tierra
```

### Criterio de uso

- **Principal (#597B9E):** todo lo que comunica identidad institucional. Si tenés dudas, este es el color por defecto.
- **Dorado (#c2b59b):** úsalo con cuidado, solo para detalles que merezcan jerarquía visual (borde lateral del welcome overlay, línea inferior del botón de navegación activo). Es el "toque institucional".
- **Oscuro (#0f1a30):** reservado para CTAs (botones de acción importantes) y el footer. Su uso debería ser limitado.
- **Tierra (#9b8579):** para diferenciar visualmente las notificaciones del resto del contenido.

---

## ✍️ Tipografía

Familia tipográfica actual:

```css
font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
```

> **Nota:** El stack actual usa fuentes del sistema. Si en algún momento se decide usar una fuente custom (Google Fonts, etc.), conviene definirla acá y reemplazarla en `index.html`.

### Jerarquía de tamaños

| Elemento | Tamaño | Peso | Color |
|---|---|---|---|
| Logo `<h1>` | 20px | normal | `--color-principal` |
| Bajada del logo | 10px uppercase, letter-spacing 1px | normal | `--color-tierra` |
| Botones de navegación | 12px uppercase | 600 | blanco |
| Hero `<h2>` | 30px | normal | `--color-principal` |
| Hero párrafo | 17px, line-height 1.6 | normal | `#444` |
| Títulos de sección (`<h2>`) | default browser | normal | heredado, con borde lateral azul |
| Títulos de cards (`<h3>`, `<h4>`) | default browser | normal | `--color-principal` |
| Texto de párrafos | 13-14px, line-height 1.7 | normal | `#555` |

---

## 🧩 Componentes

### Header

Logo + buscador. Fondo blanco, sin sombra. Padding lateral del 8%.

### Navegación principal

Barra azul (`--color-principal`) sticky en el top. Botones uppercase con hover y estado activo. El estado activo se distingue por:
- Fondo más oscuro (`--color-oscuro`)
- Borde inferior dorado de 4px

### Hero institucional

- Imagen de fondo con overlay oscuro semi-transparente (40% de `--color-oscuro`)
- Welcome overlay centrado: fondo blanco al 95%, borde lateral izquierdo dorado de 10px, sombra pronunciada
- Altura fija: 450px

### Bloque SIREPPAR

Bloque destacado con fondo `--color-secundario-azul`. Contiene título, descripción y CTA oscuro. Se usa para destacar el acceso al sistema interno.

### Cards de acceso rápido ("¿Qué necesitás hacer hoy?")

- Grilla de 4 columnas
- Fondo blanco, borde inferior dorado de 4px
- Hover: levitan -5px

### Notificaciones oficiales

Bloque blanco con borde lateral izquierdo `--color-tierra` de 6px. Listado de fechas + texto.

### Cards de noticias

- Grilla de 3 columnas
- Fondo blanco, sombra suave, border-radius 8px
- Imagen arriba (180px), contenido abajo

### Cards institucionales (página Institucional)

- Grilla de 2 columnas
- Borde superior azul (`--color-acento-azul`) o dorado para destacar
- Padding generoso (40px)

### Footer

Fondo `--color-oscuro`, texto en `--color-secundario-azul`. Tres bloques: brand+redes, columnas de enlaces, copyright. Íconos sociales con borde dorado y glow sutil.

---

## 📐 Espaciado y layout

- **Padding lateral global:** 8% (header, nav, container, footer)
- **Padding interno de secciones:** 60px vertical
- **Gap entre cards:** 20-40px según contexto
- **Border-radius:** 4px (botones), 8px (cards), 25px (search box), 50% (logo y social icons)

---

## 🔍 Convenciones para mantener coherencia

1. **No introducir colores nuevos sin documentarlos acá.** Si necesitás un color que no está, agregalo a `:root` con un nombre semántico.
2. **Usar las variables CSS, no los valores hex directamente.** Esto facilita cambios globales.
3. **Mantener los bordes laterales como recurso visual.** Los títulos de sección llevan borde izquierdo azul de 5px; las notificaciones llevan borde izquierdo tierra; el welcome overlay lleva borde izquierdo dorado. Es un patrón consistente del diseño.
4. **El dorado se reserva para detalles institucionales.** No usarlo como color de fondo amplio.

---

## 📋 Para el desarrollador WordPress

Cuando llegue el momento de pasar este mockup a WordPress, conviene:

- Convertir las variables CSS de `:root` en variables del theme (functions.php o el sistema de tokens del theme elegido)
- Cada bloque de la home (SIREPPAR, cards de acceso, notificaciones, noticias) puede ser un **bloque de Gutenberg** custom o un widget
- La estructura de "página activa por JS" del mockup debe reemplazarse por **páginas reales** de WordPress (cada `<div class="page">` se convierte en una página o template)
- Los placeholders de imágenes (logo, hero, news-img) deben reemplazarse por campos del Customizer o ACF para que los administradores puedan editarlos sin tocar código
