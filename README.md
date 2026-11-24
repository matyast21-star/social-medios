# Social Medios CL · sitio web

Sitio estático de Social Medios CL y KaKo Rojas, desarrollado por Fluva.
Secciones: eventos por tipo, servicios, KaKo, Wiki-Kubo, cotizador que arma el mensaje de WhatsApp, cobertura y eventos reales.

## Configurar
- Número de WhatsApp de cotización: constante `WA_NUMBER` en `index.html` (hoy 56978032743, el del Linktree).

## Publicar en Cloudflare Pages
1. Cloudflare → Workers & Pages → Create → Pages → Connect to Git → este repositorio.
2. Framework preset: **None**. Build command: *(vacío)*. Build output directory: `/`.
3. Custom domains → agregar `socialmedios.cl` (y `www`).

Cada push a `main` publica una nueva versión.
