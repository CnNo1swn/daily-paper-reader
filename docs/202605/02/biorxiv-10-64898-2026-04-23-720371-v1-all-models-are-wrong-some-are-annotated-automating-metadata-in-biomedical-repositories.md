---
title: "All Models are Wrong, Some are Annotated: Automating Metadata in Biomedical Repositories"
title_zh: 所有模型皆有误，部分已标注：生物医学知识库中的元数据自动化
authors: "Cohen, I., Yu, H., McDougal, R. A."
date: 2026-04-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.23.720371v1.full.pdf"
tags: ["query:ai"]
score: 8.0
evidence: 使用大语言模型在知识库中自动推断元数据
tldr: 针对生物医学知识库中元数据标注稀疏的问题，本研究评估了大语言模型从神经科学知识库ModelDB的源代码中自动推断离子通道和受体亚型元数据的能力。通过手动标注数据集，比较了GPT系列模型与XGBoost基线的性能。结果表明，大语言模型在类型和亚型分类上均优于传统特征工程方法，准确率高且错误多局限于相关类别，展现了其作为可扩展元数据生成工具的潜力。
source: biorxiv
selection_source: fresh_fetch
motivation: 生物医学知识库中元数据标注稀疏，影响科学发现，需自动从源代码推断元数据。
method: 从ModelDB提取模型文件，手动标注子集，使用GPT系列模型进行零样本和启发式增强提示，并与XGBoost基线比较。
result: "大语言模型在类型和亚型级别均优于XGBoost基线，最佳准确率分别达96.0%和88.1%，错误多局限于相关机制家族。"
conclusion: 研究表明，大语言模型可作为生物医学知识库中可扩展的元数据生成实用工具，但需谨慎评估和领域验证。
---

## 摘要
目的：高质量的元数据对科学发现至关重要，然而快速增长的知识库中稀疏的标注导致许多生物学相关细节未被捕获。我们评估了大型语言模型（LLMs）能否从神经科学知识库的源代码中准确推断离子通道和受体亚型的元数据。

材料与方法：我们从ModelDB中提取了5,133个模型文件。其中1,100个文件子集进行了人工标注；253个留作测试，其余分为训练集（80%）和验证集（20%）。基于LLM的方法（GPT-5.2和GPT-mini）在零样本和启发式增强提示下进行评估。使用准确率、精确率、召回率和F1分数在类型和亚型水平评估性能。使用基于文本和模拟衍生特征进行特征工程的XGBoost模型作为基线。

结果：LLMs的表现优于XGBoost基线。在类型水平上，采用启发式增强的GPT-mini实现了最高性能（准确率96.0%，F1分数0.962）。在亚型水平上，GPT-5.2+启发式和GPT-mini+启发式均达到了相同的准确率（88.1%），其中GPT-5.2+启发式获得了最高的F1分数（0.878）。模型输出在不同运行中保持一致，错误仅限于相关的机制家族。

讨论与结论：LLMs直接从源代码进行元数据标注显示出强大潜力，在最小调优的情况下优于特征工程方法。然而，不同亚型的性能存在差异，错误通常反映了模糊性或对更常见标签的偏向。这些发现表明，LLMs可能作为生物医学知识库中可扩展元数据生成的实用工具，尽管仔细评估和特定领域的验证仍然重要。虽然该方法在计算神经科学中得到了演示，但它可能推广到其他科学代码库中与知识库无关的元数据标注。

## Abstract
ObjectiveHigh-quality metadata is essential for scientific discovery, yet sparse annotations in rapidly growing repositories leave many biologically relevant details uncaptured. We evaluated whether large language models (LLMs) can accurately infer ion channel and receptor subtype metadata from source code in a neuroscience repository.

Materials and MethodsWe extracted 5,133 model files from ModelDB. A subset of 1,100 was manually annotated; 253 were held out for testing, and the remainder split into training (80%) and validation (20%) sets. LLM-based approaches (GPT-5.2 and GPT-mini) were evaluated under zero-shot and heuristic-augmented prompting. Performance was assessed at type and subtype levels using accuracy, precision, recall, and F1 score. A feature-engineered XGBoost model using text- and simulation-derived features served as a baseline.

ResultsLLMs outperformed the XGBoost baseline. At the type level, GPT-mini with heuristic augmentation achieved the highest performance (accuracy 96.0%, F1 0.962). At the subtype level, both GPT-5.2+heuristics and GPT-mini+heuristics achieved identical accuracy (88.1%), with GPT-5.2+heuristics achieving the highest F1(0.878). Model outputs were consistent across runs and errors confined to related mechanistic families.

Discussion and ConclusionLLMs demonstrate strong potential for metadata annotation directly from source code, outperforming feature-engineering approaches with minimal tuning. However, performance varied across subtypes, and errors often reflected ambiguity or bias toward more common labels. These findings suggest LLMs may serve as practical tools for scalable metadata generation in biomedical repositories, although careful evaluation and domain-specific validation remain important. While demonstrated in computational neuroscience, this approach may generalize to repository-agnostic metadata annotation in other scientific code repositories.

---

## 论文详细总结（自动生成）

### 论文总结：*All Models are Wrong, Some are Annotated: Automating Metadata in Biomedical Repositories*

