---
title: "PixelDeck: A local-first media library manager for biomedical imaging"
authors: "Kidder, B. L."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.719925v1.full.pdf"
tags: ["query:ai"]
score: 8.5
evidence: 用于高效检索和组织的媒体库管理器
tldr: 介绍了PixelDeck，一个用于管理和搜索大型生物医学图像及视频库的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 用于高效检索和组织的媒体库管理器。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## Abstract
Modern biomedical imaging workflows generate large volumes of derived images and short videos that must be reviewed, compared, curated, and reused following primary acquisition and analysis. In practice, these assets are often dispersed across nested filesystem hierarchies on local drives, external media, or network storage, limiting efficient retrieval, deduplication, and figure assembly. We present PixelDeck, an open-source, local-first browser application for organizing and interactively browsing large biomedical image and video libraries on commodity workstations. PixelDeck integrates recursive folder import, SHA-256-based duplicate detection, metadata extraction, thumbnail and preview generation, full-text search, and asynchronous export within a responsive interface, supported by a modular ingestion pipeline, managed storage layer, and interactive browsing environment optimized for high-volume media collections. The system is implemented using a Next.js and React frontend, a SQLite metadata store accessed via Prisma, managed local media storage, and a background worker that executes import and export tasks asynchronously, enabling scalable processing on standard hardware. To evaluate performance, we conducted structured benchmark imports using public histopathology images curated from PanopTILs, SICAPv2, and PanNuke datasets, where dataset-specific import behavior, duplicate detection, and ingestion metrics were recorded as reproducible outputs. Embedding-based analysis further demonstrates dataset-level separation consistent with underlying image characteristics. These results show that PixelDeck provides an efficient, scalable local curation layer for heterogeneous biomedical imaging collections, enabling streamlined dataset exploration and preparation for downstream analysis.