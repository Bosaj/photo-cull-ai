# 1. Architecture

1. Ingest: read RAW/JPEG, use embedded previews for speed; originals are never modified or downscaled.
2. Scores: sharpness (Laplacian variance), exposure, duplicates (perceptual hash + embeddings), eyes open (face landmarks).
3. Ranking: per-burst best frame, with user-tunable weights per genre.
4. Export: XMP ratings and colour labels so Lightroom picks them up.

## Proposed stack
- Python core (OpenCV, MediaPipe)
- Desktop UI (Tauri or Qt)
- XMP sidecar writer

## Open bases to fork
- [ncoevoet/facet](https://github.com/ncoevoet/facet) — Photo culling tool.
- [duartebarbosadev/PhotoSort](https://github.com/duartebarbosadev/PhotoSort) — Photo sorting with AI.
- [joneilcaoile/photocull-ai](https://github.com/joneilcaoile/photocull-ai) — AI photo culling.
- [h4hardik/photo-culler](https://github.com/h4hardik/photo-culler) — Photo culler.
