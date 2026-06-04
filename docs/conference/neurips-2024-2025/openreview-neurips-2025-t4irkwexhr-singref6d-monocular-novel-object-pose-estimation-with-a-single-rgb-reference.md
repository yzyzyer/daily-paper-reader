---
title: "SingRef6D: Monocular Novel Object Pose Estimation with a Single RGB Reference"
title_zh: "SingRef6D: 基于单张RGB参考的单目新物体姿态估计"
authors: "Jiahui Wang, Haiyue Zhu, Haoren Guo, Abdullah Al Mamun, Cheng Xiang, Tong Heng LEE"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=t4irkwEXhr"
tags: ["query:hoi"]
score: 5.0
evidence: 基于单RGB参考的物体姿态估计，与手操作中的物体姿态估计相关
tldr: SingRef6D提出一种轻量级流水线，仅需一张RGB参考图像即可进行6D物体姿态估计，无需深度传感器或多视角采集。该方法对透明或高反光物体鲁棒，且适用于资源受限环境。在手物交互中，该技术可用于估计被操控物体的姿态，从而支持交互分析。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1374, \"height\": 814, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 931, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1422, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1401, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 1183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1282, \"height\": 1183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1448, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1364, \"height\": 2256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1357, \"height\": 2253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t4irkwexhr/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1363, \"height\": 2253, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 631, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 565, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 875, \"height\": 633, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 686, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 802, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 745, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 809, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 636, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 862, \"height\": 1319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 947, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 533, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1448, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1171, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1172, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 733, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1171, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1100, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1174, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1436, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t4irkwexhr/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 662, \"height\": 271, \"label\": \"Table\"}]"
motivation: 现有6D姿态估计依赖深度传感器，在透明或反光表面失效；RGB方法在低光或纹理缺乏场景鲁棒性差。
method: 提出SingRef6D，仅需单张RGB参考图像，利用轻量匹配和几何推理估计物体6D姿态，避免深度传感器和多视图合成。
result: 在标准基准上达到与深度方法相当的精度，同时在挑战性表面和光照条件下表现更鲁棒。
conclusion: 单RGB参考方案降低了部署成本，拓展了姿态估计在复杂环境下的实用性。
---

## Abstract
Recent 6D pose estimation methods demonstrate notable performance but still face some practical limitations. For instance, many of them rely heavily on sensor depth, which may fail with challenging surface conditions, such as transparent or highly reflective materials. In the meantime, RGB-based solutions provide less robust matching performance in low-light and texture-less scenes due to the lack of geometry information. Motivated by these, we propose **SingRef6D**, a lightweight pipeline requiring only a **single RGB** image as a reference, eliminating the need for costly depth sensors, multi-view image acquisition, or training view synthesis models and neural fields. This enables SingRef6D to remain robust and capable even under resource-limited settings where depth or dense templates are unavailable. Our framework incorporates two key innovations. First, we propose a token-scaler-based fine-tuning mechanism with a novel optimization loss on top of Depth-Anything v2 to enhance its ability to predict accurate depth, even for challenging surfaces. Our results show a 14.41% improvement (in $\delta_{1.05}$) on REAL275 depth prediction compared to Depth-Anything v2 (with fine-tuned head). Second, benefiting from depth availability, we introduce a depth-aware matching process that effectively integrates spatial relationships within LoFTR, enabling our system to handle matching for challenging materials and lighting conditions. Evaluations of pose estimation on the REAL275, ClearPose, and Toyota-Light datasets show that our approach surpasses state-of-the-art methods, achieving a 6.1% improvement in average recall.

---

## 论文详细总结（自动生成）

# 论文详细总结：SingRef6D: Monocular Novel Object Pose Estimation with a Single RGB Reference

## 1. 核心问题与研究动机
- **问题背景**：6D物体姿态估计在机器人、工业自动化、增强现实等领域至关重要。现有方法主要依赖深度传感器（如RGB-D相机）或预先生成的CAD模型，但在透明、高反射等挑战性表面条件下，深度传感器失效严重（如ClearPose数据集中失败率超过85%）。而纯RGB方法在低光照、弱纹理场景下因缺乏几何信息而匹配不鲁棒。
- **研究动机**：受人类视觉系统启发，人类无需三维模型、多视角或双目视觉，仅凭认知机制就能高效感知深度和形状。本文旨在设计一种仅需**单张RGB参考图像**即可进行6D姿态估计的轻量级流水线，避免CAD模型、多视图采集、显式或隐式的新视角合成（如NeRF、扩散模型），从而在资源受限环境中保持鲁棒性。

## 2. 方法论
### 核心思想
- 将问题分解为两个独立阶段：**深度感知**和**姿态求解**。首先通过改进的深度估计模型从单张RGB图像预测高质量度量深度，然后利用深度信息增强特征匹配，最后通过点云配准求解相对姿态。

### 关键技术细节
- **鲁棒度量深度预测（Robust Metric Depth Prediction）**：
  - 基于Depth-Anything v2（DPAv2），引入**token scaler**机制（类似ControlNet结构）对四层特征（低、中、高、全局）进行动态缩放与调制，保留预训练知识。具体地，低中层特征加高效注意力层增强全局感知，高层特征用InceptConv增强局部细节。
  - 提出新的组合损失函数：
    - **全局损失**：SSI损失 + 正则化项 + BerHu损失（针对大误差）。
    - **局部损失**：包括**尺度对齐损失**L_scale（抑制物体级尺度偏差）、**边缘强调损失**L_edge（利用RGB梯度加权约束深度边界）、**法向一致性损失**L_norm（保持表面几何结构）。
  - 训练时仅微调token scaler和动态尺度层，冻结DPAv2的其他参数，降低计算负担。

