---
title: "Pose Prior Learner: Unsupervised Categorical Prior Learning for Pose Estimation"
title_zh: Pose Prior Learner：无监督类别先验学习用于姿态估计
authors: "Ziyu Wang, Shuangpeng Han, Mengmi Zhang"
date: 2025-01-23
pdf: "https://openreview.net/pdf?id=0OdIwdiFb7"
tags: ["query:hoi"]
score: 7.0
evidence: 无监督类别先验学习用于物体姿态估计，可迁移至手操作中的物体姿态
tldr: 针对物体姿态估计中先验获取困难的问题，本文提出Pose Prior Learner（PPL）方法，通过层次化记忆存储原型姿态的组成部件，蒸馏出通用姿态先验，从而提升姿态估计精度。该方法可泛化到任意物体类别，为手操作中的物体姿态估计提供了一种可迁移的先验学习框架。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-0odiwdifb7/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1517, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0odiwdifb7/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1390, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0odiwdifb7/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1395, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0odiwdifb7/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1201, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0odiwdifb7/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 715, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0odiwdifb7/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 820, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0odiwdifb7/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1559, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0odiwdifb7/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 868, \"height\": 611, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0odiwdifb7/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1610, \"height\": 978, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-0odiwdifb7/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0odiwdifb7/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 733, \"height\": 429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0odiwdifb7/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 602, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0odiwdifb7/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1593, \"height\": 371, \"label\": \"Table\"}]"
motivation: 现有姿态估计方法依赖标注数据学习先验，但获取通用先验困难，尤其缺乏无监督学习机制。
method: 提出PPL，利用层次化记忆存储原型姿态部件，通过模板变换和图像重建蒸馏先验。
result: 在多个物体类别上验证，该方法有效提升了姿态估计精度，且无需人为标注。
conclusion: 无监督先验学习为物体姿态估计提供了通用解决方案，可推广至手物交互场景。
---

