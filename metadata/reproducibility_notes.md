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

Full reproduction of every generated output requires access to the private controlled archive because some raw safety-test generations include self-harm, violent-threat, illegal-logistics, and slur-containing content. Those files are available from the author upon reasonable request for verification and are retained with provenance and checksums, while the public bundle carries redacted summaries and run-level metadata.

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

This public bundle enables auditability rather than full raw redistribution. It preserves the evidence structure needed to evaluate the paper's I/O-level claims while keeping high-risk generated text separate from the public release.
