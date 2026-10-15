# CLAUDE.md

Brewery Radar: static single-file web app for brewers. All HTML/CSS/JS/data live in `index.html`; topic rules are in `.claude/rules/`.

- Keep it single-file: no build step, bundler, or npm deps. External code only via pinned CDN `<script>` (today: Chart.js).
- No test suite. Verify by opening `index.html` directly in a browser (no server) and exercising the changed tool in PT, EN and ES.
- Deploy = copy `index.html` to any static host.
