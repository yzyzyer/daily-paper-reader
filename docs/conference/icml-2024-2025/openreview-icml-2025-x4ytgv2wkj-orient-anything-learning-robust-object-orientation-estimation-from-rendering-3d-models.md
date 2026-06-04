---
title: "Orient Anything: Learning Robust Object Orientation Estimation from Rendering 3D Models"
title_zh: Orient Anything：基于3D模型渲染的鲁棒物体方向估计
authors: "Zehan Wang, Ziang Zhang, Tianyu Pang, Chao Du, Hengshuang Zhao, Zhou Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=x4yTgv2WkJ"
tags: ["query:hoi"]
score: 7.0
evidence: 单目图像零样本物体方向估计，可直接用于手操作中的物体姿态估计
tldr: 针对开放世界物体方向估计缺乏标注的问题，本文提出Orient Anything，通过渲染3D模型构建200万张带标注图像，训练出首个零样本物体方向估计基础模型。该方法可直接迁移到手操作场景中，为物体姿态提供关键方向信息。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 662, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1756, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 866, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 1135, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1681, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 847, \"height\": 2263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 858, \"height\": 613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 856, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 853, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 847, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 338, \"height\": 275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 333, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 321, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 337, \"height\": 275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 333, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 321, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 311, \"height\": 317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 310, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 308, \"height\": 312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 312, \"height\": 317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 311, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 345, \"height\": 237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 331, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 335, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 345, \"height\": 238, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 331, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-x4ytgv2wkj/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 334, \"height\": 334, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-x4ytgv2wkj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-x4ytgv2wkj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-x4ytgv2wkj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-x4ytgv2wkj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-x4ytgv2wkj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-x4ytgv2wkj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 888, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-x4ytgv2wkj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 855, \"height\": 1514, \"label\": \"Table\"}]"
motivation: 开放世界物体方向估计缺乏标注数据，现有方法在新类别上表现不佳。
method: 利用3D模型库，自动标注物体正面方向并渲染多视角图像，训练基础模型。
result: 在多个数据集上达到最先进零样本性能，尤其对未见物体有良好泛化。
conclusion: 零样本方向估计为手物交互中的物体感知提供了可行方案。
---

## Abstract
Orientation is a fundamental attribute of objects, essential for understanding their spatial pose and arrangement. However, practical solutions for estimating the orientation of open-world objects in monocular images remain underexplored. In this work, we introduce Orient Anything, the first foundation model for zero-shot object orientation estimation. A key challenge in this task is the scarcity of orientation annotations for open-world objects. To address this, we propose leveraging the vast resources of 3D models. By developing a pipeline to annotate the front face of 3D objects and render them from random viewpoints, we curate 2 million images with precise orientation annotations across a wide variety of object categories. To fully leverage the dataset, we design a robust training objective that models the 3D orientation as probability distributions over three angles and predicts the object orientation by fitting these distributions. Besides, we propose several strategies to further enhance the synthetic-to-real transfer. Our model achieves state-of-the-art orientation estimation accuracy on both rendered and real images, demonstrating impressive zero-shot capabilities across various scenarios. Furthermore, it shows great potential in enhancing high-level applications, such as understanding complex spatial concepts in images and adjusting 3D object pose.

---

## 论文详细总结（自动生成）

# 论文总结：Orient Anything: Learning Robust Object Orientation Estimation from Rendering 3D Models

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：物体方向（orientation）是理解物体空间姿态和布局的基础属性，但在单目图像中估计开放世界物体的方向仍未被充分探索。现有方法（如ObjectNet3D、Omni3D）受限于特定领域和有限类别，且缺乏大规模标注数据。
- **研究动机**：当前视觉基础模型和大型视觉语言模型（如GPT-4o、Gemini）在物体识别、定位、跟踪、分割等任务上表现优异，但在物体方向理解上能力不足，甚至难以完成基本的空间推理（如判断左右）。这暴露出方向感知这一基础属性的缺失。
- **论文目标**：提出首个用于零样本物体方向估计的基础模型——**Orient Anything**，通过利用3D模型资源自动生成大规模带精确方向标注的图像，训练模型在未见过的真实场景中泛化。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
利用海量3D模型（Objaverse），通过自动标注物体正面方向并渲染随机视角，生成200万张带精确方向标注的图像，训练一个能够进行零样本方向估计的模型。

