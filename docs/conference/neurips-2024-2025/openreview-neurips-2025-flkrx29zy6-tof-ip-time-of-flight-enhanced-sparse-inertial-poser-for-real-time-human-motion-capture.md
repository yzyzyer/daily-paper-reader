---
title: "ToF-IP: Time-of-Flight Enhanced Sparse Inertial Poser for Real-time Human Motion Capture"
title_zh: ToF-IP：飞行时间增强的稀疏惯性定位器用于实时人体运动捕捉
authors: "Yuan Yao, Shifan Jiang, Yangqing Hou, Chengxu Zuo, Xinrui Chen, Shihui Guo, Yipeng Qin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=fLKrX29Zy6"
tags: ["query:imu-pose"]
score: 9.0
evidence: 稀疏IMU与ToF传感器融合实现3D全身姿态估计
tldr: 该论文针对稀疏惯性测量单元（IMU）在人体运动捕捉中因漂移和噪声导致的误差累积问题，提出ToF-IP系统，将飞行时间（ToF）传感器与稀疏IMU相结合，利用ToF直接距离测量替代IMU的时间积分，有效抑制漂移。实验表明该方法能实现实时、准确的3D全身姿态估计，同时保持可穿戴设备的便携性。该工作为低成本、低漂移的IMU姿态估计提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1379, \"height\": 502}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 393}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1411, \"height\": 517}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1397, \"height\": 484}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1359, \"height\": 603}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1413, \"height\": 346}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-flkrx29zy6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 321}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flkrx29zy6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 248}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flkrx29zy6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 210}]"
motivation: 稀疏IMU用于人体运动追踪时存在漂移和噪声导致的误差累积问题。
method: 提出ToF-IP，将ToF传感器与稀疏IMU集成，利用ToF直接距离测量修正IMU积分误差，实现实时全身姿态估计。
result: 实验证明该方法能有效减少漂移，实现高精度实时3D全身姿态估计。
conclusion: 该工作表明ToF与IMU融合是提高IMU姿态估计精度的有效途径，并保持便携优势。
---

## Abstract
Sparse inertial measurement units (IMUs) provide a portable, low-cost solution for human motion tracking but struggle with error accumulation from drift and sensor noise when estimating joint position through time-based linear acceleration integration (i.e., indirect measurement). 
To address this, we propose ToF-IP, a novel 3D full-body pose estimation system that integrates Time-of-Flight (ToF) sensors with sparse IMUs. 
The distinct advantage of our approach is that ToF sensors provide direct distance measurements, effectively mitigating error accumulation without relying on indirect time-based integration. 
From a hardware perspective, we maintain the portability of existing solutions by attaching ToF sensors to selected IMUs with a negligible volume increase of just 3\%.
On the software side, we introduce two novel techniques to enhance multi-sensor integration: (i) a Node-Centric Data Integration strategy that leverages a Transformer encoder to explicitly model both intra-node and inter-node data integration by treating each sensing node as a token; and (ii) a Dynamic Spatial Positional Encoding scheme that encodes the continuously changing spatial positions of wearable nodes as motion-conditioned functions, enabling the model to better capture human body dynamics in the embedding space.Additionally, we contribute a 208-minute human motion dataset from 10 participants, including synchronized IMU-ToF measurements and ground-truth from optical tracking.
Extensive experiments demonstrate that our method outperforms state-of-the-art approaches such as PNP, achieving superior accuracy in tracking complex and slow motions like Tai Chi, which remains challenging for inertial-only methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
稀疏惯性测量单元（IMU）用于人体运动捕捉时，具有便携、低成本的优点，但其通过加速度时间积分间接估计位置的方式，会因传感器漂移和噪声导致误差累积——位置误差随时间呈二次方增长（命题3.1）。这一问题在慢速运动（如太极）中尤为严重，因信号噪声比低，传统惯性方法难以准确跟踪。为此，论文提出ToF-IP系统，将飞行时间（ToF）距离传感器与稀疏IMU融合，利用ToF直接测量距离，从根本上避免积分误差，实现更稳定、精确的实时全身姿态估计。

### 2. 论文提出的方法论：核心思想、关键技术细节
**核心思想**：在标准6节点IMU布局的4个肢体末端节点（左/右前臂、左/右小腿）上集成轻量ToF传感器（体积仅增加3%），以提供直接的关节端点距离约束。软件上设计统一的Transformer框架，包含两项关键创新：

