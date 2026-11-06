# Architecture — Indic Voice Bench

## Pipeline
```text
Dataset card + manifest
   -> permission / provenance check
   -> audio + transcript loader
   -> metadata and slice validation
   -> ASR system adapter
   -> prediction + timing capture
   -> versioned text normalization
   -> WER / CER / latency metrics
   -> error taxonomy + slice aggregation
   -> benchmark report
```

## Modules
- `datasets/`: manifest schemas and local/external dataset loaders.
- `governance/`: license, consent, retention, and redistribution checks.
- `adapters/`: offline ASR API contract; streaming interface later.
- `normalization/`: versioned language-specific normalization policies.
- `metrics/`: WER/CER, edit operations, RTF, latency, streaming stability.
- `analysis/`: slice reports, error samples, confidence intervals.
- `reports/`: benchmark card, JSON/CSV, Markdown summaries.
- `tests/`: synthetic audio fixtures and normalization edge cases.

## Dataset manifest fields
Dataset name/version, source URL, license, consent/usage notes, audio location or reference, checksum, transcript reference, language/script, domain, recording condition, split, and permitted retention/redistribution. Sensitive speaker metadata should be excluded unless essential, authorized, and ethically reviewed.

## Adapter contract
Each ASR adapter records model/system name, immutable version, decoding parameters, input sample rate, channel handling, language hint, output transcript, request timestamps, and errors. Streaming adapters additionally record chunk boundaries, partial/final status, and revision events.

## Privacy defaults
No raw audio upload to external services by default. No raw audio in logs. Local-only paths and dataset references are preferred. Reports should use pseudonymous sample IDs and aggregate metrics. Never commit audio unless licensing and consent explicitly permit it.
