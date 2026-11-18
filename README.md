> [!CAUTION]
> **This project moved to [ProfileStudio/ProfileStudio](https://github.com/ProfileStudio/ProfileStudio).**
> This repository is archived and no longer updated. To switch the Claude Code plugin:
>
> ```text
> /plugin marketplace add ProfileStudio/ProfileStudio
> /plugin install profilestudio@profilestudio
> ```

# GitHub Profile README Generator

**English** · [Español](README.es.md)

Generate a polished GitHub profile README from your real GitHub data: SVG cards with live stats,
13 themes inspired by the tools developers use every day, light and dark modes, and an optional **animated header** made from your own image or GIF. A
Claude Code agent asks you a few design questions, builds a preview and publishes it when you
approve. No Claude? The generator is a single Python script with no dependencies.

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
![Python 3.9+](https://img.shields.io/badge/python-3.9%2B-3776ab.svg)
![Claude Code plugin](https://img.shields.io/badge/Claude%20Code-plugin-d97757.svg)

## Live example

<a href="https://github.com/WaltherMoraRivera"><img src="https://raw.githubusercontent.com/WaltherMoraRivera/WaltherMoraRivera/main/assets/header.svg" width="100%" alt="Header of github.com/WaltherMoraRivera: terminal theme, cyan accent, animated pixel-art portrait"></a>

[github.com/WaltherMoraRivera](https://github.com/WaltherMoraRivera): terminal theme, Spanish, animated pixel-art portrait.

## 13 themes, inspired by the tools you use every day

| Theme | Dark | Light |
|---|---|---|
| **terminal** · shell prompts, one accent, Linux distro variants | <img src="plugin/skills/github-profile/reference/styles/terminal-dark.jpg" alt="Terminal theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/terminal-light.jpg" alt="Terminal theme, light"> |
| **editor** · tabs, line numbers, your data written as code | <img src="plugin/skills/github-profile/reference/styles/editor-dark.jpg" alt="Editor theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/editor-light.jpg" alt="Editor theme, light"> |
| **classic** · 90s desktop windows and block progress bars | <img src="plugin/skills/github-profile/reference/styles/classic-dark.jpg" alt="Classic theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/classic-light.jpg" alt="Classic theme, light"> |
| **win11** · flat rounded windows, caption buttons | <img src="plugin/skills/github-profile/reference/styles/win11-dark.jpg" alt="Windows 11 theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/win11-light.jpg" alt="Windows 11 theme, light"> |
| **macos** · traffic lights, unified title bar | <img src="plugin/skills/github-profile/reference/styles/macos-dark.jpg" alt="macOS theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/macos-light.jpg" alt="macOS theme, light"> |
| **ide** · tool window strip, run toolbar, Kotlin-style code | <img src="plugin/skills/github-profile/reference/styles/ide-dark.jpg" alt="IDE theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/ide-light.jpg" alt="IDE theme, light"> |
| **vim** · mode in the status line, relative line numbers, markdown buffer | <img src="plugin/skills/github-profile/reference/styles/vim-dark.jpg" alt="Vim theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/vim-light.jpg" alt="Vim theme, light"> |
| **notebook** · numbered cells, code input and its output | <img src="plugin/skills/github-profile/reference/styles/notebook-dark.jpg" alt="notebook theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/notebook-light.jpg" alt="notebook theme, light"> |
| **handheld** · 90s handheld console screen: four greens, portrait recolored | <img src="plugin/skills/github-profile/reference/styles/handheld-dark.jpg" alt="handheld theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/handheld-light.jpg" alt="handheld theme, light"> |
| **crt** · phosphor screen with scan lines and glow, amber or green | <img src="plugin/skills/github-profile/reference/styles/crt-dark.jpg" alt="CRT theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/crt-light.jpg" alt="CRT theme, light"> |
| **browser** · address bar, headings highlighted like the element inspector | <img src="plugin/skills/github-profile/reference/styles/browser-dark.jpg" alt="Browser theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/browser-light.jpg" alt="Browser theme, light"> |
| **sql** · database console: headings as queries, cards as their results | <img src="plugin/skills/github-profile/reference/styles/sql-dark.jpg" alt="SQL theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/sql-light.jpg" alt="SQL theme, light"> |
| **git** · commit graph in the gutter, headings as commits with hash and refs | <img src="plugin/skills/github-profile/reference/styles/git-dark.jpg" alt="Git theme, dark"> | <img src="plugin/skills/github-profile/reference/styles/git-light.jpg" alt="Git theme, light"> |

Every card follows the viewer's GitHub theme on its own. The terminal theme also comes in Linux
distribution variants (`ubuntu`, `arch`, `debian`, `fedora`, `mint`, `cachyos`): their color, and
`you@archlinux: ~` in the title bar; `crt` takes `amber` or `green` phosphor. `classic` and `handheld`
keep a fixed palette. Themes are inspired by these systems and use no logos.

## What you get

- **Header**: name, role, bio and tags, plus an animated GIF, a still image, a neofetch-style
  panel or nothing on the right.
- **Profile signal**: four live stats of your choice (repos, contributions, pull requests, stars,
  followers, projects in production).
- **Selected work**: four project cards with description, stack, status, commit count, last push
  and language split.
- **Language stack** by bytes of code, and your **toolkit** grouped by area.
- **Contribution heatmap** for the last 52 weeks, with active weeks and longest streak.
- English or Spanish, `README.md` generated from one `profile.json`, and an optional weekly
  refresh workflow.

## Quick start with Claude Code

```text
/plugin marketplace add WaltherMoraRivera/github-profile-readme-generator
/plugin install github-profile@github-profile-readme-generator
```

Then just say **"set up my GitHub profile"**. The agent:

1. Checks `gh`, Python and git, and reads your public GitHub data.
2. Asks for a theme (13, including Linux distro variants) and a setup mode, like an installer:
   - **Quick**: one more question (do you have an image or GIF for the header?). The agent picks
     your projects, stats and texts from your GitHub data and shows you a preview.
   - **Custom**: you choose the language, featured projects, stats, header and every text.
3. Turns your GIF or image into a header that works in both themes.
4. Builds a local preview. You approve it, change something, or switch from quick to custom.
5. Backs up your current profile, then publishes only what you approve.

### Backups

Before every publish, the agent saves your profile as it is on GitHub to a `backup/<date>` branch
of your profile repository (README, images and data). Ask **"show my profile backups"** or
**"restore my profile from November 15"**: it lists them with date and theme and brings the one you
pick back as a new commit, after backing up the current one, so nothing is lost. Without Claude,
inside your profile repository:

```bash
python3 path/to/scripts/backup.py create          # save the current profile
python3 path/to/scripts/backup.py list            # see backups
python3 path/to/scripts/backup.py restore 2026-11-15-1030 && git push
```

## Quick start without Claude

You need Python 3.9+ and the [GitHub CLI](https://cli.github.com) signed in (`gh auth login`).

```bash
git clone https://github.com/WaltherMoraRivera/github-profile-readme-generator
gh repo create <you>/<you> --public --clone     # or clone it if it already exists
cd <you>
mkdir -p scripts data
cp ../github-profile-readme-generator/plugin/skills/github-profile/scripts/generate.py scripts/
cp ../github-profile-readme-generator/plugin/skills/github-profile/templates/profile.example.json data/profile.json
cp ../github-profile-readme-generator/plugin/skills/github-profile/templates/gitignore .gitignore
# edit data/profile.json, then:
python3 scripts/generate.py
```

Open `preview.html` to check it. If you already had a profile, save it first with
`python3 ../github-profile-readme-generator/plugin/skills/github-profile/scripts/backup.py create`,
then commit and push `README.md assets data scripts .gitignore`.
A public repository named exactly like your account is shown on your profile page.

Every option is documented in
[`configuration.md`](plugin/skills/github-profile/reference/configuration.md).

### Animated header from a GIF

Needs Pillow (`python3 -m pip install --user pillow`).

```bash
python3 plugin/skills/github-profile/scripts/frames.py my.gif data/portrait-sheet.png --bg white --native auto --height 450
```

- `--bg`: your GIF's solid background (`white`, `black`), or `none` if it is already transparent.
- `--native auto`: detects upscaled pixel art and keeps it sharp. A 21-frame portrait came out at
  under 100 KB.
- `--fade-sides 0.12 --colors 0`: softens a figure cut by the left and right edges.

Then set in `profile.json`: `"portrait": "data/portrait-sheet.png"`,
`"portrait_frames": "data/portrait-sheet.json"`, `"portrait_width": 250`.

For a still image on a solid dark background, `scripts/cutout.py` removes the background.

## Your own colors

Change colors in `data/profile.json`, without touching the script, so you keep getting updates:

- **Your own accent**: `"accent": {"light": "#4b5563", "dark": "#d4d8de"}` (or a single `"#ff6600"`).
- **Fine-tune a theme**: `theme_overrides` sets background, title bar, panels, text, the colors of
  numbers, language colors and extra CSS, per mode. `"color_scheme": "dark"` keeps it dark for
  everyone.

The generator warns when a color is hard to read. All keys:
[`configuration.md`](plugin/skills/github-profile/reference/configuration.md#custom-colors).

## How it works

- `generate.py` calls the GitHub REST and GraphQL APIs through your `gh` login and writes plain SVG
  files. Nothing is hosted elsewhere, so nothing can go down.
- GitHub shows README images as `<img>`. Inside an SVG, CSS still works there, so each card carries
  `prefers-color-scheme` colors for both themes, and the header animation is a CSS sprite sheet
  that steps one frame at a time. It stops for viewers who prefer reduced motion.
- Text in SVG does not wrap, so the generator wraps it by estimated width, on the safe side.

## Good to know

- **Pinned repositories** can only be set by you on your profile ("Customize your pins"); GitHub has
  no API for it.
- **Private work** shows in the heatmap only if you enable "Include private contributions on my
  profile" in your settings.
- **Weekly refresh**: `templates/update-profile.yml` runs only when the repo has a `PROFILE_TOKEN`
  secret, a read-only token you create. The default Actions token sees public activity only and
  would lower your numbers. Without it, refresh by running the generator and pushing.
- **Images look old after a push?** Each image path carries a hash of the file (`?v=…`), so new
  cards show at once; if one does not, reload with Ctrl+F5.
- **"Made with" badge**: a small badge at the bottom right, in your theme's colors, links back to
  this generator. Remove it with `"made_with": false` in `profile.json`.
- **Art by someone else** needs a visible credit (`credits` in `profile.json`).

Known pitfalls and how they were solved:
[`lessons.md`](plugin/skills/github-profile/reference/lessons.md).

## Repository layout

```
.claude-plugin/marketplace.json          Claude Code marketplace
plugin/.claude-plugin/plugin.json        plugin manifest
plugin/skills/github-profile/
├── SKILL.md                             the agent's workflow and configuration questions
├── scripts/generate.py                  generator (standard library only)
├── scripts/frames.py                    GIF → animated sprite sheet (Pillow)
├── scripts/cutout.py                    removes a dark background (Pillow + numpy)
├── templates/                           profile.example.json, workflow, .gitignore
└── reference/                           configuration, lessons, style screenshots
```

## License

[MIT](LICENSE) © 2026 Walther Mora Rivera. Built with Claude Code.
