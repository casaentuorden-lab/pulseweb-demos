# pulseweb-demos

Demos de páginas web para pequeños negocios locales (Las Rozas de Madrid y alrededores).

Cada negocio tiene su propia carpeta dentro de `demos/`. Todas las demos se
despliegan desde este único repositorio en un único proyecto de Vercel.

## Estructura

```
demos/
  glass-pamar/
    index.html
    foto.jpg / foto.webp
```

## Añadir una demo nueva

1. Crear `demos/<slug-del-negocio>/index.html`.
2. Usar únicamente datos reales del negocio (teléfono, dirección, reseñas). El
   contenido genérico del sector se marca como tal.
3. Añadir una imagen (ver abajo).
4. Añadir el enlace en el `index.html` de la raíz.
5. Commit + push. Vercel despliega automáticamente.

## Imágenes

Cada demo lleva una imagen (`foto.jpg` + `foto.webp` en la carpeta del negocio),
servida con `<picture>` en una banda a ancho completo bajo el hero, con
`<figcaption>` "Imagen orientativa del sector." cuando no es una foto real del
local.

Orden de preferencia para elegirla:

1. **Foto real** del local o del trabajo, si el CSV de Apify (`imageUrl`) o una
   fuente pública legítima tiene una nítida de al menos 1200px de lado corto.
2. Si no, **foto de stock gratuita** (Unsplash / Pexels / Pixabay) que ambiente
   el sector, genérica, sin dar a entender que es el local concreto.

Si una imagen candidata lleva **marca de agua**, se descarta — no se usa ni se
edita para quitarla.

Procesado: recorte 3:2, ~1600px de ancho, JPEG q72 (mozjpeg) + WebP q68, metadatos
eliminados. Objetivo: < ~150 KB por archivo.

## Notas

- Los datos de leads / CRM (archivos `.csv`) están excluidos por `.gitignore` y
  no deben subirse: este repositorio es público a través de Vercel.
