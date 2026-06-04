---
title: "EgoChoir: Capturing 3D Human-Object Interaction Regions from Egocentric Views"
title_zh: EgoChoir：从自我中心视角捕捉3D人-物交互区域
authors: "Yuhang Yang, Wei Zhai, Chengfeng Wang, Chengjun Yu, Yang Cao, Zheng-Jun Zha"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=ea4oxkiMP7"
tags: ["query:hoi"]
score: 9.0
evidence: 自我中心视角的人-物交互3D区域捕捉
tldr: 针对自我中心视角下人-物交互（HOI）的不完整观察导致歧义的问题，本文提出EgoChoir方法，从自我中心视角捕捉3D交互区域。该方法利用视觉和运动线索，在3D空间中准确定位交互发生的位置。实验表明，EgoChoir在多个数据集上优于现有方法，为增强现实和具身AI提供了关键的空间感知能力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1336, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1313, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1420, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1442, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1405, \"height\": 1198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1398, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1297, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 1388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1437, \"height\": 1077, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ea4oxkimp7/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1446, \"height\": 297, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-ea4oxkimp7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ea4oxkimp7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ea4oxkimp7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 713, \"height\": 119, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ea4oxkimp7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ea4oxkimp7/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 551, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ea4oxkimp7/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 573, \"height\": 201, \"label\": \"Table\"}]"
motivation: 现有方法主要从外部视角捕捉交互区域，但自我中心视角下观察不完整导致歧义。
method: 提出EgoChoir，结合视觉和运动线索从自我中心视频中推断3D交互区域。
result: 在多个数据集上显著优于现有方法，准确捕捉交互空间位置。
conclusion: EgoChoir有效解决了自我中心HOI的区域捕捉问题，支持AR/VR应用。
---

## Abstract
Understanding egocentric human-object interaction (HOI) is a fundamental aspect of human-centric perception, facilitating applications like AR/VR and embodied AI. For the egocentric HOI, in addition to perceiving semantics e.g., ''what'' interaction is occurring, capturing ''where'' the interaction specifically manifests in 3D space is also crucial, which links the perception and operation. Existing methods primarily leverage observations of HOI to capture interaction regions from an exocentric view. However, incomplete observations of interacting parties in the egocentric view introduce ambiguity between visual observations and interaction contents, impairing their efficacy. From the egocentric view, humans integrate the visual cortex, cerebellum, and brain to internalize their intentions and interaction concepts of objects, allowing for the pre-formulation of interactions and making behaviors even when interaction regions are out of sight. In light of this, we propose harmonizing the visual appearance, head motion, and 3D object to excavate the object interaction concept and subject intention, jointly inferring 3D human contact and object affordance from egocentric videos. To achieve this, we present EgoChoir, which links object structures with interaction contexts inherent in appearance and head motion to reveal object affordance, further utilizing it to model human contact. Additionally, a gradient modulation is employed to adopt appropriate clues for capturing interaction regions across various egocentric scenarios. Moreover, 3D contact and affordance are annotated for egocentric videos collected from Ego-Exo4D and GIMO to support the task. Extensive experiments on them demonstrate the effectiveness and superiority of EgoChoir.

---

## 论文详细总结（自动生成）

# 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：从自我中心视角（egocentric view）捕捉3D人-物交互（HOI）的空间区域，包括人体接触点（human contact）和物体可供性（object affordance）。现有方法大多依赖外部视角（exocentric view）或完整观察，但自我中心视角下交互双方常被部分遮挡甚至完全不可见，导致视觉观察与交互内容之间存在歧义。
- **研究动机**：认知科学表明，人类通过视觉皮层、小脑和大脑协同，将视觉观察、自我运动（头部运动）和物体概念理解相结合，从而预形成交互意图和交互区域。受此启发，本文提出整合视觉外观、头部运动和3D物体几何信息，挖掘物体交互概念和主体意图，以从自我中心视频中推断3D交互区域。
- **整体含义**：该方法为自我中心HOI提供了关键的空间表征，支撑AR/VR、具身AI、交互建模、机器人操作等应用。

