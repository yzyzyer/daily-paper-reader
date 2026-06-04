---
title: Semantic-Aware Human Object Interaction Image Generation
title_zh: 语义感知的人-物交互图像生成
authors: "Zhu Xu, Qingchao Chen, Yuxin Peng, Yang Liu"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=vITl6CqIkk"
tags: ["query:hoi"]
score: 4.0
evidence: 人-物交互图像生成，涉及姿态引导
tldr: 该论文针对文本到图像生成模型中人物交互图像生成质量差的问题，提出SA-HOI框架，利用人体姿态质量和交互边界区域信息引导去噪过程，有效改善了人体姿态的合理性和交互边界的真实性，提升了HOI图像的保真度。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-vitl6cqikk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vitl6cqikk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1740, \"height\": 1020, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vitl6cqikk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 783, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vitl6cqikk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vitl6cqikk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1776, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vitl6cqikk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1774, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-vitl6cqikk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1735, \"height\": 1959, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-vitl6cqikk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 879, \"height\": 666, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-vitl6cqikk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1783, \"height\": 753, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-vitl6cqikk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-vitl6cqikk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1794, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-vitl6cqikk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 767, \"height\": 390, \"label\": \"Table\"}]"
motivation: 当前文本到图像模型在生成人-物交互图像时，人体姿态多样性导致生成效果不佳，且交互边界区域易出现语义缺失。
method: 提出SA-HOI框架，在去噪过程中引入人体姿态质量和交互边界区域信息作为引导，重点优化这些区域。
result: 实验表明，该方法能生成更真实、语义一致的人-物交互图像，尤其在姿态和边界区域有显著提升。
conclusion: 通过显式利用人-物交互的先验知识，有效提升了生成模型在复杂交互场景下的性能。
---

## Abstract
Recent text-to-image generative models have demonstrated remarkable abilities in generating realistic images. Despite their great success, these models struggle to generate high-fidelity images with prompts oriented toward human-object interaction (HOI). The difficulty in HOI generation arises from two aspects. Firstly, the complexity and diversity of human poses challenge plausible human generation. Furthermore, untrustworthy generation of interaction boundary regions may lead to deficiency in HOI semantics. To tackle the problems, we propose a Semantic-Aware HOI generation framework SA-HOI . It utilizes human pose quality and interaction boundary region information as guidance for denoising process, thereby encouraging refinement in these regions to produce more reasonable HOI images. Based on it, we establish an iterative inversion and image refinement pipeline to continually enhance generation quality. Further, we introduce a comprehensive benchmark for HOI generation, which comprises a dataset involving diverse and fine-grained HOI categories, along with multiple custom-tailored evaluation metrics for HOI generation. Experiments demonstrate that our method significantly improves generation quality under both HOI-specific and conventional image evaluation metrics. The code is available at https://github.com/XZPKU/SA-HOI.git

---

## 论文详细总结（自动生成）

# 论文中文总结：Semantic-Aware Human Object Interaction Image Generation

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：当前文本到图像生成模型（如Stable Diffusion）在生成涉及人-物交互（HOI）的提示词时，往往产生低质量图像。主要体现在两方面：  
  - 人体姿态复杂多样，模型常生成畸形或缺失肢体（如扭曲的手、缺腿）。  
  - 交互边界区域（如人手与物体接触处）生成不可信，导致HOI语义表达缺失（如“拥抱牛”但手臂未环绕）。  
- **背景**：现有扩散模型在一般物体生成上表现优秀，但在HOI场景中，语义错位发生率达60.9%（基于人工统计）。  
- **整体目标**：提出一种无需额外训练的HOI图像生成框架，通过利用姿态质量和交互边界信息引导去噪过程，提升生成图像的合理性、真实性和语义一致性。

## 2. 论文提出的方法论

- **核心思想**：通过外部检测器识别图像中低质量姿态区域和交互边界区域，在扩散模型逆过程中对这些区域施加引导（基于高斯模糊和注意力机制），促使模型逐步修正缺陷，并通过迭代增强持续优化。  
- **关键技术细节**：  
  - **Pose and Interaction Boundary Guidance (PIBG)**：  
    1. **姿态引导**：使用姿态检测器获得人体关节坐标和置信度，低置信度关节对应区域通过高斯注意力图生成掩码`M_pose`。  
    2. **交互边界引导**：利用分割工具获取物体轮廓，计算人体关节与物体轮廓最近距离，生成交互边界注意力掩码`M_inter`。  
    3. **去噪引导**：在每个去噪步骤中，对`ˆx0`进行高斯模糊得到`˜x0`和`˜xt`；利用掩码将模糊后的特征与原始特征融合（`ˇx_pose_t = (1-M_pose)⊙xt + M_pose⊙˜xt`），然后预测噪声`ˇϵ_pose_t`；类似得到`ˇϵ_inter_t`。最终组合两种引导噪声，并通过类似自我注意力引导（SAG）的方式生成最终噪声`˜ϵt`。  
  - **掩码阈值动态调整**：阈值`ϕt`随采样时间和总体注意力值变化，实现渐进精细修正。  
  - **Iterative Inversion and Refinement (IIR)**：通过空文本反演（Null-text Inversion）从当前图像提取噪声和文本嵌入，再将其输入PIBG生成下一轮图像；使用质量评估器Q（默认PCS，即姿态置信度）判断是否继续迭代，直至质量无显著提升。  

