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

## Hecho por

Lucesdelsur
