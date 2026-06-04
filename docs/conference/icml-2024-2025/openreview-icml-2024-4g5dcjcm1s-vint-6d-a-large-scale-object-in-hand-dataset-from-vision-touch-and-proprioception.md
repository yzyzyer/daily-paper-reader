---
title: "VinT-6D: A Large-Scale Object-in-hand Dataset from Vision, Touch and Proprioception"
title_zh: VinT-6D：融合视觉、触觉与本体感觉的大规模手中物体数据集
authors: "Zhaoliang Wan, Yonggen Ling, Senlin Yi, Lu Qi, Wang Wei Lee, Minglei Lu, Sicheng Yang, Xiao Teng, Peng Lu, Xu Yang, Ming-Hsuan Yang, Hui Cheng"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=4G5Dcjcm1s"
tags: ["query:hoi"]
score: 10.0
evidence: 大规模物体在手姿态估计数据集，融合视觉、触觉和本体感觉，用于机器人手中操作
tldr: 针对手中物体姿态估计缺乏大规模数据的问题，本文构建了VinT-6D数据集，包含200万仿真和10万真实样本，同步采集视觉、触觉和本体感觉信息。该数据集专门针对机器人手设计，支持高精度6D姿态估计，为手物交互研究提供了关键资源。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 859, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1764, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1767, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1764, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1775, \"height\": 752, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1770, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1771, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1524, \"height\": 567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1765, \"height\": 870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1772, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1774, \"height\": 995, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1771, \"height\": 1111, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1731, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1771, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1774, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-4g5dcjcm1s/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1764, \"height\": 956, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-4g5dcjcm1s/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-4g5dcjcm1s/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 812, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-4g5dcjcm1s/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 791, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-4g5dcjcm1s/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 756, \"height\": 350, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-4g5dcjcm1s/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 810, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-4g5dcjcm1s/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 808, \"height\": 171, \"label\": \"Table\"}]"
motivation: 现有手中物体姿态估计数据集规模小且模态单一，难以支撑高精度感知。
method: 通过MuJoCo和Blender仿真及真实平台采集多模态数据，确保视觉-触觉-本体感觉对齐。
result: 数据集在多个基准上验证，显著提升了手中物体姿态估计的精度。
conclusion: 该数据集填补了多模态手中物体数据的空白，推动了手物交互感知研究。
---

## Abstract
This paper addresses the scarcity of large-scale datasets for accurate object-in-hand pose estimation, which is crucial for robotic in-hand manipulation within the "Perception-Planning-Control" paradigm. Specifically, we introduce VinT-6D, the first extensive multi-modal dataset integrating vision, touch, and proprioception, to enhance robotic manipulation. VinT-6D comprises 2 million VinT-Sim and 0.1 million VinT-Real entries, collected via simulations in Mujoco and Blender and a custom-designed real-world platform. This dataset is tailored for robotic hands, offering models with whole-hand tactile perception and high-quality, well-aligned data. To the best of our knowledge, the VinT-Real is the largest considering the collection difficulties in the real-world environment so it can bridge the gap of simulation to real compared to the previous works. Built upon VinT-6D, we present a benchmark method that shows significant improvements in performance by fusing multi-modal information. The project is available at https://VinT-6D.github.io/.

---

## 论文详细总结（自动生成）

# VinT-6D 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：手中物体（object-in-hand）的 6D 姿态估计是机器人灵巧操作的关键感知模块，但现有数据集存在以下不足：
  - 规模小、模态单一（大多只有视觉或触觉）；
  - 真实数据采集困难、质量低，导致 sim2real 鸿沟严重；
  - 大多针对二指夹爪设计，难以推广到多指手（三指、四指）的复杂遮挡场景。
- **整体目标**：构建首个大规模、多模态（视觉 + 触觉 + 本体感觉）的“手中物体”数据集 VinT-6D，并提供对应基准方法，以推动机器人精细操作中的感知研究。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 通过高保真仿真（MuJoCo + Blender）和精确校准的真实平台，采集覆盖全手触觉的、多视角、多模态对齐的数据，并设计一个触觉‑视觉融合网络作为基准。

