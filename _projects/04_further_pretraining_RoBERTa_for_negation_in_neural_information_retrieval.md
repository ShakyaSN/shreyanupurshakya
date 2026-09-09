---
layout: page
title: Further Pre-training RoBERTa for Negation in Neural Information Retrieval
description: Improving neural information retrieval systems' understanding of negation through targeted pre-training.
importance: 4
category: research
related_publications: false
---

Negation can substantially change the meaning of a sentence, yet neural information retrieval systems often struggle to account for it when ranking documents.

In this project, we investigate whether **targeted further pre-training** can improve RoBERTa's ability to handle negation in neural information retrieval.

We evaluate **RoBERTa-large** on **NevIR**, a benchmark designed to test whether retrieval models correctly rank documents when relevance depends on negation.

We study several negation-focused pre-training strategies and evaluate them in two settings:

- **No-supervision:** models are evaluated on NevIR without fine-tuning on its training set
- **Fine-tuning:** models are further fine-tuned on the NevIR training set

### Key Results

- Negation-focused further pre-training consistently improves RoBERTa-large in both evaluation settings.
- Combining negation-enhanced **Atomic and ANION** pre-training produces a **9.1-point improvement** in NevIR score in the no-supervision setting compared with the STSB-trained RoBERTa-large baseline.
- Further pre-training with **NSP** followed by NevIR fine-tuning achieves a **NevIR score of 80.8**.
- This exceeds the reported **RankGPT o3-mini score of 77.3** in our comparison.
- Error analysis shows that targeted pre-training helps correct cases where the model fails to properly account for negation when ranking documents.

Overall, our results suggest that targeted linguistic pre-training can improve neural retrieval models' sensitivity to negation without requiring additional inference-time computation.

**[Full Report](https://drive.google.com/file/d/14XIz-pSOHZnyJ2oYLmwp9OVrmVHouUOH/view)** · **[Code](https://github.com/mhrezaei1/csc583-nevir)**
