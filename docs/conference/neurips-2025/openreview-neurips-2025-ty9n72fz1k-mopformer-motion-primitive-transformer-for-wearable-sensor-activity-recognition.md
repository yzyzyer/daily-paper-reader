---
title: "MoPFormer: Motion-Primitive Transformer for Wearable-Sensor Activity Recognition"
title_zh: MoPFormer：面向可穿戴传感器活动识别的运动基元Transformer
authors: "Hao Zhang, Zhan Zhuang, Xuehao Wang, Xiaodong Yang, Yu Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Ty9n72fZ1K"
tags: ["query:imu-pose"]
score: 6.0
evidence: 使用IMU信号编码为运动基元，可应用于姿态估计
tldr: 针对可穿戴传感器活动识别中可解释性差和跨数据集泛化难的问题，MoPFormer提出将惯性测量单元（IMU）信号分割并量化为离散的“运动基元”编码，再通过Transformer结构学习时序表示。该方法在活动识别任务上取得了良好性能，其运动基元编码机制可直接迁移至IMU姿态估计，为利用IMU进行人体姿态估计提供了有价值的思路和基础模块。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 988, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1443, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1447, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1447, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1448, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ty9n72fz1k/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1443, \"height\": 1290, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 731, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 729, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 675, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 807, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 941, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 801, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ty9n72fz1k/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 781, \"height\": 316, \"label\": \"Table\"}]"
motivation: 现有可穿戴传感器活动识别方法可解释性差，难以跨数据集泛化，且缺乏语义级运动表示。
method: MoPFormer将IMU多通道信号分段并量化为运动基元离散编码，再利用Transformer进行上下文感知的时序建模。
result: 在多个数据集上展示了优越的活动识别准确率和跨数据集泛化能力，并增强了模型可解释性。
conclusion: 该工作为基于IMU的运动感知提供了一种可解释的基元表示方法，可推广至姿态估计等任务。
---

## Abstract
Human Activity Recognition (HAR) with wearable sensors is challenged by limited interpretability, which significantly impacts cross-dataset generalization. To address this challenge, we propose Motion-Primitive Transformer (MoPFormer), a novel self-supervised framework that enhances interpretability by tokenizing inertial measurement unit signals into semantically meaningful motion primitives and leverages a Transformer architecture to learn rich temporal representations. MoPFormer comprises two stages. The first stage is to partition multi-channel sensor streams into short segments and quantize them into discrete ``motion primitive'' codewords, while the second stage enriches those tokenized sequences through a context-aware embedding module and then processes them with a Transformer encoder. The proposed MoPFormer can be pre-trained using a masked motion-modeling objective that reconstructs missing primitives, enabling it to develop robust representations across diverse sensor configurations. Experiments on six HAR benchmarks demonstrate that MoPFormer not only outperforms state-of-the-art methods but also successfully generalizes across multiple datasets. More importantly, the learned motion primitives significantly enhance both interpretability and cross-dataset performance by capturing fundamental movement patterns that remain consistent across similar activities, regardless of dataset origin.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：可穿戴传感器（IMU）的人体活动识别（HAR）面临两大挑战：**可解释性差**（IMU信号是连续时序数据，难以理解模型学到了什么）和**跨数据集泛化困难**（传感器类型、采样率、佩戴位置、受试者差异等导致数据异质性）。
- **动机**：现有深度学习模型多为黑箱，仅关注注意力权重等浅层可解释性；且缺乏统一的表示方式以支持跨数据集训练。语言模型中将文本离散化为词元的思路启发了本文：将IMU信号分割并量化为“运动基元”（Motion Primitives），作为语义上有意义的离散构建块，从而提升可解释性和泛化能力。

