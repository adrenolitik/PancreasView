# 🔬 MedSAM2 — Interactive Medical Image Segmentation

[![Live Demo](https://img.shields.io/badge/🔗-Live_Demo-8b5cf6)](https://shadman19.github.io/medsam2/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![SAM2](https://img.shields.io/badge/Meta-SAM2-blue)](https://github.com/facebookresearch/sam2)

> Interactive medical image segmentation using Meta's Segment Anything Model 2 — click to place prompt points, get instant segmentation masks with Dice and IoU scoring.

**[Try the Live Demo →](https://shadman19.github.io/medsam2/)**

---

## What This Does

Upload any medical image. Click anywhere to place prompt points. Get instant segmentation masks with:

- Dice Similarity Coefficient scoring
- IoU (Intersection over Union) scoring
- Per-organ performance breakdown
- SAM2 attention heatmap visualization
- Multi-point prompting support
- Real-time latency measurement

## Supported Modalities

| Modality | Organs/Structures |
|----------|-------------------|
| 🫁 Chest X-Ray | Lung-L, Lung-R, Heart, Trachea |
| 🧠 Brain MRI | Cortex, Ventricle, Cerebellum, Lesion |
| 🩻 Abdominal CT | Liver, Kidney-L, Kidney-R, Spleen |
| 👁️ Fundus | Optic Disc, Macula, Vessels, Lesion |

## SAM2 Pipeline

```
Medical Image
      │
      ▼
┌─────────────────┐
│  Hiera Encoder  │  Image → 256-dim patch features
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Prompt Encoder  │  Click points → sparse embeddings
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Mask Decoder   │  Two-way transformer attention
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Multi-Scale    │  FPN → high-resolution mask
│  Fusion (FPN)   │
└────────┬────────┘
         │
         ▼
  Mask + Dice + IoU
```

## Usage

Open `index.html` in any browser. No setup, no installation, no API key.

Or use the live demo: **https://shadman19.github.io/medsam2/**

## Research Context

- Ravi et al. (2024) — SAM 2: Segment Anything in Images and Videos (Meta FAIR)
- Ma et al. (2024) — Segment Anything in Medical Images (MedSAM, Nature Communications)
- Related: False Negative Induction in Brain Tumor Segmentation by Trained Noise Attack (IEEE, 2023)

---

*Built by Shadman Mahmood Khan Pathan · [GitHub](https://github.com/Shadman19) · [LinkedIn](https://linkedin.com/in/shadmanmahmood9)*
