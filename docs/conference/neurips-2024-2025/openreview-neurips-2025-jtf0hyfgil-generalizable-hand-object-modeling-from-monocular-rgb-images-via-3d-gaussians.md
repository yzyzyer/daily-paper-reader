---
title: Generalizable Hand-Object Modeling from Monocular RGB Images via 3D Gaussians
title_zh: 基于3D高斯的单目RGB图像通用手物建模
authors: "Xingyu Liu, Pengfei Ren, Qi Qi, Haifeng Sun, Zirui Zhuang, Jing Wang, Jianxin Liao, Jingyu Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=JTF0HYfGiL"
tags: ["query:hoi"]
score: 8.0
evidence: 从单目图像进行通用手物建模，隐含姿态估计
tldr: 现有手物交互建模方法依赖密集标注或受限短视频，泛化能力差。本文提出HOGS，基于3D高斯泼溅框架，从单目RGB图像实现通用手物建模。通过融合视觉光度线索与物理结构，方法在多样化场景下鲁棒重建手和物体。实验证明HOGS在新环境和新动作上均优于现有方法，为手物交互姿态估计提供了高效的可泛化方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 823, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 611, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 690, \"height\": 1063, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 687, \"height\": 1057, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jtf0hyfgil/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1429, \"height\": 1294, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1331, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 647, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 749, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 590, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 377, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1458, \"height\": 360, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 875, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jtf0hyfgil/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 898, \"height\": 362, \"label\": \"Table\"}]"
motivation: 现有手物建模方法依赖密集标注或受限场景，无法泛化到多样化环境。
method: 提出自适应3D高斯泼溅框架，结合视觉光度线索与物理结构进行建模。
result: 在多个数据集上优于现有方法，泛化到未见场景和动作。
conclusion: 提供了一种可泛化的手物交互建模方法，可用于姿态估计等下游任务。
---

## Abstract
Recent advances in hand-object interaction modeling have employed implicit representations, such as Signed Distance Functions (SDF) and Neural Radiance Fields (NeRF) to reconstruct hands and objects with arbitrary topology and photo-realistic detail. However, these methods often rely on dense 3D surface annotations, or are tailored to short clips constrained in motion trajectories and scene contexts, limiting their generalization to diverse environments and movement patterns. In this work, we present HOGS, an adaptively perceptive 3D Gaussian Splatting (3DGS) framework for generalizable hand-object modeling from unconstrained monocular RGB images. By integrating photometric cues from the visual modality with the physically grounded structure of 3D Gaussians, HOGS disentangles inherent geometry from transient lighting and motion-induced appearance changes. This endows hand-object assets with the ability to generalize to unseen environments and dynamic motion patterns. Experiments on two challenging datasets demonstrate that HOGS outperforms state-of-the-art methods in monocular hand-object reconstruction and photo-realistic rendering.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有手-物交互建模方法大多依赖密集的3D表面标注或预扫描物体模板，成本高昂且难以扩展；另一些基于隐式表示（如SDF、NeRF）的方法虽能实现精细重建，但仅适用于短片段视频，在运动轨迹和场景上下文上存在严重偏置，无法泛化到新环境或新运动模式。
- **整体含义**：本文提出HOGS（Hand-Object Gaussian Splatting）框架，旨在从无约束的单目RGB图像中实现**可跨场景、跨运动泛化**的手-物照片级建模。通过将视觉光度线索与3D高斯的物理结构化表征相结合，解耦固有几何与瞬时光照/运动引起的表观变化，使学得的手-物资产能够直接迁移到未见过的环境和动态模式中，无需任何微调。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：采用可变形3D高斯泼溅（3DGS）表征手和物体，通过视觉驱动通用感知模块（V-PM）将高斯参数分解为几何不变模板和视觉依赖组件，通过几何驱动姿态精炼模块（G-PM）利用3D高斯的几何物理特性来精炼手-物姿态和接触，最后通过可微渲染联合优化所有组件。

- **关键技术细节**：
  - **手-物交互建模**：在规范空间初始化手和物体的3D高斯集合，利用正向线性混合蒙皮（LBS）驱动手部高斯变形，使用6DoF刚体变换驱动物体高斯变形。
  - **视觉驱动通用感知模块（V-PM）**：
    - 使用Vision Transformer提取手-物区域的全局视觉特征F，并通过可微渲染投影获得像素对齐的局部特征F(π(pt))。
    - 将视觉特征与高斯参数（含多分辨率哈希编码）通过MLP编码得到视觉依赖表观分量Z_v。
    - 通过Sigmoid加权融合球谐颜色和Z_v得到最终颜色c；对位置、尺度、旋转也进行视觉依赖的偏移调整（式(8)-(11)）。
  - **几何驱动姿态精炼模块（G-PM）**：
    - 将3D高斯视为点云，使用经ULIP预训练的PointNet++提取几何特征，再通过Transformer和MLP预测物体平移偏移ΔT_o和旋转偏移ΔR_o。
    - 同时利用手、物高斯中心点作为点云，施加接触和穿透损失来优化交互。
  - **损失函数**：包含RGB损失（分手、物、联合）、掩码损失、感知损失（LPIPS）、姿态损失（旋转、平移、角点）、蒙皮正则化、等距约束、接触/穿透损失等。

