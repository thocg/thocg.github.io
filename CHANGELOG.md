# Changelog

All notable changes to the Thai Open Cyber Glossary (TOCG) are recorded here.
Format follows Keep a Changelog; dates use ISO 8601 (YYYY-MM-DD).

## 0.1.5 — 2026-06-20
- Add Changelog page, shown in JetBrains Mono and loaded directly from changelog-data.js.
- Glossary: add "Penetration Tester (Pentester / Pen Tester)".
- Glossary: add "Vulnerability Assessment (VA Scan)".
- Total terms: 182.

## 0.1.4 — 2026-06-20
- Fix: search box text was unreadable in dark mode; it now uses the themed background.

## 0.1.3 — 2026-06-20
- Move About into its own page with header navigation (hash routing); still a single file.

## 0.1.2 — 2026-06-20
- Add dark mode toggle in the header (remembers the choice, follows the system on first visit).

## 0.1.1 — 2026-06-20
- Add About page: CC BY-SA 4.0 license and source attribution (Mark Terry, CyberOne).
- Professional UI redesign: sticky A-Z rail, term cards, refined typography.

## 0.1.0 — 2026-06-20
- Initial release: build_glossary.py converts th_data.txt into glossary.json / glossary-data.js.
- Single-page glossary with live search and A-Z navigation (180 terms).
- Read data directly via glossary-data.js so index.html works by double-click (no web server).