# 2. 论文提出的方法论
- **核心思想**：同时利用三种互补线索：视觉外观（视频帧）、头部运动（头戴设备轨迹）和3D物体点云，分别编码后通过平行交叉注意力机制互相查询，挖掘“物体交互概念”和“主体交互意图”，进而联合估计物体3D可供性和人体3D接触点。
- **关键技术细节**：
  - **模态特征提取**：
    - 视觉特征：使用HRNet提取每帧特征，再通过联合时空注意力（joint space-time attention）得到 \(F_V \in \mathbb{R}^{T \cdot 49 \times 768}\)。
    - 头部运动特征：计算相对头部姿态变化（平移差和旋转差），通过MLP构成的运动编码器 \(f_M\) 提取特征 \(F_M\)。该编码器通过最小化视觉特征差异与运动特征差异之间的KL散度进行预训练（损失 \(L_m\)），使运动特征携带变化信息。
    - 物体几何特征：使用DGCNN提取点云特征 \(F_O \in \mathbb{R}^{N \times 768}\)。
  - **物体交互概念建模**：在平行交叉注意力模块 \(\Theta_a\) 中，将功能语义token \(T_f\) 与物体特征 \(F_O\) 拼接作为查询，以视觉特征 \(F_V\) 和运动特征 \(F_M\) 作为两个关键-值对（分别经可学习调制token \(\tau_v, \tau_m\) 缩放后进行交叉注意力），得到可供性特征 \(F_a\) 和功能语义特征 \(F_{sf}\)。
  - **主体交互意图建模**：在平行交叉注意力模块 \(\Theta_c\) 中，将意图token \(T_i\) 与添加了时间位置编码的视觉特征 \(F_V\) 拼接作为查询，以可供性特征 \(F_a\) 和运动特征 \(F_M\)（均加时间编码）作为关键-值对（分别经调制token \(\tau_o, \tau_m\) 缩放），得到接触特征 \(F_c\) 和意图语义特征 \(F_{si}\)。
  - **解码与损失**：
    - 可供性特征 \(F_a\) 解码为物体可供性 \(\phi_a \in \mathbb{R}^{N \times 1}\)。
    - 接触特征 \(F_c\) 先映射特征维度再映射到SMPL顶点空间，得到人体接触 \(\phi_c \in \mathbb{R}^{T \times 6890 \times 1}\)。
    - 语义特征 \(F_s = [F_{sf}, F_{si}]\) 解码为交互类别 \(\phi_s\)。
    - 总损失 \(L = L_a + L_c + L_s\)，其中 \(L_a, L_c\) 为Focal Loss + Dice Loss，\(L_s\) 为交叉熵损失。
  - **梯度调制**：通过调制token（\(\tau_v, \tau_m, \tau_o\)）缩放输入特征，从而调节梯度，使模型在不同交互场景（如手部操作 vs 身体动作）中自适应选择合适的线索进行交互上下文提取。

# 3. 实验设计
- **数据集**：
  - 来源：从Ego-Exo4D和GIMO收集自我中心视频，涵盖12种交互（如抓取、切割、坐、躺等）与18种物体类别（如瓶子、碗、椅子、钢琴等），总计1570个视频片段，超过30万帧。
  - 3D物体实例：从多个3D数据集（Objaverse、AKB-48、ModelNet等）收集超过2万个与视频中物体类别对应的3D物体点云。
  - 标注：采用半自动方式标注人体接触点（在SMPL模型上绘制）和物体可供性（通过拉普拉斯传播标注高概率区域）。
- **基准与对比方法**：
  - 人体接触预测：BSTRO、DECO、LEMON。
  - 物体可供性预测：O2O-Afford、IAG-Net、LEMON。
  - 所有对比方法均在相同数据集上重新训练，并针对自我中心输入进行适当修改。
- **评估指标**：
  - 人体接触：Precision、Recall、F1、Geodesic distance（到真实接触点的最短测地距离）。
  - 物体可供性：AUC、aIOU、SIM。
