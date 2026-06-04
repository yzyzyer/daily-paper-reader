---
title: Towards Dynamic 3D Reconstruction of Hand-Instrument Interaction in Ophthalmic Surgery
title_zh: 面向眼科手术中手-器械交互的动态3D重建
authors: "Ming Hu, Zhengdi Yu, Feilong Tang, Kaiwen Chen, Yulong Li, Imran Razzak, Junjun He, Tolga Birdal, Kaijing Zhou, Zongyuan Ge"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=pOJBw1YQgL"
tags: ["query:hoi"]
score: 9.0
evidence: 手-器械交互3D重建，包含手部网格和器械姿态
tldr: 针对眼科显微手术中手-器械交互3D重建缺乏数据集的问题，本文提出OphNet-3D，包含41个序列、710万帧，标注了手部MANO网格和6D器械姿态。设计多阶段自动标注流程，利用多视图数据、运动先验和几何约束生成高精度标签。该数据集将推动手术场景中手物交互的研究。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1460, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 802, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 664, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1381, \"height\": 892, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1227, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1448, \"height\": 2156, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1448, \"height\": 2170, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1457, \"height\": 1591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1454, \"height\": 1612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1444, \"height\": 1641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1446, \"height\": 1634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1452, \"height\": 2447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pojbw1yqgl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1452, \"height\": 1246, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pojbw1yqgl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pojbw1yqgl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 801, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pojbw1yqgl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pojbw1yqgl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1388, \"height\": 820, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pojbw1yqgl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1386, \"height\": 780, \"label\": \"Table\"}]"
motivation: 眼科手术中缺乏大规模、高保真的手-器械3D重建数据集。
method: 构建包含密集手部网格和器械姿态的数据集，并设计自动标注流水线。
result: 数据集规模大、标注精度高，支持多种手术分析任务。
conclusion: OphNet-3D将促进手术场景中手物交互的3D感知研究。
---

## Abstract
Accurate 3D reconstruction of hands and instruments is critical for vision-based analysis of ophthalmic microsurgery, yet progress has been hampered by the lack of realistic, large-scale datasets and reliable annotation tools. In this work, we introduce OphNet-3D, the first extensive RGB-D dynamic 3D reconstruction dataset for ophthalmic surgery, comprising 41 sequences from 40 surgeons and totaling 7.1 million frames, with fine-grained annotations of 12 surgical phases, 10 instrument categories, dense MANO hand meshes, and full 6-DoF instrument poses. To scalably produce high-fidelity labels, we design a multi-stage automatic annotation pipeline that integrates multi-view data observation, data-driven motion prior with cross-view geometric consistency and biomechanical constraints, along with a combination of collision-aware interaction constraints for instrument interactions. Building upon OphNet-3D, we establish two challenging benchmarks—bimanual hand pose estimation and hand–instrument interaction reconstruction—and propose two dedicated architectures: H-Net for dual-hand mesh recovery and OH-Net for joint reconstruction of two-hand–two-instrument interactions. These models leverage a novel spatial reasoning module with weak-perspective camera modeling and collision-aware center-based representation. Both architectures outperform existing methods by substantial margins, achieving improvements of over 2mm in Mean Per Joint Position Error (MPJPE) and up to 23\% in ADD-S metrics for hand and instrument reconstruction, respectively.

---

## 论文详细总结（自动生成）

# 论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

**核心问题：**  
眼科显微手术中对手和器械的精确3D重建对于基于视觉的技能评估和训练至关重要，但目前缺乏大规模、真实的动态3D手-器械交互数据集以及可靠的自动化标注工具。现有方法多局限于通用场景或合成数据，难以处理显微手术中受限空间、精细运动尺度、频繁遮挡及双手多器械的复杂交互。

**整体含义：**  
本文旨在填补这一空白，通过构建首个大规模真实眼科手术RGB-D动态3D重建数据集OphNet-3D，并设计自动标注流水线生成高保真标签，从而推动手术场景中手物交互的3D感知研究，最终实现客观、可扩展的手术技能评估与培训。

## 2. 论文提出的方法论：核心思想、关键技术细节

**核心思想：**  
利用多视图RGB-D相机阵列采集数据，通过多阶段优化流水线自动生成手部MANO网格和6D器械姿态，并基于该数据集提出双手重建（H-Net）和双手-双器械联合重建（OH-Net）基线模型。

**关键技术细节：**

- **数据采集**：8台Intel RealSense D435 RGB-D相机（30 FPS，848×480），3个LED灯，记录40名医生在猪眼模拟器上的标准白内障手术（12个阶段，10种器械）。所有器械经工业3D扫描获得CAD模型。

