---
title: "Decoding Consciousness Under Anesthesia"
collection: portfolio
permalink: /portfolio/fmri-anesthesia/
excerpt: "Preprint-stage fMRI analysis of mental-imagery decoding under propofol anesthesia. Task identity decoding starts to collapse before clinical loss of responsiveness, and subjects with awake-like neural dynamics do not show preserved decodable task content."
date: 2026-05-11
---

This project re-analyzes the Michigan human anesthesia fMRI dataset
(doi:10.18112/openneuro.ds006623.v1.0.0), in which healthy adults performed
motor-imagery tasks during target-controlled propofol infusion. The central
question is whether task-decodable neural content tracks clinical loss of
consciousness, or whether cognitive content degrades earlier than the
neural-dynamics markers often used as proxies for consciousness level.

The analysis stack includes strict LOR/ROR labeling, block and LSS feature
generation, run-level functional-connectivity features, leave-one-subject-out
cross-validation, permutation testing, dose-response modeling, and SHAP-based
interpretability.

## Result

The first result is that task-identity information starts to disappear before
the clinical endpoint is reached. In the later within-subject analysis, a
three-class decoder trained on each subject's awake imagery blocks decoded task
identity at 76.4% balanced accuracy while awake, but only 36.9% at loss of
responsiveness. Chance is 33.3%, so the LOR signal is, at most, marginal: most
of the awake task-discriminative signal is gone by the time subjects stop
responding.

A dose-response model estimated the half-maximal collapse of task decoding at
about 1.27 ug/mL propofol effect-site concentration, below typical clinical
maintenance concentrations. In other words, the task-specific content signal
appears to fade earlier than the clinical state itself. Individual EC50
estimates correlated with the clinically observed LOR concentration, suggesting
meaningful subject-level variation in propofol sensitivity.

The second result is that this early content collapse dissociates from
consciousness-level dynamics. The dynamics model was a separate run-level
logistic decoder trained to distinguish awake from sedated runs using 49
non-task features: temporal autocorrelation by network, DMN/DAN switching
metrics, cortical-gradient geometry, and integration-segregation balance,
following prior fMRI consciousness work on propofol anesthesia. In
leave-one-subject-out testing, it produced each held-out subject's continuous
probability of being in an awake-like state at LOR. That dynamics score did not
predict preserved task decoding: subjects with the most awake-looking dynamics
spanned nearly the full range of LOR task accuracy, and the highest-scoring
subject sat near the bottom of the decoding distribution.
This supports the narrower claim that preserved neural dynamics should not be
treated as evidence of preserved decodable task content.

![Two-panel summary of propofol fMRI decoding results: task identity decoding drops from awake to LOR, while dynamics-based P(conscious) at LOR does not predict preserved task-identity accuracy.](/images/portfolio/fmri-anesthesia-summary.png)

## Follow-Up Checks

I also tested whether the conclusion was an artifact of asking the harder
three-class question, "which imagery task is this?" rather than the simpler
binary question, "is the subject doing imagery at all?" Whole-brain
imagery-vs-rest decoding at LOR remained essentially at chance, and proxy ROI
analyses modeled on the original SMA and medial-temporal targets did not reveal
a stronger group-level covert-consciousness signal.

The follow-up does not claim that all residual processing is absent. Instead,
it sharpens the interpretation: propofol appears to leave a small, diffuse
population-level residual while degrading the task-specific structure needed to
decode cognitive content. Awake-like dynamics did not identify subjects with
preserved task identity or binary task-presence decoding.

## Selected References

The neural-dynamics feature set follows prior fMRI consciousness work on
propofol-related slowing of neural timescales, dynamic DMN/DAN switching,
cortical functional gradients, and integration-segregation balance.

- Huang, Z., et al. (2021). Anterior insula regulates brain network transitions that gate conscious access. *Cell Reports*, 35(5), 109081.
- Huang, Z., et al. (2021). Asymmetric neural dynamics characterize loss and recovery of consciousness. *NeuroImage*, 236, 118042.
- Huang, Z., et al. (2023). Functional geometry of the cortex encodes dimensions of consciousness. *Nature Communications*, 14, 72.
- Jang, H., Mashour, G. A., Hudetz, A. G., & Huang, Z. (2024). Measuring the dynamic balance of integration and segregation underlying consciousness. *Nature Communications*, 15, 8843.
