---
layout: page
title: Adaptive Reasoning and Tool Routing from LLM Hidden States
description: Predicting when LLMs need additional reasoning or external tools before generation.
importance: 1
category: research
selected: true
related_publications: false
giscus_comments: false
---

Large language models can improve performance by using additional inference-time resources such as extended reasoning and external tools. However, applying these resources uniformly can waste computation or trigger unnecessary actions.

In this project, we investigate whether an LLM can predict **before generating an answer** whether a problem will require additional reasoning or tool access.

Using **Qwen3-1.7B**, we define model-adaptive measures of two types of resource necessity:

- **Reasoning necessity:** whether a problem benefits from enabling extended Thinking
- **Tool necessity:** whether the model is unable to reliably solve a problem through direct generation

We extract hidden representations from the model's final prompt token before any answer is generated and train layer-wise linear probes to predict these resource-necessity labels.

### Key Results

- Reasoning necessity reaches a peak **AUROC of 0.881** at representation index 17.
- Tool necessity reaches a peak **AUROC of 0.963** at representation index 28.
- At a 30% reasoning budget, adaptive routing achieves **0.897 success** while allocating Thinking to only **31.2%** of examples.
- At an 80% tool budget, adaptive routing achieves **0.846 success** while selectively allocating tool access.
- Necessity predictors transfer above chance between reasoning and tool-use tasks.
- Despite this transfer, we find no evidence that reasoning and tool necessity are represented by a single aligned linear direction.

We also test whether the hidden-state signal can be explained by observable factors such as prompt length, task source, environment, or difficulty. Hidden representations remain predictive beyond these measured confounds.

Overall, the results suggest that pre-generation model representations contain useful information about future inference-time resource needs. This motivates adaptive inference systems that selectively allocate reasoning and tools rather than using them uniformly.
