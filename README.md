# Universo Musical — CA7RIEL & Paco Amoroso

Sitio web sobre la carrera de CA7RIEL & Paco Amoroso, contada como "Las 7 Eras".
Estética editorial (inspirada en Rolling Stone): blanco, tipografía serif, rojo
como acento quirúrgico.

## Estructura del proyecto

```
├── index.html    → Portada: foto principal + lista de las 7 Eras
├── era1.html      → Retoños de grandeza (2011–2017) — fondo amarillo
├── era2.html      → Nace el mito (2018–2019) — fondo verde limón
├── era3.html      → La separación (2020–2021) — fondo verde
├── era4.html      → El regreso más esperado (2022) — fondo naranja
├── era5.html      → Bautismo de estudio (2024) — fondo rojo
├── era6.html      → Big Bang (2024–2025) — fondo violeta
├── era7.html      → Consolidación global (2026) — fondo blanco "Dancing Clouds"
├── historia.html  → La historia, diagramada como nota de revista
└── images/
    ├── portada-principal.jpeg
    ├── era1-astor-y-las-flores-de-marte.jpg
    └── era2-la-celebracion-obras.jpeg
```

**Cada página de Era (`eraN.html`) contiene:**
- Hero con **color sólido de fondo** (el que le corresponde a esa Era) — hasta
  que tengamos la foto real de cada una, que reemplaza ese color de fondo
- Contador de shows en esa Era
- Foto + texto de la Era (lado a lado)
- Filtros de categoría y de año
- Línea de tiempo con TODOS los hitos de esa Era (Canción, Álbum, EP, Video
  Clip, Concierto, Shortfilm), en orden cronológico (de más viejo a más nuevo)
- Navegación arriba y abajo: Era anterior / Volver al inicio / Era siguiente

**Para poner la foto real de una Era:** subí la imagen a la carpeta `images/`
y pedile a Claude que la cargue en el campo `foto` del objeto de esa Era
(dentro del array `DATA` en el archivo `eraN.html`) — automáticamente
reemplaza el color sólido de fondo por la foto.

---

## Cómo publicarlo gratis con GitHub Pages

### Opción A — Sin usar la terminal (la más simple)

1. Entrá a [github.com](https://github.com) y creá una cuenta si todavía no tenés.
2. Arriba a la derecha, tocá el **"+"** → **"New repository"**.
3. Poné un nombre (por ejemplo `universo-musical`), marcalo como **Public**, y creá el repositorio.
4. Dentro del repositorio, tocá **"Add file" → "Upload files"**.
5. Arrastrá **todos** los archivos y la carpeta `images` completa a esa pantalla.
6. Abajo, tocá **"Commit changes"**.
7. Andá a **Settings** → **Pages** (menú de la izquierda).
8. En "Source", elegí la rama **main**, carpeta **/ (root)**, y guardá.
9. GitHub te va a dar una URL así:
   `https://tu-usuario.github.io/universo-musical/`

### Opción B — Con git (si ya lo usás)

```bash
git init
git add .
git commit -m "Primera versión del sitio"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/universo-musical.git
git push -u origin main
```

---

## Cómo editar el contenido

- Los **datos de cada Era** (nombre, período, texto, foto) y **todos los
  hitos** viven en el array `DATA`, dentro de **cada archivo `eraN.html`**
  (buscá el comentario `DATOS DEL TIMELINE`). Como cada página comparte el
  mismo array completo, **si agregás o corregís un dato, hay que replicar
  el cambio en los 7 archivos** — o pedírselo a Claude.
- El **color de fondo y el contador de shows** de cada Era se definen arriba
  de cada archivo, en `window.PAGE_CONFIG = { ... }`.
- Las **fotos** están en la carpeta `images/`.
- Los **premios** (5 Latin Grammy · 1 Grammy · 7 Gardel) se editan en
  `index.html`, buscá `stat-awards`.

---

## Cómo verificar el favicon, Open Graph y SEO

Estas tres cosas no se ven "dentro" del sitio en sí — se ven en lugares específicos:

- **Favicon**: mirá la pestaña del navegador cuando tenés el sitio abierto — debería verse un cuadradito rojo con un "7" blanco, en vez del ícono genérico. En el celular, se ve en la pestaña del navegador y si guardás el sitio como acceso directo/marcador.
- **Open Graph** (cómo se ve el link al compartirlo): la forma más directa es pegar el link real de tu sitio (una vez subido) en una herramienta como **[opengraph.xyz](https://www.opengraph.xyz/)** o el **[Facebook Sharing Debugger](https://developers.facebook.com/tools/debug/)** — ahí ves exactamente la tarjetita (foto + título + descripción) que va a aparecer cuando alguien pegue tu link en WhatsApp, Twitter/X o redes. Ojo: a veces estas plataformas guardan una versión vieja en caché — si cambiás la imagen más adelante, puede tardar en actualizarse ahí, aunque tu sitio ya esté actualizado.
- **SEO**: no se ve de forma inmediata (Google tarda en indexar sitios nuevos, puede llevar días o semanas). Podés confirmar que el código está bien mirando el "código fuente" de la página en el navegador (click derecho → "Ver código fuente de la página") y buscando la línea `<meta name="description"...`.

## Roadmap y decisiones tomadas

Esta sección es un registro de qué se decidió dejar para más adelante, y por qué — para no perder el hilo entre sesiones de trabajo.

### ✅ Ya decidido / implementado

- **Contador de visitas (GoatCounter)**: está conectado, pero **no se muestra ningún número en la página pública** (decisión tomada a propósito). Para ver las estadísticas (visitas, países), entrar a `lucesdelsur.goatcounter.com` con el login de la cuenta. Es privado, solo lo ve quien tenga ese acceso.
- **CSS y datos duplicados en los 7 archivos de Era**: es intencional, no un error — prioriza que el sitio funcione siempre aunque se abra un solo archivo suelto, sin depender de archivos externos que se puedan romper o desincronizar.
- **Categorías de filtro**: consolidadas a 4 — Discografía (canciones, álbumes/EPs, cortometrajes), Colaboración, Prensa (entrevistas + artículos), Conciertos.
- **Jerarquía "hito destacado"**: los hitos más importantes de cada Era tienen tratamiento visual más grande (foto e título más grandes, franja con tinte del color de la Era), visible también en celular.

### 🕑 Pendiente para una segunda etapa

- **Página de Premios**: hoy es solo una línea de texto en la portada ("5 Latin Grammy · 1 Grammy · 7 Gardel"). Se evaluará armar una página propia con el detalle de cada premio (año, categoría) más adelante.
- **Página de Colaboradores**: un "quién es quién" del universo (Chita, Wos, Miranda!, Jack Black, Sting, Anderson .Paak, etc.), aprovechando que ya existe el filtro de "Colaboración". Se evaluará cuando el contenido principal esté más avanzado.
- **Layout en grilla para la línea de tiempo**: hoy los hitos van uno debajo del otro (franjas secuenciales). Se está evaluando una alternativa en grilla (varias columnas) para achicar el largo de cada página de Era. Pendiente de mockup antes de implementar.
- **SEO / Open Graph / favicon**: para que el link se vea bien al compartirlo en WhatsApp o redes, y que el navegador muestre un ícono propio en la pestaña.

### ❓ Sin resolver — a la espera de datos

- El texto acortado de cada Era (el usuario lo va a proveer).
- El texto completo de `historia.html` (hoy es un placeholder).
- Varios hitos sin foto, descripción o link — ver la planilla de seguimiento (`hitos-para-completar.xlsx`) para el detalle fila por fila.

## Hecho por

Lucesdelsur
