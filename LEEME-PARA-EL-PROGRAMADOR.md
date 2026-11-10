# Landing Luana Thays (marca LUVANA) — traspaso al programador

Hola. Esta carpeta tiene la landing terminada y probada. Es un sitio estático: un solo HTML con CSS y JS adentro, más las fotos y videos en `assets/`. No necesita backend, base de datos ni build. Se puede subir tal cual a cualquier hosting.

## 1. Qué hay en la carpeta

```
luvana-landing/
├─ index.html                 ← la landing completa (HTML + CSS + JS en un archivo)
├─ LEEME-PARA-EL-PROGRAMADOR.md
└─ assets/
   ├─ img/      ← 50 fotos del portfolio, avatar y logo del footer (JPG/PNG)
   ├─ video/    ← 3 clips de la sección "Cámara" (MP4, H.264)
   └─ logos/    ← variantes del isologo LUVANA en PNG (referencia de marca)
```

Probado en Chrome de escritorio (1280 px) y celular (390 px): todas las fotos y videos cargan, no hay errores de consola y no hay scroll horizontal.

## 2. Cómo publicarla

1. Subir `index.html` y la carpeta `assets/` completa a la raíz del dominio, respetando la estructura.
2. No cambiar nombres de archivos: el HTML los busca con esas rutas exactas.
3. Activar HTTPS.
4. Recomendado: compresión gzip/brotli para el HTML y caché larga para `assets/` (las fotos y videos no cambian seguido).

Peso total aprox.: 8,5 MB (3,4 MB de fotos y 4,9 MB de video). Las fotos del portfolio usan `loading="lazy"`.

## 3. Identidad visual (respetar)

**Prioridad: mobile first.** La mayoría de las visitas van a llegar desde Instagram en el celular.

**Paleta** (definida como variables CSS en `:root`):

| Variable | Hex | Uso |
|---|---|---|
| `--wine` | #441019 | texto principal, bordes, fondos oscuros |
| `--red` | #d9042b | acentos |
| `--orange` | #ff7900 | acentos, degradé |
| `--yellow` | #ffda40 | botones, destacados |
| `--olive` | #879e00 | fondos de sección |
| `--pink` | #f288c2 | resaltados, stickers |
| `--sky` | #a5bae7 | fondos de sección, cinta del hero |
| `--blue` | #1e56ba | foco de accesibilidad, acentos |
| `--cream` | #f2ead0 | fondo general |

Cada sección tiene su propio color de fondo de marca (es parte central del diseño, no unificar). La inspiración general es el **atardecer**: el degradé `--sunset` del hero va de bordó a rojo, naranja y amarillo.

**Tipografías:**
- **Montserrat** (Light 300, Medium 500, Bold 700, Extrabold 800, Black 900): cuerpo y títulos en mayúscula. Se carga desde Google Fonts.
- **Times New Roman** (Bold, Bold Italic, Italic, Regular): palabras destacadas en itálica dentro de títulos. Es fuente de sistema, no se carga.
- **Caveat**: solo para anotaciones cortas "a mano" (notas, post-its). Nunca para texto largo. Se carga desde Google Fonts.

**Logo LUVANA:** va solo en el footer, no en el menú. Siempre con fondo transparente. Los PNG de `assets/logos/` son de baja resolución; si hace falta más calidad, pedile a Luana los vectores (SVG/AI).

## 4. Estructura de la página

| # | Sección | Ancla | Qué contiene |
|---|---|---|---|
| — | Menú fijo | — | Nombre, links a secciones, botón "Escribime" a WhatsApp |
| 1 | Hero | `#top` | Titular animado, celular con clip en loop (botón de sonido), stickers y cinta ondulada |
| 2 | Marcas | — | Marquesina con las marcas con las que trabajó |
| 3 | Sobre mí | `#sobre-mi` | Carpeta con polaroids + línea de tiempo |
| 4 | Servicios | `#servicios` | Tres rubros: branding, redes, video |
| 5 | Proceso | `#proceso` | 3 pasos: Me contás → Te propongo → Lo hacemos real |
| 6 | Cámara | `#camara` | 3 videos nativos (Shell Mundial, Happy Hour, Copa BAIC) |
| 7 | Portafolio | `#portfolio` | Pestañas por marca: Historias / Posteos / Reels / Branding, links a Behance |
| 8 | Herramientas | `#herramientas` | Software que usa + tapa de revista |
| 9 | Tarifario | `#tarifario` | Selector de cliente A/B/C, precios en ARS y USD |
| 10 | Contacto | `#contacto` | CTA a WhatsApp, Behance |
| — | Footer | — | Logo LUVANA |

## 5. Interacciones (JS vanilla, sin librerías)

- Video del hero en autoplay silenciado, con botón para activar sonido.
- Pestañas del portafolio por marca.
- Selector de tier del tarifario (Cliente A / B / C).
- Stickers arrastrables, parallax suave en objetos del hero, inclinación 3D de fotos al pasar el mouse (solo en dispositivos con hover).
- Aparición con rebote al entrar en pantalla (IntersectionObserver).
- Todo respeta `prefers-reduced-motion`: si el usuario pidió menos movimiento, las animaciones se desactivan.

## 6. Datos a tener a mano

- **WhatsApp:** +54 9 3704 291376 → `https://wa.me/5493704291376` (aparece en varios botones)
- **Behance:** https://behance.net/luanacantero
- **Instagram:** @luvana.dg
- **Nombre que se muestra:** Luana Thays (no "Luana Cantero")
- **Tarifario:** Cliente A = empresas de más de 50 empleados, B = 10 a 50, C = hasta 10. Los precios en USD se calculan con 1 USD = $1.550 ARS. Los valores están escritos directamente en el HTML, dentro de `#tarifario`.

## 7. Mejoras sugeridas al pasarla a producción (opcional)

- Agregar favicon y metadatos Open Graph (imagen y título para cuando se comparte el link en WhatsApp o Instagram).
- Convertir las fotos a WebP/AVIF para que cargue más rápido.
- Separar el CSS y el JS en archivos propios si se va a seguir manteniendo.
- Sumar Google Analytics o Meta Pixel si Luana quiere medir visitas.
- Si se migra a un CMS o framework, mantener el diseño exactamente como está: paleta, tipografías, fondos por sección y animaciones.
