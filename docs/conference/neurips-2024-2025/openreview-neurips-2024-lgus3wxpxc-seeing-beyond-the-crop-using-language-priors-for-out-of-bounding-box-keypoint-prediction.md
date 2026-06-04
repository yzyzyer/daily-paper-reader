---
title: "Seeing Beyond the Crop: Using Language Priors for Out-of-Bounding Box Keypoint Prediction"
title_zh: 超越裁剪：使用语言先验进行边界框外关键点预测
authors: "Bavesh Balaji, Jerrin Bright, Yuhao Chen, Sirisha Rambhatla, John S. Zelek, David Anthony Clausi"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=LGus3wXPxc"
tags: ["query:hoi"]
score: 8.0
evidence: 使用语言先验估计人体和交互物体的姿态，直接相关手物交互中的姿态估计
tldr: 现有交互姿态估计方法需要将物体与人体同框，导致引入干扰且限制性能。该论文提出TokenCLIPose，仅利用框内人体关键点，结合CLIP语言先验预测框外物体关键点。在体育数据集上实验表明，该方法能准确估计交互物体（如曲棍球杆）的6D姿态，显著提升动作识别精度。语言先验的引入使得模型无需依赖物体可见性，拓展了交互姿态估计的适用范围。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-lgus3wxpxc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1405, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lgus3wxpxc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lgus3wxpxc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lgus3wxpxc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 841, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-lgus3wxpxc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1405, \"height\": 737, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-lgus3wxpxc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lgus3wxpxc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1167, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lgus3wxpxc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 534, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lgus3wxpxc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 542, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lgus3wxpxc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 765, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lgus3wxpxc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1146, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lgus3wxpxc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 518, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-lgus3wxpxc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1255, \"height\": 200, \"label\": \"Table\"}]"
motivation: 现有方法将交互物体与人同框，引入噪声且限制边界框大小，影响性能。
method: 提出TokenCLIPose，基于框内人体关键点，利用CLIP语言先验直接预测框外物体关键点。
result: 在体育动作数据集上，准确预测曲棍球杆等物体姿态，优于传统同框方法。
conclusion: 语言先验有效替代物体显式可见性，提升交互姿态估计的鲁棒性和实用性。
---

## Abstract
Accurate estimation of human pose and the pose of interacting objects, like a hockey stick, is crucial for action recognition and performance analysis, particularly in sports. Existing methods capture the object along with the human in the bounding boxes, assuming all keypoints are visible within the bounding box. This necessitates larger bounding boxes to capture the object, introducing unnecessary visual features and hindering performance in real-world cluttered environments. We propose a simple image and text-based multimodal solution TokenCLIPose that addresses this limitation. Our approach focuses solely on human keypoints within the bounding box, treating objects as unseen. TokenCLIPose leverages the rich semantic representations endowed by language for inducing keypoint-specific context, even for occluded keypoints. We evaluate the performance of TokenCLIPose on a real-world Ice-Hockey dataset, and demonstrate its generalizability through zero-shot transfer to a smaller Lacrosse dataset. Additionally, we showcase its flexibility on CrowdPose, a popular occlusion benchmark with keypoints within the bounding box. Our method significantly improves over state-of-the-art approaches on all three datasets, with gains of 4.36\%, 2.35\%, and 3.8\%, respectively.

---

## 论文详细总结（自动生成）

# 超越裁剪：使用语言先验进行边界框外关键点预测——论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：2D人体姿态估计对于动作识别、人-物交互检测至关重要。在体育场景（如冰球、长曲棍球）中，人体与交互物体（如球杆）的姿态联合估计困难。现有SOTA方法采用自上而下的方式：先用检测器生成包含人体和物体的边界框，再估计框内所有关键点。但将物体也框入会扩大视野、引入无关视觉特征，在杂乱场景中性能下降。
- **核心问题**：能否只将人体框入边界框，而将物体关键点视为“不可见”（unseen）？这样可减少背景干扰，但会丢失物体视觉信息。如何利用语言先验来推断这些不可见关键点的空间关系？
- **整体含义**：提出TokenCLIPose，一种基于图像和文本的多模态方法，利用CLIP语言先验为每个关键点提供语义上下文，从而预测边界框外（甚至遮挡）的关键点。该方法不仅适用于人-物交互场景，也可推广到一般遮挡场景（如CrowdPose）。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：将物体关键点视为“不可见”，仅使用人体边界框内的图像特征，结合语言先验（CLIP文本嵌入）生成关键点特定的文本token，再通过Transformer解码器融合多模态token，直接回归所有关键点坐标（包括框外）。
- **技术细节**：
  - **图像编码器**：CNN（如ResNet-50、HRNet-W48、MSPN）提取多尺度特征图，经MLP生成粗人体关键点位置 $\hat{\mu}_f$ 和尺度 $\hat{\sigma}_f$；同时将特征图投影到联合多模态嵌入空间得到图像token $F_{vis}$。
  - **文本关键点编码器**：利用CLIP预训练文本编码器，为每个关键点（人体17个+物体3个）生成文本token $F_{text}$。文本提示采用prompt ensemble（如“a photo of left wrist”等），增强表示丰富性。
  - **位置token**：将粗关键点位置 $\hat{\mu}_f$ 投影到嵌入空间得到 $F_{loc}$。
  - **Transformer解码器**：将 $F_{vis}$、$F_{text}$、$F_{loc}$ 拼接后通过自注意力层，捕获全局依赖关系，最后通过MLP输出最终关键点预测 $\hat{\mu}_d$ 和尺度 $\hat{\sigma}_d$。使用register token减少伪影。
  - **损失函数**：采用残差对数似然估计（RLE）损失，将回归建模为分布学习，使用RealNVP流模型估计偏差。总损失 $L = L_{RLE}^f + L_{RLE}^d$ 分别监督粗预测和最终预测。
