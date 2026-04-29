---
title: "Multi-Agent Orchestration for Knowledge Extraction and Retrieval: AI Expert System for GPCRs"
title_zh: 面向知识提取与检索的多智能体编排系统：GPCR人工智能专家系统
authors: "spieser, j. C., Kogan, P., Yang, J., meller, j., Patra, K., shamsaei, B."
date: 2026-04-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.696782v1.full.pdf"
tags: ["query:sr-amcr"]
score: 8.5
evidence: 用于知识提取和检索的多智能体架构
tldr: 本研究提出了GPCR-Nexus，一个AI驱动的GPCR生物学集成探索平台。它通过多智能体架构，将结构化数据库与非结构化科学文献统一，结合知识图谱和语义检索，实现了基于可验证来源的上下文感知推理。该系统提高了GPCR知识获取的准确性、可解释性和覆盖范围，为GPCR研究和药物发现提供了可信赖的AI辅助知识合成基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决传统数据库查询和独立语言模型在GPCR知识整合中的局限性，实现可验证、全面的信息访问。
method: 采用多智能体架构，协调查询规划、证据检索、验证和合成，结合知识图谱和向量检索。
result: 通过代表性查询场景验证了平台在准确性、可解释性和覆盖范围上的改进。
conclusion: GPCR-Nexus为GPCR研究和药物发现提供了一个可扩展、可信赖的AI辅助知识合成平台。
---

## 摘要
我们推出GPCR-Nexus，这是一个用于整合探索G蛋白偶联受体（GPCR）生物学的AI驱动平台，它将结构化数据库与非结构化科学文献相统一。该系统结合了GPCR-配体知识图谱与基于向量的语义检索，以实现全面、最新的信息访问。GPCR-Nexus的核心是一个多智能体架构，其中专门组件协调查询规划、证据检索、验证与合成。这一设计确保生成的响应基于可验证的来源，同时保持跨异构数据模态的一致性。通过联合利用精选数据库和原始文献，GPCR-Nexus能够对分子相互作用、功能机制和疾病关联进行情境感知推理。该平台生成带有可追溯证据的引用支持输出，解决了传统数据库查询和独立语言模型的局限性。我们详细介绍了系统架构、数据集成策略和智能体编排框架，并通过代表性查询场景展示了其实用性。GPCR-Nexus提供了一种可扩展的方法，使用基于智能体的AI结合结构化和非结构化生物医学知识，从而提高了准确性、可解释性和覆盖范围。这项工作为GPCR研究和药物发现中可信赖的AI辅助知识合成奠定了基础。

## Abstract
We present GPCR-Nexus, an AI-driven platform for integrated exploration of G protein-coupled receptor (GPCR) biology that unifies structured databases with unstructured scientific literature. The system combines a GPCR-ligand knowledge graph with vector-based semantic retrieval to enable comprehensive, up-to-date information access. Central to GPCR-Nexus is a multi-agent architecture in which specialized components coordinate query planning, evidence retrieval, validation, and synthesis. This design ensures that generated responses are grounded in verifiable sources while maintaining coherence across heterogeneous data modalities. By jointly leveraging curated databases and primary literature, GPCR-Nexus enables context-aware reasoning over molecular interactions, functional mechanisms, and disease associations. The platform produces citation-backed outputs with traceable evidence, addressing limitations of conventional database queries and standalone language models. We detail the system architecture, data integration strategy, and agent orchestration framework, and demonstrate its utility through representative query scenarios. GPCR-Nexus provides a scalable approach to combining structured and unstructured biomedical knowledge using agent-based AI, offering improved accuracy, interpretability, and coverage. This work establishes a foundation for trustworthy, AI-assisted knowledge synthesis in GPCR research and drug discovery.