### 关键技术细节
1. **方向数据收集流水线**：
   - **步骤1：规范3D模型过滤**：剔除倾斜物体（通过PCA分析边缘主方向与坐标轴对齐程度），仅保留规范姿态的物体（约55K个）。
   - **步骤2：方向标注**：利用先进的2D VLM（Gemini-1.5-Pro）从五个正交视图（x, -x, y, -y, z）中识别物体的正面。引入对称性分析（SIFT、SSIM、像素颜色相似度）减少幻觉，对对称物体标记为“无正面”。
   - **步骤3：自由视角渲染**：将物体缩放到单位立方体，对齐到原点，从随机视角渲染每物体40张512×512图像，共200万张。

2. **Orient Anything模型**：
   - 使用视觉编码器（基于DINOv2初始化）提取特征，后接多个预测头，输出三个角度（极角θ、方位角φ、旋转角δ）的概率分布和一个方向置信度c。
   - **学习目标**：将角度预测转化为概率分布拟合任务。对θ采用高斯分布离散化，对φ和δ（周期性）采用圆形高斯分布。使用交叉熵损失监督分布预测，同时用二值交叉熵损失监督有无正面的判断。
   - **推理**：置信度>0.5时取各分布最大值对应的角度作为预测。

3. **合成到真实域的迁移策略**：
   - **初始化**：对比MAE、CLIP、DINOv2，发现DINOv2因任务无关预训练和细粒度感知能力最佳。
   - **数据增强**：随机裁剪模拟遮挡；对多物体场景使用分割模型提取单个物体再估计方向。

## 3. 实验设计

### 使用的数据集/场景
- **训练数据**：Objaverse中55K个物体，渲染200万张图像。
- **评估基准**：
  - **真实场景基准**：SUN RGB-D、KITTI、nuScenes、Objectron（各1000个物体，计算方位角/极角/旋转角绝对误差）、Pascal3D+、Pix3D（Acc@30°和整体3D空间绝对误差）。
  - **零样本野外场景**：从COCO验证集中每类20张，共1600张图像，标注8方向水平方向识别。
  - **渲染图像基准**：从Objaverse中手动选择300个物体（150个有正面，150个无），每物体16个视角，共4800张图像。
  - **Ori-Bench**：自建200张图像的VQA基准，用于评估VLM的方向理解能力（包括方向识别、空间部位推理、空间关系推理）。

### 对比方法
- **全监督基线**：Cube RCNN（基于Omni3D训练）。
- **少样本基线**：FSDetView（在Pascal3D+和Pix3D上）。
- **VLM基线**：GPT-4o、Gemini-1.5-Pro（通过文本提示进行方向估计）。
- **零样本/微调基线**：ImageNet3D-ResNet50、ImageNet3D-DINOv2-B（在ImageNet3D数据集上）。

### 评估指标
- 角度绝对误差（Azimuth/Polar/Rotation）、Acc@X°（允许±X°误差）、方向判断准确率、水平方向识别准确率。

## 4. 资源与算力

- **训练硬件**：4块A100（40GB）GPU。
- **训练规模**：
  - 模型规模：ViT-S、ViT-B、ViT-L（均使用DINOv2初始化）。
  - 优化器：AdamW，视觉编码器学习率1e-5，预测头学习率1e-3。
  - 训练步数：50,000步，批大小64，总训练数据200万张图像。

## 5. 实验数量与充分性

