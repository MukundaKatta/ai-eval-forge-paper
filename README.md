# AI Eval Forge: Mixed-Check Regression Testing for LLM and Agent Workflows

This repository is the public artifact bundle for the second paper built from the `ai-eval-forge` package.

## What is in this repo

- `ai-eval-forge-mixed-check-regression-testing-preprint.pdf` for the submission-ready manuscript
- `paper.md` for the source draft
- `paper.bib` for the current references
- `assets/workflow-figure.svg` for the workflow figure
- `submission-metadata.json` for reusable submission metadata
- `ai-eval-forge-preprint-package.zip` for one-click uploads to preprint platforms

## Abstract

Large-model and agent teams often need faster regression checks than broad benchmark suites can provide. This paper presents AI Eval Forge, a zero-dependency evaluation harness for mixed-check regression testing across LLM and agent workflows. The tool supports exact-match, substring, regex, token-F1, JSON validity, JSON field equality, citation coverage, and bounded custom-expression checks in a compact case format that works with JSON or JSONL. The contribution is not a new benchmark. It is a small, inspectable evaluation layer that helps teams compare runs, catch regressions, and summarize pass rate, score, cost, and latency without standing up a heavy evaluation stack. The paper describes the harness design, check model, reporting format, and practical role of mixed-check cases in real workflow testing.

## Source package

- npm package: [@mukundakatta/ai-eval-forge](https://www.npmjs.com/package/@mukundakatta/ai-eval-forge)
- GitHub repository: [MukundaKatta/ai-eval-forge-js](https://github.com/MukundaKatta/ai-eval-forge-js)

## Submission path

This bundle is prepared for:

- Zenodo
- OSF Preprints
- SSRN

## Citation

Use the versioned preprint record once published.

## Quality Gate

Run the artifact checks before publishing a revised bundle:

```bash
python -m pip install -r requirements.txt
python -m py_compile render_preprint_pdf.py
python - <<'PY'
import json
from pathlib import Path
import render_preprint_pdf as pdf

json.loads(Path("submission-metadata.json").read_text())
assert any(kind == "title" for kind, _ in pdf.extract_blocks(Path("paper.md").read_text()))
PY
```

The GitHub Actions workflow also verifies that the manuscript source,
bibliography, figure, metadata, and generated preprint PDF are present.