## Abstract
A prior represents a set of beliefs or assumptions about a system, aiding inference and decision-making. In this paper, we introduce the challenge of unsupervised categorical prior learning in pose estimation, where AI models learn a general pose prior for an object category from images in a self-supervised manner.
Although priors are effective in estimating pose, acquiring them can be difficult. We propose a novel method, named Pose Prior Learner (PPL), to learn a general pose prior for any object category. PPL uses a hierarchical memory to store compositional parts of prototypical poses, from which we distill a general pose prior. This prior improves pose estimation accuracy through template transformation and image reconstruction. PPL learns meaningful pose priors without any additional human annotations or interventions, outperforming competitive baselines on both human and animal pose estimation datasets. Notably, our experimental results reveal the effectiveness of PPL using learned prototypical poses for pose estimation on occluded images. Through iterative inference, PPL leverages the pose prior to refine estimated poses, regressing them to any prototypical poses stored in memory. Our code, model, and data will be publicly available.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：姿态估计（pose estimation）中，先验知识（prior）对于提升推理鲁棒性至关重要，但获取通用类别先验（categorical prior）极为困难，尤其是对于新物体类别需要大量人工标注。现有无监督姿态估计方法要么完全无先验（易受背景干扰、产生不合理拓扑结构），要么依赖手工定义的先验（需人工标注、且可能引入偏差）。作者提出三个关键问题：如何自主获取先验？能否以自监督方式从数据中学习先验？能否提升先验质量？
- **整体含义**：该工作首次提出“无监督类别先验学习”（unsupervised categorical prior learning）这一挑战，并设计 Pose Prior Learner（PPL）方法，让模型从图像中自监督地学习任意物体类别的通用姿态先验，无需任何人类注释。该方法在人类、动物等多种类别上取得优越性能，并能处理遮挡场景中的姿态估计。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：使用层次化记忆（hierarchical memory）存储原型姿态的组成部件（compositional parts），从中蒸馏出通用姿态先验 \( V = (T, W) \)，其中 \( T \) 是关键点先验（N个2D坐标点），\( W \) 是连接先验（N×N连接概率矩阵）。先验通过仿射变换与图像特征结合，生成图像特定姿态，并通过图像重建进行自监督学习。
- **关键技术细节**：
  1. **记忆结构与蒸馏**：层次记忆 \( M \) 包含 \( m \) 个记忆库（memory banks），每个记忆库有 \( k \) 个可学习向量。训练时，估计的关键点 \( T' \) 经 MLP-Mixer 编码为 \( m \) 个token \( G \)，每个 token 从对应记忆库中检索最相似向量构成 \( G' \)，再解码为重构关键点 \( T'_{\text{recon}} \)。通过重构损失 \( L_{kr} \) 训练记忆。蒸馏阶段：对每个记忆库做平均池化，再解码得到关键点先验 \( T \)。
  2. **先验变换**：从图像 \( I \) 提取特征 \( h_I \)，关键点先验 \( T \) 经全连接层得到嵌入 \( h_T \)，两者连接后预测每个关键点的仿射变换参数 \( \Theta_i \)，变换得到图像特定关键点 \( T' \)。
  3. **连接先验调制**：根据连接先验 \( W \) 对任意两个关键点间的链接热图加权，并通过最大池化得到组合链接热图 \( S \)，再与参考图像 \( I_{\text{ref}} \) 拼接送入解码器重建图像。
  4. **损失函数**：图像重建感知损失 \( L_{ir} \)、边界损失 \( L_b \)、链接长度正则化损失 \( L_l \)、关键点配置重构损失 \( L_{kr} \)。
  5. **训练技巧**：使用 VQ-VAE 风格的梯度拷贝、指数移动平均更新记忆、梯度分离解决“鸡生蛋”问题。
  6. **迭代推理**：对于遮挡图像，将上一轮重建图像作为输入，利用记忆和先验逐步修正关键点，四个迭代后收敛。

## 3. 实验设计

- **数据集**：
  - **Human3.6m**（人类姿态估计）：6种活动，训练集 subjects 1,5,6,7,8,9，测试集 subject 11。
  - **Taichi**（太极拳）：3049训练视频、285测试视频，取5000帧训练、300帧测试。
  - **CUB-200-2011**（鸟类）：11788张图像，使用标准分割。
  - 定性可视化：YouTube 狗视频、11k-Hands、Horses、Flowers。
- **Benchmark**：基于关键点检测的 L2 误差（归一化或求和）。对于 CUB 报告 mean L2 error（128×128），Human3.6m 报告 normalized L2 error（256×256 或 128×128），Taichi 报告 summed L2 error（256×256）。
- **对比方法**：
  - 无先验方法：Zhang et al. 2018、He et al. 2021、He et al. 2022b、AutoLink、Jakab et al.、Thewlis et al.、Lorenz et al. 等。
  - 使用人工定义先验的方法：STT（Shape Template Transforming）。
- **评估指标**：主要用关键点 L2 误差。

## 4. 资源与算力

- **文中未明确说明**：未给出具体 GPU 型号、数量、训练时长等算力信息。仅提及使用 Adam 优化器，学习率 1e-3，batch size 64，训练 50 epochs。所有图像 resize 到 256×256（部分 128×128）。层次记忆：34个记忆库，每个库16个512维向量。未提及分布式或多卡训练。

## 5. 实验数量与充分性

- **实验组数**：
  - **定量主实验**：3个数据集（Human3.6m、Taichi、CUB-200-2011），每个数据集对比多个基线方法。
  - **消融实验**：
    - 先验变体（12种组合）：关键点先验与连接先验的不同初始化（预定义/随机）和可学习性。
    - 记忆库向量数量与维度的消融（图 A1）。
    - 关键点数量的消融（4到32个关键点）。
  - **遮挡实验**：两种掩码方式（RandomMasking、CenterMasking），多种遮挡比例/大小，监控迭代推理的效果（图 A2、A3）。
  - **定性可视化**：多种类别（人、狗、手、鸟、马、花），展示学习到的先验随训练epoch的变化（图4b）。
- **充分性与公平性**：
  - 主实验对比了充分多的基线（包括无先验和人工先验），且在同一标准设置下比较（关键点数量与 AutoLink 一致）。
  - 消融实验设计系统，覆盖先验初始化、记忆参数、关键点数等关键因素。
  - 遮挡实验展示了迭代推理的有效性，但未与其他遮挡处理方法对比（仅自身消融）。
  - 不足：部分数据集（狗、花等）仅定性展示，无定量指标；与人工先验方法（STT）对比时，仅在一个数据集（Human3.6m）上报告，且缺少统计显著性检验。

## 6. 主要结论与发现

- PPL 在所有数据集上显著优于所有无先验和人工先验基线。
- 学习到的先验比人工定义的先验更有效（例如 PPL 在 Human3.6m 上比使用人工先验的 STT 更优）。
- 连接先验（W）比关键点先验（T）更关键：冻结随机连接先验导致模型不收敛，而冻结随机关键点先验仍可训练。
- 层次化记忆能够存储原型姿态，在遮挡场景下通过迭代推理逐步恢复完整姿态，且随迭代次数增加误差降低。
- 先验随着训练逐渐收敛到合理的骨架结构（例如人类先验收敛至对应关节位置，连接权重收敛于物理连接）。
- PPL 可泛化到不同物体类别（人类、狗、鸟、手、马、花）。

## 7. 优点

- **创新性**：首次提出无监督类别先验学习挑战，并设计端到端可学习的层次记忆+蒸馏机制，无需任何人工标注。
- **自监督框架**：仅依赖图像重建信号，可适用于视频或静态图像（通过随机掩码作为参考图像）。
- **遮挡鲁棒性**：通过迭代推理利用存储的原型姿态有效修复遮挡部位，实验验证了有效性。
- **可解释性**：可视化先验随训练演化的过程，展示学习到的关键点和连接语义。
- **泛化性**：在多种物体类别上均有效，且超越人工先验方法。

## 8. 不足与局限

- **2D先验局限**：方法仅学习2D先验，无法处理3D旋转或大幅形变（如狗转身），导致对非刚性、大幅度姿态变化不鲁棒。
- **实验覆盖不全**：部分类别（狗、花、手、马）仅定性展示，缺少定量指标；遮挡实验未与传统遮挡处理方法对比；与人工先验方法的消融仅在 Human3.6m 上进行。
- **算力资源缺失**：未报告GPU型号、数量、训练时间，不利于可重复性评估。
- **潜在偏差**：训练数据来自特定分布（如 Human3.6m 背景静态、Taichi 单一动作），先验可能过拟合于该分布，泛化到真实复杂场景需验证。
- **推理迭代次数固定**：文中使用4次迭代，未分析不同迭代次数对性能的影响；且迭代过程依赖原始图像作为参考，在完全无参考信息时可能失效。

（完）
