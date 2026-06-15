# DMRA Public Artifact Bundle

This bundle is the sanitized public companion artifact for:

`Dialect-Marked Response Audit (DMRA): A Matched-Pair Safety Evaluation of AAVE-Marked Prompt Surfaces in Qwen3.5-35B-A3B`

Author: Jeffrey Shorthill  
Prepared: 2026-05-26 (updated 2026-06-15 for manuscript v2)

The manuscript itself is published on Zenodo under the concept ("all versions") DOI
`10.5281/zenodo.20449546`, which always resolves to the latest version:
<https://doi.org/10.5281/zenodo.20449546>.
This bundle is the **data/artifact companion only** and no longer embeds a manuscript copy.

## Contents

- `metadata/run_manifest_public.tsv`: consolidated run-level manifest with record counts, model/template labels, decoding settings, and source-artifact provenance.
- `metadata/model_and_decoding_settings.md`: model identifiers, hashes, templates, and deterministic decoding settings.
- `metadata/availability_and_safety_scope.md`: release scope and safety exclusions.
- `metadata/reproducibility_notes.md`: reproducibility scope, verification commands, and controlled-archive boundary.
- `case_evidence/redacted_case_evidence_index.md`: redacted index of the manuscript case labels and retained evidence identifiers.
- `case_evidence/case_label_mapping.tsv`: machine-readable mapping from manuscript case labels to retained evidence identifiers.
- `robustness/pediatric_respiratory/`: redacted derived evidence (summaries, feature counts, pair counts, manifest, provenance) for the pediatric respiratory-distress robustness check (manuscript §"Pediatric Respiratory Robustness" / Table 4). See that folder's `README.md`.
- `CHECKSUMS.sha256`: SHA-256 checksums for files in this public bundle.

## Safety Scope

This public bundle intentionally excludes model weights, `.env` files, secrets, full raw safety-test generations, slur-containing prompt text, and operationally harmful completions. Full raw generations remain in a private controlled archive and are available from the author upon reasonable request for verification. The public bundle preserves enough provenance, hashes, and redacted evidence summaries to audit the reported claims while keeping high-risk generated text separate from the public release.

## License

The public metadata and redacted public summaries in this bundle are released under CC BY 4.0. See `LICENSE.md`.
The manuscript is licensed separately on Zenodo (CC BY 4.0).

## Intended Use

This artifact is intended for reproducing the paper's I/O-level audit framing, checking run provenance, verifying deterministic settings, and reviewing redacted claim evidence. It is not a benchmark release, a model release, or a complete redistribution of the raw safety-test corpus.
