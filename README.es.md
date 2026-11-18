> [!CAUTION]
> **Este proyecto se trasladó a [ProfileStudio/ProfileStudio](https://github.com/ProfileStudio/ProfileStudio).**
> Este repositorio está archivado y ya no se actualiza. Para cambiar el plugin de Claude Code:
>
> ```text
> /plugin marketplace add ProfileStudio/ProfileStudio
> /plugin install profilestudio@profilestudio
> ```

# Generador de README para perfiles de GitHub

[English](README.md) · **Español**

Genera un README de perfil de GitHub pulido a partir de tus datos reales de GitHub: tarjetas SVG
con estadísticas en vivo, 13 temas inspirados en las herramientas que los desarrolladores usan a diario, modo claro y oscuro, y una **cabecera animada** opcional hecha con tu
propia imagen o GIF. Un agente de Claude Code te hace algunas preguntas de diseño, arma una vista
previa y publica cuando lo apruebas. ¿No usas Claude? El generador es un solo script de Python sin
dependencias.

[![Licencia: MIT](https://img.shields.io/badge/licencia-MIT-blue.svg)](LICENSE)
![Python 3.9+](https://img.shields.io/badge/python-3.9%2B-3776ab.svg)
![Plugin de Claude Code](https://img.shields.io/badge/Claude%20Code-plugin-d97757.svg)

## Ejemplo en vivo

<a href="https://github.com/WaltherMoraRivera"><img src="https://raw.githubusercontent.com/WaltherMoraRivera/WaltherMoraRivera/main/assets/header.svg" width="100%" alt="Cabecera de github.com/WaltherMoraRivera: tema terminal, acento cian, retrato pixel art animado"></a>

[github.com/WaltherMoraRivera](https://github.com/WaltherMoraRivera): tema terminal, en español, retrato pixel art animado.

## 13 temas, inspirados en las herramientas que usas a diario

| Tema | Oscuro | Claro |
|---|---|---|
| **terminal** · prompts de shell, un acento, variantes por distro de Linux | <img src="plugin/skills/github-profile/reference/styles/terminal-dark.jpg" alt="Tema terminal, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/terminal-light.jpg" alt="Tema terminal, claro"> |
| **editor** · pestañas, números de línea, tus datos escritos como código | <img src="plugin/skills/github-profile/reference/styles/editor-dark.jpg" alt="Tema editor, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/editor-light.jpg" alt="Tema editor, claro"> |
| **classic** · ventanas de escritorio de los 90 y barras de bloques | <img src="plugin/skills/github-profile/reference/styles/classic-dark.jpg" alt="Tema clásico, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/classic-light.jpg" alt="Tema clásico, claro"> |
| **win11** · ventanas planas redondeadas, botones de título | <img src="plugin/skills/github-profile/reference/styles/win11-dark.jpg" alt="Tema Windows 11, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/win11-light.jpg" alt="Tema Windows 11, claro"> |
| **macos** · semáforo, barra de título unificada | <img src="plugin/skills/github-profile/reference/styles/macos-dark.jpg" alt="Tema macOS, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/macos-light.jpg" alt="Tema macOS, claro"> |
| **ide** · barra de herramientas, franja lateral, código estilo Kotlin | <img src="plugin/skills/github-profile/reference/styles/ide-dark.jpg" alt="Tema IDE, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/ide-light.jpg" alt="Tema IDE, claro"> |
| **vim** · modo en la línea de estado, números de línea relativos, buffer markdown | <img src="plugin/skills/github-profile/reference/styles/vim-dark.jpg" alt="Tema Vim, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/vim-light.jpg" alt="Tema Vim, claro"> |
| **notebook** · celdas numeradas, código de entrada y su salida | <img src="plugin/skills/github-profile/reference/styles/notebook-dark.jpg" alt="Tema notebook, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/notebook-light.jpg" alt="Tema notebook, claro"> |
| **handheld** · pantalla de consola portátil de los 90: cuatro verdes, retrato recoloreado | <img src="plugin/skills/github-profile/reference/styles/handheld-dark.jpg" alt="Tema handheld, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/handheld-light.jpg" alt="Tema handheld, claro"> |
| **crt** · pantalla de fósforo con líneas de barrido y brillo, ámbar o verde | <img src="plugin/skills/github-profile/reference/styles/crt-dark.jpg" alt="Tema CRT, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/crt-light.jpg" alt="Tema CRT, claro"> |
| **browser** · barra de direcciones, títulos resaltados como en el inspector de elementos | <img src="plugin/skills/github-profile/reference/styles/browser-dark.jpg" alt="Tema Browser, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/browser-light.jpg" alt="Tema Browser, claro"> |
| **sql** · consola de base de datos: títulos como consultas, tarjetas como sus resultados | <img src="plugin/skills/github-profile/reference/styles/sql-dark.jpg" alt="Tema SQL, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/sql-light.jpg" alt="Tema SQL, claro"> |
| **git** · grafo de commits en el margen, títulos como commits con hash y refs | <img src="plugin/skills/github-profile/reference/styles/git-dark.jpg" alt="Tema Git, oscuro"> | <img src="plugin/skills/github-profile/reference/styles/git-light.jpg" alt="Tema Git, claro"> |

Cada tarjeta sigue sola el tema de GitHub de quien la mira. El tema terminal también tiene variantes
por distribución de Linux (`ubuntu`, `arch`, `debian`, `fedora`, `mint`, `cachyos`): su color y
`tu-usuario@archlinux: ~` en la barra de título; `crt` usa fósforo `amber` o `green`. `classic` y `handheld`
mantienen una paleta fija. Los temas se inspiran en esos sistemas y no usan logos.

## Qué incluye

- **Cabecera**: nombre, rol, bio y etiquetas, y a la derecha un GIF animado, una imagen fija, un
  panel estilo neofetch o nada.
- **Señal de perfil**: cuatro estadísticas en vivo a elección (repos, contribuciones, pull
  requests, estrellas, seguidores, proyectos en producción).
- **Trabajo seleccionado**: cuatro tarjetas de proyecto con descripción, stack, estado, commits,
  último push y reparto de lenguajes.
- **Stack de lenguajes** por bytes de código y tus **herramientas** agrupadas por área.
- **Mapa de contribuciones** de las últimas 52 semanas, con semanas activas y racha más larga.
- Inglés o español, `README.md` generado desde un solo `profile.json` y un workflow semanal
  opcional para actualizar las cifras.

## Inicio rápido con Claude Code

```text
/plugin marketplace add WaltherMoraRivera/github-profile-readme-generator
/plugin install github-profile@github-profile-readme-generator
```

Luego basta con decir **"configura mi perfil de GitHub"**. El agente:

1. Revisa `gh`, Python y git, y lee tus datos públicos de GitHub.
2. Pregunta el tema (13, con variantes por distro de Linux) y el modo de configuración, como un instalador:
   - **Rápida**: una sola pregunta más (¿tienes una imagen o GIF para la cabecera?). El agente elige
     tus proyectos, estadísticas y textos a partir de tus datos de GitHub y te muestra una vista previa.
   - **Personalizada**: eliges el idioma, los proyectos destacados, las estadísticas, la cabecera y
     cada texto.
3. Convierte tu GIF o imagen en una cabecera que funciona en ambos temas.
4. Arma una vista previa local. La apruebas, cambias algo o pasas de rápida a personalizada.
5. Respalda tu perfil actual y luego publica solo lo que apruebes.

### Respaldos

Antes de cada publicación, el agente guarda tu perfil tal como está en GitHub en una rama
`backup/<fecha>` de tu repositorio de perfil (README, imágenes y datos). Pide **"muestra los
respaldos de mi perfil"** o **"restaura mi perfil del 15 de noviembre"**: los lista con fecha y tema
y trae de vuelta el que elijas como un commit nuevo, después de respaldar el actual, así que no se
pierde nada. Sin Claude, dentro de tu repositorio de perfil:

```bash
python3 ruta/a/scripts/backup.py create           # guarda el perfil actual
python3 ruta/a/scripts/backup.py list             # muestra los respaldos
python3 ruta/a/scripts/backup.py restore 2026-11-15-1030 && git push
```

## Inicio rápido sin Claude

Necesitas Python 3.9+ y la [CLI de GitHub](https://cli.github.com) con sesión iniciada (`gh auth login`).

```bash
git clone https://github.com/WaltherMoraRivera/github-profile-readme-generator
gh repo create <tu-usuario>/<tu-usuario> --public --clone     # o clónalo si ya existe
cd <tu-usuario>
mkdir -p scripts data
cp ../github-profile-readme-generator/plugin/skills/github-profile/scripts/generate.py scripts/
cp ../github-profile-readme-generator/plugin/skills/github-profile/templates/profile.example.json data/profile.json
cp ../github-profile-readme-generator/plugin/skills/github-profile/templates/gitignore .gitignore
# edita data/profile.json y luego:
python3 scripts/generate.py
```

Abre `preview.html` para revisarlo. Si ya tenías un perfil, guárdalo antes con
`python3 ../github-profile-readme-generator/plugin/skills/github-profile/scripts/backup.py create`,
y luego haz commit y push de `README.md assets data scripts .gitignore`.
GitHub muestra en tu perfil el README de un repositorio público con el mismo nombre que tu cuenta.

Todas las opciones están en
[`configuration.md`](plugin/skills/github-profile/reference/configuration.md) (en inglés).

### Cabecera animada desde un GIF

Requiere Pillow (`python3 -m pip install --user pillow`).

```bash
python3 plugin/skills/github-profile/scripts/frames.py mi.gif data/portrait-sheet.png --bg white --native auto --height 450
```

- `--bg`: el fondo sólido de tu GIF (`white`, `black`), o `none` si ya es transparente.
- `--native auto`: detecta pixel art ampliado y lo mantiene nítido. Un retrato de 21 fotogramas
  quedó en menos de 100 KB.
- `--fade-sides 0.12 --colors 0`: suaviza una figura cortada por los bordes laterales.

Luego, en `profile.json`: `"portrait": "data/portrait-sheet.png"`,
`"portrait_frames": "data/portrait-sheet.json"`, `"portrait_width": 250`.

Para una imagen fija con fondo oscuro sólido, `scripts/cutout.py` quita el fondo.

## Tus propios colores

Los colores se cambian en `data/profile.json`, sin tocar el script, así sigues recibiendo las
actualizaciones:

- **Acento propio**: `"accent": {"light": "#4b5563", "dark": "#d4d8de"}` (o un solo `"#ff6600"`).
- **Ajustar un tema**: `theme_overrides` define fondo, barra de título, paneles, textos, colores de
  las cifras, colores de lenguajes y CSS adicional, por modo. `"color_scheme": "dark"` lo deja
  siempre oscuro.

El generador avisa cuando un color se lee mal. Todas las claves (en inglés):
[`configuration.md`](plugin/skills/github-profile/reference/configuration.md#custom-colors).

## Cómo funciona

- `generate.py` consulta las API REST y GraphQL de GitHub con tu sesión de `gh` y escribe archivos
  SVG simples. Nada queda alojado en servicios externos, así que nada puede caerse.
- GitHub muestra las imágenes del README como `<img>`. Dentro de un SVG el CSS sigue funcionando, así
  que cada tarjeta lleva colores `prefers-color-scheme` para ambos temas, y la animación de la
  cabecera es una hoja de sprites CSS que avanza un fotograma a la vez. Se detiene para quien
  prefiere movimiento reducido.
- El texto en SVG no hace saltos de línea, así que el generador lo corta según un ancho estimado,
  con margen de seguridad.

## Bueno saber

- **Repos fijados**: solo los puedes fijar tú en tu perfil ("Customize your pins"); GitHub no
  tiene API para eso.
- **Trabajo privado**: aparece en el mapa solo si activas "Include private contributions on my
  profile" en tu configuración.
- **Actualización semanal**: `templates/update-profile.yml` solo corre si el repo tiene el secreto
  `PROFILE_TOKEN`, un token de solo lectura que creas tú. El token por defecto de Actions solo ve la
  actividad pública y bajaría tus cifras. Sin él, actualiza ejecutando el generador y haciendo push.
- **¿Imágenes viejas después de un push?** Cada imagen lleva un hash del archivo (`?v=…`), así que
  las tarjetas nuevas se ven de inmediato; si alguna no, recarga con Ctrl+F5.
- **Insignia "hecho con"**: una insignia pequeña abajo a la derecha, con los colores de tu tema,
  enlaza a este generador. Se quita con `"made_with": false` en `profile.json`.
- **Arte de otra persona**: requiere un crédito visible (`credits` en `profile.json`).

Errores conocidos y cómo se resolvieron:
[`lessons.md`](plugin/skills/github-profile/reference/lessons.md) (en inglés).

## Estructura del repositorio

```
.claude-plugin/marketplace.json          marketplace de Claude Code
plugin/.claude-plugin/plugin.json        manifiesto del plugin
plugin/skills/github-profile/
├── SKILL.md                             flujo del agente y preguntas de configuración
├── scripts/generate.py                  generador (solo biblioteca estándar)
├── scripts/frames.py                    GIF → hoja de sprites animada (Pillow)
├── scripts/cutout.py                    quita un fondo oscuro (Pillow + numpy)
├── templates/                           profile.example.json, workflow, .gitignore
└── reference/                           configuración, lecciones, capturas de estilos
```

## Licencia

[MIT](LICENSE) © 2026 Walther Mora Rivera. Hecho con Claude Code.
