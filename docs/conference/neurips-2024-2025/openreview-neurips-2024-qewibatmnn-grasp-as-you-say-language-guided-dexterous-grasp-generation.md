---
title: "Grasp as You Say: Language-guided Dexterous Grasp Generation"
title_zh: 按你说的抓取：语言引导的灵巧抓取生成
authors: "Yi-Lin Wei, Jian-Jian Jiang, Chengyi Xing, Xiantuo Tan, Xiao-Ming Wu, Hao Li, Mark Cutkosky, Wei-Shi Zheng"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=QeWibaTmnn"
tags: ["query:hoi"]
score: 7.0
evidence: 语言引导的灵巧抓取生成，包含手物交互重定向
tldr: 针对自然语言引导的灵巧抓取任务缺乏高质量数据集的问题，构建了DexGYSNet数据集，通过精心设计的手物交互重定向策略和LLM辅助标注系统生成丰富抓取样本，并提出DexGYSGrasp框架实现基于语言指令的抓取姿态生成，实验表明该方法在抓取质量和语言跟随性上表现优异，为手物交互中的抓取估计提供了新范式。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1420, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1379, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1432, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1434, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1428, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1425, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1297, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1302, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1062, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1134, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qewibatmnn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1437, \"height\": 1329, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-qewibatmnn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1424, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-qewibatmnn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 639, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-qewibatmnn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1351, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-qewibatmnn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 799, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-qewibatmnn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 182, \"label\": \"Table\"}]"
motivation: 缺乏自然语言引导的灵巧抓取数据集，限制了人机交互应用。
method: 设计手物交互重定向策略和LLM辅助语言引导标注系统，构建数据集并提出抓取生成框架。
result: 在抓取质量和语言指令跟随上取得优异表现。
conclusion: DexGYS方法实现了灵活的语言引导抓取，推动了灵巧操纵领域发展。
---

## Abstract
This paper explores a novel task "Dexterous Grasp as You Say'' (DexGYS), enabling robots to perform dexterous grasping based on human commands expressed in natural language. However, the development of this field is hindered by the lack of datasets with natural human guidance; thus, we propose a language-guided dexterous grasp dataset, named DexGYSNet, offering high-quality dexterous grasp annotations along with flexible and fine-grained human language guidance. Our dataset construction is cost-efficient, with the carefully-design hand-object interaction retargeting strategy, and the LLM-assisted language guidance annotation system. Equipped with this dataset, we introduce the DexGYSGrasp framework for generating dexterous grasps based on human language instructions, with the capability of producing grasps that are intent-aligned, high quality and diversity. To achieve this capability, our framework decomposes the complex learning process into two manageable progressive objectives and introduce two components to realize them. The first component learns the grasp distribution focusing on intention alignment and generation diversity. And the second component refines the grasp quality while maintaining intention consistency. Extensive experiments are conducted on DexGYSNet and real world environments for validation.

---

## 论文详细总结（自动生成）

### 论文总结：Grasp as You Say: Language-guided Dexterous Grasp Generation

#### 1. 论文的核心问题与整体含义（研究动机和背景）
- **任务定义**：提出“Dexterous Grasp as You Say”（DexGYS）任务，即机器人根据人类自然语言指令生成灵巧抓取姿态。该任务旨在突破传统仅关注抓取稳定性或有限预定义功能的灵巧抓取方法，实现更自然、灵活的人机交互。
- **关键挑战**：
  - **数据瓶颈**：缺乏带有自然语言指导的大规模灵巧抓取数据集，标注成本极高。
  - **学习矛盾**：现有损失函数（如穿透损失）在保证抓取质量的同时会严重损害意图对齐和多样性，单一模型难以同时满足高质量、高意图一致性和高多样性。
- **研究意义**：首次将自然语言与灵巧手抓取结合，推动机器人从“稳定抓取”向“意图性、类人抓取”迈进。

#### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将复杂任务分解为两个渐进式子目标——先学习意图对齐且多样的抓取分布（不关注质量），再在保持意图的前提下细化抓取质量。通过避免穿透损失对生成过程的干扰，缓解多目标冲突。
- **数据集构建（DexGYSNet）**：
  - **手物交互重定向（HOIR）**：将低成本获取的人类手-物交互数据（来自OakInk数据集）重定向到灵巧手（如Shadow Hand）。三步优化：①姿态初始化（复制相似结构参数）；②指尖对齐（最小化指尖位置差异）；③交互细化（使用穿透损失、自穿透损失、关节限位损失、接触图一致性损失，固定平移）。
  - **LLM辅助语言指导标注**：结合物体类别、人类意图（“使用”/“握持”）及逐指接触信息，利用GPT-3.5生成自然语言指导（如“To use a trigger sprayer, press the trigger with your forefinger……”）。
- **抓取生成框架（DexGYSGrasp）**：
  - **意图与多样性组件（IDGC）**：基于条件扩散模型，以物体点云（PointNet++编码）和语言（CLIP编码）为条件，仅用回归损失（参数L2损失+手部Chamfer距离）训练，不加入穿透损失，以学习分布、保证意图和多样性。
  - **质量抓取组件（QGC）**：以IDGC生成的粗糙抓取、手部点云和物体点云为输入，输出增量姿态，使用完整损失（回归+穿透+接触图+自穿透）进行细化，旨在提升质量同时保持意图。
  - **渐进损失策略**：IDGC无穿透损失，QGC有穿透损失，避免训练干扰。

