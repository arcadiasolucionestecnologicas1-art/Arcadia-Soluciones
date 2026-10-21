# ARCADIA · Página web

Página de una sola pantalla (HTML + CSS + JavaScript), sin instalaciones ni proceso de compilación.

## Contenido

```
brand/
├── index.html                 La página completa (las fuentes van incluidas dentro)
├── img/                       Logo, favicon, imagen para redes y fotografías
├── descargar-imagenes.bat     Descarga las fotos (Windows)
├── descargar-imagenes.sh      Descarga las fotos (macOS / Linux)
└── licencias/                 Licencias de las fuentes Sora y Figtree (OFL, uso libre)
```

## Paso 1 · Descargar las fotografías (una sola vez)

Las fotos son de Unsplash (uso gratuito). Se descargan ya en formato WebP y al tamaño justo:

- **Windows:** doble clic en `descargar-imagenes.bat`.
- **macOS / Linux:** en una terminal, `sh descargar-imagenes.sh`.

Se guardan en `img/` con estos nombres: `hero.webp`, `diseno-web.webp`, `reunion.webp`,
`equipo.webp`, `cafeteria.webp`, `tienda.webp` y `emprendimiento.webp`.

Si no ejecutas el script, la página igual carga esas fotos directamente desde Unsplash cuando hay
internet. Sin internet, muestra un fondo azul con el logo en lugar de una imagen rota.

**Cambiar una foto:** reemplaza el archivo en `img/` por otro con el mismo nombre
(formato WebP, horizontal o vertical según el lugar). Revisa también su texto `alt` en `index.html`.

## Paso 2 · Ver la página

Doble clic en `index.html`. Funciona también subiendo la carpeta `brand` a cualquier hosting
(Netlify, Vercel, GitHub Pages, cPanel…).

## Datos que puedes querer cambiar en `index.html`

- **WhatsApp:** busca `59177207537` (aparece en todos los botones con su mensaje predefinido).
- **Correo:** busca `arcadiasolucionestecnologicas1`.
- **Precios y contenido de paquetes:** sección `<!-- ============ PAQUETES ============ -->`.
- **Redes sociales:** al final de la sección de contacto.

## Diseño

- Colores tomados del logo: navy `#021648`, azules `#024FC5` / `#0560D6`, celeste `#0CA2FE`.
- Tipografías: Sora (títulos) y Figtree (texto).
- Animaciones solo con `transform` y `opacity`, curvas suaves y cortas; se reducen a un
  simple fundido si el dispositivo tiene activado "reducir movimiento".

## Versión de prueba del hero (pendiente de aprobación)

- El inicio es una historia en 5 etapas que avanza con el scroll (GSAP 3.13.0 + ScrollTrigger y
  Lenis 1.3.26, cargados desde jsDelivr). Necesita internet para animarse; sin internet, o con
  "reducir movimiento" activado, muestra las 5 etapas como bloques fijos.
- El logo de ARCADIA aparece en el centro de la pantalla al empezar y al final, con el texto
  "SOLUCIONES DIGITALES" detrás del logo.
- Después del inicio está la sección con foto, titular y precio. El pie de página tiene todos los contactos.
- Redes sociales: busca `PEGAR URL` en index.html y reemplaza cada `href="#"` por tu enlace.
- Las demás secciones todavía son la versión anterior: se actualizarán cuando apruebes el hero.
