# Architecture sketch

> Design proposal, not implemented or validated.

## Data flow

```text
I²S microphone → framed audio → feature extraction ┬→ DSP comparator
                                                  └→ quantized ML classifier
                                                          ↓
                                                   confidence filter
                                                          ↓
                                                 local visual/audio alert
```

The first build performs **alert-only monitoring**. It does not control the printer or infer that a specific mechanical defect exists from an unverified audio pattern.

## Boundaries

- **Audio:** retained locally for consented experiment sessions only. Do not commit raw samples or voice recordings to Git.
- **Inference:** on-device and offline, with bounded RAM/latency requirements verified on target.
- **Evaluation:** grouped holdout by session to reduce leakage; results reported alongside classical DSP comparator.
- **Control:** no automatic pauses, firmware hooks, or printer safety claims in v0.1.
- **Fallback:** uncertain classification yields no automatic action; device fault is visible.

## First hardware candidate

ESP32-S3 development board, I²S MEMS microphone, local indicator, reversible mount, and suitably rated USB power. Exact part selection remains an issue, not a settled specification.

## Interfaces to define before implementation

1. Audio frame contract (sample rate, depth, buffer ownership, timestamps).
2. Feature contract (window/hop length, normalization, numerical equivalence).
3. Model contract (version, feature schema, label meanings, confidence behavior).
4. Event contract (time, class, score, state, reason for warning).
5. Evaluation contract (fault ground truth, held-out split, thresholds, alarm counts).
