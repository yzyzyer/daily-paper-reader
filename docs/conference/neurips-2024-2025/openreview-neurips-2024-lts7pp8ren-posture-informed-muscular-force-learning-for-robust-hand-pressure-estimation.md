---
title: Posture-Informed Muscular Force Learning for Robust Hand Pressure Estimation
title_zh: 姿态信息辅助的肌肉力学习实现鲁棒手部压力估计
authors: "Kyungjin Seo, Junghoon Seo, Hanseok Jeong, Sangpil Kim, Sang Ho Yoon"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=LtS7pP8rEn"
tags: ["query:hoi"]
score: 6.0
evidence: 手物交互中利用手部姿态估计压力
tldr: 针对手物交互中压力估计不准确的问题，本文提出PiMForce框架，融合3D手部姿态和表面肌电信号，实现鲁棒的全手压力测量。该方法利用姿态信息增强肌肉信号，在多种交互场景下表现优异。实验表明，PiMForce显著提升了压力估计精度，为触觉反馈和人机交互提供了新途径。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1420, \"height\": 977, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1395, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1252, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1289, \"height\": 844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1411, \"height\": 1068, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1430, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1447, \"height\": 926, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 435, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 898, \"height\": 1207, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1445, \"height\": 795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 729, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1433, \"height\": 1543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1433, \"height\": 1536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1435, \"height\": 1562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1436, \"height\": 1068, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1426, \"height\": 1761, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1423, \"height\": 1756, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1426, \"height\": 1758, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1427, \"height\": 1195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lts7pp8ren/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 936, \"height\": 1508, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1328, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1161, \"height\": 850, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 873, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lts7pp8ren/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1445, \"height\": 264, \"label\": \"Table\"}]"
motivation: 现有手部压力估计方法在复杂手物交互中准确性不足。
method: 结合3D手部姿态和表面肌电信号，通过多模态融合学习压力映射。
result: 在21名参与者数据集上压力估计准确率显著提升。
conclusion: PiMForce证明手部姿态信息对压力估计有重要辅助作用。
---

## Abstract
We present PiMForce, a novel framework that enhances hand pressure estimation by leveraging 3D hand posture information to augment forearm surface electromyography (sEMG) signals. Our approach utilizes detailed spatial information from 3D hand poses in conjunction with dynamic muscle activity from sEMG to enable accurate and robust whole-hand pressure measurements under diverse hand-object interactions. We also developed a multimodal data collection system that combines a pressure glove, an sEMG armband, and a markerless finger-tracking module. We created a comprehensive dataset from 21 participants, capturing synchronized data of hand posture, sEMG signals, and exerted hand pressure across various hand postures and hand-object interaction scenarios using our collection system. Our framework enables precise hand pressure estimation in complex and natural interaction scenarios. Our approach substantially mitigates the limitations of traditional sEMG-based or vision-based methods by integrating 3D hand posture information with sEMG signals.
Video demos, data, and code are available online.

---

## 论文详细总结（自动生成）

# 论文总结：Posture-Informed Muscular Force Learning for Robust Hand Pressure Estimation

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：在复杂手物交互场景中，如何准确、鲁棒地估计全手（指尖至掌心）的压力分布？传统方法存在明显局限：
  - **sEMG 单独使用**：不同手部姿态可能产生相似的肌肉激活信号，导致压力估计混淆；且通常只能估计有限手指或抓握力，无法覆盖全手。
  - **纯视觉方法**：需要无遮挡的手部图像，在抓握物体、部分手指被遮挡时失效；且仅适用于与平面交互的场景。
- **研究动机**：手部压力信息在人机交互（AR/VR）、触觉反馈、康复、假肢控制等领域有重要应用。现有非侵入式传感技术（如腕部压力传感、sEMG）或纯视觉方法均缺乏足够的鲁棒性和细粒度。作者认为，**3D 手部姿态提供了精细的空间信息，而 sEMG 提供了动态肌肉活动信息**，两者互补，有望实现更精确、鲁棒的全手压力估计。
- **整体含义**：本文提出 **PiMForce**，首次将 3D 手部姿态信息与 sEMG 信号深度融合，克服了单一模态的缺陷，实现了在手物交互中（包括多种抓取、按压、捏合等动作）的全手压力连续估计，并构建了首个包含同步手部姿态、sEMG 和压力真值的多模态数据集。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
利用 3D 手部姿态信息增强 sEMG 特征，使模型能够区分相同肌肉激活模式下不同姿态对应的不同压力分布。整体架构为端到端的多模态深度学习模型，包含三个主要模块：

