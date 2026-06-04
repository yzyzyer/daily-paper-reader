---
title: Learning Interaction-aware 3D Gaussian Splatting for One-shot Hand Avatars
title_zh: 学习交互感知的3D高斯泼溅用于单次手部化身
authors: "Xuan Huang, Hanhui Li, Wanquan Liu, Xiaodan Liang, Yiqiang Yan, Yuhao Cheng, CHENQIANG GAO"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=BxPa7Sn5Zq"
tags: ["query:hoi"]
score: 8.0
evidence: 从单张图像创建交互手的可动画化身，涉及手部姿态估计
tldr: 现有基于高斯泼溅的方法在单张输入下难以处理交互手部姿态和遮挡。本文提出两阶段交互感知框架，利用跨手先验和可学习特征，解耦身份与姿态，并在交互区域精细化高斯。实验表明该方法能从单张图像生成高质量可动画双手化身，有效处理交互姿态。该工作直接服务于交互场景中的手部姿态估计和建模。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-bxpa7sn5zq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bxpa7sn5zq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bxpa7sn5zq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bxpa7sn5zq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bxpa7sn5zq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bxpa7sn5zq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bxpa7sn5zq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1432, \"height\": 1091, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bxpa7sn5zq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bxpa7sn5zq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-bxpa7sn5zq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 160, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-bxpa7sn5zq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bxpa7sn5zq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1466, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bxpa7sn5zq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1007, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-bxpa7sn5zq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1458, \"height\": 467, \"label\": \"Table\"}]"
motivation: 单张图像下交互手部因姿态多样和遮挡，现有方法效果差。
method: 两阶段交互感知高斯泼溅框架，解耦身份与姿态，优化交互区域。
result: 生成高保真可动画双手化身，在交互姿态下优于现有方法。
conclusion: 为交互手部建模提供有效方案，可支撑手部姿态估计任务。
---

## Abstract
In this paper, we propose to create animatable avatars for interacting hands with 3D Gaussian Splatting (GS) and single-image inputs. Existing GS-based methods designed for single subjects often yield unsatisfactory results due to limited input views, various hand poses, and occlusions. To address these challenges, we introduce a novel two-stage interaction-aware GS framework that exploits cross-subject hand priors and refines 3D Gaussians in interacting areas. Particularly, to handle hand variations, we disentangle the 3D presentation of hands into optimization-based identity maps and learning-based latent geometric features and neural texture maps. Learning-based features are captured by trained networks to provide reliable priors for poses, shapes, and textures, while optimization-based identity maps enable efficient one-shot fitting of out-of-distribution hands. Furthermore, we devise an interaction-aware attention module and a self-adaptive Gaussian refinement module. These modules enhance image rendering quality in areas with intra- and inter-hand interactions, overcoming the limitations of existing GS-based methods. Our proposed method is validated via extensive experiments on the large-scale InterHand2.6M dataset, and it significantly improves the state-of-the-art performance in image quality. Code and models will be released upon acceptance.

---

## 论文详细总结（自动生成）

# 学习交互感知的3D高斯泼溅用于单次手部化身（Learning Interaction-aware 3D Gaussian Splatting for One-shot Hand Avatars）—— 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：从单张RGB图像创建可动画化的“交互手”（两只手相互作用）的虚拟化身。现有方法（如基于参数化网格、NeRF、或针对单手的3D高斯泼溅）在面对单张输入、复杂手部姿态、以及手部间与手内部的遮挡与相互作用时，渲染质量差、泛化能力弱。
- **研究背景**：交互手建模在虚拟现实、手语生成、人机交互中具有重要意义。然而，单张图像的信息极度有限（缺乏几何与纹理完整信息），且交互区域（如手指缠绕、手掌相触）导致复杂的几何变形与纹理缺失。已有方法要么依赖多视角优化（训练成本高），要么缺乏对交互区域的有效建模，要么在分布外（OOD）数据上性能下降。
- **整体含义**：本文旨在提出一种**两阶段交互感知的3D高斯泼溅（GS）框架**，从单张图像中创建高质量、可动画化的交互手化身，并支持各种编辑与动画应用。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想

