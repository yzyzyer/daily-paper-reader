---
title: "HOI-Swap: Swapping Objects in Videos with Hand-Object Interaction Awareness"
title_zh: HOI-Swap：具有手物交互感知的视频物体替换
authors: "Zihui Xue, Mi Luo, Changan Chen, Kristen Grauman"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=GkHXBasQwm"
tags: ["query:hoi"]
score: 4.0
evidence: 具有手物交互感知的视频物体替换
tldr: 为了解决视频中物体替换时手物交互细节丢失的问题，提出HOI-Swap框架，采用两阶段自监督扩散模型：首阶段在单帧中实现对象替换同时调整交互模式，第二阶段保证时序一致性，在多种HOI视频上实现高质量交互感知的对象替换，虽不直接进行姿态估计，但为HOI理解贡献了新方法。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1428, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 809, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1366, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1379, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1447, \"height\": 2308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1439, \"height\": 2297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1157, \"height\": 977, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1016, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1445, \"height\": 1166, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1443, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1444, \"height\": 1166, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gkhxbasqwm/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1446, \"height\": 514, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-gkhxbasqwm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1462, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gkhxbasqwm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gkhxbasqwm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1541, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gkhxbasqwm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1499, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gkhxbasqwm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1221, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gkhxbasqwm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1203, \"height\": 234, \"label\": \"Table\"}]"
motivation: 现有视频编辑方法难以处理手物交互的细微变化，导致替换不真实。
method: 提出两阶段自监督扩散框架，首阶段单帧对象替换同时调整交互模式，第二阶段时序一致性优化。
result: 在多种HOI视频上实现高质量交互感知的对象替换。
conclusion: 该工作为手物交互感知的视频编辑提供了新方法，虽不直接估计姿态但对HOI理解有贡献。
---

## Abstract
We study the problem of precisely swapping objects in videos, with a focus on those interacted with by hands, given one user-provided reference object image. Despite the great advancements that diffusion models have made in video editing recently, these models often fall short in handling the intricacies of hand-object interactions (HOI), failing to produce realistic edits---especially when object swapping results in object shape or functionality changes. To bridge this gap, we present HOI-Swap, a novel diffusion-based video editing framework trained in a self-supervised manner.  Designed in two stages, the first stage focuses on object swapping in a single frame with HOI awareness; the model learns to adjust the interaction patterns, such as the hand grasp, based on changes in the object's properties. The second stage extends the single-frame edit across the entire sequence; we achieve controllable motion alignment with the original video by: (1) warping a new sequence from the stage-I edited frame based on sampled motion points and (2) conditioning video generation on the warped sequence. Comprehensive qualitative and quantitative evaluations demonstrate that HOI-Swap significantly outperforms existing methods, delivering high-quality video edits with realistic HOIs.

---

## 论文详细总结（自动生成）

# 详细中文总结：HOI-Swap

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：视频中常出现手与物体交互的场景（如手拿水壶移动）。现有视频编辑方法（如扩散模型）在替换这类与手交互的物体时，难以处理手物交互（HOI）的细微变化，例如手部抓握方式需随物体形状/功能改变而调整，导致替换结果不真实。
- **核心问题**：如何根据用户提供的一张参考对象图像，精准替换视频中与手交互的物体，同时保持自然的HOI、空间对齐和可控的时序对齐。
- **整体含义**：该工作首次系统研究视频中“交互中的物体替换”问题，提出两阶段自监督扩散框架，填补了当前生成模型在HOI复杂场景下的能力空白，具有应用于娱乐、广告、机器人数据增强等领域的潜力。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：将任务分解为两个阶段，分别处理HOI感知与空间对齐（第一阶段）和时序对齐（第二阶段），采用自监督训练（无需配对视频）。
- **第一阶段（Stage I）：单帧HOI感知对象替换**
  - 输入：源帧 $I_i$、方形边界框掩码 $M_i$、参考对象图像 $I_{ref}$。
  - 训练数据构造：从同一视频中随机选取另一帧的对象图像作为参考，并施加强数据增强（旋转、翻转、透视变换等）；用文本引导修补模型去除遮挡部分。
  - 模型：基于潜在扩散模型（LDM），使用DINO编码器提取参考对象特征 $d_{obj}$ 通过交叉注意力注入；掩码帧 $I_m$ 经VAE编码后与噪声潜在变量通道拼接，输入UNet $\epsilon_{\theta_1}$。
  - 损失函数：$\mathcal{L}_{\text{stageI}} = \mathbb{E}_{z,z_m,d_{obj},\epsilon,t} \left[ \|\epsilon - \epsilon_{\theta_1}(z_t, z_m, d_{obj}, t)\|_2^2 \right]$。
- **第二阶段（Stage II）：可控运动引导视频生成**
  - 输入：第一阶段的编辑帧 $I^*_i$、源视频 $V$、掩码序列。
  - 运动引导：在编辑帧的掩码区域内均匀采样 $r\%$ 像素点，用RAFT光流跟踪到其他帧，以编辑帧为锚点扭曲生成稀疏/不完整的视频序列 $V_{warp}$。
  - 模型：视频LDM，将2D UNet膨胀为3D UNet（插入时序层），输入噪声视频潜在 $z_t$ 与扭曲序列潜在 $z_w$ 通道拼接，CLIP编码器提取锚点帧特征 $d_c$ 通过交叉注意力注入。
  - 损失函数：$\mathcal{L}_{\text{stageII}} = \mathbb{E}_{z,z_w,d_c,\epsilon,t} \left[ \|\epsilon - \epsilon_{\theta_2}(z_t, z_w, d_c, t)\|_2^2 \right]$。
  - **可控性**：训练时采样点稀疏度 $r$ 从0到100随机变化；推理时用户可根据对象变化程度调节 $r$（变化大则少采样，变化小则多采样）。