- **sEMG 特征提取器**：对 8 通道 sEMG 信号进行短时傅里叶变换（STFT），得到时频谱图（尺寸 8×32×64），然后通过 2D 编码器-解码器 CNN 提取 512 维特征向量。
- **手部姿态特征提取器**：将 15 个关节角度（θ∈ℝ¹⁵×³）通过正运动学转换为 21 个 3D 关节坐标（J∈ℝ²¹×³），再离散化为 3D 热图体积（H∈[0,1]²¹×⁴⁸×⁴⁸×⁴⁸），输入 3D ResNet34 提取 512 维特征向量。
- **特征融合与预测**：将两个 512 维特征拼接为 1024 维，经两层全连接（256 维 + BN + ReLU）、最后一层 Sigmoid 输出 I 维（I=9 个手部区域：5 指尖 + 4 掌心）的概率值 Ĉ，再通过 ReLU 映射为压力预测值（范围 [0,20] N）。

### 技术细节
- **联合训练分类与回归**：损失函数 L = L_c + λ·L_r，其中 L_c 为交叉熵分类损失（判断每个区域是否施压），L_r 为 L2 回归损失（量化压力大小）。λ 为平衡超参数。
- **数据同步**：对高速 sEMG（2000 Hz）与低速手部姿态（120 Hz）、压力数据（40 Hz）采用线性插值和最近邻插值进行时间对齐。
- **推理阶段**：训练时使用数据手套获取真值姿态和压力；推理时用户无需佩戴手套，利用现成的手部姿态检测器（如 ACR）从 RGB 图像提取 3D 姿态，并结合 sEMG 进行压力估计，实现自然交互。

## 3. 实验设计

### 数据集与场景
- **自建多模态数据集**：采集自 21 名右利手参与者（17 男 4 女，年龄 20–32 岁），包含 22 种手物交互动作（7 种手-平面按压、5 种捏合、10 种抓取）。每个动作重复 3 次，每次 30 秒，共计 1980 秒/人。总帧数 83.2M。
- **硬件**：65 节点压力手套（TactileGlove）+ 5 个指尖 FSR 传感器（采样 40 Hz），Manus 磁性手指追踪模块（120 Hz），8 通道 Delsys sEMG（2000 Hz）。

### Benchmark 与方法对比
- **对比方法**：
  1. **sEMG Only**[4]：仅使用 sEMG，压力范围 5→9 区域，架构同[4]。
  2. **3D Hand Posture Only**：仅使用 3D 手部姿态，去掉 sEMG 特征提取器。
  3. **sEMG + Hand Angles**：用关节角度 θ 替代 3D 姿态热图，输入 3 层全连接网络。
  4. **PressureVision++**[17]：纯视觉方法，估计指尖压力（预训练权重）。
  5. **PiMForce（Ours）**：本文方法。
- **评估指标**：R²（决定系数）、NRMSE（归一化均方根误差）、分类准确率（9 区域均正确分类）。还报告了 MAE。

### 实验设置
- **用户内实验**：每名参与者的 2 个 session 训练，1 个 session 测试。
- **跨用户实验**：17 人训练，4 人测试。
- **与 PressureVision++ 定量对比**：使用 Sensel 压力板和 Logitech 摄像头，5 名参与者，仅覆盖平面和捏合动作（因 PressureVision++ 不支持全手）。

## 4. 资源与算力

- **训练环境**：AMD EPYC 7763 64 核 CPU，1.0TB RAM，单块 NVIDIA RTX 6000A 48Gi 显卡。
- **训练时长**：约 12 小时（50 epochs，batch size=64，Adam 优化器，lr=0.0001）。
- **推理环境**：Intel i9-12900K，32GB RAM，NVIDIA RTX 4080 16GB。
- **模型参数量**：总计约 66.17M（sEMG 特征提取器 1.26M，姿态特征提取器 64.11M）。
- **推理速度**：单 batch 4ms，支持实时处理（256 流 batch 无延迟）。