### 关键技术细节
- **仿真部分（VinT-Sim）**：
  - **触觉模拟**：将每个触觉单元（taxel）在 MuJoCo 中建模为力传感器（圆顶柱体），模拟接触位置而非具体力值；通过 3D 扫描真实手部触觉传感器的分布，在仿真中精确复现 620（Trx 手）或 679（Allegro 手）个 taxel 的位置。
  - **抓取交互模拟**：在 MuJoCo 中执行“预抓取→接触→抬升”的物理稳定抓取流程，记录物体位姿、手部位姿和各指节位姿。
  - **视觉渲染**：将 MuJoCo 的抓取场景导入 Blender，使用 Cycles 引擎、多种 HDRI 背景、多视角（半球范围）进行逼真 RGB 渲染；深度图通过后处理模拟 Kinect Azure 的噪声、孔洞和光滑效果，最终生成对齐的 RGB‑D 图像和触觉点云。
- **真实部分（VinT-Real）**：
  - **硬件平台**：集成双目工业相机、Kinect Azure TOF 深度相机、自研压阻式全手触觉传感器、Trx 手（三指）和 ABB 机械臂，以及 Vicon 运动捕捉系统（亚毫米级物体/手部姿态真值）。
  - **数据对齐**：
    - *视觉内对齐*：标定双目相机与深度相机，重投影得到对齐的 RGB‑D 图像。
    - *视觉‑触觉对齐*：利用正向运动学计算手指接触点在全局坐标系下的位置，并结合运动捕捉系统提高精度。
    - *视觉分割*：利用触觉点作为 SAM 模型的“add/remove”提示，指导在遮挡严重时的物体分割。
  - **多样性和规模**：在机器人工作空间内密集采样 125 个关键位置，每个位置施加 8 种手部旋转，对每个物体采集约 1000 个不同姿态，总计 10 个物体共 10 万组数据。
- **基准方法（VinT-Net）**：
  - **感知聚合模块**：RGB 经 U‑Net 提取外观特征；深度和触觉点云分别经 PointNet++ 提取几何特征；深度图和触觉特征在像素级融合得到视觉‑触觉特征。
  - **3D 关键点姿态估计模块**：利用融合特征预测物体中心偏移、预定义 3D 关键点偏移和语义分割（该任务不融合触觉，避免干扰）；采用多任务损失（Focal Loss + L1 Loss），最终用最小二乘法拟合 6D 位姿（R, t）。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：VinT-6D 中的 7 个物体（blue bottle, large shaker, stick, potted meat can, tomato soup can, power drill, tuna fish can）进行评估。
- **评估指标**：ADD(S) AUC（曲线下面积），对称物体用 ADD-S，非对称用 ADD。
- **基准设置**：
  - **表3**：跨域泛化实验——分别在 Sim 只训练、Real 只训练、Sim+Real 联合训练，在 Real 测试集上评测。
  - **表4**：消融实验——对比“仅视觉”（基线为 PVN3D） vs “视觉+触觉”（VinT‑Net 完整版）。
  - **表5**：与方法对比——将 PVN3D 和 Object‑Hand‑Pose（复现为三指版本）在 tomato soup can 上比较 ADD‑0.05d 指标。
  - **表6**：遮挡鲁棒性实验——对 tomato soup can 人为设置 20%‑50% 遮挡率，比较仅视觉和视觉+触觉的准确率。
- **未与其他公开数据集（如 VITA）进行跨数据集定量对比**，但通过表 1 定性说明了规模与模态优势。

## 4. 资源与算力

- **训练资源**：6 块 Quadro RTX 8000 GPU，batch size 24，训练 25 个 epoch。
- **仿真资源**：16 块 NVIDIA P40 GPU 用于批量合成 VinT-Sim。
- **论文未提供训练单个模型的总时长或具体天数**，但上述配置表明资源充足。

