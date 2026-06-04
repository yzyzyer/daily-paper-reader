---
title: "Hamba: Single-view 3D Hand Reconstruction with Graph-guided Bi-Scanning Mamba"
title_zh: Hamba：基于图引导双向扫描Mamba的单视图3D手部重建
authors: "Haoye Dong, Aviral Chharia, Wenbo Gou, Francisco Vicente Carrasco, Fernando De la Torre"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=pCJ0l1JVUX"
tags: ["query:hoi"]
score: 8.0
evidence: 单视图3D手部重建，考虑物体交互
tldr: 针对单目3D手部重建中关节空间关系建模效率低的问题，提出图引导的Mamba框架Hamba，创新地将Mamba扫描重构为图引导的双向扫描，仅用少量token便高效学习关节间空间关系，在多个基准数据集上取得最先进的重建精度，尤其在严重遮挡和物体交互场景中表现突出，为手物交互中的手部姿态估计提供了强大工具。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 1370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1259, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1366, \"height\": 756, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1241, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1435, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1424, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1450, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1435, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1448, \"height\": 2092, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1422, \"height\": 2034, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-pcj0l1jvux/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1426, \"height\": 2039, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-pcj0l1jvux/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 888, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-pcj0l1jvux/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-pcj0l1jvux/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 707, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-pcj0l1jvux/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 895, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-pcj0l1jvux/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1458, \"height\": 691, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-pcj0l1jvux/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-pcj0l1jvux/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-pcj0l1jvux/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1012, \"height\": 144, \"label\": \"Table\"}]"
motivation: 现有方法未能有效建模关节间的空间关系，导致重建精度受限。
method: 提出图引导的Mamba框架，将Mamba扫描重构为图引导的双向扫描，用少量token学习关节空间关系。
result: 在多个基准上取得最先进的重建精度，尤其在遮挡和交互场景中表现优异。
conclusion: Hamba验证了图学习与状态空间模型结合在3D手部重建中的有效性，为手物交互任务奠定基础。
---

## Abstract
3D Hand reconstruction from a single RGB image is challenging due to the articulated motion, self-occlusion, and interaction with objects. Existing SOTA methods employ attention-based transformers to learn the 3D hand pose and shape, yet they do not fully achieve robust and accurate performance, primarily due to inefficiently modeling spatial relations between joints. To address this problem, we propose a novel graph-guided Mamba framework, named Hamba, which bridges graph learning and state space modeling. Our core idea is to reformulate Mamba's scanning into graph-guided bidirectional scanning for 3D reconstruction using a few effective tokens. This enables us to efficiently learn the spatial relationships between joints for improving reconstruction performance. Specifically, we design a Graph-guided State Space (GSS) block that learns the graph-structured relations and spatial sequences of joints and uses 88.5\% fewer tokens than attention-based methods. Additionally, we integrate the state space features and the global features using a fusion module. By utilizing the GSS block and the fusion module, Hamba effectively leverages the graph-guided state space features and jointly considers global and local features to improve performance. Experiments on several benchmarks and in-the-wild tests demonstrate that Hamba significantly outperforms existing SOTAs, achieving the PA-MPVPE of 5.3mm and F@15mm of 0.992 on FreiHAND. At the time of this paper's acceptance, Hamba holds the top position, Rank 1, in two competition leaderboards on 3D hand reconstruction.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：从单张RGB图像中重建3D手部网格是一项挑战性任务，主要难点在于手部的关节运动、严重自遮挡以及与物体的交互。现有最先进方法主要基于注意力机制的Transformer，但它们在真实复杂场景（如遮挡、截断、手-手或手-物交互）中仍不够鲁棒和精确。
- **核心问题**：现有方法未能有效建模手部关节之间的空间关系。Transformer需要大量token进行重建，注意力机制计算所有patch间的相关性，引入了不必要的背景噪声，且不能高效建模关节空间序列。
- **本文目标**：提出一种新框架，利用图学习（Graph Learning）和状态空间模型（State Space Model, SSM）——即Mamba，来高效学习关节间的空间关系，从而提升3D手部重建的鲁棒性和精度。

## 2. 论文提出的方法论

