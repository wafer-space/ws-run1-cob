# ws-run1-cob
Results from the wafer.space Run #1 chip on board packaging.

## Viewing results

Published via GitHub Pages: https://wafer-space.github.io/ws-run1-cob/

## Generating reports

Raw test data lives in `data/*.jsonl` (one file per test date). `scripts/gen_reports.py`
turns these into the static HTML reports under `<date>-results/` (one page per COB, plus
an `index.html` summarizing all of them).

```sh
python3 scripts/gen_reports.py data/2026-06-13.jsonl data/2026-06-15.jsonl -o 2026-06-13-results
```

- Pass one or more `.jsonl` files; if a COB tag appears in multiple files, the later
  file on the command line wins.
- Omit the file arguments to process every `.jsonl` file found next to the script.
- After generating a new `<date>-results/` folder, add a link to it from the root
  [index.html](index.html) so it shows up on the GitHub Pages site.
