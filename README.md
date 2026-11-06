# Indic Voice Bench

**A diagnostic evaluation framework for speech systems across Indian languages, accents, code-switching, and real-world acoustic conditions.**

Indic Voice Bench is designed to reveal *where* speech systems fail, not merely produce one aggregate WER score. It will evaluate ASR and, in later phases, speech generation or speech understanding where suitable datasets and protocols exist.

## Motivation
Speech quality can vary by language, dialect, accent, speaker, recording environment, code-switching, speaking style, and domain. A model may score well on clean read speech but fail on noisy mobile recordings, names, numbers, or mixed-language utterances. A single benchmark score can conceal these failures.

## Proposed contribution
A transparent benchmark protocol with:
- slice-based evaluation by language, domain, acoustic condition, and code-switching;
- raw and normalized transcription metrics;
- word/character error analysis and error taxonomy;
- streaming latency and partial-transcript stability where systems expose streaming APIs;
- dataset provenance, consent, licensing, and speaker privacy controls;
- reproducible adapters for ASR systems.

## Initial scope
Start with offline ASR evaluation. Add streaming ASR after the offline data model and adapter contract are stable. TTS and speech-to-speech evaluation are later, separate tracks.

## Metrics
WER, CER, normalized WER/CER, insertion/deletion/substitution rates, language-specific normalization rules, latency, real-time factor, and streaming partial stability. Metrics must be interpreted with language-specific conventions and documented normalization.

## Ethics and data governance
Voice is biometric and potentially identifying. Use only datasets with clear consent and permitted research use. Do not infer sensitive speaker traits. Do not publish raw audio or speaker identifiers unless explicit rights and consent permit it. Prefer dataset references, checksums, and derived aggregate metrics.

## Documentation
- [Research brief](docs/RESEARCH.md)
- [Architecture](docs/ARCHITECTURE.md)
- [Evaluation protocol](docs/EVALUATION_PROTOCOL.md)
- [Roadmap](docs/ROADMAP.md)

## Status
<badge>Research / design phase</badge>

No model rankings or dataset coverage claims are made until a documented evaluation has been run.
