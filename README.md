# Photo Cull AI

> A private, local tool that scores a shoot for blur, focus, duplicates and closed eyes, so you keep the best frames fast.

**Status:** pre-alpha scaffold (no code yet). **Feasibility rating:** 2/10 as a new idea — dedicated products exist; a local, genre-specific workflow is the angle.
**Idea:** #16 in the owner's ideas backlog. **Author:** Oussama EL HADJI. Part of the Bosaj ideas portfolio (sibling repo: `dual_portfolio_hub`).

---

## Problem

After a shoot a photographer spends hours rejecting blurred, duplicated and badly timed frames.

## Why build it (gap analysis)

Commercial cullers exist. A free local tool tuned to one genre (street, landscape, events) with transparent scores and RAW support is still useful, and nothing leaves the computer.

## Prior art & open bases to fork

- [ncoevoet/facet](https://github.com/ncoevoet/facet) — Photo culling tool.
- [duartebarbosadev/PhotoSort](https://github.com/duartebarbosadev/PhotoSort) — Photo sorting with AI.
- [joneilcaoile/photocull-ai](https://github.com/joneilcaoile/photocull-ai) — AI photo culling.
- [h4hardik/photo-culler](https://github.com/h4hardik/photo-culler) — Photo culler.

## Proposed architecture

1. Ingest: read RAW/JPEG, use embedded previews for speed; originals are never modified or downscaled.
2. Scores: sharpness (Laplacian variance), exposure, duplicates (perceptual hash + embeddings), eyes open (face landmarks).
3. Ranking: per-burst best frame, with user-tunable weights per genre.
4. Export: XMP ratings and colour labels so Lightroom picks them up.

## Tech stack (proposed)

- Python core (OpenCV, MediaPipe)
- Desktop UI (Tauri or Qt)
- XMP sidecar writer

## Roadmap

- v0.1 — Sharpness + exposure scores with XMP export.
- v0.2 — Duplicate and burst grouping.
- v0.3 — Eyes-open and face-quality scoring.
- v0.4 — Desktop review UI with genre presets.

---

## For LLM agents & contributors continuing this project

This repo is a **scaffold**: README + standard files, no implementation yet. If you are an AI agent asked to "continue developing", read this section first.

- Never modify or re-encode source files: write ratings to XMP sidecars only.
- Test against a hand-labelled set of the owner's own shoots.

**Ground rules:** keep this README in sync with reality as you build; prefer forking/reusing the bases above over greenfield code; write tests for anything correctness-critical; never commit secrets (see `.gitignore`); follow Conventional Commits (see `CONTRIBUTING.md`).

## Getting started

```bash
# nothing to run yet — this is a scaffold.
```

## License

[MIT](LICENSE) — © 2026 Oussama EL HADJI
