---
title: "RFMPose: Generative Category-level Object Pose Estimation via Riemannian Flow Matching"
title_zh: RFMPose：基于黎曼流匹配的生成式类别级物体姿态估计
authors: "Wenzhe Ouyang, Qi Ye, Jinghua Wang, Zenglin Xu, Jiming Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=6aaixHco6C"
tags: ["query:hoi"]
score: 4.0
evidence: 生成式类别级物体姿态估计
tldr: 针对判别式方法在多假设预测中的局限性，本文提出RFMPose生成式框架。它通过黎曼流形上的测地线插值确保几何一致性，利用最优输运缓解对称歧义，实现端到端似然估计。在合成和真实数据上，RFMPose展现了优越的精度和泛化能力，为物体姿态估计提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-6aaixhco6c/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1473, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6aaixhco6c/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1241, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6aaixhco6c/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 638, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-6aaixhco6c/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1512, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6aaixhco6c/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1407, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6aaixhco6c/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1405, \"height\": 589, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6aaixhco6c/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 743, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6aaixhco6c/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 703, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6aaixhco6c/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 891, \"height\": 208, \"label\": \"Table\"}]"
motivation: 判别式方法难以处理对称性和多假设预测，且需要专用网络。
method: 使用黎曼流匹配学习确定性姿态轨迹，结合最优输运和测地线约束。
result: 在类别级物体姿态估计基准上达到最优性能。
conclusion: RFMPose为生成式姿态估计提供了几何一致的新方法。
---

## Abstract
We introduce RFMPose, a novel generative framework for category-level 6D object pose estimation that learns deterministic pose trajectories through Riemannian Flow Matching (RFM). Existing discriminative approaches struggle with multi-hypothesis predictions (e.g., symmetry ambiguities) and often require specialized network architectures. RFMPose advances this paradigm through three key innovations:
(1) Ensuring geometric consistency via geodesic interpolation on Riemannian manifolds combined with bi-invariant metric constraints;
(2) Alleviating symmetry-induced ambiguities through Riemannian Optimal Transport for probability mass redistribution without ad-hoc design;
(3) Enabling end-to-end likelihood estimation through Hutchinson trace approximation, thereby eliminating auxiliary model dependencies.
Extensive experiments on the Omni6DPose demonstrate state-of-the-art performance of the proposed method, with significant improvements of $\textbf{+4.1}$ in $\mathrm{\textbf{IoU}_{25}}$ and $\textbf{+2.4}$  in $\textbf{5°2cm}$ metrics compared to prior generative approaches. Furthermore, the proposed RFM framework exhibits robust sim-to-real transfer capabilities and facilitates pose tracking extensions with minimal architectural adaptation.

---

## 论文详细总结（自动生成）

# 论文详细总结：RFMPose: Generative Category-level Object Pose Estimation via Riemannian Flow Matching

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：6D 物体姿态估计是计算机视觉的基础任务，广泛应用于增强现实、机器人操控、手物交互等。然而，传统方法主要分为两类：基于对应的方法（如 NOCS、关键点匹配）和直接回归的方法（如 FS-Net、VI-Net）。前者存在对应过程不可微、误差传播等局限；后者依赖专用姿态敏感网络，难以兼容新兴的视觉-语言-动作（VLA）模型。两类方法本质上属于**判别式范式**，核心局限包括：
  - 难以处理多假设预测问题（例如物体对称性导致的多个可行姿态）；
  - 需要精心设计的姿态敏感特征提取网络，缺乏灵活性。