#### 1. 核心问题与整体含义
*   **核心问题**：生物医学知识库（如神经科学模型库ModelDB）中，模型文件的元数据（如离子通道、受体类型）标注严重稀疏且不一致，这极大地阻碍了基于这些知识库的科学发现与模型复用。
*   **研究动机**：传统手动标注方法成本高昂、难以扩展。本研究旨在探索利用大语言模型（LLM）直接从模型源代码中自动、准确地推断元数据的可行性，以解决知识库增长的“标注瓶颈”问题。

#### 2. 方法论
*   **核心思想**：将元数据推断视为一个基于源代码文本的分类任务，直接利用LLM强大的代码理解和上下文学习能力，避免复杂的特征工程。
*   **关键技术细节**：
    *   **输入**：神经科学模型（NEURON/Python）的完整源代码文件。
    *   **任务**：两级分类：1) **类型**（如电压门控离子通道、配体门控离子通道）；2) **亚型**（如具体的钠通道、AMPA受体等）。
    *   **LLM方法**：
        *   **零样本提示**：直接要求LLM根据代码内容进行分类。
        *   **启发式增强提示**：在提示中整合领域知识启发式规则（例如，特定离子电流命名惯例）。
    *   **基线方法**：使用**XGBoost**模型，但需要复杂的**特征工程**，包括从代码中提取的关键词、模拟参数（如时间常数、反转电位）等作为输入特征。

#### 3. 实验设计
*   **数据集**：从ModelDB中提取5，133个计算神经科学模型文件。对其中的1，100个进行了**手动标注**，构成黄金标准数据集。
*   **数据划分**：253个文件作为测试集；其余847个文件按80%/20%划分为训练集和验证集（**仅用于XGBoost模型训练与调参**，LLM无需训练）。
*   **Benchmark（评估指标）**：准确率、精确率、召回率、F1分数。
*   **对比方法**：
    *   **主要对比**：不同配置的LLM（GPT-5.2， GPT-mini）在零样本与启发式增强提示下的表现。
    *   **基线对比**：基于特征工程的XGBoost模型。

#### 4. 资源与算力
*   论文中**未明确说明**具体的硬件配置（如GPU型号、数量）或算力消耗。
*   本研究采用的LLM（如GPT-5.2， GPT-mini）为通过API调用的闭源模型，因此实验的算力成本主要集中于API调用，而非本地训练。XGBoost模型的训练在常规计算资源上即可完成。

#### 5. 实验数量与充分性
*   **实验设置**：实验设计清晰，主要围绕两个分类任务（类型、亚型）展开，比较了**2种LLM x 2种提示策略（零样本、启发式增强）** 共4种LLM配置，并与1个强特征工程基线（XGBoost）进行对比。
*   **充分性与客观性**：
    *   **充分性较高**：涵盖了从简单到增强的LLM使用方式，并与需要大量人工特征工程的传统机器学习方法进行了公平对比。
    *   **客观公平**：使用同一手动标注的测试集进行评估；LLM方法未使用训练集进行微调，与XGBoost使用训练集的情况不同，但这正凸显了LLM“开箱即用”的优势。实验关注了模型错误的具体模式（如混淆相近亚型），分析较为客观。

#### 6. 主要结论与发现
*   **性能优越**：LLM在无需特定训练的情况下，在类型和亚型分类任务上均**显著优于**需要特征工程的XGBoost基线模型。
*   **最佳结果**：
    *   **类型分类**：GPT-mini + 启发式增强达到最佳（准确率96.0%， F1 0.962）。
    *   **亚型分类**：GPT-5.2 + 启发式增强达到最佳（准确率88.1%， F1 0.878）。
*   **错误模式**：LLM的错误大多局限于相关机制家族内（例如，混淆不同类型的钠通道），表明其理解具有语义合理性，而非随机错误。
*   **核心结论**：LLM展现出作为生物医学知识库中**可扩展元数据自动生成工具**的强大潜力，能够有效缓解标注稀疏问题。

#### 7. 优点
*   **方法创新**：开创性地将LLM直接应用于科学代码库的元数据推断任务，流程简单，避免了繁琐且领域依赖强的特征工程。
*   **实用性强**：采用“提示工程”而非“模型微调”，使得方法易于复现和推广到其他科学代码仓库。
*   **分析深入**：不仅报告性能指标，还深入分析了错误案例，指出错误多源于标注模糊性或模型对常见标签的偏好，为后续改进提供了方向。

#### 8. 不足与局限
*   **领域依赖风险**：提示中使用的启发式规则依赖于神经科学领域的先验知识，将该方法迁移到全新领域时可能需要重新设计提示。
*   **LLM固有偏差**：模型的性能可能受其训练数据中不同生物实体分布偏差的影响（例如，更常见的亚型被更频繁地预测）。
*   **“黑箱”性质**：LLM的决策过程不透明，在要求高可解释性的科学场景中可能是一个短板。
*   **泛化能力待验证**：研究仅在计算神经科学的ModelDB上进行验证，在其他生物医学或科学代码库（如生物信息学工具库）上的有效性仍需进一步测试。
*   **成本考量**：大规模调用商用LLM API会产生持续成本，而开源模型的能力是否足以媲美尚未知。

（完）