## 3. 实验设计

- **数据集**：
  - **DexYCB**：582K RGB-D帧，1000个序列，10个受试者，20个物体。按[35]的划分，训练147,526样本；测试按[2,52,27]下采样至6fps，得5,928样本。
  - **HO3D_v3**：10个受试者，10个YCB物体。按[7]的协议选18个序列训练，评估手持物体重建。
- **评估指标**：
  - 几何：Chamfer距离（CD）、F-score（不同阈值）、物体中心误差（OCE）、平均角点误差（MCE）、ADD-S。
  - 渲染：PSNR、SSIM、LPIPS（仅在手-物掩码区域内计算）。
- **对比方法**：
  - 3D密集监督方法：Hasson et al.、Grasping Field、AlignSDF、gSDF、HORT等。
  - 2D光度监督方法：MOHO、HOLD，以及扩展的GOF†、3DGS-Avatar†。
  - 姿态估计对比：Wang et al.、Lin et al.、HOISDF等。

## 4. 资源与算力

- **GPU型号**：单张NVIDIA RTX 4090 GPU。
- **训练时长**：
  - DexYCB：360k迭代，约10小时。
  - HO3D：200k迭代。
- **优化器**：AdamW。
- **注释**：文中未提及使用的GPU数量，推测为单卡；也未提及内存或存储需求。

## 5. 实验数量与充分性

- **主要实验**：在DexYCB上做了手和物体的表面重建对比（表2）、手持物体重建对比（表3）、照片级渲染对比（表4）、物体姿态估计对比（表5）。在HO3D上做了手持物体重建对比（表3的表内右半部分）。
- **消融实验**：
  - 视觉环境变化影响（表6）：模拟颜色抖动，对比HOGS全模型、无V-PM、3DGS-Avatar的渲染质量下降。
  - 各模块有效性（表7）：分别去除接触优化、预训练3D主干、G-PM、自适应表观、整个V-PM。
  - 视觉驱动组件特征（表8）：对比全局特征F、像素对齐特征F(π(pt))、高斯参数G的不同组合。
- **定性结果**：图3-6展示了渲染和重建的可视化对比。
- **充分性与公平性**：
  - 实验覆盖了重建、渲染、姿态估计多个维度，对比了13种以上方法，消融覆盖了主要设计选择。
  - 使用标准数据集划分和评估协议，与基线方法在同一设定下比较（如遵循[2,52,27]的下采样策略）。
  - 未报告误差棒或多次随机种子，但常见于该领域论文，总体公平性可接受。

## 6. 主要结论与发现

- HOGS在DexYCB和HO3D上均显著优于SOTA方法：
  - 物体重建Chamfer距离从1.55（gSDF）降至0.24，F-score@10从0.709提升至0.918。
  - 渲染PSNR达到31.12，超过3DGS-Avatar†的29.71和GOF†的29.58。
- 在无每序列微调的情况下，HOGS能够直接泛化到新的视觉环境（如颜色抖动）和新的运动模式。
- V-PM有效捕捉跨场景表观变化，G-PM显著提升物体姿态精度，接触优化进一步改善交互质量。

## 7. 优点

- **创新性**：首次将3DGS与神经网络感知结合用于手-物交互的通用建模，实现了无需密集3D标注的跨场景泛化。
- **技术设计巧妙**：V-PM将高斯参数解耦为几何不变模板和视觉依赖组件，有效分离了固有几何与瞬变表观；G-PM利用3D高斯的物理属性（位置、尺度、旋转）进行姿态精炼，无需额外3D标注。
- **实验结果全面**：涵盖重建、渲染、姿态估计三个任务，消融实验验证了每个设计的必要性。
- **泛化能力强**：在颜色抖动模拟中，HOGS的渲染质量下降远小于基线，证明其对视觉变化的鲁棒性。

## 8. 不足与局限

- **物体类别泛化受限**：性能受训练时物体类别多样性的约束，无法零样本泛化到全新物体类别（论文明确说明）。
- **未报告误差棒**：缺乏多次实验的统计意义分析，可能受随机初始化影响。
- **依赖初始姿态估计**：使用现成回归器初始化手/物姿态，若初始姿态误差过大，G-PM可能难以修正。
- **计算资源**：单卡4090训练10小时，对于大规模训练或部署仍有一定开销。
- **应用限制**：当前针对手-物资产在未见视觉上下文和运动模式下的泛化，而非新物体类别的合成；需要更大规模数据训练才能实现零样本泛化。

（完）
