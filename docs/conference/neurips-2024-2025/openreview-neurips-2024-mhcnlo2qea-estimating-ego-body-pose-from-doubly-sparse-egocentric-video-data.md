---
title: Estimating Ego-Body Pose from Doubly Sparse Egocentric Video Data
title_zh: 从双重稀疏的自我中心视频数据估计自我身体姿态
authors: "Seunggeun Chi, Pin-Hao Huang, Enna Sachdeva, Hengbo Ma, Karthik Ramani, Kwonjoon Lee"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=MHCnLo2QeA"
tags: ["query:imu-pose"]
score: 6.0
evidence: 利用头部和手部的IMU测量作为自我身体姿态参考
tldr: 针对自我中心视频中身体姿态估计对密集传感器数据的依赖问题，本文提出利用手部姿态等稀疏观测约束全身运动。方法分为时间补全和空间补全两阶段，使用掩码扩散模型。实验表明，该方法在稀疏输入下达到甚至优于密集IMU方法的效果，为可穿戴设备提供了实用解决方案。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
motivation: 现有方法依赖头部和手部的密集IMU数据，限制了实用性。
method: 提出两阶段扩散模型，先时间补全再空间补全，从稀疏观测估计全身姿态。
result: 在稀疏输入下达到与密集IMU方法相当的精度。
conclusion: 证明稀疏手部姿态足以有效约束全身运动。
---

## Abstract
We study the problem of estimating the body movements of a camera wearer from egocentric videos. Current methods for ego-body pose estimation rely on temporally dense sensor data, such as IMU measurements from spatially sparse body parts like the head and hands. However, we propose that even temporally sparse observations, such as hand poses captured intermittently from egocentric videos during natural or periodic hand movements, can effectively constrain overall body motion. Naively applying diffusion models to generate full-body pose from head pose and sparse hand pose leads to suboptimal results. To overcome this, we develop a two-stage approach that decomposes the problem into temporal completion and spatial completion. First, our method employs masked autoencoders to impute hand trajectories by leveraging the spatiotemporal correlations between the head pose sequence and intermittent hand poses, providing uncertainty estimates. Subsequently, we employ conditional diffusion models to generate plausible full-body motions based on these temporally dense trajectories of the head and hands, guided by the uncertainty estimates from the imputation. The effectiveness of our methods was rigorously tested and validated through comprehensive experiments conducted on various HMD setup with AMASS and Ego-Exo4D datasets. Project page: https://sgchi.github.io/dsposer

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在增强现实（AR）和虚拟现实（VR）应用中，准确估计头戴显示设备（HMD）用户的全身姿态是实现沉浸式体验的关键。然而，现有方法严重依赖来自头部和手部的密集传感器数据（如IMU测量），这限制了设备的适用性（例如，用户需要手持控制器或佩戴额外传感器）。本文提出，即使是从自我中心视频中**间歇性捕获的手部姿态**（时间上稀疏）也能有效约束全身运动，从而减少对密集IMU数据的依赖。

- **核心问题**：如何利用**双重稀疏**数据（空间上仅头部和手部，时间上手部仅在部分帧可见）来鲁棒地估计全身3D姿态。

- **整体意义**：提出一种无需手持控制器的HMD姿态估计框架，拓宽了AR/VR在运动训练、户外等场景中的实用性。

### 2. 论文提出的方法论

- **核心思想**：将问题分解为两个阶段：**时间补全**（Temporal Completion）和**空间补全**（Spatial Completion）。先通过掩码自编码器（MAE）补全手部轨迹，并给出不确定性估计；再以补全后的头部和手部轨迹为条件，结合不确定性引导，用条件扩散模型生成全身运动。

- **关键技术细节**：
  - **手部检测**：使用FrankMocap获取3D手部姿态，RTM-Pose估计2D关键点，通过重投影误差最小化得到相机坐标系下的3D手部位置。
  - **时间补全（MAE）**：将每个时间步的头部信号和手部姿态视为token，根据手部可见性动态掩码。MAE编码器使用注意力掩码处理不可见帧，解码器输出高斯分布的均值和方差。训练采用β-NLL损失，并训练多个模型（M=4）以分离**偶然不确定性**（aleatoric）和**认知不确定性**（epistemic），最终得到总不确定性。
  - **空间补全（VQ-Diffusion）**：使用VQ-VAE将人体运动离散化为码本，训练一个去噪Transformer。条件输入包括补全后的手部轨迹、头部信号以及不确定性。不确定性引导有三种策略：**采样**（从分布中采样手部序列）、**丢弃**（根据不确定性概率将手部特征置零）、**分布嵌入**（将均值和方差拼接作为条件）。实验表明采样策略最佳。
  - **公式化整体流程**：通过边缘化完成 \( p(P|V_{\text{ego}}, T_{\text{head}}) = \int p(P|\tilde{H}, T_{\text{head}}) p(\tilde{H}|f(V_{\text{ego}}), T_{\text{head}}) d\tilde{H} \)。

