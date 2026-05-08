# Assets pendientes — qué necesita aportar la comisión

Inventario exacto de los archivos visuales que faltan para que el sitio deje de tener placeholders. Cada ítem indica:

- **Dónde aparece** en el sitio (sección + selector HTML)
- **Marca de placeholder actual** (atributo `data-pendiente` en el HTML, para encontrarlo con `Ctrl+F`)
- **Qué se espera** (formato, tamaño, lo que sea relevante)

Cuando llegue el asset, el reemplazo es directo: se sustituye el contenido del nodo marcado por el `<img>` o `<svg>` correspondiente.

---

## 1. Escudo oficial

- **Dónde:** hero (`<img class="hero-escudo">`), nav (`.escudo-mini`), footer (`<img style="width:48px">`).
- **Estado actual:** PNG provisional `assets/escudo.png` (637×637, fondo blanco convertido a transparente). Origen: foto de perfil de la página de Facebook del club (ID `2281069708840919`), bajada vía Facebook Graph API pública. El SVG aproximado anterior fue eliminado del HTML.
- **Qué se espera para reemplazar:**
  - **SVG vectorial** (escala perfecta, peso bajo) preferido.
  - PNG transparente alta resolución (1024×1024+) si no hay vectorial.
  - Idealmente con archivo original de Illustrator/CorelDraw.
- **Ruta destino:** `assets/escudo.svg` (sobrescribir/agregar). El sitio ya hace referencia a `assets/escudo.png`; se puede dejar el `.png` como fallback y agregar `.svg` después.

## 2. Fotos por categoría (4)

- **Dónde:** sección Equipos. Cada `.equipo-foto` con atributo `data-pendiente`:
  - `data-pendiente="foto-primer-equipo"`
  - `data-pendiente="foto-dorada"`
  - `data-pendiente="foto-femenino"`
  - `data-pendiente="foto-sub0910"`
- **Estado actual:** gradientes de color con etiqueta tipográfica.
- **Qué se espera:**
  - Foto grupal de cada categoría posando con la camiseta del club.
  - Formato: **JPG** o **WebP**, 1600×1200 mínimo (proporción 4:3 — el contenedor recorta a esa relación).
  - Si hay varias opciones, elegir la que mejor identifique a la categoría (no la más reciente necesariamente).
- **Ruta destino:** `assets/equipos/{primer-equipo,dorada,femenino,sub0910}.jpg`.

## 3. Logos de sponsors (9)

Estado mixto. Algunos tienen logo provisional descargado de fuentes públicas; otros siguen como placeholder de texto.

### 3a. Provisionales descargados (reemplazar por oficiales)

| Sponsor | Archivo actual | Origen | Notas |
|---|---|---|---|
| La Argentina Pizzería | `assets/sponsors/la-argentina-pizzeria.png` (1.2 MB) | [laargentinapizzeria.cl](https://www.laargentinapizzeria.cl/) | Logo oficial del sitio, fondo negro. Pesa demasiado para producción — la comisión debería pedir versión SVG o reducirlo. |
| Stella Artois | `assets/sponsors/stella-artois.png` (82 KB) | [Wikimedia Commons](https://commons.wikimedia.org/wiki/File:Stella_Artois_current_logo_2015.png) | Logo global. La relación entre Stella Artois Chile y CSyDA está sin confirmar — puede ser solo un acuerdo informal. |
| Marca País Argentina | `assets/sponsors/marca-pais-argentina.png` (8 KB) | [argentina.gob.ar/marca-pais](https://www.argentina.gob.ar/marca-pais) | Imagotipo oficial del programa estatal. Confirmar con la comisión si efectivamente lo usan como aval. |

### 3b. Pendientes sin logo (con o sin link al sitio)

| Sponsor | Estado | Link en HTML |
|---|---|---|
| Morfi Burger | Cadena argentina, presencia en Chile a confirmar | → [morfiburger.com](https://morfiburger.com/) |
| Maresta | Probablemente PYE Maresta (metalurgia chilena) | → [maresta.net](https://www.maresta.net/) |
| FIT | No identificable sin contexto | sin link |
| La Protect | Nombre exacto no encontrado | sin link |
| Aniania Food | Sin huella web | sin link |
| ArgmsJZ | Probable handle de Instagram | sin link |

### Qué se espera de la comisión

- **SVG** vectorial (escalable, peso bajo) preferido.
- PNG transparente como alternativa, 600px de ancho mínimo.
- Versión mono-color si la tienen.
- **Confirmar la lista real de sponsors** (estos se sacaron de la documentación previa, pero algunos pueden estar desactualizados o mal escritos).
- Para los identificables que ya tienen logo provisional: confirmar si el logo descargado es el que usan, o reemplazarlo.
- **Ruta destino:** `assets/sponsors/<nombre>.svg` (sobrescribir los `.png` actuales).

## 4. Imagen / fondo del hero (opcional)

- **Dónde:** sección hero. Hoy es solo escudo + tipografía sobre fondo hueso.
- **Estado actual:** sin imagen.
- **Qué se espera (si quieren):**
  - Foto panorámica del club en cancha o de la sede.
  - Formato: **JPG** o **WebP**, 2400×1200 mínimo, proporción 2:1.
- **Ruta destino:** `assets/hero.jpg` (a discutir si vale la pena).

## 5. Foto/ilustración de Maradona para sección D10S (opcional)

- **Dónde:** sección `.d10s-section` (fondo tinta con tipografía gigante).
- **Estado actual:** tipografía "D10S" gigante sin imagen. Funciona bien sin foto.
- **Qué se espera (si quieren reforzar):**
  - Foto de archivo (con derechos resueltos) o ilustración propia.
  - **Cuidado con derechos de imagen** de fotos de Maradona — usar fuentes oficiales o ilustración encargada.
- **Ruta destino:** `assets/d10s/maradona.jpg`.

## 6. Favicon e íconos del sitio

- **Dónde:** `<head>` del HTML.
- **Estado actual:** ninguno (el navegador muestra el ícono por defecto).
- **Qué se espera:**
  - `favicon.ico` (32×32 o 16×16 multi-resolución).
  - `apple-touch-icon.png` (180×180).
  - Idealmente derivado del escudo oficial.
- **Ruta destino:** `favicon.ico` y `apple-touch-icon.png` en la raíz.

---

## Datos NO visuales que también faltan (refresca pendientes de la doc base)

Estos no son assets pero también traban el sitio:

- Plantel completo por categoría (nombres, posiciones, números).
- Comisión directiva completa (más allá del presidente).
- Palmarés oficial (qué torneos ganó cada año).
- Cita fundacional o histórica (la sección Historia tiene el bloque `data-pendiente="cita-comision"` esperando aporte).
- Número de edición vigente de la Copa D10S y fecha de la próxima.
- Confirmación / corrección de la lista de rivales (sección "Rivales y equipos amigos").

## Cómo encontrar los placeholders en el HTML

```bash
# Lista todos los nodos esperando asset:
grep -n "data-pendiente=" index.html

# Lista todos los TODOs en el HTML:
grep -n "TODO " index.html
```