- **实验数量**：
  - **零样本真实场景评估**：在6个数据集（SUN RGB-D、KITTI、nuScenes、Objectron、Pascal3D+、Pix3D）上对比了全套模型（ViT-S/B/L），并报告了与Cube RCNN、FSDetView的对比（表2）。
  - **大规模数据集评估**：在ImageNet3D上进行了零样本和微调评估（表3）。
  - **渲染图像和真实图像评估**：表4对比了Ori-Bench上的结果，包括方向判断和角度预测。
  - **消融实验**：包括方向标注方法（表5）、概率分布方差超参数（图5）、学习目标（回归 vs 分类 vs 拟合，表6）、渲染视图数量（10~80，表6）、模型初始化（CLIP/MAE/DINOv2，表6）、数据增强（表6）。
  - **应用实验**：在Ori-Bench上使用Orient Anything+LLM提升空间理解（表1），以及生成图像评分、3D模型投票等定性示例。
- **充分性**：实验覆盖了多种域内/域外场景、不同模型规模、充分的消融，对比了全监督、少样本、零样本和VLM方法，实验设计相对全面。但在某些数据集上（如Objectron）模型表现相对较弱，说明存在领域差距。
- **公平性**：与Cube RCNN等监督方法比较时，论文明确指出Orient Anything是零样本，而Cube RCNN是监督训练，这种“不公平”比较恰恰突出了零样本优势。与VLM的比较也使用了标准prompt。

## 6. 主要结论与发现

- **零样本能力卓越**：Orient Anything（ViT-L）在几乎所有真实世界基准上均优于现有方法。例如在COCO水平方向识别上平均准确率72.44%，大幅超过GPT-4o（45.78%）和Gemini（31.95%）。
- **概率分布拟合是关键**：相比直接回归或分类，分布拟合显著提升性能（表6中方位角Acc@22.5°从12.00%提升至71.88%）。
- **合成到真实迁移有效**：通过DINOv2初始化和随机裁剪增强，模型在未见过的真实图像上表现接近渲染图像（例如渲染图像方位角Acc@22.5°为71.88%，真实场景水平识别为70.19%）。
- **应用价值**：Orient Anything可赋能空间理解（解决VLM的左右混淆）、生成图像质量评估、3D模型方向投票等任务。

## 7. 优点

1. **数据生成创新**：提出自动化的3D物体方向标注流水线，利用VLM和对称性分析，低成本、大规模获得精确标注，覆盖7204个WordNet实体，远超以往数据集。
2. **学习目标设计合理**：将角度预测转化为概率分布拟合，解决了连续回归不收敛、分类忽略相邻角度相关性的问题。
3. **零样本泛化强**：无需真实标注即可在多个域上达到SOTA，展示了作为基础模型的潜力。
4. **充分的可迁移性分析**：对比多种预训练编码器，验证了DINOv2的优越性；通过数据增强缩小合成-真实域差距。
5. **开源与可复现**：论文提供了项目主页和附件，便于社区验证。

## 8. 不足与局限

1. **实验覆盖的局限性**：
   - 主要评估集中在室内/街道场景（SUN RGB-D、KITTI、nuScenes）和COCO常见类别，对极端场景（如遮挡严重、低光照、小物体）的测试较少。
   - 方向标注仅考虑八方向水平方向，缺乏对连续角度的精细评估，尤其在野外场景。
   - 未在真实操作/手物交互场景下评估（如机器人抓取、AR），应用验证偏定性。
2. **模型本身局限**：
   - 仅估计物体相对于相机的方向，未输出完整6D姿态（缺少位置和尺度）。
   - 依赖分割或检测模型先提取物体实例，引入误差累积（论文使用了SAM，但未作定量分析）。
   - 对于对称物体或无明显正面的物体（如球、凳子），模型输出“无方向”，但实际应用中可能需要更细粒度的定义。
3. **数据偏差风险**：
   - 3D模型库Objaverse本身存在类别不平衡（如家具、工具多，而某些自然物体少）。
   - 过滤倾斜物体可能导致对非规范姿态物体的泛化能力未知。
4. **与其他方法的比较**：
   - 与Cube RCNN相比，尽管零样本更优，但未报告在同等监督条件下的对比（即用相同训练数据微调Cube RCNN或Orient Anything）。
   - 与VLM的对比中，VLM的prompt设计可能影响结果，论文未提供多种prompt的消融。
5. **资源计算**：虽然给出了GPU数量和训练步数，但未提供显存占用、单步时间等细节，不利于复现。

（完）
