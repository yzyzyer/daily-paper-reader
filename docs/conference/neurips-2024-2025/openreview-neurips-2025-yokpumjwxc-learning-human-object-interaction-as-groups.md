---
title: Learning Human-Object Interaction as Groups
title_zh: 学习作为组群的人类-物体交互
authors: "Jiajun Hong, Jianan Wei, Wenguan Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yoKpumjWXc"
tags: ["query:hoi"]
score: 4.0
evidence: 人类-物体交互检测，通过组群上下文与HOI姿态估计相关
tldr: GroupHOI从组群视角重新建模人类-物体交互，超越传统成对关系。框架基于几何邻近性和语义进行上下文传播，能更准确检测多人多物情景中的交互关系。虽然侧重检测而非姿态估计，但其对交互结构的理解可为手物交互姿态估计提供上下文线索。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yokpumjwxc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yokpumjwxc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1435, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yokpumjwxc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 998, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yokpumjwxc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1384, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yokpumjwxc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1488, \"height\": 1973, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yokpumjwxc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1490, \"height\": 1087, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yokpumjwxc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1414, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yokpumjwxc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1421, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yokpumjwxc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yokpumjwxc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 694, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yokpumjwxc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 734, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yokpumjwxc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1438, \"height\": 646, \"label\": \"Table\"}]"
motivation: 现有HOI检测仅关注成对关系，忽略了真实场景中多人多物共同参与的集体行为。
method: 提出GroupHOI框架，从组群角度传播信息，利用几何和语义聚类聚合上下文。
result: 在多个HOI检测基准上超越现有方法，尤其在复杂多交互场景中提升显著。
conclusion: 组群建模更贴近真实交互，为HOI理解提供新范式。
---

## Abstract
Human-Object Interaction Detection (HOI-DET) aims to localize human-object pairs and identify their interactive relationships. To aggregate contextual cues, existing methods typically propagate information across all detected entities via self‑attention mechanisms, or establish message passing between humans and objects with  bipartite graphs. However, they primarily focus on pairwise relationships, overlooking that interactions in real-world scenarios often emerge from collective behaviors ($\textit{i}.\textit{e}.$, multiple humans and objects engaging in joint activities). In light of this, we revisit relation modeling from a $\textit{group}$ view and propose GroupHOI, a framework that propagates contextual information in terms of $\textit{geometric proximity}$ and $\textit{semantic similarity}$. To exploit the geometric proximity, humans and objects are grouped into distinct clusters using a learnable proximity estimator based on spatial features derived from bounding boxes. In each group, a soft correspondence is computed via self-attention to aggregate and dispatch contextual cues. To incorporate the semantic similarity, we enhance the vanilla transformer-based interaction decoder with local contextual  cues from HO-pair features. Extensive experiments on HICO-DET and V-COCO benchmarks demonstrate the superiority of GroupHOI over the state-of-the-art methods. It also exhibits leading performance on the more challenging Nonverbal Interaction Detection (NVI-DET) task, which involves varied forms of higher-order interactions within groups.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **现有方法局限**：当前主流的人类-物体交互检测（HOI-DET）方法主要关注成对关系，通过全局自注意力或二分图在检测实体间传播信息，忽略了真实场景中常见的集体行为——即多人多物共同参与的组群交互。
- **研究动机**：从组群视角重新审视关系建模，受Gestalt心理学中**邻近性**和**相似性**原则启发，认为实体在空间上邻近或视觉语义上相似时会自然形成组群，组群内部存在更紧密的交互关联。
- **整体含义**：提出GroupHOI框架，通过学习实体间的几何组和语义组，实现更结构化和上下文感知的交互推理，从而提升HOI检测的准确性和可解释性。

## 2. 论文提出的方法论

### 核心思想
- 放弃传统的完全连接图或二分图，转而利用**几何邻近性**和**语义相似性**两种原则构建分组，在组内进行局部上下文聚合与分发。
- 方法构建于DETR架构之上，包含三个关键模块：视觉编码器+实例解码器、几何感知局部Transformer、语义感知交互解码器。

### 关键技术细节

#### 几何组（Geometric Group）
- **构建**：对每个实体（人类或物体）的边界框，提取空间特征 \( f_{i,j} = [\text{dis}_{i,j}, \text{IoU}_{i,j}] \)，通过线性层计算邻近分数，为每个实体选取 \( K_g \) 个最近邻居形成几何邻居集 \( \mathcal{N}^g_i \)。
- **上下文聚合与分发**：引入参数化位置编码 \( p_{i,j} = \delta(q_i - q_j) \)，计算分发矩阵 \( t_{i,j} = \text{Softmax}(\gamma(\phi_1(q_i) - \phi_2(q_j) + p_{i,j})) \)，然后聚合上下文更新实体嵌入：
  \[
  \tilde{q}_i = \theta\left(\sum_{j \in \mathcal{N}^g_i} g_{i,j} \odot (\phi_3(q_j) + p_{i,j})\right) + q_i
  \]
  该过程在同类实体（human-human, object-object）间进行。

#### 语义组（Semantic Group）
- **构建**：初始化交互查询 \( Q_{int} = \text{mean}(\tilde{Q}_h, \tilde{Q}_o) \)，计算查询间的余弦相似度，为每个查询选取 \( K_s \) 个最相似的交互查询组成语义邻居集 \( \mathcal{N}^s_i \)。
- **语义上下文聚合**：使用最大池化聚合组内消息：
  \[
  m_i = \max\left( \phi_4(q_i, q_j - q_i) \right), \quad q_j \in \mathcal{N}^s_i
  \]
