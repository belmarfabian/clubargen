# csyda-web — Sitio Club Social y Deportivo Argentino

Repositorio del sitio web del **Club Social y Deportivo Argentino (CSyDA / @clubargen)**, club de la colectividad argentina residente en Chile, fundado en 2019, con sede en Vitacura, Santiago.

## Estado actual

- Documentación base recopilada (ver `docs/00-documentacion-base.md`).
- Mockup visual aprobado en HTML estático (`mockup/index.html`) — sirve como referencia de identidad antes de migrar a Astro.
- Stack acordado: **Astro + Cloudflare Pages + Cloudflare R2** para media pesada.
- Dominio `clubargen.com` registrado y vivo, sirviendo página parking de Squarespace. Pendiente: identificar quién administra el dominio y la cuenta Squarespace, y planificar migración de nameservers a Cloudflare.

## Estructura

```
csyda-web/
├── README.md                          ← este archivo
├── CLAUDE.md                          ← contexto que Claude Code lee al iniciar
├── .gitignore
├── docs/
│   ├── 00-documentacion-base.md       ← fuente de verdad (14 secciones)
│   ├── 01-extraccion-instagram.md     ← cómo se recopiló la info y limitaciones
│   └── 02-stack-tecnico.md            ← decisión Astro+CF y razonamiento
└── mockup/
    └── index.html                     ← mockup visual aprobado
```

## Cómo arrancar

```bash
# 1. Inicializar git (si todavía no está)
git init && git add . && git commit -m "Documentación base + mockup visual"

# 2. Abrir Claude Code en esta carpeta
claude
```

Al abrir Claude Code, va a leer `CLAUDE.md` automáticamente y tener cargado todo el contexto del proyecto (qué es CSyDA, stack, reglas de copy y diseño, pendientes, qué no inventar).

## Próxima fase

Transformar el mockup HTML en proyecto Astro con content collections, para que la comisión pueda actualizar contenido (partidos, fotos, noticias) sin tocar código. Antes de eso conviene:

1. Crear el repo en GitHub para que Cloudflare Pages haga deploy automático en cada commit.
2. Conseguir el export oficial del archivo Instagram (Meta → Configuración → Tu información y permisos → Descargar tu información).
3. Llenar pendientes de la sección 14 de la documentación base (plantel completo, fundadores, palmarés, etc.).

## Contacto del club

- Email institucional: presidencia@clubargen.com
- Email general: clubsocialydeportivoargentino@gmail.com
- Instagram: [@clubargen](https://www.instagram.com/clubargen/)
