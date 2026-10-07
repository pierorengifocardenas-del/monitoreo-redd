# App instalable "Monitoreo REDD+" (PWA) – Guía de publicación

Esta carpeta convierte la app de Google Earth Engine en una **aplicación instalable en Android**
(ícono propio, pantalla completa, sin barra de Chrome).

| Archivo | Para qué sirve |
|---|---|
| `index.html` | Muestra la app GEE a pantalla completa, con pantalla de carga y aviso sin internet |
| `manifest.json` | Nombre, colores e íconos de la app |
| `sw.js` | Requisito de Android para ofrecer "Instalar app" |
| `icons/` | Íconos (puede reemplazarlos por el logo de COOPAFSAMAD con los mismos nombres y tamaños) |

Si la URL de la app GEE cambia, edite la línea `var URL_APP = '...'` en `index.html`.

## 1. Publicar en GitHub Pages (gratis, una sola vez)

1. Cree una cuenta en **github.com** (si no tiene).
2. Botón **+ → New repository**
   - Repository name: `monitoreo-redd`
   - Marque **Public** → **Create repository**.
3. En el repositorio: **Add file → Upload files** → arrastre **todo el contenido de esta carpeta**
   (`index.html`, `manifest.json`, `sw.js` y la carpeta `icons`) → **Commit changes**.
4. Vaya a **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** / carpeta **/(root)** → **Save**.
5. Espere 1–2 minutos. Arriba aparecerá la dirección, por ejemplo:
   `https://SU-USUARIO.github.io/monitoreo-redd/`

## 2. Instalar en Android

1. Abra esa dirección en **Chrome** del celular.
2. Toque **"Instalar"** en el aviso que aparece abajo, o el menú **⋮ → Instalar aplicación**.
3. La app "Monitoreo REDD+" queda en la pantalla de inicio y en el cajón de apps.

Comparta solo el link de GitHub Pages con el equipo; cada uno la instala igual.

## 2b. Instalar en iPhone / iPad (iOS)

iOS no muestra un botón "Instalar"; se agrega a mano (la página muestra estas instrucciones):

1. Abra la dirección de GitHub Pages en **Safari** (en iOS 16.4 o superior también sirve Chrome).
2. Toque **Compartir** (cuadrado con flecha ↑).
3. **Agregar a pantalla de inicio** → **Agregar**.

Queda con el mismo ícono y se abre a pantalla completa, igual que en Android.

## 3. Actualizaciones

- **Cambios en el script GEE:** se ven automáticamente en la app instalada (no hay que hacer nada).
- **Cambios en estos archivos (ícono, nombre):** súbalos de nuevo a GitHub y cambie
  `monitoreo-redd-v1` por `-v2` en `sw.js` para forzar la actualización.

## Si el mapa no carga dentro de la app

Si se queda en la pantalla de carga, a los 20 s aparece el enlace "abre la app directamente".
En ese caso Earth Engine no está permitiendo mostrarse dentro de otra página; avise para cambiar
`index.html` a modo "redirección" (la app instalada abrirá el link de GEE directamente).

## Opcional: archivo APK / Play Store

Con la página ya publicada, entre a **pwabuilder.com**, pegue la dirección de GitHub Pages →
**Package for stores → Android**. Obtendrá un archivo para instalar directo en los celulares
o para subir a Play Store (cuenta de desarrollador Google: pago único de 25 USD).