- **主要实验结果**（表1）：
  - EgoChoir在所有人机接触指标上显著优于对比方法（例如F1达到0.76，地理误差12.62cm vs LEMON的0.67和21.43cm）。
  - 在物体可供性指标上也全面领先（AUC 78.02%，aIOU 14.94%，SIM 0.436）。

# 4. 资源与算力
- 文中明确说明：使用2块NVIDIA A40 GPU进行训练，训练时长约20 GPU小时（对应100个epoch）。框架使用PyTorch实现，优化器为Adam，初始学习率1e-4，余弦退火调度，批大小为8。

# 5. 实验数量与充分性
- **实验数量**：
  - 主要定量对比表1（7个基线方法在两类任务上的指标）。
  - 消融实验表2：逐项移除头部运动、可供性特征、梯度调制、语义特征、区域协同、时间位置编码、运动编码器随机初始化、不同视频骨干网络（SlowFast、Lavila）、时空注意力变体等，共12组以上。
  - 每类交互的详细指标表5（12类交互的Precision/Recall/F1/geo./AUC等）。
  - 额外实验：移除脚部接触后的指标（表6）、运动编码器在线训练与相邻帧姿态比较（表7）、全身运动输入下的性能（表3）。
  - 定性结果展示（图6、图9、图10、图11），涵盖多种动态交互场景。
- **充分性与公平性**：
  - 对比方法均为近年同类前沿方法，并在同一数据集上重新训练，修改合理。
  - 消融实验系统分析各模块贡献，验证设计必要性。
  - 提供了误差棒（表7 error bar），表明结果稳定。
  - 分析了模型对动态区域、多样性（多物体多实例）的泛化能力（图8）。
  - 实验覆盖了手部交互和身体交互，场景多样，统计完备。

# 6. 论文的主要结论与发现
- 从自我中心视频中联合估计3D人体接触和物体可供性是可行的，且通过整合视觉、头部运动和3D物体几何能有效克服自我视角下观察不完整导致的歧义。
- 提出的梯度调制机制使模型能在不同交互场景（手部精细操作 vs 身体大幅动作）中自适应选用最有效的线索，提升鲁棒性。
- 所构建的数据集（含1570视频片段、2万+3D实例及人工精标注）为自我中心3D HOI区域感知提供了首个基准。
- EgoChoir在几乎所有指标上大幅超越现有方法，尤其在身体交互（如坐、躺）场景中优势显著。
- 可供性特征有助于约束人体接触范围并维持时间一致性；头部运动对推断动态接触（如左右手切换）至关重要。

# 7. 优点
- **创新性**：首次系统地将视觉外观、头部运动和3D物体三者融合，模拟人类认知机制，从自我中心视角推断3D交互区域。
- **方法设计**：平行交叉注意力结构合理连接多种模态，梯度调制实现线索自适应选择，时间位置编码增强动态建模。
- **数据集贡献**：提供大规模、多类别、带高质量3D标注的自我中心HOI数据集，填补领域空白。
- **实验结果全面**：定量、定性、消融、分类别分析详尽，对比公平，展示方法优越性。
- **适用性广**：支持交互动态变化、多物体实例，且可通过引入全身运动进一步提升性能。

# 8. 不足与局限
- **时间对齐偏差**：当前方法可能略早或略晚于实际接触帧估计交互区域，文中归因于缺乏对交互双方空间关系的精确感知。
- **空间关系缺失**：未显式建模人体与物体之间的3D空间关系（如距离、朝向），依赖隐式学习，可能限制细粒度定位。
- **未利用全身运动**：虽然文中实验表明使用全身运动（SMPL序列）能进一步提升性能，但当前模型仅使用头部运动，未集成全身姿态估计。
- **交互类型有限**：目前仅涵盖12种交互类别，对未见过的交互类别泛化性未充分验证。
- **依赖外部3D物体模型**：需要预先提供3D物体点云，在实际应用中可能无法获得准确模型。
- **计算资源**：20 GPU小时的训练不算轻量，且推理时需处理多帧视频与点云，实时性尚待考察。

（完）
