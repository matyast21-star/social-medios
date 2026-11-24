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

Sitio en línea: https://social-medios.matyast21.workers.dev/

## Cuando se conecte socialmedios.cl
1. Reemplazar `https://social-medios.matyast21.workers.dev/` por `https://socialmedios.cl/` en `index.html` (canonical, og:url, og:image, twitter:image, JSON-LD), `robots.txt` y `sitemap.xml`:
   `grep -rl "social-medios.matyast21.workers.dev" index.html robots.txt sitemap.xml | xargs sed -i 's#https://social-medios.matyast21.workers.dev/#https://socialmedios.cl/#g'`
2. Cloudflare → socialmedios.cl → Rules → Redirect Rules: `www.socialmedios.cl/*` → `https://socialmedios.cl/${1}` (301).
3. Worker `social-medios` → Settings → Domains & Routes: agregar `socialmedios.cl` como Custom Domain y desactivar `workers.dev` (o redirigirlo) para que no quede duplicado.
