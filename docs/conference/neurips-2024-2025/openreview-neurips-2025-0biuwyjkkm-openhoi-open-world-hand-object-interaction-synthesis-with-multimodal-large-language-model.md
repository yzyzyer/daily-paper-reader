---
title: "OpenHOI: Open-World Hand-Object Interaction Synthesis with Multimodal Large Language Model"
title_zh: OpenHOI：基于多模态大语言模型的开放世界手物交互合成
authors: "Zhenhao Zhang, Ye Shi, Lingxiao Yang, Suting Ni, Qi Ye, Jingya Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0biUwyjKkm"
tags: ["query:hoi"]
score: 8.0
evidence: 基于多模态大语言模型的开放世界手物交互合成
tldr: 针对现有手物交互合成方法泛化性弱、仅支持封闭物体集的问题，提出OpenHOI框架，利用微调的3D多模态大语言模型进行联合功能定位和语义任务分解，生成可操纵的长序列交互，在开放世界条件下实现高质量HOI合成，为手物交互中的姿态估计和操纵规划提供了有力基础，推动了该领域的发展。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0biuwyjkkm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 711, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0biuwyjkkm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1415, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0biuwyjkkm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1435, \"height\": 200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0biuwyjkkm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1428, \"height\": 250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0biuwyjkkm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1368, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0biuwyjkkm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1421, \"height\": 785, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0biuwyjkkm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1369, \"height\": 692, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1474, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1473, \"height\": 578, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1453, \"height\": 575, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 696, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 910, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 681, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1409, \"height\": 573, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1413, \"height\": 574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1317, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 767, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 770, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 896, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0biuwyjkkm/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1250, \"height\": 518, \"label\": \"Table\"}]"
motivation: 现有HOI合成方法局限于封闭物体和预定义任务，无法泛化到未见物体。
method: 集成3D多模态大语言模型，实现交互区域定位和任务分解，生成长时间操纵序列。
result: 在开放世界HOI合成任务上取得最先进效果，支持语言指令引导。
conclusion: OpenHOI首次实现了开放世界HOI合成，推动了手物交互理解和生成能力。
---

## Abstract
Understanding and synthesizing realistic 3D hand-object interactions (HOI) is critical for applications ranging from immersive AR/VR to dexterous robotics. Existing methods struggle with generalization, performing well on closed-set objects and predefined tasks but failing to handle unseen objects or open-vocabulary instructions. We introduce OpenHOI, the first framework for open-world HOI synthesis, capable of generating long-horizon manipulation sequences for novel objects guided by free-form language commands. Our approach integrates a 3D Multimodal Large Language Model (MLLM) fine-tuned for joint affordance grounding and semantic task decomposition, enabling precise localization of interaction regions (e.g., handles, buttons) and breakdown of complex instructions (e.g., “Find a water bottle and take a sip”) into executable sub-tasks. To synthesize physically plausible interactions, we propose an affordance-driven diffusion model paired with a training-free physics refinement stage that minimizes penetration and optimizes affordance alignment.
Evaluations across diverse scenarios demonstrate OpenHOI’s superiority over state-of-the-art methods in generalizing to novel object categories, multi-stage tasks, and complex language instructions.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有手物交互（HOI）合成方法局限于封闭物体集和预定义任务，无法泛化到未见物体或开放词汇指令。例如，传统方法依赖手工运动先验或扩散模型直接映射文本到动作，但不能处理“Find a water bottle and take a sip”这类高自由度语言指令。
- **研究动机**：真实应用（AR/VR、灵巧机器人）需要能在开放世界中对任意物体执行多阶段操作，因此必须突破封闭集限制，实现**开放世界HOI合成**。
- **整体含义**：本文提出**OpenHOI**，这是首个支持开放世界HOI合成的框架，能在未见物体上根据自由形式语言命令生成长时间操纵序列，解决了 HOI 领域泛化性不足的关键瓶颈。

### 2. 论文提出的方法论

- **核心思想**：整合3D多模态大语言模型（3D MLLM）与扩散模型，通过MLLM实现精细的功能定位（affordance grounding）和任务分解，再以功能图为条件驱动扩散模型生成物理合理的HOI序列，并引入无训练物理精炼步骤。
- **关键技术细节**：
    - **3D MLLM 模块**：以 ShapeLLM（含 ReCon++ 点云编码器 + LLaMa 语言组件）为骨干，在其词汇表中加入特殊标记 `<AFF>` 用于表示分割输出。通过 **粗到细** 两阶段微调：先在静态功能数据集（如 AffordanceLLM）上获得通用功能先验，再在动态 HOI 数据集上精调，使其能同时输出子任务序列（如“先双手打开瓶盖，再用右手喝水”）和对应的功能点云热力图。
    - **功能驱动的 HOI 扩散模型**：
        - 条件输入 C 包括：功能图 `A_obj`、子任务的 CLIP 嵌入 `f_clip(T_sub_tasks)`、物体点云 `F_obj`。
        - 训练时使用 **分类器无关引导（CFG）**：随机将 10% 的条件输入替换为无条件的 ∅，以同时训练条件模型和无条件模型。
        - 损失函数：`L_hoi_train = L_diff + L_distance + L_orient`，其中 `L_diff` 是标准扩散重构损失，`L_distance` 惩罚手-物体表面接触误差，`L_orient` 对齐手-物体相对旋转。
    - **无训练物理精炼**（采样阶段）：
        - 三种精炼目标：**功能对齐损失**（引导手关节靠近功能区域）、**穿透避免损失**（最小化手-物体穿透）、**运动过渡损失**（使前后子序列之间生成平滑插值）。
        - 采用 **DSG（Spherical Gaussian Constraint）** 方法计算最陡梯度下降方向，并与随机采样方向混合，得到更新方向 `D_mix`，再通过 `X_{t-1} = μ_t + σ_t * D_mix / ||D_mix||` 完成一步去噪。该策略避免了单纯梯度下降带来的分布偏移问题。

