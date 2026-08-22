# aminmiral.github.io

Personal site for Miral Amin — Odoo backend developer at RDFlex, Ahmedabad.

Single hand-written HTML file. No framework, no build step, no dependencies
beyond two webfonts. Open `index.html` in a browser and it runs.

## The idea

Everything on the site is organised around one thing: the systems I build read
something messy and decide what it means. The page reflects that literally.

A canvas of ~9,000 purchase-order events sits fixed behind the whole document.
Seven of them are fraudulent — the same seven fraud typologies injected in
[erp-anomaly-bench](https://github.com/aminmiral/erp-anomaly-bench). Scrolling
runs the detector: the clean records fade out, the flagged ones stay lit, and
then they clear too, so the later projects get a surface of their own. Every
mark is readable — drag across the wall and it reports that record's PO number,
vendor, action, amount, and whether it's flagged.

Each project then gets its own image rather than sharing one:

| Project | Visual |
|---|---|
| ERP Anomaly Bench | the record wall, and AUPRC 1.000 vs 0.099 at full page scale |
| SignSpeak | the 21 MediaPipe hand landmarks, idling |
| Chat Analyzer | an activity heatmap, hour of day against day of week |

## Structure

```
index.html              everything — markup, styles, canvas work
Miral_Amin_Resume.pdf   linked from the site
```

## Local preview

```bash
python3 -m http.server 8080
# http://127.0.0.1:8080
```

## Notes

- Type is Archivo and IBM Plex Mono.
- Content is visible without JavaScript; the scroll reveal is JS-gated so a
  script failure can't blank the page.
- `prefers-reduced-motion` is respected throughout — the wall renders static,
  the hand stops idling, reveals are disabled.
- The wall works on touch as well as cursor.