## 2. 论文提出的方法论：核心思想、关键技术细节
### 核心思想
- 将多通道IMU时序数据先**分段**（每段0.5秒），再通过**向量量化（VQ）**映射为固定码本中的离散索引（运动基元），形成类似“词”的序列；然后通过**上下文感知嵌入模块**融合统计特征、传感器元数据和时间位置信息，最后用**Transformer编码器**学习时序表示，并通过**掩码自编码（MAE）预训练**和**分类（CLS）微调**完成下游任务。

### 关键技术细节
1. **运动基元模块**
   - 对每个传感器通道的时窗（T×C）独立分割为长度L=50的短段，得到S×C个段。
   - 对每个段进行实例归一化（公式1）：$\hat{s}_i = (s_i - \mu(s_i)) / (\sigma(s_i) + \epsilon)$。
   - 用VQ找最近邻原型索引（公式2）：$q_i = \arg\min_k \|\hat{s}_i - z_k\|_2^2$，码本大小K=1024，维度L=50。
   - 同时提取每个段的统计特征（均值、方差）作为补充信息。
   - 使用承诺损失（公式3）：$L_{VQ} = \|sg[\hat{s}_i] - z_{q_i}\|_2^2 + \beta \|\hat{s}_i - sg[z_{q_i}]\|_2^2$。

2. **上下文感知嵌入模块**
   - 将VQ索引通过可学习嵌入矩阵映射到D=256维空间（公式4）。
   - 统计特征通过线性投影（公式5）映射到同一空间。
   - 传感器元数据（如身体部位、传感器类型）通过预训练文本嵌入（Google text-embedding-004）获得固定向量，再经线性适配器映射（公式6中$e_i = e_{VQ}^i + e_{stat}^i + W_{adapter}(e_{meta}^c) + b_{adapter}$）。
   - 添加特殊标记：[CLS]、[START]、[END]、[MASK]，并按传感器通道组织输入序列（公式7）。
   - 加入可学习位置编码（公式8），不同通道在同一时间步共享相同位置编码。

3. **任务头**
   - **MAE头**：预训练时随机掩蔽25%的运动基元，通过交叉熵损失（公式9-10）预测被掩蔽的VQ索引。
   - **CLS头**：微调时利用[CLS] token的Transformer输出进行活动分类（公式11-12）。
   - 总损失（公式13）：$L = \lambda_{mae} L_{mae} + \lambda_{cls} L_{cls} + \lambda_{vq} L_{vq}$。

4. **训练策略**：两阶段——先在多数据集上预训练（MAE任务），再冻结特征提取模块，仅微调分类头和Transformer层。

## 3. 实验设计
### 数据集与场景
- 使用 **6个公开HAR基准数据集**：
  - PAMAP2（9受试者，18种活动，3个IMU，100Hz）
  - DSADS（8受试者，19种活动，5个传感器单元，25Hz）
  - MHealth（10受试者，12种活动，3个传感器，50Hz）
  - Realworld（15受试者，8种活动，7个身体位置，50Hz）
  - UCI-HAR（30受试者，6种活动，智能手机，50Hz）
  - USC-HAD（12种活动，100Hz）
- **预处理**：所有数据重采样至100Hz，滑动窗口500样本，步长500（无重叠），20%用于微调，80%测试。

### 对比方法
- **自监督对比学习基线**：BYOL（三种增强：perm_jit、lfc、Mixup）、ModCL（最先进的对比学习）。
- **监督基线**：TSLANet（ICML 2024）、CALANet（NeurIPS 2024）。
- **消融基线**：w/o Pretrain（不预训练）、w/o Statistical Feature、w/o Metadata Embedding。

## 4. 资源与算力
- **GPU型号**：Quadro RTX 8000（40GB显存）。
- **训练配置**：batch size 512（通过梯度累积实现），AdamW优化器，学习率1e-4，权重衰减1e-5。
- **未明确说明**：训练轮数、单次预训练时长、总计算量等具体数值未给出。仅提及“所有实验在Quadro RTX 8000上运行”，但附录A.1提到“需要用到梯度累积技术”以适配显存。

