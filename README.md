# Arcadia — Página de marca

Landing page de **Arcadia — Agencia de Desarrollo y Consultoría Tecnológica**. Es un único archivo HTML autocontenido (`index.html`): sin build, sin dependencias de npm, sin backend. Se abre directamente en el navegador o se sirve como archivo estático.

## Cómo verla

```bash
open brand/index.html          # macOS
xdg-open brand/index.html      # Linux
# o simplemente arrástralo a una pestaña del navegador
```

También puede servirse con cualquier servidor estático, por ejemplo:

```bash
cd brand
python -m http.server 8000
# luego abre http://localhost:8000
```

## Estructura de la página

La navegación y las secciones siguen este orden:

1. **Inicio** — hero con propuesta de valor, CTA e ilustración SVG.
2. **Nosotros** — origen del nombre, misión, visión, filosofía de trabajo ("Entender · Diseñar · Transformar"), valores (Innovación, Calidad, Compromiso, Transparencia, Confidencialidad, Aprendizaje continuo) y equipo.
3. **Servicios** — catálogo de servicios destacados (desarrollo de software, desarrollo web, consultoría tecnológica, automatización e IA, soporte y mantenimiento).
4. **Promociones** — paquetes y precios (planes con tarjetas comparativas).
5. **Catálogo** — catálogo general de servicios, más allá de las promociones puntuales.
6. **Contacto** — footer con datos de contacto, navegación y redes sociales.

Además incluye un **widget de chat** flotante (esquina inferior derecha) con respuestas predefinidas por tema (`data-topic`) que siempre termina derivando a WhatsApp.

## Logo

El header, el footer y el encabezado del chat referencian el logo como:

```html
<img src="logo.png" alt="Arcadia">
```

Para que se vea correctamente, coloca el archivo del logo como `brand/logo.png` (junto a `index.html`).

## Contacto e integración con WhatsApp

- WhatsApp / teléfono: `+591 772 07537` (`https://wa.me/59177207537`)
- Email: `hola@arcadia.tech`
- Ubicación: El Alto, Bolivia

Los botones de contacto y el widget de chat usan enlaces `wa.me` con mensajes predefinidos para abrir directamente una conversación de WhatsApp.

## Diseño

- **Colores de marca**: `#0D1B2A` (navy), `#1E3A8A` (indigo), `#2563EB` (azure), `#60A5FA` (sky), `#F1F5F9` (on-navy). Definidos como custom properties CSS en `:root`.
- **Tipografías**: Poppins (títulos) e Inter (cuerpo), vía Google Fonts.
- **Tema claro/oscuro**: soporte automático con `prefers-color-scheme` y override manual vía `[data-theme]`.
- **Animaciones**: revelado al hacer scroll con `IntersectionObserver` (clases `.reveal` / `.is-visible` y `.stagger` para grupos de elementos).
- Todos los íconos son SVG inline (sin librerías externas de íconos).

## Notas técnicas

- Archivo único (`index.html`): HTML + CSS + JavaScript inline. No requiere instalación ni proceso de build.
- Cualquier elemento con la clase `.stagger` debe llevar también `.reveal`, o sus hijos nunca recibirán `.is-visible` y quedarán invisibles.
- No hay backend: el "asistente" del chat es un bot de reglas (sin IA real) que redirige siempre a WhatsApp para la conversación real.
