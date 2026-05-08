# Extracción de información desde Instagram

Documento de procedencia de la información volcada en `00-documentacion-base.md`. Sirve para que un futuro lector entienda qué está validado, qué es inferido y qué hay que reconfirmar con la comisión.

## Fuente principal

- Cuenta: **@clubargen** en Instagram (perfil público).
- Espejo usado en el proceso de scraping/lectura: `imginn.com/clubargen/`.
  - **Limitación:** `imginn.com` es un scraper de terceros, depende de que el perfil siga público y cae con frecuencia. No es fuente confiable a largo plazo.
  - **Reemplazo recomendado:** export oficial de Meta (Configuración → Tu información y permisos → Descargar tu información, formato JSON + media en alta resolución). Solo el administrador de la cuenta puede generarlo.

## Qué se extrajo

- Bio del perfil (literal, con emojis).
- Métricas: 1.5K seguidores, 577 publicaciones, 631–648 cuentas siguiendo (rango porque varió entre lecturas).
- Listado parcial de hashtags recurrentes: `#copadenaciones`, etc.
- Posts ancla que permitieron identificar:
  - Año de fundación (2019, declarado en escudo y en posts aniversario).
  - Categorías deportivas activas (Primer equipo, Dorada, Femenino, Sub 2009/2010).
  - Torneos disputados (Copa D10S La Serena, Copa Santiago, Copa Plata, Copa de Naciones, Liga Dos Ligados).
  - Rivales y equipos amigos mencionados con regularidad.
  - Sponsors etiquetados en publicaciones.
  - Componente social: colectas Albergue Protege, entrega de cajas Escuela Técnica Las Nieves.
  - Conmemoraciones: 24 de marzo (Memoria), 2 de abril (Malvinas).
- Nombres de comisión recogidos de tags y menciones repetidas:
  - Presidente: Fidel Di Tomaso (@fidelditomaso)
  - DT primer equipo: Jonatan Miranda (@jonatanjmiranda)
  - Capitán: Rama Corbascio (@ramacorbascio)
  - Indumentaria: Seba (+56 9 9485 0007), Gonza (+56 9 4232 6793)

## Qué NO se logró extraer

- Plantel completo con nombres y posiciones por categoría.
- Comisión directiva completa (más allá del presidente).
- Estatutos y figura legal del club.
- Palmarés (resultados oficiales por torneo y temporada).
- Quién fundó el club y la historia narrada del origen.
- Fotos en alta resolución (Instagram comprime; lo descargado vía espejo es web-quality).

## Otras fuentes consultadas

- **Facebook:** página "Club Social y Deportivo Argentino", 360+ seguidores, 5.0 con 2 reseñas. Aporta menos contenido que Instagram.
- **Dominio `clubargen.com`:** activo, sirviendo página parking de Squarespace ("En construcción. Regresa pronto..."). Implica que alguien paga una suscripción Squarespace; identificar quién y desde cuándo antes de migrar.

## Riesgos y notas para el lector futuro

1. **No tratar `imginn.com` como fuente persistente.** Si el perfil se vuelve privado o el scraper cae, esta fuente desaparece.
2. **El export oficial de Meta es prioridad alta.** Sin él no hay archivo robusto ni fotos en alta para el sitio.
3. **Algunos datos pueden estar desactualizados.** El club tiene rotación de cuerpo técnico, capitanía y sponsors. Validar con la comisión antes de publicar.
4. **Privacidad:** los teléfonos de comisión de indumentaria están en bio/posts públicos del club, así que su inclusión en documentación interna es razonable; si van al sitio público hay que confirmar consentimiento.
