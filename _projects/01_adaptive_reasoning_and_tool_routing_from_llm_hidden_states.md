---
layout: page
title: Predicting Resource Necessity from LLM Hidden States
description: Predicting when LLMs need additional reasoning or external tools before generation.
importance: 1
category: research
selected: true
related_publications: false
giscus_comments: false
---
**[Project Report](/assets/pdf/resource-necessity-hidden-states.pdf)**

Large language models can allocate additional inference-time resources through extended reasoning or external tools. However, different prompts may require different amounts or types of resources.

In this project, I investigate whether an LLM's internal representations can predict **before generation** whether a prompt will require additional reasoning computation or external tool access.

Using **Qwen3-1.7B**, I study two model-adaptive resource decisions:

- **Reasoning necessity:** whether enabling extended Thinking improves the model's ability to solve a problem
- **Tool necessity:** whether the model is unable to reliably answer a problem through direct generation

I extract the hidden representation of the model's final prompt token before any answer is generated and train layer-wise linear probes to predict these empirically defined necessity labels.

### Key Results

- Reasoning necessity reaches a best observed five-fold cross-validated **AUROC of 0.881** at layer 17.
- Tool necessity reaches a best observed five-fold cross-validated **AUROC of 0.963** at layer 28.
- Hidden representations remain predictive beyond measured prompt-level characteristics such as prompt length, dataset or environment, and difficulty.
- Raw cross-task evaluation produces above-chance AUROC point estimates for transferring probes between reasoning and tool necessity, although the statistical reliability and robustness of this transfer remain unestablished.
- Probe directions show low alignment across the two tasks, providing no evidence for a single shared linear "resource necessity" direction.

### Exploratory Resource Routing

I also explore whether these predictions could be used to selectively allocate inference-time resources.

At a requested **30% Thinking budget**, the reasoning router allocates Thinking to **31.25%** of retained examples and achieves an estimated **89.69% success rate**.

At an **80% tool-access budget**, selective tool routing achieves an estimated **84.57% success rate**, compared with **89.29%** when tool access is always enabled.

These routing results are **exploratory rather than independently validated**. Some of the outcomes used to evaluate routing were also used when constructing the resource-necessity labels. The allocation percentages measure whether a resource was enabled, not actual reductions in FLOPs, latency, energy, or monetary cost.

### What This Suggests

The results provide evidence that pre-generation hidden representations contain linearly decodable information about **model-specific future resource needs** under the evaluated conditions.

Rather than treating every prompt identically, this motivates further work on adaptive inference systems that decide when additional reasoning or tools are likely to be useful.

The current study uses one model and relatively small benchmark samples. Independent fresh-rollout evaluation, replication across models and tasks, and direct measurement of computational costs are important next steps.