- **局部-全局集成**：将聚合的语义上下文通过残差连接注入Transformer交互解码器的自注意力层之前：
  \[
  \hat{q}_i = q_i + \phi_5(m_i)
  \]
  随后经过标准的自注意力和交叉注意力模块。

### 总损失函数
\[
\mathcal{L}_{HOI} = \lambda_b \mathcal{L}_b + \lambda_u \mathcal{L}_u + \lambda_{oc} \mathcal{L}_{oc} + \lambda_{ac} \mathcal{L}_{ac}
\]
其中 \( \mathcal{L}_b \) 为边界框回归损失，\( \mathcal{L}_u \) 为IoU损失，\( \mathcal{L}_{oc} \) 和 \( \mathcal{L}_{ac} \) 分别为物体和交互分类的交叉熵损失。

## 3. 实验设计

### 使用的数据集与Benchmark
- **HICO-DET**：47,776张图像（训练38,118，测试9,658），600种HOI类别，117种动作，80种物体。评估指标为mAP（Full / Rare / Non-Rare）。
- **V-COCO**：10,346张图像（训练5,400，测试4,946），263种交互，29种动作。评估指标为mAP（场景1和场景2）。
- **NVI-DET**（非语言交互检测）：13,711张图像（训练9,634，验证1,418，测试2,659），22种原子级非语言行为（个人和组群类别）。使用平均Recall@K（mR@25/50/100）及AR。

### 对比方法
- 主流HOI-DET方法：QPIC、CDN、MSTR、STIP、Pose-Aware、HOICLIP、GEN-VLKT、CMMP、ViPLO等。
- NVI-DET对比：m-QPIC、m-CDN、m-GEN-VLKT、NVI-DEHR。
- 消融实验：对比几何组与语义组单独作用、组大小、融合策略（同质vs异质）、组层数等。

## 4. 资源与算力

- **硬件**：2张 GeForce RTX 4090 GPU。
- **训练配置**：batchsize = 8，训练90个epoch。
- **优化器**：AdamW，初始学习率5e-5，每30 epoch衰减10倍。
- **骨干网络**：ResNet-50，部分实验结合CLIP（ViT-B/16、ViT-L/14）或BLIP2（ViT-L）预训练模型。
- **模型规模**：GroupHOI（R50）参数79.2M，FLOPs 83.67G，推理速度16.42 FPS。

## 5. 实验数量与充分性

- **主实验**：① HICO-DET上与18种方法对比；② V-COCO上与16种方法对比；③ NVI-DET上与4种方法对比（Table 1-3）。
- **消融实验**：Table 4 涵盖了6项消融分析（关键模块、几何组大小、语义组大小、融合策略同质vs异质、几何组层数、语义组层数）。
- **效率对比**：Table 5 比较参数量、FLOPs、FPS。
- **附加实验**：附录中补充了几何邻近性测量策略对比（Table S1）和更全面的效率对比（Table S2）。
- **充分性与公平性**：实验覆盖三个数据集、多种评估设置、多种骨干与VLMs；消融设计完整，控制变量；与现有方法在相同骨干和条件下比较，实验客观公平。

## 6. 论文的主要结论与发现

- GroupHOI在HICO-DET上以R50+CLIP/B16达到36.70 mAP（Full），超过之前SOTA（Pose-Aware）0.84 mAP；在V-COCO上达到65.0 mAP。使用更强VLM后持续领先。
- 在NVI-DET上，GroupHOI在验证集和测试集分别取得73.19 AR和75.21 AR，超过所有对比方法，尤其在组群交互上优势显著。
- 消融实验证实：几何组和语义组各自贡献性能提升，两者结合最优；同质（homogeneous）分组策略优于异质（heterogeneous）；组大小存在最佳值（几何组4、语义组2）；在解码器多层独立构建分组效果更好。
- 可视化显示几何组能聚集空间邻近实体，语义组能聚集执行相同交互的实体，增强了模型可解释性。

## 7. 优点

- **创新视角**：首次从组群角度建模HOI，引入Gestalt邻近性与相似性原则，突破了传统成对关系的局限。
- **设计简洁有效**：基于可学习邻近估计和自注意力的局部聚合，额外计算开销小（FLOPs低于HOICLIP），性能提升显著。
- **强泛化能力**：在标准HOI数据和更复杂的NVI组群交互数据上均达SOTA，验证了方法的通用性。
- **可解释性**：通过可视化分组结果，直观展示模型如何组织实体和交互，有助于理解推理过程。
- **消融充分**：对关键组件、超参数、层数等进行了系统分析，提供了深入的设计洞察。

## 8. 不足与局限

- **未集成检测分支**：当前分组机制仅作用于交互推理部分，未应用于物体检测阶段，限制了潜在提升。
- **标签多样性有限**：训练数据仍集中于室内/常见场景，对开放世界或极端场景泛化能力不足。
- **失败案例**：严重遮挡、模糊交互（如注视方向）、缺乏领域知识（如篮球规则）导致误检；分组可能引入无关上下文噪声，产生“幻觉”预测。
- **潜在偏见风险**：组级聚类可能放大系统性偏差，需引入公平性约束避免不公平分组。
- **计算资源未充分提及**：论文仅给出训练GPU型号和时长，未报告总训练时间或单卡耗时。

（完）