- **深度感知匹配与姿态求解（Depth-Aware Matching & Pose-Solving）**：
  - 将RGB特征与归一化度量深度特征在潜在空间相加融合，保留LoFTR的预训练参数（冻结），采用粗到细（coarse-to-fine）匹配策略。
  - 利用深度值作为空间线索，减少纯RGB匹配时的前景/背景误匹配，提升低纹理区域的对应密度。
  - 获得点对应后，使用PointDSC进行点云配准，得到查询与参考的相对姿态T_q→r，进而求解6D姿态。

### 算法流程
1. 输入查询图像I_q和参考图像I_r。
2. 通过微调的DPAv2 + token scaler预测两者的度量深度图D_q, D_r。
3. 将RGB与深度特征融合，通过深度感知LoFTR建立粗-细对应关系。
4. 使用对象的作物区域（通过SAM等分割模型获取）筛选对应点。
5. 利用PointDSC求解相对姿态，结合参考的绝对姿态计算查询的6D姿态。

## 3. 实验设计
### 数据集与场景
- **REAL275**：复杂场景，含多种工业及日常物体。
- **Toyota-Light (Tyo-L)**：BOP挑战赛子集，侧重光照变化。
- **ClearPose**：透明物体，具有挑战性表面条件。
- 每个数据集均手动划分训练/测试集，确保测试场景未在微调中出现过。

### 基准与对比方法
- **深度估计基线**：UniDepthv1（FT）、Depth-Anything v2（FT，微调头部）。
- **姿态估计基线**：SIFT、Oryon（基于VLM）、RoMA（密集特征匹配）、Any-6D、FS6D、3DAHV、DVMNet、ICP、LePard等。
- **指标**：深度预测采用δ1.05、RMSE、Abs.Rel等；姿态估计采用Average Recall（AR，包含VSD/MSSD/MSPD）和ADD(S)-0.1d。

## 4. 资源与算力
- **文中明确说明硬件**：两台Nvidia RTX3090 GPU，操作系统Ubuntu 22.04，PyTorch 2.2.0 + CUDA 12.4。
- **训练时长**：每个数据集微调80个epoch，批量大小16（ClearPose为40个epoch）。但未提供精确的总训练时间（如小时数）。

## 5. 实验数量与充分性
论文进行了大量实验，包括：
- **深度预测定量评估**：在三个数据集上对比多种基线，并展示不同训练数据比例下的性能。
- **姿态估计定量评估**：在三个主要数据集上，结合多种匹配器（SIFT、Oryon、RoMA、Ours）和深度源（Oracle、DPAv2、Ours）进行对比。
- **消融实验**：
  - 损失函数各分量（L_scale, L_edge, L_norm）的作用（Table 6）。
  - 不同微调策略（仅头部、头部+scaler、仅scaler）及LoRA对比（Table 7）。
  - 不同深度融合方式（位置编码 vs 加法融合，Table 9）。
  - 不同匹配策略（有无深度、有无潜在融合）对比（Table 8）。
  - 模块有效性（Token Scaler + Depth-Aware Matching）的逐步验证（Table 9底部）。
- **额外分析**：跨域泛化（Table 13）、视角差距影响（Table 20-21）、更多基线对比（Table 15-19）、对反射物体（HouseCat6D）的验证等。
- **计算效率**：参数、FLOPs、内存比较（Table 5）。
总体而言，实验覆盖了多种场景、多个维度，消融充分，对比客观公平（均采用公开数据集和标准指标），结论可信。

## 6. 主要结论与发现
- **深度预测**：所提token scaler + 组合损失显著优于微调后的DPAv2和UniDepth，特别是在透明物体（ClearPose: 54.30% vs 31.23% δ1.05）和复杂光照（Tyo-L: 80.09% vs 14.64%）下。
- **姿态估计**：在三个基准上均达到SOTA，平均召回率（AR）提升6.1%。相较于Oryon，在真实深度和预测深度下均有显著改进。
- **深度感知匹配**：融合深度空间信息有效减少了误匹配，提升了低纹理区域对应质量，从而改善姿态精度。
- **计算高效**：提出的匹配器（LoFTR变体）参数量仅11.6M，GFLOPs 13.9，远低于Oryon和RoMA。

## 7. 优点
- **极简输入要求**：仅需单张RGB参考图像，无需CAD、多视图、深度传感器或任何形式的新视角合成，实用性强。
- **对挑战性表面鲁棒**：通过改进的深度预测，有效处理透明、反光等传感器失效场景。
- **轻量且高效的微调**：仅微调token scaler（约数千万参数），冻结主干，训练负担小。
- **深度感知匹配无额外训练**：在预训练LoFTR基础上直接融合深度特征，无需重训练，保持原有匹配能力。
- **充分的消融与对比**：验证了每个组件的贡献，且与多种SOTA方法公平比较。

## 8. 不足与局限
- **依赖分割掩码**：姿态估计中需要目标掩码（SAM等提供），限制了无分割场景的泛化。
- **受限于预训练模型**：深度预测和匹配性能受限于DPAv2和LoFTR的能力，在极暗环境（RGB信息极少）下可能失败。
- **跨场景泛化**：当参考与查询视角差异过大（>90°）或场景变化剧烈时，性能下降明显（Table 20-21）。
- **计算资源**：虽然推理轻量，但微调仍需双RTX3090，未报告具体训练时长，可能对资源受限团队有门槛。
- **实验覆盖**：未包含真实机器人实验或动态场景，仅基于静态数据集；且对遮挡场景的验证（如LM-O）性能较低，说明对严重遮挡仍不够鲁棒。

（完）
