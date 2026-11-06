# Roadmap — Indic Voice Bench

## Phase 0 — Governance and prior art
- [ ] Review Indic speech benchmarks and recent papers.
- [ ] Select one dataset with clear terms and a manageable pilot split.
- [ ] Define language-specific normalization and privacy policy.
**Exit:** dataset use and scoring conventions are defensible.

## Phase 1 — Offline ASR MVP
- [ ] Create dataset manifest schema.
- [ ] Implement one ASR adapter and local reference scorer.
- [ ] Implement WER/CER and raw/normalized outputs.
- [ ] Generate per-language and per-condition reports.
**Exit:** fully reproducible pilot evaluation.

## Phase 2 — Diagnostic analysis
- [ ] Add error taxonomy and stratified sample inspection.
- [ ] Add confidence intervals and slice coverage warnings.
- [ ] Add additional ASR adapters.
**Exit:** report explains where and how systems fail.

## Phase 3 — Streaming track
- [ ] Define streaming adapter contract and chunk protocol.
- [ ] Capture partial hypotheses and revision events.
- [ ] Add first-partial and finalization latency metrics.
**Exit:** apples-to-apples streaming evaluation.

## Phase 4 — Release
- [ ] Publish benchmark card and governance statement.
- [ ] Publish adapter guide and reproducibility package.
- [ ] Seek external review from speech researchers and dataset maintainers.
