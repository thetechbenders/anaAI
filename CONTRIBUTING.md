# Contributing to anaAI

We welcome focused, reproducible contributions in acoustics, signal processing, embedded inference, test design, and documentation.

## Before opening a PR

1. Pick or open an issue identifying the user-facing problem and evidence required.
2. Keep changes narrow, with reproducible tests or explicit reasons tests are unavailable.
3. Mark **simulated**, **host-tested**, **target-compiled**, and **physically tested** outcomes separately.
4. Do not include captured speech, private printer telemetry, credentials, or licensed datasets in commits.
5. For fault-detection claims, compare with a non-ML baseline on a session-held-out test set.
6. Document power/thermal and safe-failure limits for electrical hardware changes.

Repository-specific practices may evolve when a build system is selected. Do not claim build success without an actual build.
