# pulseweb-demos

Demos de páginas web para pequeños negocios locales (Las Rozas de Madrid y alrededores).

Cada negocio tiene su propia carpeta dentro de `demos/`. Todas las demos se
despliegan desde este único repositorio en un único proyecto de Vercel.

## Estructura

```
demos/
  glass-pamar/
    index.html
    hero-wide.jpg / hero-wide.webp   (>= 720px de viewport)
    hero-tall.jpg / hero-tall.webp   (movil, retrato)
```

## Añadir una demo nueva

1. Crear `demos/<slug-del-negocio>/index.html`.
2. Usar únicamente datos reales del negocio (teléfono, dirección, reseñas). El
   contenido genérico del sector se marca como tal.
3. Añadir una imagen (ver abajo).
4. Añadir el enlace en el `index.html` de la raíz.
5. Commit + push. Vercel despliega automáticamente.

## Imágenes

La foto es el **fondo del hero a pantalla completa**. El texto (título, reseña,
botón de llamada) va superpuesto, con un degradado oscuro (`.hero-scrim`) entre
la foto y el texto: más opaco abajo y a la izquierda (donde va el texto), casi
transparente arriba. **Nunca texto directo sobre foto sin ese scrim.** Además,
`text-shadow` suave en `.hero-content` como refuerzo.

Dos recortes por demo, servidos con `<picture>` + `media`:

- `hero-wide` — 2000×1150, para viewport >= 720px.
- `hero-tall` — 1400×1800, para móvil (retrato).

Pie "Imagen orientativa del sector." (`.hero-credit`) dentro del hero cuando no
es una foto real del local.

Orden de preferencia para elegir la foto:

1. **Foto real** del local o del trabajo, si el CSV de Apify (`imageUrl`) o una
   fuente pública legítima tiene una nítida que aguante el tamaño del hero sin
   pixelarse (~2000px de lado largo).
2. Si no, **foto de stock gratuita** (Unsplash / Pexels / Pixabay) que ambiente
   el sector, genérica, sin dar a entender (ni con IA) que es el local concreto.

Si una imagen candidata lleva **marca de agua**, se descarta — no se usa ni se
edita para quitarla.

Procesado (`sharp`): recorte al ratio de cada variante, JPEG q70 (mozjpeg) +
WebP q66, metadatos eliminados.

## Notas

- Los datos de leads / CRM (archivos `.csv`) están excluidos por `.gitignore` y
  no deben subirse: este repositorio es público a través de Vercel.
