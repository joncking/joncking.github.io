---
title: "Landscape Explorer"
collection: portfolio
permalink: /portfolio/landscape-explorer/
excerpt: "Active prototype for mapping LLM behavior under weight-space perturbations. A GPT-2 perplexity run perturbs the model in three orthogonal directions and renders the resulting landscape as an interactive 3D Plotly visualization. [Open the interactive landscape](/files/portfolio/landscape-explorer/scatter3d.html)."
date: 2026-05-11
---

[Open the interactive 3D landscape](/files/portfolio/landscape-explorer/scatter3d.html){: .btn .btn--primary}

The source code is private while this remains active research; the linked
artifact is a generated run output from the current prototype.

Landscape Explorer is an active prototype for exploring how model properties
change under structured weight-space perturbations. The toolkit builds
layer-normalized directions, traverses the model through that low-dimensional
subspace, evaluates a selected metric at each point, then analyzes and
visualizes the resulting landscape.

The highlighted run uses GPT-2 perplexity as the metric and perturbs the model
along three orthogonal directions to generate an interactive 3D landscape. It is
a concrete example of the tool's goal: making local model-behavior geometry
visible enough to inspect, compare, and reason about.

![Contour plot of GPT-2 perplexity under two perturbation directions](/images/portfolio/landscape-explorer-contour.png)

The static contour plot is included as a lightweight fallback; the interactive
3D version is the best way to inspect the structure.