### 3. 实验设计

- **数据集**：
    - **GRAB**：包含 51 个日常物体，单人全手抓取数据。
    - **ARCTIC**：大规模双手交互数据集，含可动关节物体。
    - 两个数据集均按 80% 训练 / 20% 测试（未见物体）划分，同时使用 MLLM 将低层动作描述转换为高层意图指令以增强开放词汇能力。
- **基准方法**：MDM、TM2T、MotionGPT、Text2HOI。
- **评估指标**：
    - **运动精度**：平均每关节位置误差 (MPJPE)、最终物体位置误差 (FOL)。
    - **生成真实感**：Fréchet Inception Distance (FID)。
    - **多样性与多模态性**：Diversity（不同提示间方差）、MModality（同一提示不同样本间方差）。

### 4. 资源与算力

- 论文中仅说明实验在 **NVIDIA A100 GPU** 上完成（Section 4），未提及具体 GPU 数量、训练轮次时长或显存消耗。附录 A 提供了部分超参数（如 AdamW 学习率、余弦退火调度、扩散步数 T=1000 等），但**算力信息不完整**，无法完全复现训练成本。

### 5. 实验数量与充分性

- **主要实验**：在 GRAB 和 ARCTIC 上分别对 Seen/Unseen 设置进行对比（表 2、表 3），每个指标报告均值和标准差，重复次数未知但符合惯例。
- **消融实验**：在 GRAB（表 4）和 ARCTIC（表 5）上依次去除功能图、CFG、穿透损失、功能对齐损失，验证各组件贡献。
- **补充实验**（附录）：
    - 在 **H2O** 数据集上进行极端跨域泛化测试（表 A1）。
    - 物理真实感评估（表 A2、A3）。
    - 指导率敏感性分析（表 A5、A6）。
    - 多 `<AFF>` 标记 vs 单标记（表 A7）。
    - 运动插值平滑率比较（表 A8、A9、A10）。
    - 统计显著性检验（表 A11）。
- **充分性与客观性**：实验覆盖了不同数据集、消融组件、超参数灵敏度、极端泛化场景，且进行了统计检验，设计较为全面。但未见与 HOIGPT 的直接比较（因其代码未公开），仅与文本方案对比，存在一定偏差。

### 6. 论文的主要结论与发现

- OpenHOI 在 **Seen** 和 **Unseen** 物体上均大幅优于现有方法，MPJPE 降低 10-30%，FID 降低 20-40%，同时保持了更高的多样性和多模态性。
- 功能图先验是开放世界泛化的关键，移除后效果显著下降。
- CFG 和无训练物理精炼（功能对齐+穿透避免+运动过渡）均能有效提升生成质量和物理合理性。
- 在 H2O 这种完全未见过的数据集上，OpenHOI 仍展现出鲁棒泛化能力，证明了框架的开放世界设计有效。

### 7. 优点

- **首创性**：首个开放世界 HOI 合成框架，突破了封闭集限制。
- **方法创新**：巧妙结合 3D MLLM 的语义推理与扩散模型的生成能力，利用功能作为中介先验，显式引导交互区域。
- **无训练精炼**：无需额外训练即可修正穿透和不连续问题，保持分布不变。
- **长序列支持**：通过运动过渡精炼实现子任务间平滑衔接，可生成超 450 帧的长时间交互。
- **泛化能力强**：在未见物体、开放词汇、长周期任务上均表现优秀。

### 8. 不足与局限

- **目标定位不足**：对于需要精确数序的指令（如“打开第二个柜子”）无法正确处理，因为模型未在大规模 3D QA 数据上训练。
- **长序列累积误差**：超过 3 个连续动作（约 450 帧）后性能明显下降。
- **细粒度动力缺失**：无法模拟倒液等需要流体动力学的交互，未来需混合神经符号物理模型。
- **计算资源信息不完整**：未提供 GPU 数量、训练时长等关键复现细节，影响可复现性。
- **对比方法不完全**：未与同期的 HOIGPT（代码未公开）进行定量比较，结论的排他性有待补充。
- **数据集局限**：仅使用 GRAB 和 ARCTIC，虽然补充了 H2O 测试，但仍主要基于人造数据集，真实世界应用（如噪声点云、动态背景）未验证。

（完）
