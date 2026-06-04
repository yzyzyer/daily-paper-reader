---
title: Learning Dense Hand Contact Estimation from Imbalanced Data
title_zh: 从非平衡数据中学习密集手部接触估计
authors: "Daniel Sungho Jung, Kyoung Mu Lee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SAGZBti9lj"
tags: ["query:hoi"]
score: 8.0
evidence: 从非平衡数据中学习密集手部接触估计
tldr: 针对手部接触数据集中的类别不平衡和指尖空间不平衡两大挑战，提出一种有效学习密集手部接触估计的方法，通过设计特殊的采样和损失函数，利用现有多种接触数据集进行训练，能够准确预测手与物体、场景等的接触区域，为手物交互中的接触建模提供关键支撑，促进对手部功能的全面理解。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sagzbti9lj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 707, \"height\": 888, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sagzbti9lj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1422, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sagzbti9lj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 683, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sagzbti9lj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sagzbti9lj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sagzbti9lj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1469, \"height\": 2045, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sagzbti9lj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1469, \"height\": 2063, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sagzbti9lj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1431, \"height\": 1912, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sagzbti9lj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 1912, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sagzbti9lj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1438, \"height\": 1907, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1427, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 710, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 786, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1042, \"height\": 726, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 640, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 787, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 719, \"height\": 168, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 790, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 895, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1361, \"height\": 692, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1331, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1136, \"height\": 555, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 903, \"height\": 197, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sagzbti9lj/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1422, \"height\": 554, \"label\": \"Table\"}]"
motivation: 手部接触估计面临类别和空间不平衡两大挑战，影响学习效果。
method: 提出应对两类不平衡的训练策略和网络设计，充分利用现有接触数据集。
result: 在多个接触数据上取得准确密集接触图，有效改善手部功能理解。
conclusion: 该方法为手物交互中的接触估计提供了可行方案，促进了对手部功能的全面理解。
---

## Abstract
Hands are essential to human interaction, and exploring contact between hands and the world can promote comprehensive understanding of their function. Recently, there have been growing number of hand interaction datasets that cover interaction with object, other hand, scene, and body. Despite the significance of the task and increasing high-quality data, how to effectively learn dense hand contact estimation remains largely underexplored. There are two major challenges for learning dense hand contact estimation. First, there exists class imbalance issue from hand contact datasets where majority of regions are not in contact. Second, hand contact datasets contain spatial imbalance issue with most of hand contact exhibited in finger tips, resulting in challenges for generalization towards contacts in other hand regions. To tackle these issues, we present a framework that learns dense HAnd COntact estimation (HACO) from imbalanced data. To resolve the class imbalance issue, we introduce balanced contact sampling, which builds and samples from multiple sampling groups that fairly represent diverse contact statistics for both contact and non-contact vertices. Moreover, to address the spatial imbalance issue, we propose vertex-level class-balanced (VCB) loss, which incorporates spatially varying contact distribution by separately reweighting loss contribution of each vertex based on its contact frequency across dataset. As a result, we effectively learn to predict dense hand contact estimation with large-scale hand contact data without suffering from class and spatial imbalance issue. The codes are available at https://github.com/dqj5182/HACO_RELEASE.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

手部接触估计旨在从单张RGB图像中预测手部每个3D顶点的接触状态（接触/非接触）。该任务对于理解人机交互、机器人抓取、AR/VR等应用至关重要。近年来出现了大量手部交互数据集（如手-物、手-手、手-场景、手-身体），但两个关键挑战阻碍了有效的密集接触学习：

- **类别不平衡（Class Imbalance）**：大多数数据中，手部只有很小区域（如指尖）接触，绝大部分顶点处于非接触状态。例如InterHand2.6M数据集中非接触与接触顶点比例高达19.5:1。
- **空间不平衡（Spatial Imbalance）**：接触分布高度集中在指尖，其他区域（如手掌中心、手背）极少出现接触，导致模型泛化能力差。

现有方法多专注于人体-场景接触估计（如POSA、BSTRO、DECO），缺乏专门针对手部接触估计且处理不平衡数据的系统研究。本文提出HACO框架，首次在大规模混合数据集上学习密集手部接触估计，并通过平衡采样和顶点级损失函数解决上述不平衡问题。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 整体架构
输入图像经ViT骨干网络（初始化为HaMeR预训练权重）提取特征，经过自注意力和交叉注意力Transformer，结合一个可学习的接触token，最终通过线性层和sigmoid输出每个MANO顶点（V=778）的接触概率。

### 2.2 平衡接触采样（Balanced Contact Sampling, BCS）
为缓解类别不平衡，BCS构建多个采样桶，每个桶内的样本具有相似的接触平衡分数，该分数衡量每个样本的接触模式与数据集平均接触分布的偏差：
- 定义数据集平均接触向量 \(\bar{c}\)。
- 每个样本的平衡分数 \(s_i = \frac{1}{V} \left[ c_i^\top (1 - \bar{c}) - c_i^\top \bar{c} \right]\)，高分表示样本接触模式偏离平均。
- 采用对数间隔将分数范围划分为K个桶，使接触丰富的样本被精细分组。
- 训练时对每个桶进行分层重采样，确保每个桶对最终训练集贡献相同数量，从而提升接触正样本的代表性。

### 2.3 顶点级类别平衡损失（Vertex-Level Class-Balanced Loss, VCB Loss）
为处理空间不平衡，基于类平衡损失（CB Loss）扩展为顶点级别：
- 常规CB Loss对全局的接触/非接触类赋予不同权重，但忽略空间差异。
- VCB Loss为每个顶点v分别计算该类别的有效样本数 \(n_{y_v}\)，并据此得到权重 \(\alpha_{y_v} = \frac{1 - \beta}{1 - \beta^{n_{y_v}}}\)。
- 最终损失 \(L_{VCB} = \frac{1}{|V|}\sum_{v} \alpha_{y_v} \ell_{BCE}(y_v, p_v)\)。
- 训练前期使用全局CB Loss，后期逐渐增加VCB分量，实现平滑过渡。

