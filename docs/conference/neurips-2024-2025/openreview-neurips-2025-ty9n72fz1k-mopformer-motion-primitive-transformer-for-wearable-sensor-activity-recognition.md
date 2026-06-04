---
title: "MoPFormer: Motion-Primitive Transformer for Wearable-Sensor Activity Recognition"
title_zh: "MoPFormer: 用于可穿戴传感器活动识别的运动原语变换器"
authors: "Hao Zhang, Zhan Zhuang, Xuehao Wang, Xiaodong Yang, Yu Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Ty9n72fZ1K"
tags: ["query:imu-pose"]
score: 6.0
evidence: 使用IMU信号和Transformer进行活动识别
tldr: 针对可穿戴传感器活动识别可解释性差的问题，提出MoPFormer框架，将惯性测量单元信号离散化为运动原语，并通过Transformer编码时间依赖。实验证明该方法在多个基准数据集上取得优异表现，且跨数据集泛化能力强。该方法为IMU信号处理提供了新思路，可迁移至姿态估计等任务。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 376}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 597}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 988}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 683}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 487}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 479}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1443, \"height\": 482}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 488}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 477}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1447, \"height\": 483}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1447, \"height\": 486}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1448, \"height\": 493}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1443, \"height\": 1290}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 731}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 729, \"height\": 241}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 675, \"height\": 312}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 807, \"height\": 275}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 941, \"height\": 275}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 801, \"height\": 316}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 781, \"height\": 316}]"
motivation: 可穿戴传感器活动识别缺乏可解释性，跨数据集泛化差。
method: 将IMU信号分词化为运动原语，利用Transformer学习时间表征。
result: 在多个数据集上提升活动识别准确性和泛化性能。
conclusion: 运动原语化方法为IMU数据提供可解释表示，可支持姿态估计。
---

## Abstract
Human Activity Recognition (HAR) with wearable sensors is challenged by limited interpretability, which significantly impacts cross-dataset generalization. To address this challenge, we propose Motion-Primitive Transformer (MoPFormer), a novel self-supervised framework that enhances interpretability by tokenizing inertial measurement unit signals into semantically meaningful motion primitives and leverages a Transformer architecture to learn rich temporal representations. MoPFormer comprises two stages. The first stage is to partition multi-channel sensor streams into short segments and quantize them into discrete ``motion primitive'' codewords, while the second stage enriches those tokenized sequences through a context-aware embedding module and then processes them with a Transformer encoder. The proposed MoPFormer can be pre-trained using a masked motion-modeling objective that reconstructs missing primitives, enabling it to develop robust representations across diverse sensor configurations. Experiments on six HAR benchmarks demonstrate that MoPFormer not only outperforms state-of-the-art methods but also successfully generalizes across multiple datasets. More importantly, the learned motion primitives significantly enhance both interpretability and cross-dataset performance by capturing fundamental movement patterns that remain consistent across similar activities, regardless of dataset origin.

---

## 论文详细总结（自动生成）

# 论文总结：MoPFormer: Motion-Primitive Transformer for Wearable-Sensor Activity Recognition

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：基于可穿戴传感器（IMU）的人类活动识别（HAR）面临两大核心挑战：**可解释性差**（IMU数据不如视频直观，模型学习的内容难以理解）和**数据异质性**（传感器类型、采样率、佩戴位置、被试个体差异等导致跨数据集泛化困难）。
- **整体含义**：现有HAR模型多为黑箱，难以揭示模型是否真正理解了活动的层次结构（如“洗手”可分解为“开水龙头、抹肥皂、搓手”等子活动）。同时，不同数据集之间的分布偏移严重阻碍了模型的迁移能力。论文旨在通过将IMU信号离散化为语义上有意义的“运动原语”，同时提升可解释性和跨数据集泛化性能。

