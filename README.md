# Avance de obra PLMB · sitio publicado

Sitio estático (GitHub Pages) con la app de Experience Builder que muestra el avance de obra de E15, I16 y E16 con el
widget *Avance de obra 3D* (repositorio `avance-obra-3d-exb`) y los datos que ese widget lee.

## Contenido

| Ruta | Qué es |
|---|---|
| `data/avance-elements.json` | Un registro por elemento: % de avance, estado, actividad, contratista y fechas de cronograma |
| `predial-station-footprints.json` | Huellas prediales de E15 y E16 (WGS84) |
| `.nojekyll` | Hace que GitHub Pages sirva todas las carpetas de la app tal cual |
| *(app de Experience Builder)* | Se agrega en el paso 2 |

## Pasos

1. **Publicar este repositorio** desde GitHub Desktop (público, para usar GitHub Pages gratis) y activar
   **Settings → Pages → Deploy from branch → main / (root)**. La URL queda como
   `https://<usuario>.github.io/avance-plmb/`.
2. **Agregar la app.** En Experience Builder Developer:
   - Abre la experiencia y, en la configuración del widget *Avance de obra 3D*, cambia **URL de serve.mjs** por
     `https://<usuario>.github.io/avance-plmb` (sin barra al final). Guarda y publica.
   - **⋯ → Descargar**, descomprime el .zip y copia su contenido en la raíz de este repositorio, junto a `data/`.
   - Haz commit y push desde GitHub Desktop.
3. **Registrar en ArcGIS Online:** Contenido → Nuevo elemento → Aplicación, pega la URL del paso 1 y comparte el
   elemento.

La escena (web scene *Avance de obra - PLMB* del portal de la SDP) y los servicios de escena son públicos, así que la app
abre sin iniciar sesión.

## Actualizar el avance

Reemplaza `data/avance-elements.json` por la versión nueva que genera `export_elements.py` y haz commit y push; no hace
falta volver a descargar la app.
