# P.I.P.E.R.

**Push `index.html`, `site.webmanifest` and the `icons/` folder.** That's the whole website. `index.html` is the complete page; the other two give it its browser-tab icon, home-screen icon and link-preview image.

| File | What it is |
|---|---|
| `index.html` | The working page. Upload this. |
| `site.webmanifest` | Tells phones the app's name and icon when it's saved to the home screen. |
| `icons/` | Favicons (black lettering for light browser tabs, `favicon-dark-*` with white lettering for dark ones), iPhone / Android home-screen icons, and the 1200 × 630 link-preview image. |
| `src/app.html` | The copy that gets edited, and the source for the claude.ai version. Don't upload it; it doesn't work on its own. |
| `src/build.py` | Rebuilds `index.html` from `src/app.html`. |
| `PIPER.md` | PIPER's personality: who she is, how she talks, what she will and won't do. The app carries a condensed copy (`PIPER_PERSONA` in `src/app.html`); change both together. Don't upload it. |
| `assets/` | The P.I.P.E.R. favicon artwork the `icons/` files are made from: `piper-favicon-light-bg.svg` (black lettering) and `piper-favicon-dark-bg.svg` (white lettering). `astro-la.jpg` is the skyline outside the Astro Protocol windows, already built into `index.html`. The site doesn't need this folder. |

After any change to `src/app.html`, rebuild the working page:

```bash
python3 src/build.py
```

## Putting it on GitHub Pages

1. Push this folder to a GitHub repository, with `index.html` at the top level.
2. In the repository, go to **Settings → Pages**, set **Source** to *Deploy from a branch*, pick `main` and `/ (root)`, and save.
3. After a minute or two the page is live at `https://<your-username>.github.io/<repo-name>/`.

4. Once you know the address, put it in `SITE_URL` at the top of `src/build.py` (with the trailing slash), run `python3 src/build.py`, and push again. Link previews in iMessage, Slack and LinkedIn need that full address to show the image.

After rebuilding `index.html`, commit and push it again to update the live page.