#### 3. 实验设计
- **数据集**：DexGYSNet（约50000个抓取-语言对，1800个常见家庭物体）。训练/测试按物体实例划分（80%训练，20%测试），确保测试物体在训练中未见。
- **评估指标**：
  - 意图一致性：FID、P-FID（基于点云特征和渲染图像特征）、Chamfer距离（CD）、接触距离（Con.）。
  - 抓取质量：成功率和Q1（模拟环境）、最大穿深（Pen.）。
  - 多样性：平移标准差δt、旋转标准差δr、关节角标准差δq（8次采样）。
- **对比方法**：GraspCVAE、GraspTTA、SceneDiffuser、DGTR（均用相同编码器和损失复现）。
- **实验类型**：
  - **主对比**：表1显示Ours在意图一致性和多样性上远超所有SOTA，质量持平。
  - **消融实验**：
    - 组件消融（表2）：验证IDGC不使用穿透损失、QGC细化、渐进策略的必要性。
    - HOIR步骤消融（表3）：三步重定向逐步提升质量和意图一致性。
    - 插件实验（表4）：将QGC应用于其他SOTA方法（去除穿透损失后意图改善，加QGC质量提升）。
  - **真实世界实验**（表5、图7）：使用Allegro手+Flexiv Rizon4臂+D415相机，经SAM+Grounding DINO+点云补全获取完整点云，测试多种物体（成功率从3/10到9/10不等）。
- **实验充分性与公平性**：
  - 实验覆盖了合成数据和真实场景，消融全面，对比方法复现一致，指标多样（意图+质量+多样性）。
  - 数据集按物体实例划分避免物体泄露；真实世界实验尽管成功率有限但证明了可行性。
  - 但未报告置信区间或多次重复的标准差，算力有限。

#### 4. 资源与算力
- **硬件**：单张NVIDIA RTX 4090 GPU。
- **训练设置**：IDGC训练100个epoch，QGC训练20个epoch；batch size=64；Adam优化器，学习率2×10⁻⁴（余弦退火至2×10⁻⁵）。
- **未提及**：未报告总训练时长、GPU内存消耗及数据构建的算力开销（仅说明HOIR优化迭代次数）。

#### 5. 实验数量与充分性
- **丰富度**：共包含5张主要表格（表1-5）和大量可视化（图2-7），涵盖主对比、组件消融、HOIR消融、插件实验、真实世界实验。
- **充分性**：实验设计合理，对比了4种SOTA方法，消融了关键组件和损失，并通过真实场景验证。但缺少对噪声、部分遮挡、跨域泛化（如不同灵巧手型号）的测试，真实实验样本量较少（每物体10次，共70次）。
- **公平性**：对比方法均使用相同编码器和损失复现，数据集划分严格，评价指标客观。

#### 6. 论文的主要结论与发现
- **主要结论**：提出的DexGYSGrasp框架能够同时实现意图对齐、高质量和高多样性的灵巧抓取生成，在DexGYSNet数据集上显著优于所有SOTA方法。
- **关键发现**：
  - 穿透损失是导致意图偏离和多样性降低的主因，将其从生成组件中移除可优雅地解决矛盾。
  - 渐进式两阶段设计（生成+细化）比单阶段联合优化更有效。
  - 手物交互重定向（HOIR）策略能以低成本生成高质量高一致性的灵巧抓取数据。
  - 将QGC作为插件可用于提升其他方法的抓取质量。

#### 7. 优点
- **数据集创新**：首次提供带有自然语言指导的大规模灵巧抓取数据集，构建流程成本高效（利用人类数据+LLM）。
- **方法论创新**：渐进式框架巧妙化解穿透损失带来的多目标冲突，且组件解耦使得训练更简单。
- **实验全面**：同时评估意图、质量、多样性三个维度，并包含真实机器人验证。
- **可扩展性**：HOIR可推广至不同灵巧手（Shadow/Allegro/Leap），方法可跨模型使用。

#### 8. 不足与局限
- **真实世界性能有限**：真实实验中部分物体成功率较低（如锤子4/10，扳手5/10），可能受机械臂控制精度、手爪物理限制及感知误差影响。
- **输入依赖**：框架要求完整物体点云，真实场景需级联多个现成模型（检测、分割、补全），误差累积。
- **未考虑动态环境**：仅处理静态抓取，未考虑抓取过程中的物体移动或障碍物。
- **实验局限**：测试仅在DexGYSNet内部物体上进行，缺乏跨数据集或零样本泛化测试；未分析语言指令的多样性（如同义词、歧义性）对模型鲁棒性的影响。
- **未公开代码和数据**（论文承诺发布后公开），复现依赖匿名补充材料。
- **计算资源描述不完整**：未报告训练实际时长，也未对能耗进行估计。

（完）
