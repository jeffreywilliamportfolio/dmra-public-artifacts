# Availability and Safety Scope

## Public Bundle

The public bundle contains:

- consolidated run-level provenance;
- model identifiers and hashes;
- deterministic decoding settings;
- redacted claim-evidence index;
- redacted pediatric-respiratory robustness evidence (summaries, feature/pair counts, manifest, provenance);
- file checksums.

The manuscript itself is not included in this bundle; it is published on Zenodo
(<https://zenodo.org/records/20449547>, DOI `10.5281/zenodo.20449547`).

## Exclusions

The public bundle excludes:

- model weights and `.gguf` files;
- `.env`, `.env.*`, API keys, tokens, and credentials;
- full raw safety-test generations;
- full slur-containing prompt text;
- operationally harmful violent or illegal-logistics completions;
- untrimmed run files and source archives containing high-risk safety-test content.

## Controlled Archive

The private controlled archive retains raw generations, untrimmed outputs, and exact safety-test prompt artifacts. These retained materials are available from the author upon reasonable request for verification. The public bundle is designed to preserve provenance and claim auditability while keeping high-risk generated text separate from the public release.

## License Note

The public metadata and redacted public summaries in this bundle are released under Creative Commons Attribution 4.0 International (CC BY 4.0). The manuscript is licensed separately on Zenodo (CC BY 4.0). The controlled archive has no public reuse license.