### 2.1 核心思想
- 将Mamba的扫描（scanning）重构为**图引导的双向扫描（Graph-guided Bidirectional Scan, GBS）**，仅使用少量有效token（21个关节token+1个全局均值token，共22个，相比注意力方法减少约88.5%）来重建3D手部。
- 设计了**图引导状态空间（Graph-guided State Space, GSS）块**，结合图卷积（GCN）和Mamba块（SS2D），同时学习关节的图结构关系和空间序列。

### 2.2 关键技术细节
- **整体架构**：输入图像 → ViT-H骨干网络提取token → 下采样 → 关节回归器（JR）预测初始2D关节 → Token采样器（TS）根据2D关节位置进行双线性插值采样得到21个有效token → 多个GSS块处理 → 融合模块将GSS token、全局均值token、2D关节特征和采样token融合 → MLP回归MANO参数（姿态θ、形状β、相机π）。
- **Token Sampler (TS)**：利用JR预测的2D关节位置，用`grid_sample`从下采样后的feature map中采样21个token，避免背景干扰。
- **Joint Regressor (JR)**：由4个VSSM（SS2D）块和MLP组成，预测初始MANO参数，并通过投影得到2D关节。
- **Graph-guided State Space (GSS) Block**：每个GSS块内，首先对21个关节token进行图卷积（GCN），使用学习到的权重矩阵和预定义的骨架邻接矩阵捕获关节间拓扑关系；然后将GCN输出与全局均值token（从下采样图像token平均得到）拼接，送入SS2D块（双向扫描），再经过层归一化和FFN，最后残差连接。后续GSS块中，输入来自上一块的输出，并分割后仅关节部分进入GCN。
- **融合模块**：将GSS token、TS采样token、2D关节特征和全局均值token拼接后输入MLP。
- **损失函数**：综合L1损失（2D/3D关节）、L2损失（MANO参数）和对抗损失（防止不合理手势）。

### 2.3 公式与算法流程（文字说明）
- 状态空间模型（S6）的连续离散化：使用零阶保持（ZOH）将连续微分方程离散化，得到递推形式。
- 图卷积操作：`TGCN = σ(W * T * P_i(M ⊙ G))`，其中M是可学习权重矩阵，G是邻接矩阵，⊙是逐元素乘，P_i是softmax归一化。
- 算法步骤：输入token → TS采样 → 循环L次：GCN → 拼接均值token → SS2D → 残差 → LN+FFN → 残差 → 分割 → 输出GSS token。

## 3. 实验设计

- **使用数据集**：
  - 训练集：约2.7M样本，混合自FreiHAND、HO3Dv2/v3、MTC、RHD、InterHand2.6M、H2O3D、DexYCB、COCO-Wholebody、Halpe、MPII NZSL等。采样权重参照HaMeR。
  - 测试基准：FreiHAND（132K训练/4K测试）、HO3Dv2（~70K训练/10K测试）、HO3Dv3（>103K训练/20K测试）、HInt（NewDays、EpicKitchensVISOR、Ego4D，仅2D关键点，不用于训练）。
- **评估指标**：PA-MPJPE、PA-MPVPE、F@5mm、F@15mm、AUC_J、AUC_V、PCK（用于HInt）。
- **对比方法**：
  - 基于FreiHAND训练：METRO、MeshGraphormer、MobRecon、SimpleHand、HHMR等。
  - 与HaMeR公平比较（相同训练集）：使用HaMeR的相同数据混合，包括HaMeR、HaMeR-170k。
  - 在HO3Dv2/v3上对比：ObMan、Pose2Mesh、I2L-MeshNet、HandOccNet、HFL-Net、H2ONet、HandBooster等。
  - 在HInt上对比：METRO、FrankMocap、MeshGraphormer、HandOccNet、HaMeR等。

## 4. 资源与算力

- **关节回归器（JR）训练**：单张NVIDIA A4500 GPU，batch size 8，训练1M steps，耗时5天，需约300GB RAM。
- **完整模型（Hamba）训练**：两张NVIDIA A6000 GPU，batch size 56，训练170k steps，耗时2天。使用AdamW优化器，学习率1e-5，权重衰减1e-4。
- **ViT骨干网络**：使用HaMeR发布的ViT-H检查点初始化，全程保持未冻结。
- 消融实验（用于快速验证）在单台GPU上运行60k steps。

## 5. 实验数量与充分性