### 2.4 其他损失
包括平滑损失（抑制孤立接触区域）和正则化损失（L1约束预测接近数据集平均接触），总损失权重分别为1、0.1、1。

## 3. 实验设计：数据集、评估基准、对比方法

### 3.1 数据集
使用14个公开数据集，涵盖五类交互：手-物（ObMan, DexYCB, MOW, HO3D, H2O3D, ARCTIC, HOI4D, H2O）、手-手（InterHand2.6M, HIC）、手-场景（PROX, RICH）、手-脸（Decaf）、手-身体（Hi4D）。总计约655K张图像，包含稠密接触标注（通过距离阈值生成，对部分数据集直接使用已有标注）。

### 3.2 评估指标
- 密集接触估计：精确率、召回率、F1分数（跳过完全无接触的样本）。
- 下游任务评估：
  - 3D手部抓取优化（ContactOpt）：交并体积、MPJPE、接触指标。
  - 3D手-物重建（EasyHOI）：MPVPE、MPJPE、Chamfer距离、F@5mm/F@10mm。

### 3.3 对比方法
- 密集接触估计：POSA、BSTRO、DECO（人体接触方法直接迁移）。
- 额外对比：将上述方法改为手部版本（替换为MANO模型）的变体，以及Decaf/CHOI/DICE等模块（部分复现）。
- 下游任务：ContactOpt（几何驱动）、EasyHOI（启发式接触区域）。

## 4. 资源与算力

论文明确指出：使用单张NVIDIA A6000 GPU，训练10个epoch，批量大小24，学习率 \(10^{-5}\)。骨干网络为ViT-H（约671M参数），训练显存约26GB，推理速度约54fps（完整模型）。附录提供了不同骨干的算力对比（如ResNet-18仅需3.8GB训练显存，111fps）。

## 5. 实验数量与充分性

论文进行了大量实验，主要涵盖：

- **消融实验**：
  - BCS有效性（提升Recall 12.0%，F1 8.5%）。
  - VCB损失对比CE、Focal、CB、LDAM、Asymmetric等多种损失，VCB取得最佳F1。
  - 不同训练数据配置（仅HS/HS+HH/…/全部14个数据集），验证各交互类型的贡献。
  - 训练数据规模（1、3、14个数据集）的影响。
  - 接触初始化方式对比。
  - 骨干网络对比（ViT、HRNet、ResNet等）。
- **与SOTA对比**：
  - 在MOW、HIC、RICH、Hi4D四个数据集上与POSA、BSTRO、DECO及其手部变体比较，HACO全面领先（MOW上F1从0.197（DECO）提升至0.522）。
  - 在DexYCB上优化抓取任务优于DeepContact。
  - 在MOW上改善EasyHOI重建的多个指标。
- **定性展示**：多场景接触预测可视化。
- **附录**：额外消融、不同骨干量化、计算需求表、局限性讨论。

实验覆盖了主要手部交互场景，对比方法包括基于不同模型家族的最先进方法，消融系统全面，公平性体现在：尽量使用相同训练数据重新训练对比方法（如手部变体），使用官方代码或复现。评估指标标准化。

## 6. 论文的主要结论与发现

- 所提HACO框架能有效学习密集手部接触，显著优于现有方法（F1得分在MOW上达到0.522，是DECO的2.6倍）。
- 平衡接触采样（BCS）有效缓解类别不平衡，尤其是提升召回率。
- 顶点级类别平衡损失（VCB Loss）优于全局级CB损失及其他不平衡处理方法，能更好地捕捉空间不平衡。
- 大规模多样化训练数据（14个数据集）对提升泛化能力至关重要。
- HACO在3D抓取优化和手物重建下游任务中也能带来改进，说明估计的接触信息质量高。

## 7. 优点：方法或实验设计上的亮点

- **问题定义新颖**：首次系统研究手部密集接触估计的两个不平衡问题，并给出专门解决方案。
- **方法设计精巧**：BCS通过平衡分数对样本分组，既保留接触多样性又缓解不平衡；VCB Loss将类平衡思想扩展到顶点级别，空间自适应。
- **实验规模大**：整合14个数据集，涵盖多种交互类型，体现数据的多样性。
- **公平性良好**：将基线改为手部版本重新训练，排除模型差异；对无开源方法进行复现。
- **下游应用验证**：不限于本任务评估，还验证了对实际下游任务（抓取优化、重建）的促进作用。
- **公开代码**：提供开源代码，促进可复现性。

## 8. 不足与局限

- **未处理自接触**：有意排除手-手自接触（如手指交叉），可能导致在包含自接触的场景中预测不准。
- **时序信息缺失**：未利用视频时序，而接触在动态中更易识别。
- **对数据分布敏感**：BCS基于单一数据集平均接触向量，若接触分布多模态，可能效果受限。
- **评估局限**：仅对至少有一个接触顶点的样本评测，忽略了全无接触样本上的假阳性问题。
- **手-手交互性能相对较低**：附录指出在手-手数据集（HIC）上F1仅0.263，仍有较大提升空间。
- **无误差棒**：未报告多次运行的标准差，置信度信息缺失。
- **部分数据集接触标注依赖距离阈值**：阈值手动设定，可能引入噪声；不同数据集阈值不统一（0.5cm~3.5cm）。

（完）
