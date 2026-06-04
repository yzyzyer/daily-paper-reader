---
title: "ToF-IP: Time-of-Flight Enhanced Sparse Inertial Poser for Real-time Human Motion Capture"
title_zh: ToF-IP：飞行时间增强的稀疏惯性定位器用于实时人体运动捕捉
authors: "Yuan Yao, Shifan Jiang, Yangqing Hou, Chengxu Zuo, Xinrui Chen, Shihui Guo, Yipeng Qin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=fLKrX29Zy6"
tags: ["query:imu-pose"]
score: 9.0
evidence: 利用稀疏IMU和飞行时间传感器进行人体运动捕捉
tldr: 针对稀疏惯性测量单元（IMU）在人体运动追踪中因漂移和噪声导致误差累积的问题，本文提出ToF-IP系统，将飞行时间（ToF）传感器与稀疏IMU相结合。通过ToF直接距离测量替代间接时间积分，有效抑制了误差累积，同时保持了便携性。实验表明，该方法在实时全身体位估计中显著提升了精度，为IMU人体运动捕捉提供了鲁棒解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1379, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1411, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1397, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1359, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-flkrx29zy6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1413, \"height\": 346, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-flkrx29zy6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flkrx29zy6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-flkrx29zy6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 210, \"label\": \"Table\"}]"
motivation: 解决稀疏IMU人体运动追踪中由于加速度积分导致的误差累积问题。
method: 将飞行时间（ToF）传感器附加到选定的IMU上，利用直接距离测量来校正漂移。
result: 在实时全身体位估计中显著降低误差，优于纯IMU方法。
conclusion: 融合ToF与IMU可有效提升惯性运动捕捉的准确性和鲁棒性。
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

### 论文中文总结

#### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：稀疏惯性测量单元（IMU）虽便携、低成本，但在人体运动捕捉中依赖加速度的二次时间积分来估计关节位置，会导致漂移和传感器噪声引起的**误差累积**，尤其在慢速运动（如太极拳）中信噪比低，误差被放大。
- **背景**：现有纯IMU方法多为软件优化（如RNN、注意力模型），只能缓解而非根治误差累积问题。因此，作者提出通过引入直接距离测量（Time-of-Flight, ToF）来提供学习约束，从根本上抑制积分误差。

#### 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：将ToF传感器与稀疏IMU融合，利用ToF直接测量关节端点与身体/地面的距离，替代间接积分，同时保持便携性。
- **硬件设计**：在标准6-IMU布局（左/右前臂、左/右小腿、骨盆、头部）中，**选择前臂和小腿的4个节点集成ToF传感器**（内手腕和后脚踝处），总体积仅增加3%，兼顾佩戴轻量。
- **软件架构**（统一Transformer框架）：
  - **节点中心数据集成（Node-Centric Data Integration）**：
    - 将每个传感节点（含IMU和ToF数据）视为独立token，通过**Transformer编码器**显式建模节点内（intra-node）和节点间（inter-node）交互。
    - 节点内集成：将节点多模态数据（ToF深度图 d ∈ R¹⁶、IMU加速度 a ∈ R³、IMU方向 R ∈ R³ˣ³）编码为 token z_intra。
    - 节点间集成：利用自注意力机制计算节点间权重，融合所有节点 token 得到最终嵌入 Z_NCI。
  - **动态空间位置编码（Dynamic Spatial Positional Encoding）**：
    - 针对传统静态位置编码（如正弦波函数）不适用于动态节点位置的问题，提出将节点位置建模为**运动信号的函数**：ϕ_n(t) = f_ϕ(X_all(t))，其中 X_all(t) 为所有6个节点的数据，f_ϕ 由2层MLP实现。然后按正弦/余弦公式生成随时间变化的位置编码。
  - **运动估计器**：将嵌入 Z_NCI 输入三个级联LSTM网络（f_v, f_p, f_φ），分别输出关节速度 v ∈ R^(J×3)、位置 p ∈ R^(J×3)、旋转 φ ∈ R^(J×6)（J=18个关节）。训练损失为三者与真值的L2范数。
  - **全局平移追踪**：结合运动估计器输出的速度与SMPL运动学模型，利用伪静止标签（基于端点速度阈值）融合前向运动学与神经网络估计的根平移，减少漂移。