## 2. 方法论：核心思想、技术细节与算法流程
- **核心思想**：借鉴自然语言处理中的词元化思想，将多通道IMU时间序列分割成短片段，并通过向量量化（Vector Quantization, VQ）映射到离散的“运动原语”码本中，形成可解释的“词汇表”。然后利用Transformer编码器学习时间依赖，并通过掩码自编码（Masked Auto-Encoding, MAE）进行预训练。
- **关键技术细节**：
  - **运动原语模块**：
    - 将每个通道的T×C数据窗口分割为长度L的非重叠段（例如L=50个采样点，对应0.5秒@100Hz），得到每通道S=⌊T/L⌋个段。
    - 对每个段进行实例归一化：$\hat{s}_i = \frac{s_i - \mu(s_i)}{\sigma(s_i) + \epsilon}$。
    - 使用可学习的码本$Z=\{z_1,...,z_K\}$（K=1024），通过最近邻搜索得到离散索引$q_i = \arg\min_k \|\hat{s}_i - z_k\|_2^2$。
    - 同步提取统计特征（均值、方差）作为补充信息。
    - 码本通过承诺损失$L_{VQ}$端到端学习。
  - **上下文感知嵌入模块**：
    - 对离散索引使用可学习嵌入矩阵$E_{VQ}$映射到D维空间，同时通过线性层将统计特征投影到同一空间。
    - 引入**元数据嵌入适配器**：将传感器元数据（类型、位置等）通过预训练文本嵌入模型（Google text-embedding-004）转换为固定向量，再通过线性层映射到模型维度。
    - 最终每个片段的嵌入为：$e_i = e_i^{VQ} + e_i^{stat} + W_{adapter}(e_c^{meta}) + b_{adapter}$。
    - 输入序列结构为：[CLS], [START], e_1^1,...,e_{n1}^1, [END], [START], e_1^C,...,e_{nC}^C, [END]。
    - 添加可学习的同一时间步位置编码（不同通道同一时间步共享同一位置编码）。
  - **任务头**：
    - **MAE头**：预训练时随机掩盖25%的运动嵌入，通过交叉熵损失预测被掩盖的原始VQ索引。损失$L_{mae} = -\frac{1}{|M|}\sum_{i\in M}\log\hat{q}_i[q_i]$。
    - **分类头**：在[CLS] token上接MLP+Softmax，用于下游活动分类，损失$L_{cls}$。
    - 总损失：$L = \lambda_{mae}L_{mae} + \lambda_{cls}L_{cls} + \lambda_{vq}L_{vq}$。
  - **训练流程**：两阶段——第一阶段在多数据集上预训练（使用MAE任务）；第二阶段冻结运动原语和嵌入模块，仅微调分类头和Transformer层。
- **公式/算法流程**（文字描述）：
  - 输入：多通道IMU数据窗口（形状T×C）
  - 步骤1：分通道分割为长度L的片段 → 归一化 → VQ量化 → 得到离散索引序列 + 统计特征
  - 步骤2：嵌入（VQ嵌入 + 统计特征投影 + 元数据嵌入适配器）→ 添加特殊标记和位置编码
  - 步骤3：通过Transformer Encoder
  - 步骤4：预训练时使用MAE头重建被掩码的索引；微调时使用CLS头分类

## 3. 实验设计
- **数据集**：6个公开基准数据集：PAMAP2、DSADS、MHealth、Realworld、UCI-HAR、USC-HAD。所有数据重采样至100Hz，采用500样本窗口（5秒），步长等于窗口大小（无重叠）。
- **Benchmark与对比方法**：
  - 监督式预训练-迁移基线：BYOL（三种增强策略：perm_jit、lfc、Mixup）、ModCL（对比学习）、TSLANet（ICML 2024时间序列基础模型）、CALANet（NeurIPS 2024专用HAR模型）。
  - 监督式从头训练基线：TSLANet、CALANet。
  - 自消融：w/o Pretrain（去掉预训练）。
- **评估指标**：准确率（Accuracy）和宏F1分数（macro-F1）。
- **训练协议**：在5个数据集上预训练，在剩余1个上微调评估，保持0.2:0.8的微调-测试分割比例。