- **核心问题**：如何设计一个**生成式框架**，既能自然地处理对称性等歧义，又能保持几何一致性，同时实现端到端训练，避免辅助模型依赖。
- **整体含义**：本文提出 RFMPose，首次将黎曼流匹配（Riemannian Flow Matching）应用于类别级 6D 姿态估计，通过学习确定性姿态轨迹，在 SE(3) 流形上显式保证几何约束，并通过黎曼最优传输解决对称性歧义，利用 Hutchinson 迹估计实现端到端似然估计。实验在挑战性的 Omni6DPose 数据集上达到 SOTA，尤其在合成→真实场景下展现鲁棒迁移能力。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 核心思想
- 将类别级 6D 姿态估计视为**条件概率分布建模**问题：给定部分点云和裁剪图像作为条件 c，学习姿态 [R, T] 的条件分布 q([R,T]|c)。
- 通过**黎曼流匹配**学习确定性姿态轨迹：将姿态空间视为 SE(3) 流形，利用测地线插值（SO(3) 上的李代数变换 + R³ 上的欧氏插值）构造条件速度场，由概率流 ODE 驱动初始分布演化至目标分布。
- 关键创新三点：**几何一致性**（黎曼测地线插值与双不变度量）、**对称性处理**（黎曼最优输运，无需对称专用架构）、**端到端似然估计**（Hutchinson 迹估计替代辅助能量模型）。

### 2.2 关键技术细节
1. **黎曼流匹配框架**：
   - 定义条件概率路径 ρₜ([R,T]|c)，由速度场 vθ(t,c,[R,T]) 通过 ODE 控制。
   - 速度场构造：在 SO(3) 上使用测地线插值：`R(t) = R₀ · exp(t · log(R₀^T R₁))`；在 R³ 上使用欧氏线性插值：`T(t) = (1-t)T₀ + tT₁`。
   - 损失函数：黎曼条件流匹配损失 `L_RCFM(θ) = E_{t,q,pt} ||vθ - u||²_{SE(3)}`，强制速度场逼近真实条件速度。
2. **黎曼最优输运处理对称性**：
   - 对于对称物体，多个地面真值姿态同时成立，传统方法需要对称专用架构。
   - 将目标分布视为离散混合分布 `ρ₁ = Σ βⱼ δ_{[Ry,j,Ty,j]}`，通过最小化加权黎曼代价（SE(3) 上的测地距离）将概率质量从单个源分布最优传输到多个目标分布，无需额外设计。
   - 代价函数定义为 `c([R₁,t₁],[R₂,t₂]) = ||log([R₁,t₁]⁻¹[R₂,t₂])||_{se(3)}`。
3. **端到端似然估计**：
   - 通过概率流 ODE 的对数似然积分公式：`log p₁ - log p₀ = -∫₀¹ ∇·vθ dt`。
   - 使用 **Hutchinson 迹估计**近似速度场的散度（即 Jacobian 的迹）：`tr(Jt) = E[ε^T Jt ε]`，ε ~ N(0,I)，通过自动微分计算 Jacobian-向量积（JVP），重复 N 次取期望。
   - 初始对数似然 `log p₀` 来自标准正态分布，结合积分项得到每个候选姿态的似然值，然后剔除低似然候选，对剩余候选进行加权平均（SO(3) 和 R³ 分别加权）获得最终估计。

## 3. 实验设计

### 3.1 数据集
- 主要使用 **Omni6DPose** 数据集，包含 807K 张合成/真实图像、超过 650 万标注、覆盖 149 个物体类别，规模和多样性远超 REAL275 等传统数据集。
- 合成数据基于 ScanNet++、IKEA、Matterport3D 三个经典场景。
- 训练仅使用合成数据，评估分别在合成测试集（ScanNet++ 测试集）和真实场景（Omni6DPose ROPE 集）上进行。

### 3.2 对比方法
- **确定性方法**：HS-Pose、AG-Pose、SecondPose、NOCS、SGPA、IST-Net 等。
- **概率性方法**：GenPose、GenPose++（GenPose 的增强版）。
- 评价指标：IoU AUC、IoU₂₅、IoU₅₀、IoU₇₅、5°2cm、5°5cm、10°2cm、10°5cm 等多个姿态精度指标。

### 3.3 实现细节
- 输入双模态：RGB 图像（使用冻结的 DINOv2 提取语义特征） + 点云（FPS 采样 1024 点后经 PointNet++ 提取全局特征）。
- 模态融合：RGB 特征与点坐标空间拼接。