- **主要实验**：
  - 在FreiHAND、HO3Dv2、HO3Dv3上报告定量结果（表1、2、3），均与多个SOTA比较。
  - 在HInt数据集上评估跨数据集泛化能力（表5），区分所有关节、可见关节、遮挡关节，并全部优于HaMeR。
  - 提供定性比较（图5、S5-S7），展示在遮挡、截断、物体交互等复杂场景下的视觉优势。
  - 消融实验（表4）：共9组，包括分支级（移除Token_Sampler_Branch、2D_Joints_Feature_Branch、GSS_Token_Branch、Global_Mean_Token_Branch）和组件级（移除Token_Sampler、Bidirectional_Scan、GCN、Graph-guided_Bi_scan、Mamba块），验证每个组件的贡献。
  - 额外消融（表S1）：GCN+SS2D vs GCN+Attention，证明SS2D更优。
  - 效率对比（表S2）：token数、参数量、FLOPs、推理时间、GPU内存，表明Hamba更轻量快速。
  - 迁移实验（表S3）：将GSS块用于人体网格恢复任务（3DPW、LSP-Ext、COCO），达到与4D-Humans（HMR2.0b）相当或更好的性能。
- **充分性与客观性**：实验覆盖多种基准（室内受控和真实野外）、多个指标、公平对比（相同训练集、有无TTA），消融设计全面，结论可靠。但部分数据集（HO3Dv2/v3）通过Codalab在线评估，未开放GT，因此无法提供误差棒，但符合领域惯例。

## 6. 论文的主要结论与发现

- **主要结论**：Hamba在所有基准上均显著超越现有SOTA。例如在FreiHAND上，不使用TTA时PA-MPVPE为5.5mm，F@15mm为0.991；使用TTA后PA-MPVPE达5.3mm，F@15mm达0.992（排名第一）。在HO3Dv2/v3上同样取得最优。
- **关键发现**：图引导的双向扫描（GBS）能有效捕获手部关节的空间关系，GSS块（GCN+SS2D）缺一不可；使用少量token（22个）即可高效重建，比注意力方法减少88.5% token，同时更轻量（参数减少51.8%，FLOPs减少6%，GPU内存减少83.7%）。
- **泛化能力**：在未参与训练的HInt数据集上，Hamba在所有子集和指标上超过HaMeR，证明其鲁棒性。
- **可迁移性**：GSS块可作为即插即用模块用于其他3D重建任务（如人体网格恢复），性能与专用模型相当。

## 7. 优点

- **方法论创新**：首次将Mamba（状态空间模型）与图学习结合应用于3D手部重建，提出了图引导双向扫描（GBS）和GSS块，高效建模关节空间关系。
- **效率优势**：使用极少token（22个），大幅减少计算量和内存消耗，同时保持甚至提升精度。
- **鲁棒性强**：在严重遮挡、截断、手-物/手-手交互等复杂野外场景中表现优异，显著优于现有基于Transformer的方法。
- **实验充分**：在多个基准（FreiHAND、HO3Dv2/v3、HInt）上全面评估，包括定量、定性、消融、效率、迁移等，验证了每个组件的必要性。
- **公开性好**：代码已开源（提供GitHub链接），利于复现与后续研究。
- **实际贡献**：在HO3Dv2和HO3Dv3的Codalab排行榜上取得Rank 1。

## 8. 不足与局限

- **视频时序信息未利用**：当前模型仅处理单帧图像，未探索视频中的时序特征，受限于难以获取大规模视频3D标注数据。
- **训练数据偏差**：约95%训练数据来自室内受控环境（如工作室、多相机设置），尽管使用HInt验证了泛化性，但可能仍不足以完全覆盖所有真实野外场景。
- **潜在的隐私风险**：3D手部重建技术可能被用于未授权的监控或隐私侵犯，作者在论文中已提及此消极影响，但未提出具体缓解措施。
- **实验统计信息缺失**：由于部分排行榜仅提供最终分数，未报告误差棒或置信区间，尽管这符合领域惯例，但缺乏不确定性量化。
- **失败案例分析**：附录中展示了若干失败案例（如错误手掌朝向、运动模糊导致的手指缺失等），表明模型在极端模糊或复杂手势下仍有改进空间。
- **资源需求**：完整模型训练需两张A6000 GPU约2天，JR训练需单张A4500 GPU 5天，虽然比同类方法高效，但仍有较高计算门槛。

（完）