- **Node-Centric Data Integration（节点中心数据整合）**：将每个传感节点视为独立token。首先通过tokenize函数将节点内多模态数据（ToF深度图d∈R¹⁶、IMU加速度a∈R³、姿态R∈R³ˣ³）编码为节点内token（式2）；然后通过Transformer自注意力机制实现节点间交互，计算注意力权重Aᵢⱼ并加权聚合（式3），从而显式建模层次化多传感器融合。

- **Dynamic Spatial Positional Encoding（动态空间位置编码，Dyn-PE）**：区别于传统静态位置编码（如正弦/余弦固定索引），Dyn-PE将传感节点的时空位置建模为全局运动信号（所有6节点数据）的可学习函数ϕₙ(t)（通过2层MLP输出），生成随时间变化的编码（式5），使模型能感知节点随人体运动而变化的物理位移，增强空间感知能力。

此外，采用三个级联LSTM作为运动估计器（fᵥ、fₚ、fφ），分别预测关节速度、位置和旋转，并融合前向运动学与神经网络输出进行全局平移跟踪（式8-11）。

### 3. 实验设计
- **数据集**：
  - **AMASS合成数据集**：预训练用，通过Unity模拟ToF深度图（4×4分辨率）与IMU信号。
  - **自采ToF-IP-DB数据集**：208分钟（749,000帧），10名参与者（3男7女），20余种动作（舞蹈、有氧、太极、八段锦等），同步采集ToF深度、6-DoF IMU信号和光学捕捉（NOKOV）真实姿态。
- **评估指标**：SIP角度误差（°）、全局角度误差（°）、位置误差（cm）、端点位置误差（cm）、抖动（km/s³）。
- **对比方法**：Transpose、TIP、PIP、DynaIP、PNP等SOTA稀疏IMU方法。在DIP（论文合成ToF）和ToF-IP-DB两个数据集上评测。

### 4. 资源与算力
论文明确说明：实验使用Intel i7-13700KF CPU与NVIDIA RTX 4080 GPU，PyTorch 1.12.1，CUDA 11.3。优化器为Adam（lr=1×10⁻³，weight decay=1×10⁻⁶），batch size=512。未给出具体训练时长，仅提及epoch数（n epochs，未说明具体值）。

### 5. 实验数量与充分性
实验包括三组主要评估：
- **与SOTA定量对比（表1）**：在两个数据集上共展示10项指标比较，ToF-IP在全部指标上最优。
- **ToF集成消融（表2）**：4种配置（有/无ToF × 有/无NCI），验证ToF和节点中心整合的必要性。
- **位置编码消融（表3）**：对比静态、可学习静态与动态空间编码，证明Dyn-PE的有效性。
- **定性可视化（图4、5）**：展示太极、八段锦等慢速运动的姿态对比，以及有无ToF的示例。
实验设计较完整，覆盖不同运动速度（快慢）、不同消融因素，且对比方法均为近年领先工作，公平性良好。但未报告误差棒或统计显著性检验，可能削弱结论的稳健性。

### 6. 论文的主要结论与发现
- ToF直接距离测量显著降低端点位置误差（较PNP降低约1.7cm在DIP数据集上），并改善全身角度估计。
- 所提出的节点中心整合策略和动态位置编码均能独立提升性能，二者结合达到最佳。
- 在慢速、低信噪比运动（如太极）中，惯性方法严重失真，而ToF-IP能保持准确姿态。

### 7. 优点
- **硬件创新极小侵入**：在标准6-IMU布局上仅增加4个ToF传感器，体积增幅3%，保留便携性。
- **软件设计针对性强**：节点token化解决了多模态数据层次结构忽略问题；动态位置编码适应可穿戴节点的连续空间变化，是Transformer在可穿戴领域的新应用。
- **数据集贡献**：提供融合ToF-IMU-光学真值的208分钟数据集，覆盖多种日常与慢速运动，弥补领域空白。
- **理论支撑**：给出误差累积的数学证明（命题3.1），强化了问题的严重性和方法动机。

### 8. 不足与局限
- **ToF局限性**：当传感器视野被遮挡、目标表面反射差或距离超出范围时，测量不可靠，影响性能。
- **噪声引入**：ToF测量本身存在噪声，导致抖动指标（jitter）未明显优于某些基线（如表1中jitter与PNP持平或略高）。
- **实验环境受限**：仅在受控实验室环境采集数据，未在户外或复杂真实场景验证泛化能力。
- **无统计显著性报告**：未给出多次重复实验的标准差或置信区间，结果可靠性证据略弱。
- **运动类型覆盖**：虽含20余种动作，但未涉及剧烈跳跃、旋转或高速运动中ToF与IMU协同的极端情况。

（完）
