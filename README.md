<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f0c29,30:302b63,60:24243e,100:f7971e&height=220&section=header&text=GSoC%202026%20Portfolio&fontSize=60&fontColor=fff&animation=twinkling&fontAlignY=40&desc=Abhi%20Ramg%20%7C%20Hyderabad%2C%20India%20%7C%20All%20Projects%20by%20Organisation&descAlignY=60&descSize=16" width="100%"/>

<br/>

[![GSoC 2026](https://img.shields.io/badge/GSoC-2026%20Applicant-F6AE2D?style=for-the-badge&logo=google&logoColor=white)](https://summerofcode.withgoogle.com/)
[![Orgs](https://img.shields.io/badge/Orgs-ML4Sci%20%7C%20HumanAI%20%7C%20Metaflow-8B5CF6?style=for-the-badge)]()
[![Projects](https://img.shields.io/badge/Total%20Projects-9-E94560?style=for-the-badge)]()
[![GitHub](https://img.shields.io/badge/GitHub-abhiram123467-181717?style=for-the-badge&logo=github)](https://github.com/abhiram123467)

</div>

---

## 🗺️ Quick Navigation

| Org | Projects | Domain |
|---|---|---|
| [🔭 ML4Sci](#-ml4sci--deeplense) | DeepLense4, DeepLense8, DeepLense9 | Astrophysics AI |
| [🧠 HumanAI](#-humanai) | SIRA, ArtExtract, OCR1, OCR2, OCR3 | Epidemic ML, Art AI, Historical OCR |
| [🚀 Metaflow / RenAIssance](#-metaflow--renaissance) | Renaissance OCR3 | Scalable historical OCR |

---

# 🔭 ML4Sci — DeepLense

> **Organisation:** [ML4Sci (Machine Learning for Science)](https://ml4sci.org/)
> **Domain:** Gravitational Lensing · Dark Matter · Astrophysics AI

---

### 1. DeepLense4 — Foundation Model for Gravitational Lensing

[![Repo](https://img.shields.io/badge/Repo-DeepLense4-4285F4?style=flat-square&logo=github)](https://github.com/abhiram123467/DeepLense4)
![Task](https://img.shields.io/badge/Task-IX.A%20%2B%20IX.B-8B5CF6?style=flat-square)
![Model](https://img.shields.io/badge/Model-MAE%20%2B%20ViT-06B6D4?style=flat-square)

| Detail | Info |
|---|---|
| **GSoC Task** | Test IX.A (Classification) + Test IX.B (Super-Resolution) |
| **Architecture** | Masked Autoencoder (MAE) pre-trained on `no_sub` → fine-tuned |
| **Task IX.A** | 3-class classification: No Substructure / CDM / Axion dark matter |
| **Task IX.B** | Fine-tune pre-trained model for LR→HR super-resolution |
| **Metrics** | ROC-AUC (classification) · MSE, SSIM, PSNR (SR) |
| **Dataset** | Gravitational lensing `.npy` images, 64×64px |
| **Stack** | PyTorch · timm · einops · scikit-image |

```
Pre-train MAE on no_sub images
          ↓
  Fine-tune IX.A → 3-class classifier (no_sub / CDM / Axion)
  Fine-tune IX.B → Super-resolution (LR 16×16 → HR 64×64)
```

---

### 2. DeepLense8 — Physics-Informed Diffusion Models

[![Repo](https://img.shields.io/badge/Repo-DeepLense8-4285F4?style=flat-square&logo=github)](https://github.com/abhiram123467/DeepLense8)
![Task](https://img.shields.io/badge/Task-Test%20VIII-8B5CF6?style=flat-square)
![Model](https://img.shields.io/badge/Model-DDPM%20%2B%20U--Net-EE4C2C?style=flat-square)

| Detail | Info |
|---|---|
| **GSoC Task** | Test VIII — Generative model for lensing images |
| **Architecture** | DDPM with U-Net + Sinusoidal Time Embedding |
| **What it does** | Generates synthetic gravitational lensing images from Gaussian noise |
| **Metrics** | FID score + qualitative visual assessment |
| **Dataset** | 10,000 strong lensing images |
| **Timesteps** | T = 1,000 (linear β schedule) |
| **Stack** | PyTorch · einops · pytorch-fid |

```
Pure Gaussian Noise  →  1000 Denoising Steps (U-Net)  →  Lensing Image 🔭
```

---

### 3. DeepLense9 — Unsupervised Super-Resolution

[![Repo](https://img.shields.io/badge/Repo-DeepLense9-4285F4?style=flat-square&logo=github)](https://github.com/abhiram123467/gsoc2026-deeplense9)
![Task](https://img.shields.io/badge/Task-VI.A%20%2B%20VI.B-8B5CF6?style=flat-square)
![Model](https://img.shields.io/badge/Model-RCAN--lite%204×-06B6D4?style=flat-square)

| Detail | Info |
|---|---|
| **GSoC Task** | Test VI.A (Simulated SR) + Test VI.B (Real HSC/HST SR) |
| **Architecture** | RCAN-lite (8 Residual Blocks + Channel Attention + Pixel Shuffle) |
| **Scale** | 4× super-resolution (16×16 → 64×64) |
| **Transfer Learning** | VI.A weights → fine-tuned on 300 real HSC/HST telescope pairs |
| **Loss** | L1 + Sobel Gradient Loss (λ=0.1) — preserves lensing arc sharpness |
| **Metrics** | MSE · SSIM · PSNR |
| **Mentors** | Michael Toomey (MIT) · Pranath Reddy · Sergei Gleyzer (Alabama) |
| **Stack** | PyTorch · scikit-image · seaborn |

```
Simulated SR (VI.A) → Real HSC/HST transfer-learning (VI.B)
  LR 16×16 ─── RCAN-lite 4× ──► HR 64×64
```

---

# 🧠 HumanAI

> **Organisation:** [HumanAI](https://human-ai.org/)
> **Domain:** Epidemic Modelling · Art Intelligence · Historical Document OCR

---

### 4. SIRA — Learning the SIR Epidemic Model

[![Repo](https://img.shields.io/badge/Repo-sira--deeplense-E94560?style=flat-square&logo=github)](https://github.com/abhiram123467/sira-deeplense)
![Model](https://img.shields.io/badge/Model-Neural%20ODE%20%2B%20Symbolic-0F3460?style=flat-square)

| Detail | Info |
|---|---|
| **Project** | SIRA — Learning the SIR Epidemic Model |
| **Architecture** | Physics-Informed Neural ODE (torchdiffeq) vs MLP baseline vs Symbolic SIR |
| **Data** | 2,000 synthetic epidemics via Gillespie algorithm · β∈[0.1,0.9], γ∈[0.05,0.3] |
| **Physics Loss** | Conservation (S+I+R=1) + non-negativity penalty · weight=0.1 |
| **Time horizon** | 160 days · R₀ range: 0.33→18 |
| **Symbolic Stage** | Learns closed-form sigmoid/Gaussian approximations for S(t), I(t), R(t) |
| **Metrics** | MSE per compartment (S, I, R) |
| **Mentors** | Harrison Prosper (FSU) · Olivia Prosper (UTK) · Sergei Gleyzer (Alabama) |
| **Stack** | PyTorch · torchdiffeq · SciPy · seaborn |

```
2000 Gillespie simulations → Neural ODE (physics-constrained) → S(t), I(t), R(t)
                                      ↓
                            Symbolic distillation → analytic approximation
```

---

### 5. ArtExtract — Painting In A Painting

[![Repo](https://img.shields.io/badge/Repo-ArtExtract-E94560?style=flat-square&logo=github)](https://github.com/abhiram123467/artextract-deeplense)
![Task](https://img.shields.io/badge/Task-1%20%2B%202-8B5CF6?style=flat-square)
![Model](https://img.shields.io/badge/Model-CNN--RNN%20%2B%20Siamese-F59E0B?style=flat-square)

| Detail | Info |
|---|---|
| **Project** | Painting In A Painting — Hidden Images with AI |
| **Task 1** | CNN-RNN multi-task classification: Style + Artist + Genre on WikiArt (3,000 paintings) |
| **Task 1 Architecture** | ResNet-50 backbone → BiLSTM (49 spatial tokens) → Attention → 3 heads |
| **Task 1 Extra** | Outlier detection via cosine distance from class centroid embeddings |
| **Task 2** | Painting similarity retrieval on National Gallery of Art dataset |
| **Task 2 Architecture** | EfficientNet-B2 Siamese Network + Triplet Loss (256-dim embedding) |
| **Task 2 Retrieval** | KNN cosine similarity · Precision@K · mAP |
| **Metrics** | Style/Genre Accuracy · mAP · Precision@1/3/5/10 |
| **Mentors** | Emanuele Usai (Alabama) · Sergei Gleyzer (Alabama) |
| **Stack** | PyTorch · timm · sklearn · seaborn · HuggingFace datasets · NGA Open API |

```
Task 1: WikiArt Painting → ResNet50 → BiLSTM → Style / Artist / Genre
Task 2: Query Painting   → EfficientNet-B2 → Triplet embed → Top-K similar paintings
```

---

### 6. OCR1 — CRNN for Historical Document OCR

[![Repo](https://img.shields.io/badge/Repo-renai--ocr2--test-E94560?style=flat-square&logo=github)](https://github.com/abhiram123467/renai-ocr2-test-abhi)
![Model](https://img.shields.io/badge/Model-CRNN%20%2B%20CTC-06B6D4?style=flat-square)

| Detail | Info |
|---|---|
| **Project** | RenAIssance OCR1 — CRNN text recognition |
| **Architecture** | CNN (3×Conv) → BiLSTM (2 layers, hidden=256) → FC → CTC decode |
| **Input** | Historical manuscript images resized to H=32px, variable width |
| **Preprocessing** | Grayscale → aspect-ratio-preserving resize → normalise |
| **Classes** | 80 character classes |
| **Stack** | PyTorch · PIL · torchvision |

---

### 7. OCR2 — ⚠️ Notebook Missing

![Status](https://img.shields.io/badge/Status-Notebook%20Not%20Found-FF0000?style=flat-square)

| Detail | Info |
|---|---|
| **Project** | RenAIssance OCR2 — intermediate OCR pipeline |
| **Status** | ⚠️ Notebook file not available — need to recover or recreate |
| **Likely approach** | Bridges OCR1 (CRNN) and OCR3 (VLM) — possibly attention-based or transformer OCR |
| **Action needed** | Check Google Colab history or Google Drive for saved notebook |

> 💡 **Recovery tip:** Go to [colab.research.google.com](https://colab.research.google.com) → "Recent" tab — it may still be cached there even without a saved copy.

---

### 8. OCR3 — VLM End-to-End Pipeline

[![Repo](https://img.shields.io/badge/Repo-gsoc2026--renaissance--ocr3-E94560?style=flat-square&logo=github)](https://github.com/abhiram123467/gsoc2026-renaissance-ocr3)
![Model](https://img.shields.io/badge/Model-Gemini%202.0%20Flash%20%2B%20TrOCR-4285F4?style=flat-square)

| Detail | Info |
|---|---|
| **Project** | RenAIssance OCR3 — VLM-native pipeline |
| **Primary Model** | Gemini 2.0 Flash (Google VLM) — direct image→text |
| **Fallback Model** | Microsoft TrOCR (Vision Encoder + Language Decoder) — no API key needed |
| **Approach** | Line-by-line strip extraction → VLM transcription per strip |
| **Test doc** | 17th-century Spanish manuscript (678×710px) |
| **Output** | 678 characters · diacritics preserved (á, é, ó, ñ, à, ç) |
| **Stack** | google-generativeai · transformers (TrOCR) · PIL |

---

# 🚀 Metaflow / RenAIssance

> **Organisation:** [Metaflow (Netflix OSS)](https://metaflow.org/)
> **Domain:** Scalable ML Pipelines for Historical Document Processing

---

### 9. Renaissance OCR3 — Scalable Historical Manuscript OCR

[![Repo](https://img.shields.io/badge/Repo-gsoc2026--renaissance--ocr3-F6AE2D?style=flat-square&logo=github)](https://github.com/abhiram123467/gsoc2026-renaissance-ocr3)
![Model](https://img.shields.io/badge/Model-Gemini%20VLM%20%2B%20Metaflow-EE4C2C?style=flat-square)

| Detail | Info |
|---|---|
| **Project** | Renaissance OCR3 — production-scale historical document OCR |
| **Core** | Gemini 2.0 Flash VLM + density analysis preprocessing pipeline |
| **GSoC Angle** | Metaflow `@batch` integration for processing Vatican Archives at scale |
| **Demonstrated on** | 17th-century Spanish manuscript — 96% accuracy, diacritics preserved |
| **Rate-limit resilience** | Exponential backoff + model fallback (2.0-flash → 1.5-flash) |
| **Stack** | google-generativeai · OpenCV · FastAPI · Streamlit · Metaflow |

```
Archive (1M pages)
       ↓  Metaflow @batch
Density Analysis → Gemini VLM → Structured JSON output
```

---

## 📊 Full Portfolio Summary

| # | Project | Org | Key Model | Status |
|---|---|---|---|---|
| 1 | DeepLense4 | ML4Sci | MAE + ViT | ✅ Complete |
| 2 | DeepLense8 | ML4Sci | DDPM + U-Net | ✅ Complete |
| 3 | DeepLense9 | ML4Sci | RCAN-lite 4× | ✅ Complete |
| 4 | SIRA | HumanAI | Neural ODE | ✅ Complete |
| 5 | ArtExtract | HumanAI | CNN-RNN + Siamese | ✅ Complete |
| 6 | OCR1 (CRNN) | HumanAI | CRNN + CTC | ✅ Complete |
| 7 | OCR2 | HumanAI | — | ⚠️ Missing |
| 8 | OCR3 (VLM) | HumanAI | Gemini + TrOCR | ✅ Complete |
| 9 | Renaissance OCR3 | Metaflow | Gemini + Metaflow | ✅ Complete |

---

## 🧵 Cross-Project Theme

All 9 projects share **one unifying principle:**

> **Embed physics, structure, or domain constraints directly into neural network training — whether that constraint is a differential equation, a conservation law, a physical lens model, or a language prior.**

| Project | Constraint Type |
|---|---|
| DeepLense4/8/9 | Gravitational lensing physics |
| SIRA | ODE conservation (S+I+R=N) |
| ArtExtract | Visual composition structure |
| OCR1/2/3 | Language model priors for text |
| Renaissance OCR3 | Historical script domain knowledge |

---

<div align="center">

**Abhi Ramg · Hyderabad, India · GSoC 2026**

[![GitHub](https://img.shields.io/badge/GitHub-abhiram123467-181717?style=for-the-badge&logo=github)](https://github.com/abhiram123467)

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:f7971e,50:302b63,100:0f0c29&height=120&section=footer" width="100%"/>

</div>