- **算法流程（文字说明）**：  
  - 初始化图像`I0`，检测姿态和交互边界，生成掩码`M_pose`、`M_inter`。  
  - 对每个去噪步骤`t=T到1`：计算噪声和中间重建，应用高斯模糊，根据掩码融合特征，预测引导噪声，结合文本条件形成最终噪声，更新`x_{t-1}`。  
  - 完成一轮生成后，通过IIR反复“反演-评估-精炼”，直到连续两轮PCS提升小于阈值。

## 3. 实验设计

- **数据集与场景**：  
  - 使用**HICO-DET**数据集构建HOI生成Benchmark，包含150个HOI类别，分三个子场景：  
    - **H-A**（人类-动物）：91个类别（如“pet horse”）。  
    - **H-O**（人类-物体）：49个类别，动词均为“hold”（如“hold a bottle”）。  
    - **H-H**（人类-人类）：10个类别（如“hug a person”）。  
  - 每个类别随机采样最多200张真实图片，共约5k张作为参考分布。  
- **对比方法**：Stable Diffusion v1.5（基线）、SAG（Self-Attention Guidance）、Diffusion HPC（利用SMPL额外姿态先验）。  
- **评估指标**：  
  - 通用指标：FID、KID。  
  - HOI定制指标：  
    - **Authenticity**：姿态分布距离（PDD）、人-物距离分布（HODD）。  
    - **Plausibility**：姿态置信度得分（PCS，分身体/手）。  
    - **Fidelity**：HOI检测置信度（HOIF）、CLIP检索准确率（R-accuracy）。  
  - 主观评价：26名参与者对4个维度（人体姿态真实性、物体外观、交互语义、总体质量）评分。  
- **实验分组**：  
  - 在H-A、H-O、H-H三个场景下分别对比。  
  - 消融实验：组件贡献（姿态引导、交互边界引导、迭代精炼）、姿态引导形式（身体/手/动物）、参数敏感性（引导尺度s、高斯核标准差σ、阈值ϕ0、α）。

## 4. 资源与算力

- **算力**：使用**两张A100 80G GPU**，基于Stable Diffusion v1.5的预训练权重。未说明额外训练或训练时长，也未给出单次推理时间。论文强调是**无需额外训练**的零样本方法。

## 5. 实验数量与充分性

- **实验数量**：  
  - 通用指标对比：3个场景 × 4种方法 = 12组FID/KID结果。  
  - HOI定制指标对比：3场景 × 4方法 × 7个子指标 = 84个数值。  
  - 消融实验：组件贡献（7行表格）、姿态引导形式（7行表格）、参数敏感性（4张图，每个参数4-6个点）。  
  - 主观评价：10个提示词 × 5种条件（含真实图片）× 26人 = 5200份评分。  
- **充分性与公平性**：实验覆盖三种交互场景，对比了主流基线；消融实验验证了每个组件的必要性；参数敏感性分析展示了鲁棒性。但缺乏与其他基线（如ControlNet）的直接比较，且所有实验均基于同一数据集HICO-DET，未在额外数据集上验证泛化性。主观评价样本量适中，但评分者可能非专业。

## 6. 论文的主要结论与发现

- 所提SA-HOI在所有场景下，**通用指标（FID/KID）和HOI定制指标**均优于Stable Diffusion、SAG和Diffusion HPC。  
- 姿态引导显著提升身体和手部姿态置信度（PCS），交互边界引导提升语义一致性（HOIF、R-accuracy）。  
- 迭代精炼(IIR)可持续提升质量，基于PCS的停止准则有效。  
- 消融实验表明：组合所有组件达到最佳性能；手部姿态引导可融入框架；参数选择对性能有影响但非剧烈。

## 7. 优点

- **无需额外训练**：直接利用预训练的Stable Diffusion和现成检测器，零样本迁移。  
- **针对性强**：明确针对HOI生成的两大难点（姿态畸形和边界缺失），设计专门的引导机制。  
- **可扩展性好**：可灵活添加不同类型姿态引导（身体、手、动物），适应不同类别。  
- **迭代优化**：通过反演-精炼-评估循环实现渐进式改善，且用质量指标自动停止。  
- **首次提出HOI生成Benchmark**：涵盖150类别、三类交互，并提供专门评价指标，填补领域空白。

## 8. 不足与局限

- **依赖外部检测器**：姿态和分割检测器质量直接影响引导准确性，若检测器在复杂场景下失效，引导可能误判。  
- **计算开销**：每次精炼迭代都需要完整的去噪过程（50步）加反演，多轮迭代耗时明显。  
- **实验覆盖不足**：  
  - 未与其他定制化生成方法（如ControlNet在姿态控制上）对比。  
  - 仅基于HICO-DET数据集，未在更复杂或真实弱监督场景下验证。  
  - 主观评价中真实图片（GT）评分可能因标注偏差而偏高。  
- **应用限制**：仅针对2D图像生成，未考虑3D HOI；掩码阈值参数需手动调节（如ϕ0、α）。  
- **潜在偏差风险**：姿态检测器可能对少见姿态或不常见物体表现不佳，导致引导失败；HOI检测器作为评估器可能存在偏差。

（完）