- **公式简要**：RLE损失形式为 $L_{RLE} = -\log Q(\bar{\mu}_g) - \log G_{\phi}(\bar{\mu}_g) - \log s + \log \hat{\sigma}$，其中 $\bar{\mu}_g = (\mu_g - \hat{\mu})/\hat{\sigma}$。
- **关键创新**：用文本先验初始化可学习token，而非直接对齐图像与文本嵌入；通过Transformer自注意力融合多模态信息，避免全局结构丢失。

## 3. 实验设计

- **数据集**：
  - **冰球数据集**：自建，来自NHL比赛视频，10个片段（30-45秒，30fps），共11.66K姿态标注。17个人体关键点 + 3个冰球杆关键点（柄端、跟部、趾部）。训练集9个片段（9.13K），测试集1个片段（2.53K）。
  - **长曲棍球数据集**：自建，1个视频，300个姿态标注，12个人体关键点 + 2个球杆关键点（无趾部），用于零样本迁移测试。
  - **CrowdPose**：标准遮挡基准，12K训练图像（43.4K人），8K测试图像（29K人），17个人体关键点，用于验证框内不可见关键点预测。
- **Benchmark**：PCKh@0.5（冰球、长曲棍球），AP/AP50/AP75（CrowdPose）。
- **对比方法**：SimpleBaseline (ResNet-50)、MSPN、HRNet-W48、TokenPose-L/D24、ViTPose、Mask-RCNN、AlphaPose、CrowdPose、Hourglass-104、KAPAO-L、Transpose-H、HRFormer-B、LAMP（多模态）等。

## 4. 资源与算力

- 文中明确提到：所有模型在单张NVIDIA GeForce RTX 4090 GPU上训练。
- 训练参数：图像尺寸256×192或384×288，batch size 64，优化器Adam/AdamW，学习率6e-4或3e-4，权重衰减1e-5，总epoch 200，使用stepLR学习率衰减。
- 具体训练时长未明确给出，但指出使用了单张4090。

## 5. 实验数量与充分性

- **主要实验**：三个数据集上的性能对比（表1、2、3），每组均与多种SOTA方法对比。
- **消融实验**：四大类共7组，包括：
  - 各模态贡献（表4）：移除文本token、位置token等。
  - 注意力机制选择（表5）：自注意力 vs 交叉注意力 vs Intention。
  - 文本提示影响（表6）：无文本、单提示、prompt ensemble。
  - 边界框质量影响（表7）：Faster-RCNN vs 真实边界框。
- **零样本迁移**：从冰球模型直接迁移到长曲棍球（表2）。
- **与LAMP对比**（附录表8）。
- **定性结果**：多幅示例图。
- **充分性**：实验覆盖了主要任务（人体+物体、人体+遮挡）、多数据集、多消融，且与多个SOTA公平对比（相同阈值、相同输入尺寸等）。实验设计客观、全面。

## 6. 论文的主要结论与发现

- 将物体关键点视为“不可见”并使用语言先验，可有效预测边界框外关键点，性能显著优于传统将物体同框的方法。
- 多模态融合（图像+文本+位置token）通过自注意力捕捉全局关系比直接对齐图像-文本嵌入更有效。
- 文本先验质量影响性能：prompt ensemble比单提示更优；使用CLIP预训练嵌入比随机初始化提升2.31%准确率。
- 模型对边界框质量鲁棒（真实框仅比检测框高2.47%）。
- 零样本迁移能力：冰球模型直接应用于长曲棍球数据集，取得2.35%提升，证明语义泛化性。
- 在CrowdPose上同样提升3.8%，证明方法对框内遮挡关键点也有效。

## 7. 优点

- **方法创新**：将物体姿态估计重构为不可见关键点预测，利用语言先验替代显式视觉信息，思路新颖简洁。
- **实用价值**：避免扩大边界框引入噪声，适用于体育分析、动作识别等场景，减少对传感器依赖。
- **实验充分**：自建两个体育数据集填补空白，并在标准遮挡基准上验证通用性；消融实验覆盖各组件，结论可靠。
- **泛化性**：零样本迁移成功，展示语言先验的跨域适应能力。
- **公平性**：所有对比使用相同阈值和评价指标，明确说明数据拆分。

## 8. 不足与局限

- **未公开代码和数据集**：文中提及需机构许可，但不可复现，限制后续验证。
- **未报告误差棒**：未提供多次运行的标准差，难以评估结果稳定性（尽管遵循领域惯例）。
- **局限性未单独讨论**：论文未明确讨论局限性章节，如对极端遮挡或复杂背景的鲁棒性边界、计算成本、模型规模等。
- **数据集规模较小**：冰球数据集仅10个视频，长曲棍球仅300标注，可能存在偏差或过拟合风险。
- **物体类型有限**：仅测试了球杆类刚体，未验证对非刚体或更复杂交互物体的适用性。
- **语言先验依赖**：提示工程（prompt engineering）可能影响性能，且需预先定义关键点名称，难以处理未知物体。

（完）
