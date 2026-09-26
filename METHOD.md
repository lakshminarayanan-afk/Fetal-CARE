# Method

## 1. Problem

Fetal ultrasound data are heterogeneous because of variation in acquisition, imaging systems, image quality, probe positioning, operator technique, and motion artifacts. Conventional annotation workflows apply the same verification burden to all images.

Fetal-CARE addresses this by estimating image-level uncertainty and matching reviewer expertise to the estimated difficulty of each case.

## 2. Evidential uncertainty

Fetal-CARE uses an Evidential Deep Learning classifier.

The framework derives **vacuity** as the uncertainty signal used for reviewer routing.

Vacuity represents the lack of evidence supporting the prediction.

## 3. Reviewer routing

Two calibrated thresholds define three reviewer tiers:

| Vacuity | Tier | Reviewer |
|---|---|---|
| 0.0–0.30 | R1 | Junior Reviewer |
| 0.30–0.62 | R2 | Senior Reviewer |
| 0.62–1.0 | R3 | Expert Reviewer |

The thresholds were derived from cumulative misclassification coverage so that higher-probability errors are concentrated in the higher reviewer tiers.

## 4. Reviewer protocol

Reviewers independently assess the AI-predicted plane label and either:

- accept the prediction, or
- assign a corrected label.

Reviewers are blinded to the underlying vacuity score and to the rationale for the assigned reviewer tier.

Review time is measured from image presentation until completion of the verification decision using the same timing procedure across workflows.

## 5. Ground-truth repository

Verified labels from Cohort B are consolidated into a curated repository containing:

- accepted predictions
- corrected labels
- reviewer decisions
- review durations
- uncertainty estimates

The resulting repository can subsequently support model refinement and active-learning workflows.
