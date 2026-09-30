# Police Cop

*Police Cop*, a book of poems by Danny Collier, as a web page that prints itself
line by line on continuous-feed paper. Live at [police-cop.com](https://police-cop.com/).

## How it works

The whole site is one static page, `index.html`: the poems are plain HTML in that file,
with the styles and the printer script beside them. There is no build step, and the book
reads fine with JavaScript off. GitHub Pages serves the `main`
branch as-is (`.nojekyll` keeps Jekyll out of the way; `CNAME` holds the custom domain).

- **Feeding the paper.** Each block (cover, contents, section banners, poems) prints
  when the reader scrolls past the end of the paper, presses the space bar there, or
  clicks `[feed]`. Clicking a block mid-print finishes it; clicking a printed block
  prints it again. `[random]` and the contents list jump by URL hash, so every poem
  has a link.
- **Sound.** A synthesized 9-pin buzz, on by default. Browsers keep audio muted
  until the first click, tap or keypress, so the AudioContext is created on that
  gesture. The reader's on/off choice is kept in `localStorage`.
- **"On Recursion."** The closing poem is a two-line BASIC program that runs until
  the reader clicks it or presses Escape.
- **Reduced motion.** With `prefers-reduced-motion`, everything is printed at once.
- **Light and dark** follow the system setting.

Other files: `fonts/` (Courier Prime, self-hosted under the SIL Open Font License,
see `fonts/OFL.txt`), `favicon.*` and `apple-touch-icon.png`, `og-image.png` for
link previews, and `404.html`.

## Working on it

Open `index.html` in a browser, or serve the folder (`python3 -m http.server`) so
the fonts load over HTTP. Work on a branch and open a pull request against `main`;
merging deploys.

## Copyright

The poems and everything else here are © Danny Collier. All rights reserved.
