---
title: "PixelDeck: A local-first media library manager for biomedical imaging"
title_zh: PixelDeck：面向生物医学成像的本地优先媒体库管理器
authors: "Kidder, B. L."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.719925v1.full.pdf"
tags: ["query:ai"]
score: 7.5
evidence: 用于生物医学图像检索和管理的媒体库管理器
tldr: PixelDeck是一款开源、本地优先的浏览器应用，用于管理生物医学图像和视频库。针对衍生图像分散存储导致的检索和去重效率低下的问题，它通过递归导入、SHA-256重复检测、元数据提取、预览生成和全文搜索等功能，在标准硬件上提供可扩展的媒体组织与交互浏览。该系统为异构生物医学图像集合提供了高效的本地管理工具，简化了数据探索和下游分析准备。
source: biorxiv
selection_source: fresh_fetch
motivation: 生物医学成像工作流产生大量衍生图像和视频，分散在不同存储中，导致检索、去重和组装效率低下。
method: 系统采用Next.js和React前端、SQLite元数据存储、本地媒体管理和后台异步任务处理，实现递归文件夹导入、重复检测、元数据提取、预览生成和全文搜索等功能。
result: 在公开组织病理学数据集上的基准测试显示，系统能有效处理导入、去重和嵌入分析，实现与图像特征一致的数据集级分离。
conclusion: PixelDeck为异构生物医学图像集提供了一个高效、可扩展的本地管理工具，简化了数据探索和下游分析准备。
---

## 摘要
现代生物医学成像工作流程会产生大量衍生图像和短视频，这些内容在初步采集和分析后需要被审阅、比较、整理和复用。实践中，这些资产常分散在本地驱动器、外部介质或网络存储的嵌套文件系统层级中，限制了高效检索、去重和图表组装。我们推出PixelDeck，一款开源、本地优先的浏览器应用程序，用于在商用工作站上组织和交互式浏览大型生物医学图像及视频库。PixelDeck集成了递归文件夹导入、基于SHA-256的重复检测、元数据提取、缩略图和预览生成、全文搜索以及响应式界面内的异步导出功能，其背后由模块化摄取管道、受管理的存储层以及针对海量媒体集合优化的交互式浏览环境提供支持。该系统采用Next.js和React前端、通过Prisma访问的SQLite元数据存储、受管理的本地媒体存储以及异步执行导入导出任务的背景工作器实现，从而在标准硬件上实现可扩展处理。为评估性能，我们使用从PanopTILs、SICAPv2和PanNuke数据集中整理的公开组织病理学图像进行了结构化基准导入，其中记录了数据集特定的导入行为、重复检测和摄取指标作为可复现输出。基于嵌入的分析进一步展示了与底层图像特征一致的数据集级分离。这些结果表明，PixelDeck为异构生物医学成像集合提供了一个高效、可扩展的本地整理层，能够简化数据集探索并为下游分析做好准备。

## Abstract
Modern biomedical imaging workflows generate large volumes of derived images and short videos that must be reviewed, compared, curated, and reused following primary acquisition and analysis. In practice, these assets are often dispersed across nested filesystem hierarchies on local drives, external media, or network storage, limiting efficient retrieval, deduplication, and figure assembly. We present PixelDeck, an open-source, local-first browser application for organizing and interactively browsing large biomedical image and video libraries on commodity workstations. PixelDeck integrates recursive folder import, SHA-256-based duplicate detection, metadata extraction, thumbnail and preview generation, full-text search, and asynchronous export within a responsive interface, supported by a modular ingestion pipeline, managed storage layer, and interactive browsing environment optimized for high-volume media collections. The system is implemented using a Next.js and React frontend, a SQLite metadata store accessed via Prisma, managed local media storage, and a background worker that executes import and export tasks asynchronously, enabling scalable processing on standard hardware. To evaluate performance, we conducted structured benchmark imports using public histopathology images curated from PanopTILs, SICAPv2, and PanNuke datasets, where dataset-specific import behavior, duplicate detection, and ingestion metrics were recorded as reproducible outputs. Embedding-based analysis further demonstrates dataset-level separation consistent with underlying image characteristics. These results show that PixelDeck provides an efficient, scalable local curation layer for heterogeneous biomedical imaging collections, enabling streamlined dataset exploration and preparation for downstream analysis.