## 4. 资源与算力
- 论文明确说明所有实验在一张**NVIDIA Quadro RTX 8000 GPU（40GB VRAM）** 上运行。
- 使用了**梯度累积技术**（PyTorch Lightning）以支持较大的虚拟批次。
- **未明确给出**详细的训练时长（每个epoch时间或总预训练时间）。附录中提供了超参数：batch size 512（梯度累积实现）、AdamW优化器、学习率1e-4、权重衰减1e-5。

## 5. 实验数量与充分性
- **主要实验**：在6个数据集上与6种基线方法对比（表1），报告了准确率和F1分数。
- **消融实验**：
  - 模块消融（表2）：移除预训练、移除统计特征、移除元数据嵌入，在PAMAP2和DSADS上验证。
  - 超参数消融（附录B）：运动原语窗口长度（25/50/100）、Transformer层数（2/5/7/10）、嵌入维度（32/64/128/256）、VQ码本大小（16/64/256/1024）。
  - 稳定性测试（附录B.5）：在PAMAP2、DSADS、RealWorld上使用不同随机种子微调3次，报告均值和标准差。
  - 运动原语分析：相似性热力图（图3）、频率分布（图4）、各活动原语分布（附录C图5-12）、马尔可夫转移矩阵（图13）。
- **充分性评价**：实验覆盖了多个数据集、多种基线、多维度消融，且进行了稳定性检验，整体较为充分。但**未报告误差棒/置信区间**（主要结果表1仅单一结果），且缺乏对预训练数据量影响的探究（如不同规模预训练数据的泛化效果）。

## 6. 主要结论与发现
- MoPFormer在6个数据集上的平均准确率**90.17%**、F1**89.23%**，优于所有对比方法（包括TSLANet、CALANet、ModCL等）。
- **预训练至关重要**：无预训练时性能显著下降（如UCI-HAR准确率下降13个百分点）。
- 运动原语具有语义意义：相似运动形状的原语具有高余弦相似度；不同活动（动态vs静态）的原语使用分布呈现明显差异。
- 跨数据集泛化能力强：模型在不同传感器配置下仍能捕捉一致的基本运动模式。

## 7. 优点：方法或实验设计上的亮点
- **创新性**：首次将HAR中的IMU信号系统性地离散化为“运动原语”，借鉴NLP词元化思想，既提升了可解释性（可分析哪些原语对决策重要），又通过码本共享实现了跨数据集特征一致。
- **元数据嵌入适配器**：利用预训练文本嵌入处理传感器元数据，使得模型能自然处理不同传感器类型和位置，增强了跨数据集的适应性。
- **统一的预训练框架**：MAE预训练目标简单有效，使模型学习到鲁棒的上下文表示。
- **丰富的可解释性分析**：不仅报告了性能，还通过相似性矩阵、频率分布、活动原语分布等可视化手段深入揭示了模型学到的内容，体现了对“可解释性”贡献的扎实验证。
- **消融实验全面**：涵盖模块、超参数、随机种子稳定性的系统性评估。

## 8. 不足与局限
- **计算开销**：VQ码本搜索和多层Transformer处理可能带来计算负担，论文在附录E中指出这可能对资源受限的可穿戴设备实时推理造成问题。
- **实验报告缺乏统计不确定性**：主要结果（表1）仅报告单次运行值，未提供多轮平均和标准差（虽然附录B.5做了3次稳定性测试，仅覆盖3个数据集）。
- **预训练数据规模有限**：仅在5个公开数据集上预训练，未探索更大规模或更真实场景的预训练数据，泛化性可能受限。
- **标签粒度不足**：论文未利用层次化标签（子活动标注）进行更细粒度的评估，这与引言中强调的“层级结构”目标有一定差距。
- **未与其他基于运动原语的方法直接对比**：虽然引用了机器人领域的原语研究，但实验对比主要针对通用时间序列模型，缺少与专门研究运动原语分解的HAR方法的对比（如Chen et al. 2021）。
- **应用局限**：所有实验基于固定窗口（500样本/5秒），实际应用中窗口大小适应性未验证。

（完）
