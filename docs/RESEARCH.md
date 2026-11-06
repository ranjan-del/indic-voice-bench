# Research brief — Indic Voice Bench

## 1. Problem
Speech systems for Indian languages operate across diverse phonologies, scripts, dialects, accents, recording devices, acoustic environments, and code-switching patterns. Public leaderboards often compress these dimensions into one score, making it hard to understand operational suitability.

## 2. Research questions
- Which language/domain/acoustic slices cause the largest ASR errors?
- How much do text normalization conventions change WER/CER?
- How do systems handle code-switching, named entities, numbers, and borrowed words?
- How robust are models to noise, reverberation, distance, and mobile-device recording?
- For streaming systems, how quickly do partial hypotheses appear and how often are they revised?
- Can a benchmark report expose data gaps and uncertainty rather than imply complete language coverage?

## 3. Existing ecosystem and prior art
Review and compare:
- **IndicSUPERB** and related Indic speech evaluation work.
- **IndicVoices** and other large-scale Indic speech resources.
- **AI4Bharat** speech datasets and models.
- **Mozilla Common Voice** language-specific datasets.
- **LAHAJA** and other accent/dialect-focused speech resources where access and terms permit.
- **Open ASR benchmarks** and standard metrics/tooling such as jiwer.

This project is not novel merely because it evaluates ASR in Indian languages. Its intended contribution is a carefully governed, slice-first diagnostic protocol, explicit normalization variants, reproducible system adapters, and streaming stability metrics. Confirm this gap through a paper and benchmark review before claiming novelty.

## 4. Evaluation tracks
### Track A — Offline ASR (MVP)
Input audio file -> transcription -> reference comparison. Report WER/CER, normalized variants, latency, and real-time factor.

### Track B — Robustness
Predefined acoustic slices: clean, background noise, reverberation, distance, low volume, and device variation. Do not synthesize transformations and present them as naturally occurring data.

### Track C — Code-switching and language mixing
Define annotation conventions for language boundaries, borrowed words, transliteration, and script choice. Provide separate metrics for mixed utterances.

### Track D — Streaming ASR (later)
Measure first partial latency, finalization latency, revision rate, stability of committed tokens, and end-to-end delay. Only compare systems with equivalent streaming interfaces and chunk policies.

### Track E — TTS (deferred)
Requires separate human evaluation, pronunciation and prosody protocols, speaker consent, and safety review. Do not collapse TTS quality into ASR scores.

## 5. Metrics and caveats
- **WER:** word substitutions + deletions + insertions divided by reference word count. Tokenization/spacing conventions strongly affect Indic language scores.
- **CER:** character edit distance normalized by reference characters; script normalization still matters.
- **Normalized WER/CER:** apply a published, versioned normalization policy; always also report raw results.
- **Real-time factor:** processing duration divided by audio duration; define whether queue and network time are included.
- **Partial stability:** quantify revisions to previously emitted tokens; distinguish provisional from committed output.
- **Slice coverage:** sample count and uncertainty per language/domain/acoustic slice.

No single metric represents intelligibility, usefulness, or fairness.

## 6. Dataset governance
For every dataset, record the dataset card, license, collection method, consent basis, speaker demographics only where legitimately provided and ethically appropriate, language labels, domain, recording conditions, and redistribution rules. Do not assume public download implies permission to rehost.

Potential sources to investigate include AI4Bharat, Common Voice, IndicVoices, and FLORES-related text resources for normalization or language metadata. Verify exact dataset versions and terms before use. The initial benchmark should support external dataset references and local-only evaluation.

## 7. Experimental design
- Freeze dataset versions and reference transcripts.
- Publish normalization rules and alternate scoring modes.
- Use identical audio and decode settings across systems.
- Separate model inference time from network and queue time.
- Report per-slice sample sizes and confidence intervals.
- Manually inspect a stratified error sample under an approved protocol.
- Document unsupported languages and missing slices explicitly.

## 8. Risks
Speaker privacy, consent ambiguity, dataset imbalance, annotation inconsistency, normalization bias, and misleading rankings. Mitigate with governance review, minimal data retention, clear benchmark cards, and no unsupported demographic inference.

## 9. References and starting points
- AI4Bharat: https://ai4bharat.org/
- Mozilla Common Voice: https://commonvoice.mozilla.org/
- Hugging Face datasets: https://huggingface.co/datasets
- jiwer: https://github.com/jitsi/jiwer
- ACL Anthology: https://aclanthology.org/
- Papers with Code: https://paperswithcode.com/

Verify current dataset versions, licenses, and relevant publications before any public benchmark release.
