# 🌺 LPC Pattern Clothier

A tiny, zero-build browser tool for **re-skinning [Liberated Pixel Cup (LPC)](https://lpc.opengameart.org) clothing spritesheets** with your own texture, colour, speckle pattern, or a chest "print" — previewed live on an animated character, browsing the **entire Universal-LPC catalogue** straight from GitHub.

It's a single `index.html`. No build step, no server, no dependencies to install. Just open it (it needs internet, because the art streams live from the LPC repository).

> **Heads-up on credits:** this tool contains **no artwork** — it downloads LPC art live and produces derivative spritesheets in your browser. If you ship any sprite you make with it, **you must credit the original LPC artists.** See [Credits & licensing](#-credits--licensing) below and [CREDITS.md](CREDITS.md).

---

## ✨ Features

- **Browse the whole Universal-LPC catalogue** live — torso (shirts, jackets, armour…), legs, feet, dresses, capes, hats, and more.
- **Re-skin any garment four ways:**
  - **Texture** — tile an imported image through the fabric (auto colour-reduced to read at pixel scale).
  - **Colour** — a solid recolour that keeps the folds/shading.
  - **Speckle** — an impressionistic scattered-dot print.
  - **Print** — stamp a single graphic (logo, skull…) on the chest and/or back, clipped to the shirt and shaded with its folds.
- **Large animated character preview** — body + head + clothes composited, idle/walk/run/slash/…; pick the facing; per-slot "wearing" dropdowns to assemble an outfit; 🎲 to roll a random outfit from your picks.
- **Download** a single item (all its animations) from the ⬇ next to each slot, or the **whole outfit** as one zip.
- **Configurable default** outfit/body (saved in your browser), a **Max sheets** guard, and an **Upload** mode for re-skinning your own sheets.

## 🚀 Use it

- **Hosted (GitHub Pages):** <https://obsidianttrpgproject.github.io/LPC-Pattern-Clothier/> *(enable Pages in repo settings if the link 404s)*
- **Repository:** <https://github.com/ObsidianTTRPGProject/LPC-Pattern-Clothier>
- **Locally:** download/clone the repo and open `index.html` in a modern browser (Chrome, Edge, Firefox). Needs internet access to GitHub.

### How re-skinning works (in one line)
Each LPC sheet already encodes the garment's **shape (alpha) and shading (luminance)** per frame. The tool paints your pattern *through* that mask — so the result keeps the fabric's folds and lines up with every animation automatically.

## 🌐 Hosting on GitHub Pages

1. Push this folder to a GitHub repo (done — <https://github.com/ObsidianTTRPGProject/LPC-Pattern-Clothier>).
2. Repo **Settings → Pages → Build and deployment → Deploy from a branch**, pick `main` / `/ (root)`.
3. The tool goes live at <https://obsidianttrpgproject.github.io/LPC-Pattern-Clothier/>.

Because everything runs client-side and the art is fetched from `raw.githubusercontent.com` (which allows cross-origin requests), no backend is needed.

## ⚠️ Notes & limits

- **Needs internet + GitHub.** Art is fetched live; if GitHub is down or you're offline, the catalogue won't load.
- **GitHub rate limit.** The unauthenticated API allows ~60 requests/hour per IP. Each category you open is 1 request (cached); the actual sheet downloads don't count against it. Heavy "select-all-then-download" sessions can hit the wall — the tool reports failures and has a Max-sheets guard.
- **Coverage varies.** Many LPC items only have `male`/`female` art (e.g. most footwear), so `teen`/`child`/etc. may show a bare body for those slots — the tool tells you which.
- **Prints are small.** At ~16px a chest graphic reads as a *suggestion* of the logo; bold high-contrast silhouettes survive best.

---

## 🙏 Credits & licensing

This project stands entirely on the shoulders of the **Liberated Pixel Cup** community. Enormous thanks to everyone who created and maintains that art and the generator it comes from.

- **Universal LPC Spritesheet Character Generator** — source, assets & full credits: <https://github.com/liberatedpixelcup/Universal-LPC-Spritesheet-Character-Generator>
- **Try the official generator:** <https://liberatedpixelcup.github.io/Universal-LPC-Spritesheet-Character-Generator/>
- **Liberated Pixel Cup project:** <https://lpc.opengameart.org>
- **LPC collection on OpenGameArt:** <https://opengameart.org/content/lpc-collection>

### Do I need to include attribution? **Yes.**

The **code** in this repository (the tool) is MIT licensed (see [LICENSE](LICENSE)). That covers the tool only.

The **artwork** — and therefore **every spritesheet this tool produces** — is a derivative of LPC art, licensed under one or more of **CC-BY-SA, CC-BY, OGA-BY, GPL, and/or CC0**, depending on the specific asset. This means:

- If you use any sprite made with this tool in a project (game, app, video, etc.), you **must credit the original authors** (everything except CC0), and comply with the specific licence(s) of the assets you used. For example, **CC-BY-SA requires you to release your derivative artwork under CC-BY-SA too**, and the no-DRM clause of CC-BY-SA may matter for some storefronts (OGA-BY exists to remove that clause if needed).
- The authoritative, per-asset author/licence list is the upstream **[CREDITS.csv](https://github.com/liberatedpixelcup/Universal-LPC-Spritesheet-Character-Generator/blob/master/CREDITS.csv)**. Ship it (or a composed subset for the assets you actually use) with your project, and make it discoverable to users.
- A ready-to-paste author list and the standard attribution statement are in **[CREDITS.md](CREDITS.md)**.

This tool does **not** redistribute LPC artwork — it streams it from the upstream repository at runtime — so this repository itself isn't a redistribution of the assets. Your *output*, however, is, and carries the obligations above.

> Not legal advice — when in doubt, read the licences linked above and the upstream README.