## 5. 实验数量与充分性

- **实验组数**：
  - 表3：7 个物体 × 3 种训练数据组合 = 21 组。
  - 表4：7 个物体 × 2 种输入模式 = 14 组。
  - 表5：1 个物体 × 3 种方法。
  - 表6：1 个物体 × 4 种遮挡率 × 2 种输入 = 8 组。
  - 总计约 44 组主要定量实验，加上附录中的定性可视化。
- **充分性评价**：
  - 优点是覆盖了跨域、消融、对比、鲁棒性等关键维度，实验设计较为系统。
  - **不足之处**：对比方法仅两个（PVN3D 和 Object‑Hand‑Pose），未与同样支持触觉的 VITA 等工作进行端到端比较（因硬件差异，复现困难）；消融实验中未单独分析本体感觉（proprioception）的影响（触觉与本体感觉作为整体输入）；遮挡实验仅在一个物体上进行，泛化性不足。

## 6. 论文的主要结论与发现

1. **数据集价值**：VinT-6D 结合仿真和真实数据，能有效缩小 sim2real 差距（表3 中 Sim+Real 联合训练性能超过单独使用任一源）。
2. **触觉增益**：融合触觉和本体感觉可以显著提升姿态估计精度（表4 中视觉+触觉比纯视觉平均提升 ~5‑8% AUC）。
3. **遮挡鲁棒性**：当视觉遮挡从 20% 加剧到 50% 时，纯视觉精度从 93.3% 降至 80.4%，而多模态方法仅从 94.8% 降至 88.8%，表现出强鲁棒性。
4. **多指手适用性**：数据集包含三指和四指手，覆盖了全手触觉（指尖、指腹、手掌），为复杂多指遮挡场景提供了稀缺资源。

## 7. 优点：方法或实验设计上的亮点

- **大规模与多模态**：200 万仿真 + 10 万真实样本，同时提供 RGB、深度、触觉点云、本体感觉、分割标签和亚毫米级真值，是目前同类数据集中最全面的。
- **高保真仿真**：在 MuJoCo 中进行物理接触模拟，在 Blender 中进行照片级渲染（包括透明/反射物体的光线追踪），并模拟真实深度相机的噪声特性，显著缩小 sim2real 差距。
- **真实平台精心设计**：使用运动捕捉系统而非 ArUco 标签获取亚毫米精度真值；通过定制夹具将标记物固定于物体，避免遮挡；采用 SAM + 触觉提示实现高效分割。
- **全手触觉覆盖**：区别于仅指尖触觉的现有数据集，本工作将触觉传感器布满手指和手掌，提供更丰富的局部接触信息。
- **基准方法有效且简洁**：VinT-Net 采用经典的 U‑Net + PointNet++ 融合架构，在多个评测中证实触觉信息的作用，可作为后续研究的易复现基线。

## 8. 不足与局限

- **物体和场景多样性有限**：仿真仅使用 25 个物体，真实仅 10 个物体，且场景背景单一（HDRI 天空球），可能无法充分覆盖真实世界中的各类物品和环境。
- **仅实例级姿态估计**：当前数据集和基线均为特定物体训练，未支持类别级或零样本泛化，限制了在新物体上的直接应用。
- **融合策略简单**：VinT-Net 只是简单的特征拼接和逐点融合，未探索更先进的跨模态注意力机制或图神经网络，留有性能提升空间。
- **未独立分析本体感觉**：触觉和本体感觉捆绑作为输入，未单独评估本体感觉对姿态估计的贡献。
- **对比实验不充分**：未与其他多模态方法（如 Dikhale et al. 的 VITA 框架）进行定量对比，仅用两个纯视觉基线作参照。
- **遮挡实验代表性不足**：仅在番茄汤罐头上测试，未在更多物体或更广遮挡范围验证。
- **数据集公开性**：虽然网站已公布，但论文未提供完整的数据集下载链接和详细的物体 CAD 文件（除部分 fixture 模型外），这可能会影响可复现性。

（完）
