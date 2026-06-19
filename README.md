# SABRIN — Landing Page

Landing page del proyecto **SABRIN**, plataforma SaaS de gestión jurídica para abogados independientes y pequeñas firmas (clientes, expedientes, términos legales, honorarios y generación documental con IA).

Construida con **Astro 6** + **Tailwind CSS v4**.

## Estructura de la página

Sigue la guía de elementos imprescindibles de una landing:

1. **Hero** — propuesta principal + "folio" visual de un expediente con término legal en seguimiento.
2. **Propuesta de valor** — qué hace, qué problema resuelve, qué diferencia a SABRIN.
3. **Beneficios** — las 6 funciones núcleo (términos, IA, expediente digital, exportación, agenda, honorarios).
4. **Prueba social** — métricas del producto en fase piloto (sin testimonios inventados).
5. **Planes** — Independiente (gratis en piloto) y Firma (a cotizar).
6. **Formulario de conversión** — nombre, correo, teléfono, perfil.
7. **FAQ** — 6 preguntas frecuentes con acordeón nativo (`<details>`).
8. **Footer** — contacto, redes, políticas.

## Sistema de diseño

- **Paleta**: papel/pergamino (`--color-paper`), tinta noche (`--color-ink`, `--color-navy`) y un acento "sello" terracota (`--color-seal`) que evoca documentos jurídicos y alertas de vencimiento.
- **Tipografía**: [Fraunces](https://fonts.google.com/specimen/Fraunces) (display, con carácter editorial) + [Inter](https://fonts.google.com/specimen/Inter) (cuerpo) + IBM Plex Mono (eyebrows/datos).
- **Elemento firma**: la clase `.folio`, una ficha con bordes tipo "expediente sellado", reutilizada en el hero, los planes y el formulario.
- Todos los tokens están centralizados en `src/styles/global.css` usando `@theme` de Tailwind v4 (no hay `tailwind.config.js`; Tailwind v4 se configura vía CSS).

## Comandos

```bash
npm install
npm run dev      # http://localhost:4321
npm run build    # genera dist/
npm run preview  # sirve el build de producción
```

## Estructura de archivos

```
src/
  layouts/Layout.astro       # <head>, fuentes, metadata SEO/OG
  components/
    Header.astro
    Hero.astro
    Propuesta.astro
    Beneficios.astro
    Confianza.astro          # prueba social
    Planes.astro
    FormularioDemo.astro
    FAQ.astro
    Footer.astro
  styles/global.css          # paleta, tipografía, tokens, utilidades
  pages/index.astro          # ensamblaje de la página
```

## Próximos pasos sugeridos

- Conectar el formulario de `#demo` a un endpoint real (API route de Astro, o un servicio como Formspree/Resend).
- Reemplazar las métricas de la sección de prueba social por datos reales una vez SABRIN tenga usuarios activos.
- Si se requiere multi-idioma o blog, considerar `astro:content` para colecciones.
