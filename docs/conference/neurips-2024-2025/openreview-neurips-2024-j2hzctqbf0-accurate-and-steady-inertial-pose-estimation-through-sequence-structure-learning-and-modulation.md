---
title: Accurate and Steady Inertial Pose Estimation through Sequence Structure Learning and Modulation
title_zh: 通过序列结构学习与调制实现准确稳定的惯性姿态估计
authors: "Yinghao Wu, chaoran wang, Lu Yin, Shihui Guo, Yipeng Qin"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=j2hzCTqbF0"
tags: ["query:imu-pose"]
score: 9.0
evidence: 直接利用惯性传感器数据进行姿态估计
tldr: 针对Transformer在处理固定长度惯性序列时未能显式利用结构模式的问题，本文提出序列结构学习与调制方法，通过引入序列结构模块（SSM）调整Transformer输入特征，使其能够建模并利用惯性传感器读数中的固定结构信息。在惯性姿态估计任务上，该方法显著提升了估计的准确性和稳定性，为基于IMU的人体姿态估计提供了一种有效的序列建模新范式。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-j2hzctqbf0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1415, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-j2hzctqbf0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-j2hzctqbf0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-j2hzctqbf0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-j2hzctqbf0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 534, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-j2hzctqbf0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1457, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-j2hzctqbf0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 793, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-j2hzctqbf0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1441, \"height\": 410, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 875, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 550, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 905, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 510, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 603, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 644, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 949, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1278, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1206, \"height\": 491, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-j2hzctqbf0/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 952, \"height\": 180, \"label\": \"Table\"}]"
motivation: 现有Transformer缺乏利用固定长度惯性序列结构模式的能力，导致姿态估计精度和稳定性不足。
method: 提出序列结构模块（SSM），通过学习或先验指定固定长度惯性读数的结构信息，调制Transformer输入特征。
result: 在惯性姿态估计任务上，该方法相比基线取得了更高的准确性和稳定性。
conclusion: 所提方法有效提升了Transformer对惯性序列结构信息的利用，为IMU姿态估计提供了有力工具。
---

## Abstract
Transformer models excel at capturing long-range dependencies in sequential data, but lack explicit mechanisms to leverage structural patterns inherent in fixed-length input sequences. 
In this paper, we propose a novel sequence structure learning and modulation approach that endows Transformers with the ability to model and utilize such fixed-sequence structural properties for improved performance on inertial pose estimation tasks.
Specifically, our method introduces a Sequence Structure Module (SSM) that utilizes structural information of fixed-length inertial sensor readings to adjust the input features of transformers.
Such structural information can either be acquired by learning or specified based on users' prior knowledge.
To justify the prospect of our approach, we show that i) injecting spatial structural information of IMUs/joints learned from data improves accuracy, while ii) injecting temporal structural information based on smooth priors reduces jitter (i.e., improves steadiness), in a spatial-temporal transformer solution for inertial pose estimation.
Extensive experiments across multiple benchmark datasets demonstrate the superiority of our approach against state-of-the-art methods and has the potential to advance the design of the transformer architecture for fixed-length sequences.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与研究动机

- **任务背景**：基于稀疏惯性测量单元（IMU）的人体姿态估计具有环境无关、不受遮挡、隐私友好等优势，是视觉方案的理想补充。现有方法多采用RNN或Transformer对IMU序列进行时序建模。
- **核心问题**：原生Transformer的自注意力机制设计用于处理可变长度序列，缺乏对**固定长度序列中固有结构模式（如空间关节相关性、时间帧连续性）的显式建模能力**。直接应用Transformer进行IMU姿态估计会导致严重的抖动和姿态不准确。
- **研究动机**：提出一种序列结构学习与调制方法，赋予Transformer利用固定长度序列结构信息的能力，以提高惯性姿态估计的准确性和稳定性。

## 2. 方法论

- **核心思想**：引入**序列结构模块（SSM）**，通过一个与输入内容无关的结构矩阵 \( S \in \mathbb{R}^{N \times N} \) 对Transformer的输入特征进行调制，使Transformer能够捕获并利用固定长度序列中的结构先验。
- **SSM模块流程**：
  1. 输入序列嵌入 \( X \in \mathbb{R}^{N \times d} \)。
  2. 与结构矩阵 \( S \) 相乘：\( SX \)。
  3. 经过层归一化（LN）和多层感知机（MLP）得到增强特征 \( \tilde{X} = \text{MLP}(\text{LN}(SX)) \)。
  4. 将 \( \tilde{X} \) 送入后续Transformer编码器。
- **结构矩阵的三种类型**：
  - **显式结构（ES）**：基于先验知识预设（例如用统计相关矩阵表示空间关节相关性，或用线性递减函数表示时间帧距离）。
  - **隐式结构（IS）**：可学习矩阵 \( P \)，初始化后通过数据驱动优化：\( S_I = I + P \)。
  - **显式-隐式混合（EIHS）**：先验显式矩阵 \( S_E \) 加上可学习的偏移 \( P \)：\( S_{EI} = S_E + P \)。
- **针对惯性姿态估计的两个变体**：
  - **SSM-S**（空间）：采用 EIHS 方式。空间显式结构 \( S_{E-S} \) 由 AMASS 数据集计算各关节旋转的相关系数得到，捕捉肢体间协同运动模式。
  - **SSM-T**（时间）：采用 ES 方式。时间显式结构 \( S_{E-T} \) 基于帧间距离线性衰减函数：\( S_{E-T}(i,j) = \max(0, 1 - |i-j|/\sigma) \)，\( \sigma = 10 \) 为超参数，体现平滑先验。