#### 3. 实验设计：数据集、基准与对比方法
- **合成数据集**：基于AMASS仿真ToF-IMU-动作配对数据（Unity模拟ToF深度图降采样至4×4），用于预训练。
- **真实数据集（ToF-IP-DB）**：自行采集，208分钟（749,000帧），来自10名参与者（3男7女，身高170-185cm），包含舞蹈、有氧、太极拳、八段锦等20+种动作，同步记录IMU、ToF、光学追踪真值（NOKOV系统，60Hz）。
- **基准（Benchmark）**：DIP数据集（带合成ToF）和ToF-IP-DB数据集。
- **对比方法**：Transpose、TIP、PIP、DynaIP、PNP等SOTA方法。
- **评价指标**：SIP误差（肩髋旋转）、角度误差、位置误差、端点位置误差、抖动（jerk）。

#### 4. 资源与算力
- **硬件**：Intel i7-13700KF CPU + NVIDIA RTX 4080 GPU。
- **软件**：PyTorch 1.12.1, CUDA 11.3。
- **训练配置**：Adam优化器，学习率1e-3，权重衰减1e-6，batch size 512。
- **训练时长**：论文未明确说明总训练时长，但提及模型在单PC上运行。

#### 5. 实验数量与充分性
- **主实验**：在DIP和ToF-IP-DB两个数据集上对比6种SOTA方法，报告所有5项指标（表1）。
- **消融实验1**：验证ToF集成效果（表2）——4种设置：无ToF+无NCI、有ToF+无NCI、无ToF+有NCI、有ToF+有NCI（完整方法），在两个数据集上均进行。
- **消融实验2**：验证动态位置编码效果（表3）——对比静态编码、可学习静态编码、动态空间编码（本文）。
- **定性实验**：提供太极拳、八段锦等慢速运动的姿态对比图（图4、图5、图6）。
- **充分性**：实验覆盖了不同运动类型、不同误差维度，消融设计合理，对比方法全面，重复性较好。但未提供多次运行的标准差/置信区间，统计显著性未明确。

#### 6. 主要结论与发现
- ToF-IP在所有指标上超越SOTA方法，尤其在**SIP误差和端点位置误差**上提升显著（表1）。
- 在慢速、长时间运动（如太极拳）中，ToF直接距离测量有效抑制了纯IMU的漂移，姿态更接近真值（图4）。
- 消融证明：ToF集成和节点中心数据集成缺一不可；动态空间位置编码优于静态方案。

#### 7. 优点
- **硬件创新**：在标准6-IMU布局上仅通过4个ToF传感器实现轻量（体积+3%）、可穿戴的混合传感。
- **软件创新**：节点中心数据集成保留了多传感器结构语义，动态位置编码适应穿戴节点连续运动的空间变化，解决了传统位置编码不适用于非静态场景的问题。
- **数据贡献**：提供了首个含同步ToF-IMU-光学真值的大型数据集（208分钟，20+动作类型），促进后续研究。
- **性能强**：对慢速、复杂动作（如太极拳）的精度提升验证了实际价值。

#### 8. 不足与局限
- **ToF传感器依赖**：性能受限于ToF视场、遮挡和距离范围，在遮挡严重或反射面复杂时可能失效。
- **噪声引入**：ToF传感器自身噪声导致估计结果出现轻微抖动（jitter指标未显著优于纯IMU方法）。
- **环境约束**：当前实验仅在受控室内环境进行，未在真实野外或恶劣光照条件下验证泛化性。
- **统计缺失**：未报告多次运行的标准差，无法判断性能的波动性。
- **单模态局限性**：对头部、骨盆等无ToF的节点，仍依赖纯IMU的积分估计，可能引入误差。

（完）