## 3. 实验设计

- **数据集**：
  - 训练：HOI4D（2679个视频，79.9K帧，16类物体）、Ego-Exo4D（18.7K帧，18类常用物体）。
  - 评估：图像编辑：1250源图像 × 4参考对象 = 5000编辑图像（含20%无手场景）；视频编辑：25源视频 × 4参考对象 = 100编辑视频（含HOI4D、EPIC-Kitchens、TCN Pouring等零样本场景）。
- **Baseline**：
  - 图像编辑：Paint by Example（PBE）、AnyDoor、Afford Diffusion（HOI领域）。
  - 视频编辑：Per-frame（最佳图像baseline逐帧应用）、AnyV2V（结合AnyDoor）、VideoSwap（SOTA对象替换）。
- **评估指标**：
  - 自动指标：接触一致性、手部交并比、手部真实度（图像）；主体一致性、运动平滑度（VBench）（视频）。
  - 用户研究：15名参与者，对260图像编辑和100视频编辑进行偏好投票（随机打乱HOI-Swap与三个baseline）。

## 4. 资源与算力

- **GPU型号**：NVIDIA V100 32G。
- **数量与训练时长**：使用8卡节点（8×V100）。
  - Stage I：训练25K步，约3天。
  - Stage II：训练50K步，约3天。
- **推理**：光流提取（RAFT）仅需数秒/视频，整体推理效率高。
- **说明**：文中明确给出了GPU型号、数量及训练天数。

## 5. 实验数量与充分性

- **实验数量**：
  - 图像编辑：1个定量表（Table 1）、多个定性图（图4、图9-10）、用户研究。
  - 视频编辑：1个定量表（Table 1）、多个定性图（图4、图15）、消融实验（运动点稀疏度、两阶段 vs 单阶段、编码器选择、掩码策略、编辑帧选择、采样区域讨论、与文本引导方法对比等）。
  - 额外消融：表5（DINO vs CLIP编码器）、表6（真实框 vs SAM-2自动框）。
  - 不同数据划分：表2（按主体/动作划分）、表3（域内/域外分解）。
- **充分性与公平性**：
  - 定量指标覆盖HOI、图像质量、视频质量多维度。
  - 用户研究采用随机打乱、多人评估，包含“都不满意”选项避免偏见。
  - 与baseline对比时使用官方代码及最佳超参，且baseline要求更严格的输入（如分割掩码、文本提示、每视频点击点），HOI-Swap仅需边界框，实验设置公平。
  - 消融实验设计全面，验证了各组件有效性。
  - **结论**：实验充分、客观、公平，但视频评估集规模较小（25源视频），因baseline如VideoSwap需要大量预处理。

## 6. 论文的主要结论与发现

- **HOI-Swap在图像编辑和视频编辑任务上均显著超越现有方法**：
  - 图像编辑：用户偏好率72.1%，远高于PBE（4.5%）、AnyDoor（15.6%）、Afford Diff（7.6%）。
  - 视频编辑：用户偏好率86.4%，远高于Per-frame（0.2%）、AnyV2V（1.2%）、VideoSwap（1.2%）。
- **两阶段设计优于单阶段**：单阶段无法同时处理空间和时序对齐，两阶段分别解决，提升编辑质量。
- **可控运动引导有效**：通过调节采样点稀疏度，可在保持运动对齐与允许运动自由之间灵活切换，适应不同对象变化。
- **自监督训练成功**：无需配对视频，利用同一视频不同帧的对象图像作为参考即可学习HOI感知和时空对齐。
- **零样本泛化能力**：在未见过的数据集（EPIC-Kitchens、TCN Pouring）上也能生成合理结果。

## 7. 优点

- **方法创新**：
  - 首次系统解决视频中交互物体替换问题，提出两阶段分解策略，降低生成难度。
  - 可控运动引导：通过采样点稀疏度实现运动对齐的灵活控制，适应不同对象变化。
  - 自监督训练：无需人工标注配对数据，利用同一视频内的对象图像，扩展性强。
  - 仅需边界框输入，比baseline要求更低（如分割掩码、文本提示）。
- **实验设计**：
  - 全面的定量+定性+用户研究评估，覆盖HOI、图像质量、视频质量等多个维度。
  - 多个消融实验验证各组件有效性（两阶段、运动点、编码器、掩码策略等）。
  - 包含域内和域外场景的零样本测试，泛化性验证充分。
  - 用户研究设置“都不满意”选项，避免强制选择偏差。
- **结果优异**：在自动指标和人类偏好上均大幅超越现有SOTA。

## 8. 不足与局限

- **泛化到全新对象有限**：当参考对象类型在训练集中未出现（如剪刀）时，模型可能无法准确描绘手部交互，需具备“世界知识”。
- **长视频复杂交互处理不足**：两阶段设计假设HOI在短片段内稳定，但长视频中物体可能经历多次不同手部交互，需要更复杂的时序建模。
- **可控性需进一步加强**：当前只有全局运动点稀疏度控制，未来可探索空间特定区域控制（如仅对物体某部分转移运动）。
- **采样点可能携带错误运动**：当新旧物体形状差异大时，采样点可能将背景点误判为前景，导致扭曲序列有噪声；虽模型有一定鲁棒性，但高采样密度下仍有失败风险（见图16）。
- **视频评估集规模较小**：仅25源视频（100编辑视频），主要因baseline（如VideoSwap）需要每视频点击点和文本描述，预处理成本高。
- **计算成本**：训练需8×V100约6天（两阶段合计），但推理较快。
- **潜在社会影响**：可能被用于制作误导性视频，但作者建议使用水印和噪声扰动防御。

（完）
