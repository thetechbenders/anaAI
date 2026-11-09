# Roadmap

This is an evidence-led research roadmap, not a delivery promise.

| Milestone | Goal | Exit gate |
|---|---|---|
| M0 · Foundation | Scope, documentation, issue plan, evaluation definitions | Reviewable baseline and prioritized backlog |
| M1 · Acoustic Evidence | Recorded and independently labeled positive/negative examples | Dataset coverage and recording provenance documented |
| M2 · Classical Baseline | Reproducible non-ML detector | Held-out metrics, false alarms/hour and error analysis |
| M3 · Embedded Intelligence | Quantized ML running on ESP32-S3 | Actual target timings and paired comparison with DSP |
| M4 · Prototype | Self-contained alert-only module | Documented hardware tests and repeatable demonstration |

**Decision gates:** If extruder skips are not consistently audible above normal printer noise, narrow or abandon the target. If learning does not outperform an appropriately tuned non-ML detector under comparable conditions, report that result instead of manufacturing an AI success story.

Non-goals until after validation: auto-pause, scrape detection, custom PCB, fleet control, cloud services.