## 5. 实验数量与充分性

- **实验组数**：包含用户内、跨用户、与 vision 方法定量对比共三组主要实验；另有手部区域细粒度分析、姿态类型（按压/捏合/抓取）分类性能、以及时序可视化。
- **消融实验**：对比了 sEMG Only、姿态 Only、sEMG+角度、本文完整模型，充分验证了各模态贡献。
- **充分性评价**：实验设计较为全面，覆盖了多种交互类型，跨用户验证了泛化性，且与最先进的 vision 方法进行了公平比较（使用相同硬件和采集协议）。数据量较大（83.2M 帧），参与人数 21（虽然性别比例不平衡）。
- **公平性**：对比方法中，sEMG Only 和 sEMG+Angles 使用了与本文相同的训练/测试划分；PressureVision++ 使用了官方预训练权重（跨用户评估），但注意其训练数据集与本文不同，可能存在偏差。

## 6. 主要结论与发现

1. **PiMForce 显著优于单一模态方法**：用户内实验中，R²=88.86%，NRMSE=6.65%，分类准确率 83.17%，均大幅超过 sEMG Only（R²=83.49%，准确率 77.83%）和姿态 Only（准确率 70.08%）。
2. **引入 3D 姿态热图比直接用关节角度更有效**：sEMG+角度比 sEMG Only 提升微弱（<0.5%p），而完整模型提升显著（准确率 +5.34%p 相对于 sEMG Only）。
3. **全手压力估计中手掌区域受益更大**：加入姿态信息后，手掌区域 NRMSE 改善（+1.95%p）高于指尖（+1.05%p），说明姿态对区分不同抓取的手掌压力分布尤为关键。
4. **跨用户泛化性明显增强**：R² 从 47.90%（sEMG Only）提升至 70.06%，准确率从 57.40% 提升至 72.01%。
5. **与纯视觉方法相比优势突出**：在平面和捏合场景下，PiMForce 准确率 82.20%，远高于 PressureVision++ 的 67.90% 和 sEMG Only 的 66.00%。

## 7. 优点

- **创新性**：首次将 3D 手部姿态信息与 sEMG 结合进行全手压力估计，解决了肌肉信号混淆的问题。
- **多模态数据集**：构建了包含姿态、sEMG、压力真值的同步数据集，为后续研究提供基础。
- **实用化设计**：推理时无需数据手套，仅需 RGB 相机和 sEMG 臂环，易于部署和用户接受。
- **联合分类-回归训练**：同时区分有无压力及精确量化，提高了整体性能。
- **实时性**：推理仅需 4ms，满足交互应用需求。

## 8. 不足与局限

- **姿态估计依赖**：推理时需要准确的 3D 手部姿态（来自 RGB 图像），若现成检测器精度不足（如严重遮挡），可能导致压力估计错误。
- **部分姿态性能较低**：如 Palm-Press（准确率 68.42%）和复杂抓取（Power Sphere、Fixed Hook）表现相对较差，说明对某些动作泛化不足。
- **数据集局限性**：
  - 仅 21 名参与者，且 81% 为男性，手型偏大（>180mm），缺乏多样性，可能引入人口统计偏差。
  - 未覆盖全部 33 种抓取类型（仅选 10 种），也未包含手部网格和物体网格信息。
  - 缺乏长时间疲劳数据或动态连续动作的测试。
- **模态融合方式简单**：仅采用特征拼接，未探索注意力机制或分层融合等更复杂的方法。
- **与 PressureVision++ 对比不完全公平**：虽然使用了相同硬件和采集协议，但 PressureVision++ 训练数据与本文不同，且只能估计指尖（无法对比掌心）。
- **sEMG 个体差异**：跨用户性能虽有提升，但仍存在一定差距（准确率从 83% 下降到 72%），表明仍需更多适应策略。

（完）