## 5. 实验数量与充分性
### 实验组别
1. **主实验（表1）**：在6个数据集上对比6种基线，报告Accuracy和Macro-F1，并给出平均值。
2. **消融实验（表2）**：在PAMAP2和DSADS上验证Pre-train、Stat Feature、Metadata Embedding的必要性。
3. **超参数消融（附录B）**：对运动基元窗口长度（25/50/100）、Transformer层数（2/5/7/10）、嵌入维度（32/64/128/256）、码本大小（16/64/256/1024）进行了系统探索。
4. **稳定性实验（附录B.5）**：在PAMAP2、DSADS、Realworld上使用不同随机种子重复3次，报告均值和标准差。
5. **运动基元分析**：包括相似性矩阵（图3）、频率分布（图4）、马尔可夫转移矩阵（图13）等定性分析。

### 充分性与客观性评价
- **优点**：消融覆盖全面（组件、超参数），且遵循相同数据划分（0.2:0.8），对比基线选用了近期知名方法（TSLANet、CALANet）。
- **不足**：
  - 主实验结果**未报告误差棒或多次运行的标准差**，仅附录B.5给出了少量稳定性结果，但未纳入主表。
  - 对比方法（如BYOL、ModCL）的调参细节不完整（尽管附录A给出了部分参数）。
  - 跨数据集泛化实验仅通过预训练后在同一数据集微调实现，未做严格的“源域→目标域”零样本泛化验证。

## 6. 论文的主要结论与发现
- **性能优势**：MoPFormer在6个数据集上平均Accuracy 90.17%、F1 89.23%，优于所有对比方法，尤其在MHealth（+3%以上）和USC-HAD上提升明显。
- **可解释性**：学到的运动基元具有语义意义——相似运动形态的基元在嵌入空间中聚集，不同活动类别的基元使用分布有显著差异（动态活动集中于少数基元，静态活动分布更均匀）。
- **跨数据集一致性**：基元频率分析（图4）显示相同活动（如走路、跑步）在不同数据集上共享高频基元，表明基础运动模式具有跨数据集聚类能力。
- **组件必要性**：预训练、统计特征和元数据嵌入均对性能有重要贡献，缺失任一组件会导致显著下降（尤其移除元数据嵌入时PAMAP2准确率从86%降至58%）。

## 7. 优点：方法或实验设计上的亮点
- **创新性**：首次将IMU信号离散化为可解释的“运动基元”词汇表，类比自然语言处理中的词元，显著提升了模型透明度。
- **统一表示框架**：通过上下文感知嵌入（统计特征+元数据文本嵌入）使不同传感器配置的数据能被统一处理，支持多数据集联合预训练。
- **预训练策略**：掩码运动建模（MAE）任务有效利用了无标签数据，且微调时仅更新分类头，计算高效。
- **实验全面性**：覆盖6个数据集、多种基线（自监督与监督）、详细的超参数消融和可视化分析，提供了足够的实证支撑。

## 8. 不足与局限
- **计算开销**：VQ和Transformer编码器增加了计算复杂度，附录E明确指出“可能对资源受限的可穿戴设备上的实时推理造成问题”。
- **统计显著性缺失**：主实验未报告多次运行的均值和标准差，难以判断性能差异的统计显著性（仅附录B.5有少量重复实验）。
- **跨数据集泛化验证不足**：虽然声称“跨数据集泛化”，但实验设置是预训练后在各数据集内微调测试，而非严格的跨域零样本评估（如在未见过的数据集上直接分类）。
- **超参数敏感度**：尽管进行了消融，但最优参数（如窗口长度50、码本大小1024）可能依赖预训练数据规模，未讨论在小数据量下的鲁棒性。
- **可解释性评估**：运动基元的语义分析以定性为主，缺乏量化指标（如基元簇纯度、与人工标注子活动的对齐度）来评估可解释性的准确程度。

（完）
