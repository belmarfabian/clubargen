# Stack técnico — decisión y razonamiento

## Decisión

**Astro + Cloudflare Pages + Cloudflare R2.**

- **Framework:** Astro (sitio estático, content collections en Markdown)
- **Hosting:** Cloudflare Pages
- **Media pesada:** Cloudflare R2
- **Videos largos:** embebidos desde Instagram o YouTube (no autoalojados)
- **Dominio:** `clubargen.com`

## Por qué Astro

1. **Sitio estático por defecto.** El sitio del club no necesita backend: es un repositorio editorial (equipos, partidos, fotos, sponsors, noticias). HTML estático sirve mejor que cualquier framework SSR.
2. **Content collections en Markdown.** Los contenidos viven como archivos `.md` con frontmatter validado por Zod. Quien actualice el sitio (el cuñado del usuario) edita un archivo Markdown y commitea — no toca HTML, JS ni base de datos.
3. **Zero JS por defecto.** Astro envía cero JavaScript al cliente salvo donde se pida explícitamente (islands). Esto da carga rápida en mobile, que es donde la hinchada va a abrirlo.
4. **Curva baja.** Para alguien que sabe HTML/Markdown, Astro es más amigable que Next.js o SvelteKit.
5. **Comunidad y plantillas.** Hay templates para clubes/equipos deportivos que se pueden adaptar.

## Por qué Cloudflare Pages

1. **Gratis con cuotas amplias.** Plan gratuito: ancho de banda ilimitado, 500 builds/mes, 100 builds simultáneos. Para un club que va a deployar pocas veces al mes sobra de lejos.
2. **Deploy desde Git automático.** Conectado a GitHub: cada push a `main` despliega; cada PR genera preview deploy con URL única.
3. **Edge global.** Sirve desde la red Cloudflare (300+ ciudades). Latencia baja en LATAM.
4. **HTTPS automático.** Certificado en cuestión de minutos cuando se conecta el dominio.
5. **Integración natural con R2.** Mismo proveedor, sin egress fees entre Pages y R2.

## Por qué Cloudflare R2 para media

1. **10 GB gratis.** Suficiente para el archivo histórico del club si se comprimen razonablemente las fotos.
2. **Sin egress fees.** A diferencia de S3, R2 no cobra por descarga. Crítico cuando se sirven fotos a la hinchada en redes.
3. **API S3-compatible.** Cualquier herramienta que sepa hablar con S3 (rclone, aws-cli, librerías) funciona contra R2.
4. **Custom domain.** Se puede servir el bucket bajo `media.clubargen.com` o similar.

## Alternativas descartadas y por qué

- **WordPress:** mantenimiento, plugins, seguridad. Para un club chico sin sysadmin, es liability.
- **Squarespace / Wix:** locked-in, costoso a mediano plazo, sin control sobre código ni archivo. Curiosamente, hoy `clubargen.com` está en parking de Squarespace, lo que confirma que probaron por ahí pero no terminaron de construir nada.
- **Next.js + Vercel:** overkill. Vercel también tiene buen plan gratis, pero Next.js suma complejidad que el sitio no necesita (no hay autenticación, ni dashboard, ni rendering dinámico).
- **GitHub Pages:** funciona, pero CF Pages es estrictamente mejor (build hooks, previews, edge, R2 cerca).
- **S3 + CloudFront:** más caro y más complejo de configurar. R2 + Pages cubre el caso con menos piezas.

## Riesgos y mitigaciones

1. **Lock-in con Cloudflare.** Mitigación: el código vive en GitHub, los Markdown son portables, las fotos en R2 se pueden migrar a S3 con `rclone` en una tarde si hace falta.
2. **Quien actualiza no sabe Git.** Mitigación: editar Markdown vía GitHub web (interfaz simple) o, si crece la necesidad, sumar un CMS headless gratuito como Decap CMS / TinaCMS sobre los mismos archivos.
3. **Builds en CF Pages tienen tiempo límite (20 min plan free).** No es problema para un sitio Astro estático con menos de 1000 páginas.
4. **R2 todavía no tiene clase de almacenamiento "frío".** Si el archivo crece mucho con video, hay que evaluar mover los videos a YouTube/Vimeo (que es lo recomendado igual).

## Pasos de implementación (orden propuesto)

1. **GitHub:** crear repo `clubargen/csyda-web` (cuenta del club o personal del admin).
2. **Astro init:** `npm create astro@latest` con template minimalista.
3. **Migrar el mockup:** convertir `mockup/index.html` en layout Astro con secciones reusables.
4. **Content collections:** definir esquemas Zod para `equipos`, `jugadores`, `partidos`, `torneos`, `posts`, `sponsors`.
5. **R2:** crear bucket `csyda-media`, configurar custom domain.
6. **CF Pages:** conectar a GitHub, configurar build (`npm run build`, output `dist/`).
7. **DNS:** una vez el sitio esté listo, coordinar con la comisión para mover nameservers de Squarespace a Cloudflare (esto requiere acceso a la cuenta donde el dominio está registrado — pendiente identificar).
8. **Cancelar Squarespace** una vez confirmado que el sitio nuevo está vivo.