- **解耦表示**：将手的3D表示分为两部分：
    - **学习特征**（通过训练网络捕获）：包括潜在几何特征（从手部网格获取）和神经纹理图（从身份图与姿态嵌入推断），提供跨主体的可靠先验（姿态、形状、纹理）。
    - **可优化身份图**：在单次拟合阶段针对新个体独立优化，保留个体特征，避免对网络微调的需求。
- **两阶段框架**：
    - **Stage-I**：学习解耦的手部先验（训练交互感知高斯泼洒网络IGSN）。
    - **Stage-II**：单次交互手化身拟合（针对新个体优化身份图与纹理偏差）。

### 关键技术细节

- **参数化手部网格**：使用MANO模型（高分辨率版本）重建网格，提供几何初始化与UV纹理坐标。
- **几何编码**：姿态编码器（MLP处理姿态参数θ和相机参数c） + 位置编码器（PointNet+Transformer解码器） → 得到几何特征向量。
- **纹理编码**：从可优化的“跨主体身份图”（2C×H×W）中根据UV坐标采样，结合位置编码生成身份嵌入，再与姿态嵌入结合形成纹理条件图 → 经Transformer解码器生成神经纹理图 → 与几何特征逐元素相加得到统一隐式特征f。
- **交互感知注意力模块（IAttn）**：通过比较给定查询点在标准态网格与动态网格上的邻近点集重叠程度，检测出交互点（自交互、手间交互），仅对这些点施加自注意力机制，增强交互区域的几何变形与纹理细节重建。
- **自适应高斯细化模块（GRM）**：利用MLP预测高斯点的有效性（validity），去除冗余点（ϕ(fp) < T_d）或分裂密集区域点（ϕ(fp) > T_s），同时预测偏移量调整高斯位置，从而自适应控制高斯密度与位置，克服MANO网格的粗糙几何。
- **损失函数**：Stage-I使用L1损失+感知损失（VGG）；Stage-II增加掩码损失和纹理偏差正则化项。
- **单次拟合**：固定IGSN参数，仅优化新个体的身份图m*（从零初始化）和共享纹理偏差Δt（左右手共享），共50步优化，约2.5分钟。

## 3. 实验设计

- **数据集**：使用大规模公开数据集 **InterHand2.6M**（CC-BY-NC 4.0许可），包含多视角序列，多个主体执行各种手部姿态。
- **训练/测试划分**：
    - Stage-I 预训练：21个主体的交互手姿态序列，每个主体留出一个未见序列用于评估。
    - Stage-II 评估：测试集“test/capture0”中的4个姿态序列，共349帧（新姿态合成）；50个视图（新视角合成）。
- **对比方法**：选择4个SOTA方法：
    - **KeypointNeRF**（通用NeRF，用于人体新视角合成）
    - **SMPLpix**（图像空间渲染方法）
    - **VANeRF**（专门用于单视图交互手新视角合成）
    - **OHTA***（将OHTA框架的单手策略适配到本任务，使用本文预训练模型作为对比）
- **评估指标**：PSNR ↑、SSIM ↑、LPIPS ↓（渲染质量）。
- **实验结果**：
    - 定量上，本文在所有指标上显著优于所有对比方法（见表1）。例如，新视角合成PSNR 26.14 vs 第二好VANeRF 25.38；新姿态合成PSNR 26.56 vs OHTA* 25.93。
    - 定性上，本文能够恢复手指甲、皱纹、血管等细节，而其他方法模糊或丢失细节。

## 4. 资源与算力

- **文中明确说明**：训练IGSN使用 **3块A6000 GPU**，Adam优化器，学习率1e-4，训练 **8个epoch**。
- **单次拟合**：在 **1块A6000 GPU** 上运行，共50步优化，耗时约 **2.5分钟**。
- **未说明**：未提及总训练时长（小时/天），未说明数据预处理及推理的额外算力需求。

## 5. 实验数量与充分性

