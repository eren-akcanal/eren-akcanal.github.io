# Eren Akçanal — portfolio site

Static site (plain HTML/CSS, no build step) for GitHub Pages.
Design rules: `DESIGN.md`. Colours/fonts/spacing: `assets/css/tokens.css`. Layout: `assets/css/site.css`.

## To do before publishing
- [ ] **Project media** — put files in `assets/media/` and replace each placeholder
      (search `TODO media` in `index.html`). For videos use:
      `<video src="assets/media/NAME.mp4" poster="assets/media/NAME.jpg" autoplay muted loop playsinline></video>`
      inside the `.media` div, and remove the `placeholder` class and `<span>`. Images: `<img src="…" alt="…">`.
      Keep clips 16:9, under ~3 MB (MP4, H.264).
- [x] **GitHub button** — added (github.com/eren-akcanal).
- [ ] **LinkedIn URL** — check `https://www.linkedin.com/in/erenakcanal` is correct.
- [ ] **Logos** — timeline uses text badges (ETH, AV, AR, EPFL, METU). Optionally swap for small
      monochrome logos.
- [ ] **CV PDF** — `assets/docs/Eren_Akcanal_CV.pdf` is the default LaTeX build; replace when the CV changes.

## Publish on GitHub Pages
1. Create a public repo named `eren-akcanal.github.io`.
2. Copy the contents of this `website/` folder into it and push to `main`.
3. Repo → Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/`.
4. The site appears at `https://eren-akcanal.github.io` within a minute or two.

## Preview locally
Open `index.html` in a browser, or run `python3 -m http.server` in this folder and visit
http://localhost:8000.
