# CLAUDE.md — Contexto del proyecto csyda-web

## Qué es esto

Sitio web del **Club Social y Deportivo Argentino (CSyDA)**, club de la colectividad argentina residente en Chile (Santiago, Vitacura), fundado en 2019. Instagram: [@clubargen](https://www.instagram.com/clubargen/). Dominio: `clubargen.com`.

El proyecto está en fase de documentación + mockup visual aprobado. La siguiente fase es construir el sitio en Astro y desplegarlo en Cloudflare Pages.

## Fuente de verdad

**Antes de proponer cambios o agregar contenido, leer `docs/00-documentacion-base.md`.** Es la documentación oficial del club, con 14 secciones (identidad, estructura, contacto, identidad visual, categorías, rivales, torneos, componente social, conmemoraciones, sponsors, sede, archivo, propuesta técnica, pendientes).

No inventar datos del club. Si falta información, va a la lista de pendientes (sección 14), no se rellena con suposiciones.

## Stack acordado

- **Framework:** Astro (sitio estático con content collections en Markdown)
- **Hosting:** Cloudflare Pages (gratis, ancho de banda ilimitado, 500 builds/mes)
- **Media pesada:** Cloudflare R2 (10 GB gratis, sin egress fees)
- **Videos largos:** embebidos desde Instagram o YouTube
- **Dominio:** `clubargen.com` (hoy en Squarespace; migrar nameservers a Cloudflare cuando se despliegue)

Razonamiento detallado en `docs/02-stack-tecnico.md`.

## Reglas de diseño y copy

### Identidad visual (del mockup aprobado)

- **Paleta:**
  - Celeste argentino: `#74ACDF`
  - Hueso: `#FAF8F3` (fondo, no blanco puro — el sitio es archivo/editorial, no startup)
  - Tinta: `#0E1116`
  - Oro sol de mayo: `#F4B940`
- **Tipografía:**
  - Titulares: Archivo Black (gancho periodístico-deportivo)
  - Acentos / bajadas: Fraunces itálica (románticos, identitarios)
  - Cuerpo: DM Sans
- **Escudo:** hexagonal celeste con sol de mayo, leyenda "CLUB SOCIAL Y DEPORTIVO ARGENTINO 2019". El SVG del mockup es una aproximación; reemplazar por el oficial cuando lo aporte la comisión.
- **D10S:** pieza editorial gigante con el "10" en oro y subrayado. El guiño a Maradona pesa mucho en la identidad y merece protagonismo visual. No achicar.
- **Memoria (24M / 2A):** sección propia, no diluida entre "actividades". El club lo trata como eje, no decoración.

### Tono

- Editorial, archivo, club de barrio con historia — no startup ni marketing deportivo.
- Castellano rioplatense + chileno mezclado es válido (es la realidad de la colectividad).
- Evitar lenguaje publicitario inflado. El club se presenta como lo que es.

## Reglas de comportamiento para Claude Code

1. **No inventar datos del club.** Nombres, fechas, palmarés, plantel, fundadores: si no está en la documentación, va a pendientes.
2. **Antes de tocar el dominio o DNS, confirmar con el usuario.** El dominio hoy lo administra Squarespace; cualquier cambio de nameservers es coordinación con la comisión, no acción autónoma.
3. **Para imágenes de placeholder usar SVG inline o cuadros de color**, nunca URLs de servicios externos como `via.placeholder.com` o stock photos genéricos. Cuando llegue el export oficial de Meta, ahí entran las fotos reales.
4. **El archivo de Instagram debe venir del export oficial de Meta**, no de scrapers de terceros como `imginn.com` (caen, dependen de que el perfil siga público, sin alta resolución).
5. **No agregar features hipotéticas:** tienda, sistema de socios pago, calendario sincronizado, etc. — solo si la comisión las pide explícitamente.
6. **Idioma del usuario: español.** Comunicación, comentarios y commits en español.
7. **Auto-aceptación de tool calls está activada.** No pedir confirmación para edits locales reversibles. Sí confirmar para acciones destructivas o que afecten sistemas compartidos (push a remote, deploy, cambios DNS).

## Pendientes que solo puede aportar la comisión

(Resumen de la sección 14 de la documentación base.)

- Plantel completo con nombres y fotos por categoría
- Historia detallada (quién fundó, por qué nació el club)
- Estatutos y comisión directiva completa
- Palmarés oficial (campeonatos por temporada)
- Banco de fotos en alta resolución (export oficial de Meta)
- Estado del dominio `clubargen.com` (¿quién lo administra hoy en Squarespace?)
- Definir si quieren formulario de socios / aporte mensual / tienda de indumentaria

## Persona de contacto

El usuario (Fabián Belmar) coordina con su cuñado, que será quien actualice contenido del sitio una vez desplegado. El sitio debe ser editable sin tocar código (de ahí la elección de content collections en Markdown).