- **实验组数**：
    - **主实验**：与4个基线方法进行定量与定性比较（表1、图4）。
    - **消融实验（Stage-I）**：4个变体（w/o IAttn、w/o GRM、w/o IMap、OHTA*对比），见表2 Stage-One。
    - **消融实验（Stage-II）**：4个变体（去掉身份图、去掉注意力、去掉GRM、去掉纹理偏差等），见表2 Stage-Two。
    - **附录附加实验**：
        - 统计显著性（5次运行均值和标准差，表3）
        - 阴影分离可视化（图9）
        - 单只手vs两只手输入对比（表4 “Ablation Hand Num.”）
        - 不同分割掩码（SAM vs 网格掩码）对比（表4 “Ablation Mask”）
        - 相机参数影响、阴影系数、低高斯点数、网格估计噪声（表4 “Ablation S1”和“Ablation Noise”）
        - 应用演示（图7）
- **充分性判断**：
    - **充分**：消融覆盖了提出的所有核心模块（注意力、高斯细化、身份图、纹理偏差），并考虑了手部数量、分割方法、估计噪声等外部因素。对比方法均为SOTA且针对基线做了适配（OHTA*）。实验设置在公开数据集上，随机种子/多轮运行确保了统计可靠性。
    - **客观公平**：所有对比方法均使用官方或适配版本，在相同评估设置下比较。消融实验控制变量合理。不足之处：未与其他基于3D高斯泼溅的交互手方法（如3D-PSHR）直接比较（但3D-PSHR需要多视角视频，不适合单次任务）。

## 6. 论文的主要结论与发现

- **主要结论**：提出的两阶段交互感知高斯泼洒框架能够从单张图像生成高保真、可动画化的交互手化身，在InterHand2.6M数据集上的PSNR、SSIM、LPIPS均显著超过现有SOTA。
- **关键发现**：
    - 解耦的身份图（空间结构保持）比向量式身份编码（如OHTA）能捕获更精细的个体纹理特征，提升渲染质量。
    - 交互感知注意力模块有效检测并增强自交互/手间交互区域，改善了皱纹、阴影等细节。
    - 自适应高斯细化模块可以去除冗余点、在复杂区域增加点，克服了MANO网格的粗糙几何限制。
    - 纹理偏差（Δt）加速单次拟合并防止过度变化。
- **应用展示**：支持纹理编辑、文本到手、姿态动画、手部组合等（图1、图7）。

## 7. 优点

- **方法创新点**：
    - 首次将3D高斯泼洒用于单张图像**交互手**的可动画化身创建。
    - 提出“学习特征 + 可优化身份图”的解耦表示，兼顾跨主体泛化与个体保真。
    - 设计的交互点检测策略简单有效（基于邻域重叠），无需额外标注。
    - 自适应高斯细化模块在保持高效的同时提升了细节质量。
- **实验设计优点**：
    - 与多个代表不同技术路线的基线方法对比，且适配了OHTA*保证公平。
    - 消融实验全面，覆盖所有核心组件。
    - 统计显著性分析（5次运行）增强了结果可信度。
    - 支持多种应用场景（编辑、文本、野外图像），展示了实用潜力。
- **效率**：单次拟合仅2.5分钟，无需网络微调。

## 8. 不足与局限

- **实验覆盖局限**：
    - 仅在InterHand2.6M一个数据集上验证，未涉及其他交互手数据集（如H2O、DexYCB）或真实野外场景。
    - 未与近期基于3DGS的交互手方法（如3D-PSHR，但该方法是多视角视频输入，不可直接对比）进行比较。
- **技术局限**：
    - 单次拟合仍需要单独优化（2.5分钟），不如单次前向推理快速。
    - 对姿态估计误差敏感：当MANO参数估计严重错误时，模型会产生错误对齐和伪影（附录图10）。论文虽声称对噪声有一定鲁棒性（表4 Ablation Noise），但极端情况仍会失败。
    - 纹理偏差Δt假设左右手对称，实际中可能不完全成立（如不同肤色或涂色）。
    - 交互检测阈值T（=100）是人工设定的，可能在其他场景需调整。
- **偏差风险**：
    - 数据集InterHand2.6M为实验室多视角采集，缺少真实世界复杂光照、背景、遮挡的变化，模型在野外场景的泛化性未充分验证。
    - 未讨论种族、肤色多样性导致的潜在偏差（因消融实验包括肤色编辑，但未作系统分析）。
- **社会影响**：积极（辅助手语生成、虚拟交流），但可能被用于生成虚假手部动作，文中承认存在被滥用的风险但未给出具体防范措施（附录提及“无负面社会影响”，略显乐观）。

（完）
