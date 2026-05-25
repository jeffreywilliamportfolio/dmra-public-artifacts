# Reproducibility Notes

This artifact supports public verification of the manuscript source, run provenance, model identifiers, deterministic decoding settings, and redacted case-evidence index.

## Publicly Checkable Items

From this bundle, a reviewer can check:

- the exact manuscript snapshot used for the public preprint;
- the model identifiers and model-file SHA-256 hashes reported in the paper;
- the deterministic decoding settings reported in the paper;
- the number and organization of run/prompt records in the consolidated manifest;
- the redacted mapping between paper claims and retained local evidence files.

## Controlled-Archive Items

Full reproduction of every generated output requires the controlled local archive because the raw sensitive-prompt generations include self-harm, violent-threat, illegal-logistics, and slur-containing content. Those files are retained with provenance and checksums, but they are excluded from the public bundle to reduce redistribution of harmful text.

## Source-Build Check

The manuscript source can be compiled from the arXiv source package with:

```sh
cd output/arxiv_source/dmra_paper
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=build dmra_paper.tex
```

The public PDF metadata can be checked with:

```sh
pdfinfo output/pdf/dmra_paper.pdf
```

The public artifact bundle checksums can be checked with:

```sh
cd output/public_artifacts/dmra_public_artifacts
shasum -a 256 -c CHECKSUMS.sha256
```

## Replication Boundary

This public bundle enables auditability rather than full redistribution. It preserves the evidence structure needed to evaluate the paper's I/O-level claims while keeping high-risk raw text in controlled storage.
