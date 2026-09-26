# Fetal-CARE

## Collaborative Annotation with Reviewer-Stratified Expertise for Fetal Ultrasound Standard Plane Classification

Fetal-CARE is a human-AI collaborative framework for fetal ultrasound (US) standard-plane verification. It uses **Evidential Deep Learning (EDL)** to derive **vacuity**, an epistemic uncertainty measure reflecting the lack of evidence supporting a prediction, and uses calibrated vacuity thresholds to route images to reviewer tiers with different levels of expertise.

### Paper

**Fetal-CARE: Collaborative Annotation with Reviewer-Stratified Expertise for Fetal Ultrasound Standard Plane Classification**

Lakshminarayanan M*, Srivibha Parthasarathy*, Keerthi Ram, Shyam Ayyasamy, Suresh Seshadri, Manojkumar Lakshmanan, and Mohanasankar Sivaprakasam

*Equal contribution.

- Department of Electrical Engineering, Indian Institute of Technology Madras, India
- Healthcare Technology Innovation Centre (HTIC), IIT Madras, India
- Sudha Gopalakrishnan Brain Centre, IIT Madras, India
- MediScan Systems, Chennai, India

### Overview

Conventional AI-assisted annotation workflows typically expose every case to the same reviewer pathway. Fetal-CARE instead uses image-level uncertainty to allocate human effort according to case difficulty:

```text
Fetal Ultrasound Image
        │
        ▼
Fetal US Plane Classifier
        │
        ├── Predicted plane
        │
        └── EDL-derived vacuity
                │
        ┌───────┼────────┐
        ▼       ▼        ▼
     Low      Medium     High
    vacuity   vacuity   vacuity
        │       │        │
        ▼       ▼        ▼
       R1      R2       R3
     Junior   Senior   Expert
```

The calibrated thresholds used in the study are:

- τ₁ = 0.30
- τ₂ = 0.62

### Dataset

The study uses two independent patient cohorts from a tertiary scan center:

| Cohort | Purpose | Patients | Images |
|---|---|---:|---:|
| Cohort A | Initial model development | 500 patient examinations | — |
| Cohort B | Comparative evaluation | 1,500 patient examinations | 22,987 |

The dataset covers **20 standard fetal US planes recommended by ISUOG**.

The dataset is privately acquired and is **not included in this repository**.

### Main results

Compared with the conventional AI-assisted verification (CAV) workflow:

| Metric | CAV | Fetal-CARE | Change |
|---|---:|---:|---:|
| Mean review time/image | 3.02 s | 2.41 s | ↓ 20.2% |
| Median review time/image | 3.01 s | 2.40 s | ↓ 20.3% |
| Total review time | 19.05 h | 14.84 h | ↓ 22.1% |
| Images reviewed/hour | 1206 | 1548 | ↑ 28.4% |
| Acceptance rate | 92.77% | 92.73% | ≈ |
| Correction rate | 7.23% | 7.27% | ≈ |

Reviewer stratification showed that the majority of images were handled by the junior tier, while higher-vacuity cases were concentrated among the senior and expert tiers.

### Repository structure

```text
fetal-care/
├── README.md
├── CITATION.cff
├── DATA.md
├── METHOD.md
├── RESULTS.md
├── REPRODUCIBILITY.md
├── LICENSE.md
├── .gitignore
├── paper/
│   └── README.md
├── figures/
│   └── README.md
├── src/
│   └── README.md
└── configs/
    └── vacuity_thresholds.yaml
```

### Code and data availability

The paper reports a privately acquired clinical dataset. Patient-level ultrasound images and annotations are therefore not distributed in this repository.

Implementation files can be placed under `src/` when the corresponding code is released.

### Citation

If you use Fetal-CARE, please cite the paper:

```bibtex
@inproceedings{lakshminarayanan2026fetalcare,
  title     = {Fetal-CARE: Collaborative Annotation with Reviewer-Stratified Expertise for Fetal Ultrasound Standard Plane Classification},
  author    = {Lakshminarayanan, M. and Parthasarathy, Srivibha and Ram, Keerthi and Ayyasamy, Shyam and Seshadri, Suresh and Lakshmanan, Manojkumar and Sivaprakasam, Mohanasankar},
  year      = {2026}
}
```

### Contact

For questions regarding the work, contact the corresponding authors through their institutional affiliations.
