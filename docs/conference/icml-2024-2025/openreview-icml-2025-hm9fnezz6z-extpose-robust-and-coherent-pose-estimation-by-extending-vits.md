---
title: "ExtPose: Robust and Coherent Pose Estimation by Extending ViTs"
title_zh: "ExtPose: 通过扩展ViT实现鲁棒且一致的姿态估计"
authors: "Rongyu Chen, Li'an Zhuo, Linlin Yang, Qi WANG, Liefeng Bo, Bang Zhang, Angela Yao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hm9FNEZZ6z"
tags: ["query:hoi"]
score: 6.0
evidence: 3D姿态估计框架，将ViT扩展到视频，可用于手部姿态估计
tldr: 本文针对ViT在3D姿态估计中缺乏时序信息和像素对齐的问题，提出ExtPose框架，通过引入2D人体骨架图和多模态时序注意力，将图像ViT扩展到视频。该方法在视频3D姿态估计中表现鲁棒且一致，其核心设计可迁移至手物交互场景的手部姿态估计。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hm9fnezz6z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 775, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hm9fnezz6z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1672, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hm9fnezz6z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 800, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hm9fnezz6z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 782, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hm9fnezz6z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 800, \"height\": 594, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hm9fnezz6z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 802, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hm9fnezz6z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1759, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hm9fnezz6z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1749, \"height\": 789, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hm9fnezz6z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 817, \"height\": 809, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hm9fnezz6z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 837, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hm9fnezz6z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 873, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hm9fnezz6z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 873, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hm9fnezz6z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 823, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hm9fnezz6z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 825, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hm9fnezz6z/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 568, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hm9fnezz6z/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 817, \"height\": 791, \"label\": \"Table\"}]"
motivation: 现有ViT用于姿态估计时缺乏时序信息且预测与图像不对齐。
method: 结合2D骨架证据和全注意力时序建模，扩展ViT至视频。
result: 在视频姿态估计任务上实现鲁棒和一致的预测。
conclusion: ExtPose为视频3D姿态估计提供了新方案，具有通用性。
---

## Abstract
Vision Transformers (ViT) are remarkable at 3D pose estimation, yet they still encounter certain challenges. One issue is that the popular ViT architecture for pose estimation is limited to images and lacks temporal information. Another challenge is that the prediction often fails to maintain pixel alignment with the original images. To address these issues, we propose a systematic framework for 3D pose estimation, called ExtPose. ExtPose extends image ViT to the challenging scenario and video setting by taking in additional 2D pose evidence and capturing temporal information in a full attention-based manner. We use 2D human skeleton images to integrate structured 2D pose information. By sharing parameters and attending across modalities and frames, we enhance the consistency between 3D poses and 2D videos without introducing additional parameters. We achieve state-of-the-art (SOTA) performance on multiple human and hand pose estimation benchmarks with substantial improvements to 34.0mm (-23%) on 3DPW and 4.9mm (-18%) on FreiHAND in PA-MPJPE over the other ViT-based methods respectively.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）
- **问题**：视觉Transformer（ViT）在3D姿态估计中虽表现优异，但仍面临两大挑战：（1）现有ViT架构局限于单帧图像，缺乏时序信息，导致视频输入时预测抖动；（2）预测结果与原始图像像素对齐不佳，尤其在遮挡、运动模糊、光照变化等复杂场景下，出现全局翻转或定位错误。
- **动机**：2D姿态估计模型（如ViTPose）在像素对齐上表现更好，而时序信息有助于处理深度模糊和遮挡。因此，论文希望将图像ViT扩展至视频，同时引入结构化2D姿态先验，提升鲁棒性和一致性。
- **整体含义**：提出一个系统化框架**ExtPose**，通过扩展注意力机制，无需额外参数或模块，即可利用2D骨架图和时序上下文增强ViT基的3D姿态估计。

### 方法论：核心思想、关键技术细节
- **核心思想**：基于“扩展” paradigm，复用预训练ViT骨干，通过跨模态（图像与2D骨架图）和跨帧（时序）的全注意力融合，增强特征表示。
- **关键设计**：
  - **统一2D姿态表征**：采用**骨架图像**（skeleton image）——将2D关键点用彩色圆圈和骨骼连线渲染在空白背景上，与RGB图像同尺寸、同通道。通过共享ViT的Patch Embedding和位置编码，将2D姿态统一到视觉token空间。
  - **双流跨模态注意力**：RGB图像和骨架图像分别经同一ViT backbone处理，但注意力的Query、Key、Value计算同时考虑同模态和跨模态（公式5-9）。即每个token的更新会聚合来自另一模态的信息，实现深度融合。
  - **视频时序注意力**：将ViT的自注意力从单帧扩展到多帧（3D spatiotemporal attention），各帧的patch token在全部帧的所有token上进行注意力计算（公式10）。通过注意力掩码（公式11）隔离不同模态的跨帧交互，正交于跨模态注意力。
  - **损失函数**：包括3D关节损失L_joint、SMPL参数损失L_param、2D重投影损失L_reproj、对抗损失L_adv（公式12-15）。训练时以50%概率整体遮蔽一个模态，增强单模态特征提取能力。