- **整体网络架构**：输入为 \( T \) 帧 × \( N \) 个IMU × 12维测量值 → 线性嵌入 → SSM-S → 空间Transformer编码器 → SSM-T → 时间Transformer编码器 → 回归头输出全身关节点旋转。训练采用 MSE 损失。

## 3. 实验设计

- **数据集与场景**：
  - 合成数据集：AMASS（用于预训练）。
  - 真实数据集：DIP-IMU、TotalCapture（使用SMPL骨架）；AnDy、CIP、Emokine（使用Xsens骨架）。
  - 场景覆盖日常动作、工业动作、挑战性动作等。
- **基准与对比方法**：与当前SOTA方法对比：TransPose、TIP、PIP、DynaIP、PNP（部分实验）。
- **评估指标**：
  - SIP误差（上肢和上腿平均全局旋转误差，度）
  - 角度误差（所有关节平均全局旋转误差，度）
  - 位置误差（根关节对齐后的平均关节欧氏距离，cm）
  - 网格误差（SMPL网格顶点平均欧氏距离，cm）
  - 抖动（全局空间关节的平均 jerk，反映平滑性）

## 4. 资源与算力

- **训练资源**：单块 NVIDIA GeForce RTX 4090 GPU，PyTorch 2.0.0，CUDA 11.8。
- **训练设置**：batch size = 4096，优化器 AdamW，初始学习率 0.0001，每 epoch 衰减 0.99。
- **实时演示**：笔记本配置 Intel® Core™ i9-13900HX CPU + NVIDIA GeForce RTX 4060 GPU。
- **说明**：论文未明确报告总训练时长。

## 5. 实验数量与充分性

- **主要对比实验**：在4个数据集（DIP-IMU, TotalCapture, AnDy, CIP）上报告了多个指标，与5种以上SOTA方法比较，结果表格详尽。
- **消融实验**：
  - 不同结构类型组合（IS/ES/EIHS）对SSM-S和SSM-T的影响（9种组合，表4）。
  - 超参数 \( \sigma \) 对时间结构的影响（7个值，表5）。
  - 单独添加SSM-S和SSM-T的贡献（表3）。
  - 时间结构另一种定义（式(18)）的比较（表6）。
  - 空间-时间编码器顺序交换（SE-TE vs. TE-SE，表7）。
- **泛化性实验**：
  - 增加传感器数量（从6个到10个，表8），验证SSM的通用性。
  - 不同体型的用户（按BMI分组，表9, 10），验证鲁棒性。
  - 与其他网络结构（GCN+Conv1d）对比（表11）。
- **评估**：实验设计全面，覆盖多数据集、多指标、多种消融场景，对比方法均为近年顶级工作，结果公平客观。但未报告误差棒或统计显著性检验，可重复性良好。

## 6. 主要结论与发现

- 所提方法在四个基准数据集上均大幅超越现有SOTA：DIP-IMU上SIP误差降低44%，TotalCapture上降低44%，AnDy降低49%，CIP降低29%。
- **SSM-S**主要通过注入空间关节相关性信息提升姿态预测的**准确性**（降低角度误差）。
- **SSM-T**主要通过注入帧间平滑先验降低**抖动**，提升运动序列的稳定性。
- 结合两者可实现精度与稳定性的最佳平衡（以复合指标 \( \tau = \text{Ang Err} \times e^{\text{Jitter}} \) 衡量）。
- 定性展示（图4）和实时演示也验证了方法的有效性和泛化能力。

## 7. 优点

- **创新性**：明确指出原生Transformer在固定长度序列建模中的结构偏差缺失，并提出简单有效的解决方案（SSM）。
- **设计巧妙**：SSM模块结构简单（一个矩阵乘积+LN+MLP），易于嵌入现有Transformer架构，且支持多种结构先验（显式/隐式/混合）。
- **效果显著**：在多个指标上实现超过13%~49%的性能提升，尤其大幅降低抖动，视觉效果更稳定。
- **实验充分**：消融全面，泛化验证（更多传感器、不同体型、不同网络结构）展示了方法的鲁棒性。
- **可解释性**：可视化了空间结构矩阵（图6），展示了先验与学习调整的交互，符合直观理解。

## 8. 不足与局限

- **缺乏全局平移**：方法只估计人体姿态（旋转），未恢复全局轨迹。作者指出纯IMU漂移限制，建议结合其他传感器。
- **显式结构构造依赖领域知识**：空间结构基于AMASS统计结果，时间结构基于线性衰减假设，对其他任务可能需要重新设计，通用性有待验证。
- **未报告统计误差**：缺少多次运行的误差棒或置信区间，实验结果的稳定性和可复现性需进一步确认。
- **计算资源披露不完整**：未说明完整训练时长或推理速度（虽然展示了实时演示），对实际部署的算力需求描述不够详细。
- **传感器数量与位置固定**：主要测试了6个IMU的配置，虽额外验证了10个，但未探讨不同传感器布局下的表现，可能对位置敏感。
- **应用限制**：当前方法针对人体姿态估计，对其他固定长度序列任务（如音频、金融时间序列）的泛化未验证。

（完）