## 4. 资源与算力
- 论文正文未明确提及具体的 GPU 型号、数量、训练时长等算力信息。
- 仅在补充材料（可能）中会提供，但主文中缺失。因此我们指出：**文中未明确说明所用 GPU 型号、数量及训练时间**。

## 5. 实验数量与充分性
- 实验覆盖三大方面：
  1. **合成数据集对比**（表 1）：在 Omni6DPose ScanNet++ 测试集上与 3 种确定性方法和 1 种概率性方法（GenPose++）对比，所有 149 类平均。
  2. **真实场景对比**（表 2）：在 Omni6DPose ROPE 集上对比 6 种确定性方法和 2 种概率性方法。
  3. **物体姿态跟踪**（表 3）：在 ROPE 集上对比 GenPose 和 GenPose++，并报告 FPS、5°5cm、mIoU、旋转误差、平移误差等。
  4. **消融实验**（表 4-6）：分别验证黎曼插值与度量、似然估计与样本聚合策略、黎曼最优传输（ROT）对对称物体的作用。
- **充分性评价**：实验设计较为充分，涵盖合成/真实、多模态输入、对比方法多样（包括当前最强基准 GenPose++），消融实验紧扣三个核心创新点。但缺少对更多数据集（如 REAL275）的跨数据集泛化测试，以及对称物体类型细分分析。

## 6. 论文的主要结论与发现
- **RFMPose 在所有指标上显著超越现有方法**：
  - 合成集上相比 GenPose++ 提升 IoU₂₅ +4.1、5°2cm +2.4。
  - 真实场景下 IoU₂₅ 达到 42.1，验证了 sim-to-real 迁移能力。
- **消融实验结论**：
  - 黎曼插值比欧氏插值提升 IoU₂₅ +1.7，结合黎曼度量再提 +4.6。
  - 加权平均样本聚合优于最大似然单样本和简单平均，证实似然估计的有效性。
  - 黎曼最优输运对对称物体带来显著提升（IoU₂₅ 提升 +5.1，5°2cm 提升 +1.6）。
- **物体姿态跟踪**：通过轻微修改（添加噪声、设置 t=0.55）即可扩展至跟踪任务，性能优于 GenPose++，且推理速度更快（FPS 11.3 vs 8.7）。
- **方法优势**：端到端训练、架构灵活（无需对称专用网络）、可兼容 VLA 模型。

## 7. 优点
- **理论创新**：首次将黎曼流匹配应用于 6D 姿态估计，提出测地线插值 + 双不变度量，确保轨迹物理可行性。
- **对称物体处理简洁有效**：用黎曼最优输运统一处理多假设，无需对称专用设计或额外损失函数。
- **端到端训练**：通过 Hutchinson 迹估计实现似然计算，摆脱辅助能量模型，简化训练流程。
- **泛化能力强**：仅用合成数据训练即可在真实场景取得优异表现，且可自然扩展至跟踪任务。
- **实验充分**：在大型 Omni6DPose 数据集上进行了全面的对比和消融，结果可信。

## 8. 不足与局限
- **全文中未公开算力细节**，如 GPU 型号、数量、训练时间，影响可重复性评估。
- **对铰接物体（如笔记本电脑）的精度仍不令人满意**，论文在“局限与未来工作”中明确指出了这一点。
- **实验数据集局限**：仅使用 Omni6DPose，缺乏在传统常用数据集（如 REAL275、LINEMOD）上的评估，不利于与历史方法直接对比。
- **消融实验未深入分析**：如多种对称物体类别下的分解表现、不同 N 值对 Hutchinson 迹估计的影响、不同 tδ 值对跟踪精度的影响等。
- **方法复杂度**：虽然端到端，但推理时需要多次采样（N 次 JVP 计算），可能带来计算开销，论文未详细分析推理时间与精度权衡。
- **假设限制**：假设对称物体的多个地面真值姿态等概率出现（β 相同），在非等概率情况下可能不是最优。

（完）