### 3. 实验设计

- **数据集**：
  - **AMASS**：大型动作捕捉数据集，用于合成HMD场景。通过视角角度（90° FoV）模拟手部可见性。共有CMU、BMLrub、HDM05子集。
  - **Ego-Exo4D**：真实自我中心视频数据集，包含334个训练视频和83个验证视频，提供头部IMU、手部检测标签等。

- **评估指标**：MPJPE（关节位置误差）、MPJVE（关节速度误差）、MPJRE（关节旋转误差，仅AMASS）。还报告手部、上半身、下半身的细分误差。

- **对比方法**：
  - 基线：EgoEgo、BoDiffusion、AvatarPoser、AvatarJLM。
  - 扩展：在稀疏数据情况下，使用线性插值或MAE补全手部轨迹后输入基线模型。
  - 自身消融：对比有无不确定性、不同不确定性类型（偶然、认知、总）、不同引导策略（采样、丢弃、分布嵌入）、不同β值等。

- **实验场景**：包括双重稀疏（TS=20或1）和空间稀疏（密集时间）两种设定。

### 4. 资源与算力

- **硬件配置**：单台工作站，CPU为AMD Ryzen Threadripper PRO 7975WX，内存256GB DDR5，4块NVIDIA GeForce RTX 4090 GPU。
- **存储需求**：AMASS约512GB，Ego-Exo4D约11TB。
- **训练时间**：AMASS约18小时/GPU，Ego-Exo4D约12小时/GPU。
- **推理时间**：AMASS验证集约40分钟/GPU，Ego-Exo4D约10分钟/GPU。
- **总耗时**：包括预实验和失败实验，总计约300 GPU小时。

### 5. 实验数量与充分性

- **实验组数**：主要包括：
  - 双重稀疏实验（AMASS和Ego-Exo4D各在不同窗口大小下的对比）。
  - 空间稀疏（密集时间）实验。
  - 消融实验：不确定性引导策略（4种）、不确定性类型（3种）、β参数（3种）。
  - 手部检测精度和可见性统计。
  - 额外定性可视化。
- **充分性**：实验覆盖了合成和真实数据集，对比了多个基线方法，消融实验系统分析了各个组件贡献。不确定性分析展示了MAE的预测质量。总体设计较为全面客观。但仅测试了手部作为稀疏信号，未探索其他身体部位。

### 6. 论文的主要结论与发现

- 即使仅使用时间稀疏的手部姿态，也能显著提升全身姿态估计精度。例如在AMASS上，MPJPE从12.08cm降至5.51cm。
- 提出的两阶段方法（MAE+扩散）优于直接使用扩散模型的基线，也优于线性插值+基线的组合。
- 引入不确定性引导（尤其是采样策略）能进一步改善效果，其中偶然不确定性比认知不确定性贡献更大。
- 在密集时间输入下，本方法性能与其他专为密集数据设计的方法相当，证明了其通用性。

### 7. 优点

- **创新性**：将问题分解为时间和空间补全，并引入不确定性估计来指导生成，解决了双重稀疏数据下的挑战。
- **实用性**：无需额外传感器（如手部控制器），仅依赖HMD自带的头部追踪和单目RGB视频，适用范围广。
- **鲁棒性**：通过MAE的预测不确定性，模型能感知手部检测不可靠的区域并降低其影响。
- **实验严谨**：报告了95%置信区间，进行了充分的消融和分析，计算资源公开详细。

### 8. 不足与局限

- **仅限于手部**：未利用其他可见身体部位（如脚、肘），可能限制了精度进一步提升。
- **检测依赖**：手部检测受光照、遮挡影响，错误会传播到后续阶段。论文未讨论极端情况下的鲁棒性。
- **计算开销**：扩散模型推理较慢（约1秒），且计算认知不确定性需要多个MAE模型，不适用于实时应用。
- **数据集局限**：AMASS为合成数据，手部可见性模拟简单（仅基于角度）；Ego-Exo4D虽然真实，但手部3D标注质量有限（仅使用手腕位置）。公平性方面未测试不同人群。
- **窗口大小有限**：仅测试了1~20帧（约几秒），更大窗口的表现未知。
- **未开源代码**：组织政策限制，影响可复现性。

（完）
