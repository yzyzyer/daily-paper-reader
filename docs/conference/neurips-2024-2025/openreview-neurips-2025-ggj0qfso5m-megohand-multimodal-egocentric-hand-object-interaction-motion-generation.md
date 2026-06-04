---
title: "MEgoHand: Multimodal Egocentric Hand-Object Interaction Motion Generation"
title_zh: MEgoHand：多模态自我中心手-物交互运动生成
authors: "Bohan Zhou, Yi Zhan, Zhongbin Zhang, Zongqing Lu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=GGj0QFSo5m"
tags: ["query:hoi"]
score: 9.0
evidence: 多模态自我中心手-物交互运动生成
tldr: 针对自我中心手-物交互运动生成中视角不稳定、自遮挡和物体泛化限制等问题，本文提出MEgoHand多模态框架。它融合RGB、文本和初始手部姿态，通过双向关联建模手-物相关性，生成物理合理的交互运动。实验证明MEgoHand在生成质量和泛化性上优于现有方法，为虚拟现实和机器人模仿提供了新方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1376, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 543, \"height\": 301, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1147, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1377, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1267, \"height\": 1204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1251, \"height\": 695, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 757, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1393, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1215, \"height\": 783, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ggj0qfso5m/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1478, \"height\": 1415, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ggj0qfso5m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 865, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ggj0qfso5m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ggj0qfso5m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 739, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ggj0qfso5m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 510, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ggj0qfso5m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 587, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ggj0qfso5m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1049, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ggj0qfso5m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 458, \"label\": \"Table\"}]"
motivation: 现有方法依赖预定义3D物体先验，限制了对新颖物体的泛化能力。
method: 提出MEgoHand，利用多模态输入和双向关联模块建模手-物交互。
result: 在多个基准上生成更真实且泛化性更强的交互运动。
conclusion: MEgoHand有效解决了自我中心HOI运动生成的泛化问题。
---

## Abstract
Egocentric hand-object motion generation is crucial for immersive AR/VR and robotic imitation but remains challenging due to unstable viewpoints, self-occlusions, perspective distortion, and noisy ego-motion. Existing methods rely on predefined 3D object priors, limiting generalization to novel objects, which restricts their generalizability to novel objects. Meanwhile, recent multimodal approaches suffer from ambiguous generation from abstract textual cues, intricate pipelines for modeling 3D hand-object correlation, and compounding errors in open-loop prediction. We propose **MEgoHand**, a multimodal framework that synthesizes physically plausible hand-object interactions from egocentric RGB, text, and initial hand pose. MEgoHand introduces a bi-level architecture: a high-level “cerebrum” leverages a vision language model (VLM) to infer motion priors from visual-textual context and a monocular depth estimator for object-agnostic spatial reasoning, while a low-level DiT-based flow-matching policy generates fine-grained trajectories with temporal orthogonal filtering to enhance stability. To address dataset inconsistency, we design a dataset curation paradigm with an Inverse MANO Retargeting Network and Virtual RGB-D Renderer, curating a unified dataset of **3.35M** RGB-D frames, **24K** interactions, and **1.2K** objects. Extensive experiments across **five** in-domain and **two** cross-domain datasets demonstrate the effectiveness of MEgoHand, achieving substantial reductions in wrist translation error (**86.9%**) and joint rotation error (**34.1%**), highlighting its capacity to accurately model fine-grained hand joint structures and generalize robustly across diverse scenarios.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：自我中心视角（第一人称）的手-物交互（HOI）运动生成对沉浸式AR/VR和机器人模仿学习至关重要。然而，这一任务面临四大挑战：
  - 摄像机随头部运动导致视角不稳定，破坏空间一致性；
  - 用户自身身体频繁遮挡手或物体，造成视觉信息缺失；
  - 近距离拍摄带来强烈透视畸变和尺度快速变化；
  - 需要将有意的手部运动与头部自我运动（ego-motion）分离，推理难度大。
- **现有方法局限**：
  - 依赖预定义3D物体属性（质量、几何等）的方法（如GEARS、MACS）无法泛化到新物体；
  - 多模态方法（如LatentAct）虽然结合文本和图像，但需要手工设计接触图生成流水线，实用性差；
  - 大多数方法采用开环预测（仅基于第一帧），误差随时间累积导致级联失败。

---

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：提出**MEgoHand**——一个多模态框架，输入包括RGB图像、文本指令和初始手部姿态（MANO参数），输出物理合理的手-物交互运动序列。采用**双层架构**：
  - **高层“大脑”**：利用视觉-语言模型（VLM，基于Eagle-2）从视觉和文本上下文中推断运动先验；并集成单目度量深度估计器（UniDepthV2）进行物体无关的3D空间推理，增强对深度关系的理解。
  - **低层“小脑”**：基于DiT（扩散Transformer）的流匹配（flow matching）策略生成细粒度手部轨迹；并设计**时间正交滤波（TOF）**解码策略：对相邻帧的重叠预测结果进行时域卷积和SVD投影，抑制抖动，提升时间稳定性。
