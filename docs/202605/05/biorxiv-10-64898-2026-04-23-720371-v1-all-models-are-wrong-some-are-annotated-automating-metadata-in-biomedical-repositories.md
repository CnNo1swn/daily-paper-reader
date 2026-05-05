---
title: "All Models are Wrong, Some are Annotated: Automating Metadata in Biomedical Repositories"
authors: "Cohen, I., Yu, H., McDougal, R. A."
date: 2026-04-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.23.720371v1.full.pdf"
tags: ["query:ai"]
score: 8.0
evidence: 使用大语言模型自动生成生物医学库中的元数据
tldr: 评估大语言模型在科学数据库中自动提取元数据的能力，以促进科研发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 使用大语言模型自动生成生物医学库中的元数据。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## Abstract
ObjectiveHigh-quality metadata is essential for scientific discovery, yet sparse annotations in rapidly growing repositories leave many biologically relevant details uncaptured. We evaluated whether large language models (LLMs) can accurately infer ion channel and receptor subtype metadata from source code in a neuroscience repository.

Materials and MethodsWe extracted 5,133 model files from ModelDB. A subset of 1,100 was manually annotated; 253 were held out for testing, and the remainder split into training (80%) and validation (20%) sets. LLM-based approaches (GPT-5.2 and GPT-mini) were evaluated under zero-shot and heuristic-augmented prompting. Performance was assessed at type and subtype levels using accuracy, precision, recall, and F1 score. A feature-engineered XGBoost model using text- and simulation-derived features served as a baseline.

ResultsLLMs outperformed the XGBoost baseline. At the type level, GPT-mini with heuristic augmentation achieved the highest performance (accuracy 96.0%, F1 0.962). At the subtype level, both GPT-5.2+heuristics and GPT-mini+heuristics achieved identical accuracy (88.1%), with GPT-5.2+heuristics achieving the highest F1(0.878). Model outputs were consistent across runs and errors confined to related mechanistic families.

Discussion and ConclusionLLMs demonstrate strong potential for metadata annotation directly from source code, outperforming feature-engineering approaches with minimal tuning. However, performance varied across subtypes, and errors often reflected ambiguity or bias toward more common labels. These findings suggest LLMs may serve as practical tools for scalable metadata generation in biomedical repositories, although careful evaluation and domain-specific validation remain important. While demonstrated in computational neuroscience, this approach may generalize to repository-agnostic metadata annotation in other scientific code repositories.