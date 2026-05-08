# DOCUMENTACIÓN BASE — Web Club Social y Deportivo Argentino (CSyDA / @clubargen)

Este documento es la fuente de verdad del proyecto. Contiene toda la información recopilada del club para construir su sitio web.

**Stack acordado:** Astro + Cloudflare Pages + Cloudflare R2 para media pesada.

---

## 1. IDENTIDAD

- **Nombre completo:** Club Social y Deportivo Argentino
- **Sigla oficial:** CSyDA
- **Apodo de la hinchada:** ARGar (de "Vamos ARGar")
- **Año de fundación:** 2019 (cumple 7 años en 2026)
- **Ubicación:** Alonso de Córdova, Vitacura, Santiago de Chile (RM)
- **Tipo:** club de la colectividad argentina residente en Chile
- **Bio Instagram literal:** "Club Social y Deportivo Argentino AR 🌎 📍 Santiago de Chile RM CL ✉️ clubsocialydeportivoargentino@gmail.com"
- **Métricas IG:** 1.5K seguidores, 577 publicaciones, 631–648 siguiendo

## 2. ESTRUCTURA INSTITUCIONAL

- **Presidente:** Fidel Di Tomaso (@fidelditomaso) — además fundador de Marca Argentina SpA
- **DT primer equipo:** Jonatan Miranda (@jonatanjmiranda)
- **Capitán:** Rama Corbascio (@ramacorbascio)
- **Comisión de indumentaria:** Seba (+56 9 9485 0007), Gonza (+56 9 4232 6793)
- Otros nombres mencionados: "Seba de Dorada"

## 3. CONTACTO

- **Dominio:** `clubargen.com` (registrado y activo, hoy sirve página parking de Squarespace — verificar acceso con la comisión)
- **Email institucional:** presidencia@clubargen.com
- **Email general:** clubsocialydeportivoargentino@gmail.com
- **Email deporte:** deportescsyda@gmail.com
- **Instagram:** [@clubargen](https://www.instagram.com/clubargen/)
- **Facebook:** Club Social y Deportivo Argentino (360+ seguidores, 5.0 estrellas con 2 reseñas)

## 4. IDENTIDAD VISUAL

- **Escudo:** hexagonal celeste con sol de mayo, leyenda "CLUB SOCIAL Y DEPORTIVO ARGENTINO 2019"
- **Colores:** celeste y blanco
- **Camiseta titular:** rayas celeste y blanca, short negro
- **Sponsor frontal histórico de camiseta:** Fit
- **Concurso UNIFORME OFICIAL 2026** en curso (camiseta, short y medias deben respetar la identidad)

## 5. CATEGORÍAS DEPORTIVAS

- Fútbol 11 (cancha grande)
- Categoría DORADA (adultos / +35 / oro)
- Sub 2009/2010 masculino (formativas)
- Equipo femenino (activo desde el origen)

## 6. RIVALES Y EQUIPOS AMIGOS

Quiltros FC (QFC), Cancheros, Maestros FC (fundado 2000), Halcones, Fortaleza, Crecer, Estudiantes Unidos, Academia.

## 7. TORNEOS

- **Copa D10S — La Serena** (5ª edición en 2026) — torneo emblemático del club, juego de palabras D10S = Dios + 10 (homenaje a Maradona)
- Copa Santiago
- Copa Plata
- Copa de Naciones (#copadenaciones)
- Liga "Dos Ligados 2026"

## 8. COMPONENTE SOCIAL Y COMUNITARIO (eje identitario)

- Colecta solidaria en cada Copa D10S → **Albergue Protege** (personas en situación de calle, La Serena), en alianza con Municipalidad de La Serena
- IV Entrega de Cajas de Alimentos a Familias **Escuela Técnica Las Nieves**, en alianza con La Protect (compañía de seguros)
- Acompañamiento a familias de la colectividad argentina en Chile

## 9. CONMEMORACIONES

- **24 de marzo:** "A 50 años del Golpe militar — Nunca Más" (Memoria, Verdad y Justicia)
- **2 de abril:** Día del Veterano y Caídos en la Guerra de Malvinas
- Visitas a "La Casa de D10S" (mural Maradona, La Boca)

## 10. SPONSORS Y PARTNERS

Fit (camiseta), Stella Artois, La Argentina Pizzería (sponsor fundacional, sede de presentaciones), La Protect (seguros), Marca Argentina SpA, anianiaifood, morfiburger, argmsjz, Maresta.

## 11. SEDE E INFRAESTRUCTURA

- **Sede principal:** Vitacura (Alonso de Córdova), Santiago
- **Comedor en remodelación 2026**
- Han jugado en el Estadio La Serena

## 12. ARCHIVO DISPONIBLE

- 577 publicaciones en Instagram (2019–2026) accesibles vía `imginn.com/clubargen/`
- **Recomendación:** que la comisión exporte el archivo oficial desde Meta para tener fotos en alta resolución (Configuración → Tu información y permisos → Descargar tu información, formato JSON + media en alta).

## 13. PROPUESTA TÉCNICA

**Stack:**

- Framework: Astro (sitio estático, content collections en Markdown)
- Hosting: Cloudflare Pages (gratis, ancho de banda ilimitado, 500 builds/mes)
- Media pesada: Cloudflare R2 (10 GB gratis)
- Videos largos: embebidos desde Instagram o YouTube
- Dominio: `clubargen.com`

**Secciones de la web:**

- Inicio
- Historia
- Equipos (primer equipo, Dorada, Femenino, Sub 2009/2010)
- Copa D10S (sección destacada)
- Sede Vitacura
- Comisión Directiva
- Acción social
- Memoria (24M / 2A)
- Galería / Archivo
- Sponsors
- Sumate (formulario)
- Contacto

## 14. PENDIENTES (info que solo puede aportar la comisión)

- Plantel completo con nombres y fotos por categoría
- Historia detallada (quién fundó, por qué nació el club)
- Estatutos y comisión directiva completa
- Palmarés oficial (campeonatos por temporada)
- Banco de fotos en alta resolución (export oficial de Meta)
- Estado del dominio `clubargen.com` (¿quién lo administra hoy en Squarespace?, desde cuándo se paga, transferir registrar a Cloudflare o no)
- Definir si quieren formulario de socios / aporte mensual / tienda de indumentaria

---

**Próxima fase a pedir cuando se retome el chat:** estructura de carpetas Astro lista para clonar + esquemas de content collections en Markdown.
