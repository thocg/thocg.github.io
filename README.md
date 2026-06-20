# Thai Open Cyber Glossary (TOCG)

อภิธานศัพท์ความมั่นคงปลอดภัยทางไซเบอร์ ไทย–อังกฤษ แบบเปิด

A bilingual (Thai–English) open glossary of cyber security terms, published as a
single static page. Browse it live, search any term or definition, and use it as
a free reference for study and work.

🔗 **Live site:** https://thocg.github.io

## Features

- **Bilingual entries** — English term (with abbreviation) paired with the Thai
  term and a Thai definition.
- **Live search** — instant client-side filtering across terms and definitions,
  with match highlighting.
- **A–Z navigation** — a sticky alphabetical rail jumps to each letter section.
- **Dark mode** — toggle in the header; remembers your choice and follows the
  system theme on first visit.
- **Changelog & About pages** — hash-based routing, still a single HTML file.
- **No build step to view** — `index.html` reads `glossary-data.js` directly, so
  it works by double-clicking the file (`file://`) with no web server.

## Repository layout

| File | Purpose |
| --- | --- |
| `index.html` | The entire web app (HTML, CSS, JS in one file). |
| `glossary-data.js` | Generated glossary data the page loads (`window.GLOSSARY`). |
| `glossary.json` | Same data as plain JSON, for tooling / serving over HTTP. |
| `changelog-data.js` | Generated changelog text the page loads (`window.CHANGELOG`). |
| `CHANGELOG.md` | Human-readable source of the changelog. |
| `th_data.txt` | Raw Thai source text the glossary is built from. |
| `eng_data.txt` | Raw English reference source. |
| `build_glossary.py` | Local build script (generates the `*-data.js` files). |
| `LICENSE` | CC BY-SA 4.0 license text. |

## Building the data files

The website only needs the generated `*-data.js` files. Regenerate them whenever
`th_data.txt` or `CHANGELOG.md` changes:

```bash
python build_glossary.py
```

This reads `th_data.txt` / `CHANGELOG.md` and writes `glossary.json`,
`glossary-data.js`, and `changelog-data.js`. No third-party dependencies are
required (standard library only).

### Source format (`th_data.txt`)

- A line that is a single A–Z letter starts a new alphabetical section.
- A term header is an English line, optionally `English (ABBR) — Thai`
  (separated by an em dash `—`).
- Lines after a header (in the same blank-line-separated block) form the
  definition. Further blocks that start with Thai text become extra paragraphs
  of the same term.

```
A

Advanced Persistent Threat (APT) — ภัยคุกคามขั้นสูงแบบต่อเนื่อง
การโจมตีทางไซเบอร์ที่ใช้เทคนิคซับซ้อน…

อีกย่อหน้าหนึ่งของคำเดิม…
```

## Running locally

Because the page loads `glossary-data.js` directly, no server is needed — just
open `index.html` in a browser. To serve it over HTTP instead:

```bash
python -m http.server
# then visit http://localhost:8000
```

## Deployment

The site is hosted with **GitHub Pages** from this repository. The files the
page loads at runtime — `index.html`, `glossary-data.js`, and
`changelog-data.js` — must be committed and pushed.

## License

Released under the
[Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/)
license. You may share and adapt the material, provided you give appropriate
credit and distribute your contributions under the same license. See
[`LICENSE`](LICENSE) for the full text.

## Source & attribution

Terms are adapted and translated from
“[Cyber Security Glossary of Terms: The Ultimate List](https://cyberone.security/blog/cyber-security-glossary-of-terms-the-ultimate-list)”
by **Mark Terry**, Head of Marketing, CyberOne.
