---
layout: page
title: Efficient LLM Reasoning in Low-Resource Languages
description: Evaluating reasoning-efficiency tradeoffs in English and Nepali.
importance: 2
category: research
related_publications: false
---

This project investigates how much reasoning is actually necessary for large language models to solve tasks effectively, particularly in low-resource language settings.

We compare three prompting strategies:

- **No-CoT**: direct answers without explicit reasoning
- **Minimal-CoT**: short, targeted reasoning
- **Standard-CoT**: full chain-of-thought reasoning

Our experiments evaluate **Llama-3-8B-Instruct** and **Qwen2.5-7B-Instruct** on GSM8K in English and Nepali.

We study the tradeoff between model performance and computational efficiency by evaluating:

- task accuracy
- generated token usage
- inference latency
- performance under different reasoning budgets

We also analyze common failure modes, including truncation, semantic grounding errors in Nepali numerical expressions, numerical and reasoning drift, and paraphrase loops.

Our results show that Minimal-CoT can remain competitive with Standard-CoT while using substantially fewer generated tokens and shorter inference times. In Nepali, Minimal-CoT achieves comparable or, in some settings, better performance than Standard-CoT. We also find that increasing the reasoning budget beyond a certain point provides little additional benefit and can reduce stability.

This project contributes to our broader goal of understanding how language models can reason more efficiently and reliably, particularly in low-resource settings.

**[Full Project Report](https://uazhlt-ms-program.github.io/ling-582-fall-2025-course-blog/snshakya/course-project/)** · **[Code](https://github.com/uazhlt-ms-program/ling-582-fall-2025-course-project-code-shreya-vovwe)**
