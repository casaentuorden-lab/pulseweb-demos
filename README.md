# pulseweb-demos

Demos de páginas web para pequeños negocios locales (Las Rozas de Madrid y alrededores).

Cada negocio tiene su propia carpeta dentro de `demos/`. Todas las demos se
despliegan desde este único repositorio en un único proyecto de Vercel.

## Estructura

```
demos/
  glass-pamar/
    index.html
```

## Añadir una demo nueva

1. Crear `demos/<slug-del-negocio>/index.html`.
2. Usar únicamente datos reales del negocio (teléfono, dirección, reseñas). El
   contenido genérico del sector se marca como tal.
3. Añadir el enlace en el `index.html` de la raíz.
4. Commit + push. Vercel despliega automáticamente.

## Notas

- Los datos de leads / CRM (archivos `.csv`) están excluidos por `.gitignore` y
  no deben subirse: este repositorio es público a través de Vercel.