- **无需额外参数**：所有模块均为原ViT自注意力，只是扩展计算范围，参数共享，不引入新层。

### 实验设计：数据集、Benchmark、对比方法
- **人体姿态估计**：
  - 训练集：3DPW、Human3.6M、MPI-INF-3DHP、COCO（混合3D和2D数据）。
  - 测试集：3DPW（图像和视频）、Human3.6M（视频）。
  - Benchmark指标：MPJPE、PA-MPJPE、MPVPE等。
  - 对比方法：HMR2.0、TokenHMR、WHAM、VIBE、TCMR等。
- **手部姿态估计**：
  - 训练集：FreiHAND、HO3D、MTC、RHD、InterHand2.6M、H2O3D、DexYCB及2D数据集（COCO WholeBody、Halpe等）。
  - 测试集：FreiHAND（图像）、HO3D（图像和视频）、HInt（2D PCK）。
  - Benchmark指标：PA-MPJPE、PA-MPVPE、F@5、F@15、AUC等。
  - 对比方法：HaMeR、METRO、Mesh Graphormer等。
- **消融实验**：包括2D姿态表征（1D坐标 vs. heatmap vs. 骨架图像）、融合策略（晚融合、通道拼接、ControlNet vs. 跨模态注意力）、训练策略（初始化、可训练层数）、序列长度（T=1,8,16,32）等。

### 资源与算力
- 文中明确说明：使用**8块A100 GPU**，batch size为32，训练50K iterations，采用AdamW优化器（lr=1e-5, β1=0.9, β2=0.999, weight decay=1e-3）。
- 未给出具体训练时长，但结合50K steps和batch size可推断训练时间较短（约数十小时）。推理时，扩展注意力虽增加计算量，但通过flash attention加速，在A100上仍可达实时（如T=16时延迟约12ms，见Fig.6）。

### 实验数量与充分性
- **实验充分性**：覆盖人体和手部两个任务，包括图像和视频两种设置，共8个主要数据集（含4个以上指标）。消融实验系统探究了2D姿态表示、融合方法、训练策略、序列长度等关键因素，对比了多种SOTA方法。
- **客观性与公平性**：所有对比基于相同的骨干初始化（HMR2.0或HaMeR），控制变量；使用标准评估协议；在多个公开基准上均取得一致提升。
- **局限性**：未在多人或全身姿态估计上验证；视频序列长度实验仅到T=32，未探索更长时间窗口；部分消融仅在FreiHAND上进行，跨数据集泛化性结论稍显单薄。

### 主要结论与发现
1. **ExtPose显著提升对齐与时序一致性**：在3DPW上PA-MPJPE从44.4mm降至35.5mm（图像），视频进一步降至34.0mm；FreiHAND上PA-MPJPE从6.0mm降至4.9mm。
2. **骨架图像作为2D姿态表征最佳**：优于1D坐标和heatmap，收敛更快，性能更高。
3. **跨模态注意力优于其他融合策略**：与通道拼接、晚融合、ControlNet相比，全注意力融合提升2D PCK（如HInt @0.05从48.0%增至59.6%）。
4. **视频扩展无需额外模块**：直接扩展ViT注意力到时间维度即可超越现有视频方法（如WHAM），并克服了以往视频方法精度低于图像方法的“反常现象”。
5. **预训练初始化与全参数训练关键**：仅调部分层或从ViTPose初始化效果较差。

### 优点
- **方法简洁通用**：核心仅修改注意力计算范围，无需新架构或额外参数，易于推广至其他ViT基方法（如TokenHMR、HaMeR）。
- **统一处理图像和视频**：同一框架同时支持两种输入，且视频性能不降反升。
- **高效训练**：利用预训练权重，快速收敛（约50K steps即达SOTA）。
- **全面实验**：覆盖人体和手部、图像和视频、多种表征和融合选项，结论可靠。

### 不足与局限
- **依赖2D检测质量**：实验显示使用GT 2D姿态性能显著优于检测器输出（如FreiHAND PA-MPJPE从4.9mm降至3.7mm），说明框架受限于2D先验的准确度。
- **未解决多人/全身场景**：当前聚焦单人人体或单手，未验证多实例或全身（face+body+hand）情况。
- **视频序列长度有限**：最佳长度T=16，未探索更长时间依赖（对比lifting方法常用243帧）。
- **失败案例**：在严重模糊、遮挡、缺失检测时仍可能出错（如Fig.8），依赖更强先验（如SAM2）可改进但未集成。
- **计算开销**：双流处理和跨帧注意力增加计算量，但文中通过flash attention和注意力掩码优化，对实时性影响可控（图6）。
- **消融实验数据集集中**：部分消融仅在FreiHAND上，结论的跨数据集泛化性需更多验证。

（完）
