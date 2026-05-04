# 📄 Assignment 1: Systematic Paper Analysis — SIREN

> **Paper:** *Implicit Neural Representations with Periodic Activation Functions*
> Sitzmann et al., NeurIPS 2020 · [arXiv:2006.09661](https://arxiv.org/abs/2006.09661)

---

## 🏫 Course Info

| Field | Details |
|---|---|
| **Institution** | FAST–NUCES, School of Computing |
| **Department** | AI & Data Science |
| **Instructor** | Dr. Zohair Ahmed |
| **Program** | BS DS / AI |
| **Group** | ID09 |

---

## 👥 Group Members

| Name | Roll No. | Sections |
|---|---|---|
| Valeena Afzal | 25I-8023 | Introduction & Paper Summary |
| Maryam Zafar | 25I-8033 | Methodology & Experimental Results |
| Laiba Noor | 25I-8035 | Critical Analysis & Research Opportunities |

> Section 7 (References) compiled jointly by all members.

---

## 📑 Report Sections

1. **Introduction** — Background on implicit neural representations (INRs) and the need for periodic activations
2. **Paper Summary** — Problem statement, motivation, target task, prior methods, and key differences
3. **Methodology Analysis** — SIREN architecture, sine activation role, ω₀ frequency scaling, weight initialisation scheme
4. **Experimental Results** — Main results, baseline comparisons (ReLU, Tanh, Fourier Features), ablation studies
5. **Critical Analysis** — Limitations of the method, dataset/evaluation gaps, reproducibility and scalability concerns
6. **Research Opportunities** — Three proposed extensions
7. **References**

---

## 🔬 Paper Overview

**SIREN** (Sinusoidal Representation Network) replaces standard non-periodic activations (like ReLU) with **sine functions**, enabling:

- Accurate representation of **high-frequency signals** (sharp textures, audio, 3D geometry)
- Well-behaved **higher-order derivatives** at any order
- Solving **physics-based PDEs** (Poisson, Eikonal, Helmholtz) using only derivative supervision

The network maps input coordinates → signal values:

```
Φ(x) = W_L ( sin(ω₀·(W_{L-1}x + b)) ∘ ... ∘ sin(ω₀·(W₀x + b₀)) ) + b_L
```

Weights are initialised from `U(−√6/n, √6/n)` for stable gradient flow across deep periodic layers.

---

## 🧪 Proposed Extensions

| # | Extension | Key Idea |
|---|---|---|
| 1 | Larger & more diverse image evaluation | Benchmark on full BSDS500 + medical imaging datasets |
| 2 | Adaptive frequency scaling | Make ω₀ a learnable per-layer parameter, initialised via FFT |
| 3 | Knowledge distillation | Compress large SIREN teacher → small student with ~12× fewer parameters |

---

## 📁 File

```
Deep_Learning_Assignment_1_25i-8023_25i-8033_25i-8035.pdf
```

---

## 📚 Citation

```bibtex
@inproceedings{sitzmann2020siren,
  title     = {Implicit Neural Representations with Periodic Activation Functions},
  author    = {Sitzmann, Vincent and Martel, Julien N.P. and Bergman, Alexander W. and Lindell, David B. and Wetzstein, Gordon},
  booktitle = {Advances in Neural Information Processing Systems (NeurIPS)},
  volume    = {33},
  pages     = {7462--7473},
  year      = {2020}
}
```
