# Open-Source Actuation — Project Page

Static project website (plain HTML/CSS/JS, no build step), modeled on
[Mobile ALOHA](https://mobile-aloha.github.io/) / [Nerfies](https://nerfies.github.io/).

## Structure

```
index.html              # all page content — search for "TODO"
static/css/style.css    # styling (light + dark mode)
static/js/main.js       # BibTeX copy button, play videos only when visible
static/images/          # teaser.jpg (poster/social preview), favicon, people/ photos
static/videos/          # .mp4 clips referenced in index.html
```

## Preview locally

```sh
python -m http.server 8000
```

Then open http://localhost:8000.

## Adding content

- **Text:** edit `index.html`; every placeholder is marked `TODO`.
- **Videos:** drop `.mp4` files into `static/videos/` using the names in `index.html`,
  or rename the `src` attributes. To add a section, copy an existing `<section>` block.
  Use `.grid` for 2 columns or `.grid three` for 3.
- **Photos:** put square headshots in `static/images/people/` and update the `<img src>`.
- **Keep videos small.** GitHub rejects files over 100 MB and Pages sites should stay
  under ~1 GB total. Re-encode clips for the web, e.g.:

  ```sh
  ffmpeg -i in.mov -vcodec libx264 -crf 28 -preset slow -an -vf "scale=1280:-2" -movflags +faststart out.mp4
  ```

## Deploying

Settings → Pages → *Deploy from a branch* → `main` / `(root)`.
The site will be at `https://<owner>.github.io/<repo>/`.
