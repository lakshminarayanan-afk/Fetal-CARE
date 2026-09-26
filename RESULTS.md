# Results

## Annotation efficiency

Fetal-CARE was compared with Conventional AI-assisted Verification (CAV) on 22,987 images.

| Metric | CAV | Fetal-CARE | Improvement |
|---|---:|---:|---:|
| Images reviewed | 22,987 | 22,987 | — |
| Mean review time/image | 3.02 s | 2.41 s | ↓ 20.2% |
| Median review time/image | 3.01 s | 2.40 s | ↓ 20.3% |
| Total review time | 19.05 h | 14.84 h | ↓ 22.1% |
| Images reviewed/hour | 1206 | 1548 | ↑ 28.4% |
| Acceptance rate | 92.77% | 92.73% | ≈ |
| Correction rate | 7.23% | 7.27% | ≈ |

### Interpretation

The reported efficiency gain is associated with reduced time per image through reviewer-tier routing rather than a change in reviewer decisions.

## Reviewer stratification

| Reviewer | Images | Dataset | Vacuity | Time/image | Correction |
|---|---:|---:|---|---:|---:|
| R1 — Junior | 20,154 | 87.67% | 0.0–0.30 | 2.10 s | 3.25% |
| R2 — Senior | 1,854 | 8.06% | 0.30–0.62 | 3.30 s | 36.29% |
| R3 — Expert | 979 | 4.25% | 0.62–1.0 | 4.18 s | 35.22% |

Higher vacuity is associated with substantially higher correction rates, indicating that error-prone predictions are concentrated in the higher-vacuity tiers.

Only 12.31% of the dataset required senior or expert review.

## Standard-plane analysis

Fetal-CARE reduces reviewer time across the reported standard planes.

The paper reports higher mean vacuity in anatomically challenging planes, including upper and lower limbs, while also observing substantial variability within individual classes. This supports image-level rather than class-level reviewer routing.

## Main takeaway

**Fetal-CARE concentrates expert effort on uncertain cases while reducing overall verification time and preserving review quality.**
