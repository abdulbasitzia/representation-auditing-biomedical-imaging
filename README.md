# Auditing Learned Representations Beyond Accuracy

**Case studies in droplet agglutination and gastric histopathology**

Abdul Basit Zia, PhD and Ian G. Foulds
EMPIRe Lab, School of Engineering, University of British Columbia (Okanagan Campus)

Presented at the **UBC School of Biomedical Engineering 2026 Symposium**, Vancouver, June 2026. Poster 44, L2 Atrium, Gordon B. Shrum Building.

---

## Poster

The full poster is available here: [SBME_Symposium2026_Poster.pdf](./SBME_Symposium2026_Poster.pdf)

---

## Overview

This repository ties together two case studies that share a single question: clean accuracy can hide class level fragility, and two models that score the same on clean data may preserve very different information underneath. The poster brings both studies under one diagnostic protocol, so this repo sits between the two separate project repositories listed below.

The work treats robustness as a property of representations and data rather than architecture. Using PCA on penultimate features alongside representation drift and confusion drift as joint diagnostics, it shows that failures are structured and class specific, with predictable confusion directions.

## Two modalities, one protocol

The same auditing protocol is applied across two biomedical imaging settings:

- **Droplet agglutination assays** (8.9k droplets), comparing a HOG plus SVM pipeline against an EfficientNet model.
- **Gastric histopathology** (31k H&E patches), using EfficientNet.

Both are trained on clean data and tested under brightness, contrast, blur, and noise corruptions across several severities.

## Key findings

- Robustness is a representation and data property, not architectural.
- Failures are structured and class specific, with predictable confusion directions.
- Centroid drift explains dominant confusions geometrically and flags residual classes that drift off axis.
- CNNs deliver invariance, while handcrafted features preserve temporal structure.
- For agglutination, HOG keeps incubation as a dominant axis (silhouette 0.56) while EfficientNet discards window structure, so the two reach similar accuracy while preserving different information.
- HOG collapses under noise (around 15 percent accuracy) while EfficientNet stays above 80 percent.
- Histopathology loses roughly 30 points of accuracy under brightness.

## Take home message

- Audit representations, not just accuracy.
- Use representation drift and confusion drift as joint diagnostics.
- PCA surfaces corruption response and information loss.
- One method, two case studies, two failure modes.

## Related repositories

This poster combines results from two underlying projects, each with its own repository:

- Histopathology corruption robustness: [PASTE FIRST REPO URL]
- Droplet agglutination representation analysis: [PASTE SECOND REPO URL]

## References

1. Hendrycks D, Dietterich T. Benchmarking neural network robustness to common corruptions and perturbations. ICLR 2019.
2. Di Salvo F, Doerrich S, Ledig C. MedMNIST-C: a comprehensive benchmark and improved classifier robustness by simulating realistic image corruptions. arXiv 2024.

## Contact

Abdul Basit Zia, PhD
EMPIRe Lab, School of Engineering, UBC Okanagan
abzia7@student.ubc.ca
GitHub: [your-username]
