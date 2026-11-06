# Evaluation protocol

## Offline ASR baseline
1. Select a dataset with documented rights and a stable version.
2. Define language/domain/acoustic slices before evaluation.
3. Pin the ASR system version and decoding parameters.
4. Run all samples with identical preprocessing.
5. Score raw transcripts and versioned normalized transcripts.
6. Report WER, CER, substitutions, deletions, insertions, latency, and RTF.
7. Report per-slice sample counts and confidence intervals.
8. Inspect a stratified error sample and classify error types.

## Normalization policy
Document handling of Unicode normalization, punctuation, whitespace, numerals, abbreviations, spelling variants, and script/transliteration. Never silently normalize references differently from hypotheses. Publish raw and normalized scores together.

## Streaming protocol (future)
Fix audio chunk size and pacing. Record audio start, first partial, every revision, first stable/committed token, final transcript, and completion. Report first-partial latency, finalization latency, revision rate, and stability. Do not compare streaming systems with different chunking or endpointing settings without disclosing them.

## Report requirements
Dataset card, system revision, hardware, preprocessing, scoring version, sample counts, slice definitions, confidence intervals, failures, and limitations are mandatory.
