---
title: "Decoding Consciousness Under Anesthesia"
collection: portfolio
permalink: /portfolio/fmri-anesthesia/
excerpt: "Research pipeline for decoding mental-imagery and consciousness-related neural signals in propofol anesthesia fMRI. The headline result is a graded decoding curve: task identity is robust while awake, degrades with increasing sedation, remains weakly above chance during loss of responsiveness, and partially recovers after return of responsiveness."
date: 2026-05-11
---

fMRI Anesthesia is a research pipeline for studying covert-consciousness signals
in the Michigan human anesthesia fMRI dataset. The project analyzes mental
imagery tasks performed under graded propofol sedation, with a focus on whether
machine-learning models can recover task-discriminative neural structure during
loss of responsiveness.

The analysis stack includes strict LOR/ROR labeling, block and LSS feature
generation, run-level functional-connectivity features, leave-one-subject-out
cross-validation, permutation testing, dose-response modeling, and SHAP-based
interpretability.

## Result

The main result is a graded loss and partial recovery of task decoding as
propofol concentration changes. In the publication-style analysis, whole-brain
task decoding reached 79.3% balanced accuracy while awake, 64.6% before loss of
responsiveness, 36.1% during loss of responsiveness, and 58.6% after return of
responsiveness. Chance for the three-class task problem is 33.3%; the LOR group
result is weak but above chance by permutation testing.

A dose-response model estimated a group EC50 of about 1.27 ug/ml for loss of
task-discriminative signal. Individual EC50 estimates correlated with LOR
decoding performance, and recovery differed from induction, consistent with a
neural-inertia interpretation.

The interpretability analyses separate complementary signals: cortical task
representations degrade strongly at LOR, thalamic parcels retain some
task-specific signal, and run-level connectivity features highlight subcortical
circuits linked to propofol's pharmacology.