- **关键技术细节**：
  - **手部表示**：MANO模型参数化（形状β、手指旋转θ、腕部旋转r和平移t），采用6D旋转表示。
  - **公式化**：条件流匹配损失训练生成器，推理时从高斯噪声通过欧拉法逐步去噪得到未来l帧的MANO参数。
  - **数据集统一**：
    - **逆MANO重定向网络**：两阶段训练（先优化手形，再优化腕部姿态），从3D关节位置恢复MANO参数，用于标注缺乏MANO参数的早期数据集（如FPHA）。
    - **虚拟RGB-D渲染器**：为只提供RGB的数据集（如ARCTIC、HOT3D）生成对齐的深度图。
  - 最终整合成包含**3.35M帧、24K交互轨迹、1.2K物体**的统一多模态数据集。

---

### 3. 实验设计：数据集/场景、Benchmark、对比方法

- **数据集**：
  - **训练集**（6个）：TACO、FPHA、HOI4D、H2O、HOT3D、OakInk2（其中FPHA重新标注后仅用于评估）。
  - **域内评估集**：从5个训练数据集各留出10%（保证动作或物体类别不重叠）。
  - **跨域测试集**：完整ARCTIC数据集、HOLO数据集的10%部分（参考LatentAct划分）。
- **Benchmark指标**：
  - MPJPE（平均每关节位置误差）、MPJPE-PA（Procrustes对齐后）、MPVE（平均每顶点误差）、MPVE-PA、MWTE（平均腕部平移误差）、MRE（平均旋转误差，弧度）。
- **对比方法**：
  - **LatentAct**（Transformer基线）及其扩散变体LatentAct-Diff；
  - 去除接触图的LatentAct变体；
  - MEgoHand的多种模态配置（仅文本、仅RGB、RGB+深度、文本+RGB、全模态）。

---

### 4. 资源与算力

- **训练**：8×80GB NVIDIA A800 GPU，训练约24小时。
- **评估与可视化**：单张80GB A800 GPU，约3小时。
- **推理效率**：在单张RTX 4090上生成16帧序列，MEgoHand耗时74ms（13.5 FPS），显存5.8GB；而LatentAct需156ms（6.4 FPS），显存10.8GB（附录A.6表2）。

---

### 5. 实验数量与充分性

- **实验数量**：
  - 域内评估：5个数据集的平均指标（表1）；
  - 跨域评估：2个数据集（ARCTIC、HOLO）的零样本迁移结果（表2）；
  - 消融实验：
    - 不同模态组合（表1中绿色部分：T、I、ID、TI、全模态）；
    - 不同深度估计器（UniDepthV2 vs. DepthAnythingV2）；
    - 有无深度监督；
    - 相对深度 vs. 度量深度（表3）；
  - 每个数据集单独指标（附录C表3）；
  - 视觉展示（图5、图6及附录图5）。
- **充分性与公平性**：
  - 对比方法采用了强基线LatentAct及其变体，并确保与它们使用相同的初始手部姿态；
  - 消除了接触图等额外输入的影响（本文方法不需要接触图）；
  - 消融实验覆盖了关键设计选择（深度模块、文本引导、TOF等）；
  - 跨域测试验证泛化能力，且报告了误差条（图4），统计可靠性较好。

---

### 6. 论文的主要结论与发现

- MEgoHand在域内和跨域评估中均**显著优于所有基线**：
  - 手腕平移误差降低**86.9%**，关节旋转误差降低**34.1%**；
  - Procrustes对齐后，关节误差（MPJPE-PA）降至**0.424cm**，网格顶点误差（MPVE-PA）降至**0.409cm**，相对改进分别为**71.2%** 和**71.9%**。
- 消融实验表明：
  - **文本+RGB+深度**全模态效果最佳；
  - 深度信息是关键：无深度监督或使用相对深度均导致性能下降；
  - 度量深度在域内更好，但跨域时对相机参数变化敏感，相对深度反而更鲁棒（在HOLO上）。
- 跨域零样本迁移中，MEgoHand在ARCTIC和HOLO上分别比最强基线提升**33.9%** 和**29.8%** MPJPE，展现了强泛化能力。

---

### 7. 优点

- **创新性**：首次将VLM与单目深度估计相结合用于自我中心HOI运动生成，避免了传统方法对物体模型的依赖；
- **实用性**：设计了统一数据集预处理流水线（逆MANO重定向 + 虚拟RGB-D渲染），解决了多数据集不一致问题，方便后续研究；
- **高效性**：推理速度是LatentAct的两倍以上，显存占用减少近一半，更适合实时应用；
- **全面性**：在7个数据集（5个域内+2个跨域）上进行了详尽评估，消融实验系统深入，结果稳健。

---

### 8. 不足与局限

- **数据规模可进一步提升**：作者指出可利用逆MANO网络标注更多HOI数据集或使用现代手部检测器标注野外视频，以扩大训练数据（当前为3.35M帧，但动作种类和物体数量仍有增长空间）。
- **仅考虑右手运动**：论文明确只处理右手交互，未涉及双手或左手交互，限制了应用场景。
- **深度估计的局限性**：度量深度对跨域相机参数敏感（在ARCTIC上表现不如相对深度），表明单目深度估计的泛化仍有提升空间。
- **开环预测的固有问题**：尽管TOF提供了时域平滑，但框架本质上仍基于滑动窗口预测未来l帧，对于长程运动规划可能存在误差累积（但相比纯开环已有改善）。
- **未涉及物理仿真验证**：虽然提到“物理合理”，但实验仅基于几何指标评估，未在物理仿真器中验证交互的接触稳定性或穿透程度。

（完）
