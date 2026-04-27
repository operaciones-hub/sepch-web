# sepch-web
# Mockup Sitio Web SEP Chubut

Mockup institucional para el sitio web de la **Secretaría Electoral Permanente de la Provincia del Chubut**. Este repositorio contiene el diseño en HTML/CSS que servirá de referencia para la posterior implementación en WordPress.

> **Estado actual:** Diseño en iteración. Páginas desarrolladas: Inicio e Institucional. Páginas pendientes: Registros Electorales, Procesos Electorales, Partidos Políticos, Capacitación y Contacto.

---

## 📁 Estructura del proyecto

```
sep-chubut-mockup/
├── index.html              ← Todo el mockup en un solo archivo
├── README.md               ← Este archivo
└── DESIGN_SYSTEM.md        ← Paleta de colores, tipografías y componentes
```

Decisión consciente: todo el HTML, CSS y JS están en `index.html` para que sea fácil editar el diseño sin saltar entre archivos. Cuando se pase a WordPress, el desarrollador separará los estilos y plantillas.

---

## 👀 Cómo previsualizar el sitio

### Opción 1: Abrir directamente (lo más rápido)

1. Cloná o descargá el repositorio
2. Hacé doble clic sobre `index.html`
3. Se abre en tu navegador. Listo.

### Opción 2: Ver la versión publicada online

Una vez que actives GitHub Pages (ver más abajo), el sitio queda visible en una URL pública que podés compartir.

---

## 🚀 Cómo activar GitHub Pages

GitHub Pages es un servicio gratuito de GitHub que publica el sitio en una URL real. **No hace falta servidor ni configuración técnica.**

1. Subí el repositorio a GitHub (si todavía no lo hiciste)
2. En el repo, andá a **Settings** (arriba a la derecha)
3. En el menú izquierdo, buscá **Pages**
4. En "Source", elegí:
   - **Branch:** `main` (o `master`, según corresponda)
   - **Folder:** `/ (root)`
5. Hacé clic en **Save**
6. Esperá 1-2 minutos. Arriba aparece un mensaje verde con la URL del sitio, algo así como:
   ```
   https://[tu-usuario].github.io/sep-chubut-mockup/
   ```

Cada vez que hagas `push` a la rama configurada, el sitio se actualiza automáticamente.

---

## ✏️ Cómo proponer cambios al diseño

### Si tenés acceso de escritura al repo

Lo más simple: editá `index.html` directamente, hacé commit y push.

```bash
git clone https://github.com/[usuario]/sep-chubut-mockup.git
cd sep-chubut-mockup
# editás index.html con el editor que prefieras
git add index.html
git commit -m "Cambio en sección Hero: ajusto color del overlay"
git push
```

### Si querés trabajar sin pisar la versión actual

Creá una rama nueva para tus cambios. Así el equipo puede revisar antes de mezclar:

```bash
git checkout -b diseno/nuevo-hero
# hacés tus cambios
git add index.html
git commit -m "Propongo nuevo hero institucional"
git push -u origin diseno/nuevo-hero
```

Después abrís un Pull Request desde GitHub para que se discuta el cambio.

### Si preferís editar desde el navegador (sin instalar git)

GitHub permite editar archivos directamente desde la web:

1. Abrí `index.html` en GitHub
2. Hacé clic en el ícono del lápiz ✏️ arriba a la derecha
3. Editá, escribí un mensaje describiendo el cambio y guardá

---

## 🎨 Sobre los estilos

Toda la paleta de colores, tipografías y componentes están documentados en [`DESIGN_SYSTEM.md`](./DESIGN_SYSTEM.md). Recomiendo leerlo antes de hacer cambios grandes para mantener coherencia visual.

Los colores están definidos como **variables CSS** al principio del `<style>` en `index.html`:

```css
:root {
    --color-principal: #597B9E;
    --color-acento-azul: #5b9bd5;
    --color-dorado: #c2b59b;
    /* ... */
}
```

Para cambiar un color en todo el sitio, alcanza con modificar el valor en `:root`.

---

## 🔄 Próximos pasos

- [ ] Diseñar las páginas internas que faltan (Registros, Procesos, Partidos, Capacitación, Contacto)
- [ ] Reemplazar el placeholder del logo por el logo oficial de la SEP
- [ ] Definir imágenes finales para hero y sección de noticias
- [ ] Validar accesibilidad (contraste, navegación con teclado)
- [ ] Pasar el diseño aprobado a un theme de WordPress

---

## 📞 Contacto

Cualquier consulta sobre el código o la estructura, escribime.
