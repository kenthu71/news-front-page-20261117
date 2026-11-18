# News Front Page — Tuesday 17 November 2026

A make.fun bounty entry for **news-image-20261117** ("Sum up 17 November's
world news in one image"). The entry is a single 1024×1024 newspaper front
page that sums up the world's news of Tuesday 17 November 2026: 3 lead
stories with original illustrations, 12 secondary stories, a stat strip of
the day's key numbers, a world map with pins for stories 1–15, and a
numbered "Also on Tuesday" list that brings the total to 48 stories.

## How it works

- `page.html` — the front page itself: one self-contained HTML file with
  inline CSS and inline SVG illustrations (system fonts only, no network
  resources), laid out at exactly 1024×1024.
- `render.py` — renders `page.html` to `entry.png` with headless Chromium
  via Playwright (run it with a Python that has Playwright installed).
  The rendered PNG is 1024×1024 and ~314 KB, well under the 1 MiB gate.
- `entry.png` — the rendered front page, committed to the repository.
- `main.ts` — the entry program (Node, zero dependencies). It validates
  the bundled `entry.png` (exists, PNG signature, ≤ 1 MiB) and writes it
  to `/output/entry.png` atomically (temp file + rename), so every run
  produces byte-identical output.

## Date discipline

Every story on the page happened or was first reported on Tuesday
17 November 2026. Stories that broke before Tuesday were left out on
purpose, and contested claims (for example Iran's claim that tankers hit
mines in Hormuz) are worded as claims, with sources credited in the
footer.

## License

MIT — see `LICENSE`. The front-page artwork and text are original.