- **自动标注流水线**（图2）：
  - **阶段1**：场景点云生成与分割。利用SAM2获取手和器械掩码，通过跨视图滤波得到纯净点云。
  - **阶段2**：初始化。使用[61]和ViTPose初始化手部状态，利用ICP注册器械CAD模型以初始化6D姿态（对关节器械额外估计1D关节因子α）。
  - **阶段3**：联合优化。优化目标包括：
    - 2D重投影损失 \(L_{2d}\)、掩膜损失 \(L_{sil}\)、3D点云距离损失 \(L_{3d}\)、时间平滑损失 \(L_{smooth}\)
    - 运动先验损失 \(L_{prior}\)（基于HMP模型）
    - 生物力学约束 \(L_{bio}\)（关节角度、骨骼长度、手掌弯曲等）
    - 交互损失 \(L_{inter}\)（吸引+排斥）和带符号距离场损失 \(L_{sdf}\)（防止穿透）

- **基线模型**：
  - **H-Net**：从单目RGB输入估计双手MANO参数。使用碰撞感知中心表示分离两手特征，T-Net预测两手间相对平移。
  - **OH-Net**：扩展至双手-双器械。增加器械中心热图、器械参数图（6D姿态+1D关节），联合优化手和器械的掩膜及3D损失。
  - 弱透视相机模型用于将3D点投影到2D。

## 3. 实验设计：数据集、基准测试、对比方法

**数据集：** OphNet-3D（41个序列，40名医生，710万帧，8视角RGB-D）。划分为30/3/8人的训练/验证/测试集。

**基准测试：**
1. **双手姿态估计**：评估指标MPJPE、MPVPE、MRRTE（均根对齐后）。
2. **手-器械交互**：额外评估ADD-S（医疗器械定位误差）、MAE（关节器械关节角度误差）、Pen（穿透体积）、MRRTE_{h,o}（手-器械相对平移误差）。

**对比方法：**
- 双手姿态：DIR[68]、InterWild[55]、IntagHand[44]、ACR[90]
- 手-器械交互：Hasson et al.[26]、HFL-Net[48]、HOISDF[65]
- 额外消融：H-Net/OH-Net变体（有无T-Net、RGB-D版本）

## 4. 资源与算力

- **模型训练**：1块NVIDIA A100 GPU，batch size 64，骨干网络ResNet-50。
- **标注流水线**：在A100上，1000帧视频的优化耗时约15分钟（阶段II约10.9分钟，阶段III约4.1分钟）。
- 未报告具体训练总时长或迭代次数，但提供了训练细节（学习率、损失权重等）。

## 5. 实验数量与充分性

- **实验组数**：两个benchmark共包含2个主表（表2、表3），每个主表列出7-8种方法对比，含消融变体（H-Net w/o T-Net、H-Net-D、OH-Net变体）。
- **充分性**：覆盖了通用和手术场景下的主流方法，通过增减组件（T-Net、深度输入）验证模块贡献。消融实验设计合理，指标全面。但未报告多次重复实验的误差棒（如标准差），因此统计显著性未明确。
- **公平性**：所有方法在同一数据集、相同评价指标下比较，数据划分按受试者避免数据泄露。但对比方法可能未针对手术场景微调，存在一定偏差。

## 6. 论文的主要结论与发现

- OphNet-3D是首个大规模、真实眼科手术RGB-D动态3D重建数据集，规模远超现有手术手部数据集（710万帧，21M分割实例）。
- 提出的多阶段自动标注流水线能产生高精度的手部网格和6D器械姿态，可用于监督学习。
- H-Net和OH-Net在双手和手-器械交互任务上显著优于现有方法：MPJPE改善超过2mm，ADD-S提升高达23%（OH-Net-D在测试集上ADD-S达76.31%）。
- 深度信息（RGB-D版本）进一步提升了交互精度和物理合理性（减少穿透）。

## 7. 优点：方法或实验设计上的亮点

- **数据集层面**：真实临床场景，多视图RGB-D，包含不同经验水平医生、多种器械、完整手术阶段，支持多种任务（姿态、交互、视频级重建）。
- **标注流水线**：巧妙融合数据驱动先验和多视图几何约束，结合生物力学和交互物理约束，有效处理遮挡和穿透。
- **模型设计**：碰撞感知中心表示和T-Net相对平移模块针对手术场景优化；弱透视相机建模实用；能够同时处理双手-双器械，是首个此类方法。
- **实验覆盖**：设立两个基准，对比多种通用和任务特定方法，消融实验清晰。

## 8. 不足与局限

- **数据局限**：单一中心、单一手术类型（白内障），仅使用猪眼模拟器，可能不直接泛化到真实人体手术或多中心设置。
- **硬件局限**：显微镜强光导致器械尖端过曝，影响可见性和标注精度。作者建议未来采用同步运动捕捉或红外。
- **未利用显微镜视图**：当前未整合显微镜视角进行眼表、手和器械的联合重建，限制了临床直接应用。
- **评估局限**：未报告置信区间或统计显著性检验，对比方法可能未针对手术域优化，部分SOTA方法（如2024-2025的HOI方法）未被包含。
- **计算成本**：标注流水线对每帧的优化耗时较长（15分钟/1000帧），可能难以扩展到更大规模。

（完）
