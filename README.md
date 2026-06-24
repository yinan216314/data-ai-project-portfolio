# Data Analysis & AI Application Portfolio

## 个人定位

面向**数据分析、AI 应用、数据产品、智能汽车数据**方向。具备工程热物理背景与 AI/机器学习建模交叉能力，擅长将数值仿真、深度学习、优化算法应用于真实工程问题，并完成从数据处理、建模、调优到结果呈现的完整流程。

## Featured Projects

| 项目名称 | 技术栈 | 项目目标 | 核心方法 | 主要结果 | GitHub 链接 |
|---|---|---|---|---|---|
| PINN 一维非稳态热传导建模与数据分析 | Python, PyTorch, Physics-Informed Neural Networks, NumPy, Matplotlib | 用神经网络求解一维非稳态热传导 PDE，并与解析解对比验证精度 | 自动微分构造物理残差损失 + 边界/初始条件损失联合训练 | 数值解与解析解在多个时间切片下高度吻合，损失曲线稳定收敛 | [pinn-heat-conduction](https://github.com/yinan216314/pinn-heat-conduction) |
| YOLOv8 铝型材表面缺陷检测模型构建与训练优化 | Python, YOLOv8 / Ultralytics, OpenCV, Pandas, scikit-learn | 工业质检场景下的铝型材表面 9 类缺陷自动检测 | LabelMe→YOLO 格式转换 + 多组 epoch/学习率超参数对比训练 | 最佳配置（500 epoch, lr0=0.005）mAP50=0.714，Precision=0.772 | [yolov8-aluminum-defect-detection](https://github.com/yinan216314/yolov8-aluminum-defect-detection) |
| 基于遗传算法的最低温度分布优化项目 | MATLAB, Genetic Algorithm, 有限差分法 | 在材料用量受限条件下优化高导热材料空间分布以最小化区域温度 | 编码 + 锦标赛选择 + 交叉 + 变异 + 连通性约束修复，适应度内嵌有限差分 PDE 求解器 | 完整实现约束优化算法及正问题仿真验证，提供两套工具箱依赖/无依赖版本 | [genetic-algorithm-temperature-optimization](https://github.com/yinan216314/genetic-algorithm-temperature-optimization) |
| 底盘大数据 Agent（车辆底盘故障分析） | Python, Pandas, Streamlit, pyecharts, Rule-based Agent | 自动化车辆底盘故障数据清洗、关联、评分与分析，替代人工 Excel 处理流程 | 多源数据清洗关联 → 可配置规则评分引擎 → 规则驱动自然语言问答 Agent → 离线可视化看板 | 12 个可视化组件覆盖总览/故障/健康/明细四大板块，全流程一键运行 | [chassis-bigdata-agent](https://github.com/yinan216314/chassis-bigdata-agent) |

## 技术栈

- **编程与数据处理**：Python, MATLAB, SQL, Excel, NumPy, Pandas
- **可视化**：Matplotlib, pyecharts, Streamlit, Data Visualization
- **AI / 建模**：PyTorch, Physics-Informed Neural Networks (PINN), YOLOv8 / Ultralytics, Rule-based AI Agent
- **优化算法**：Genetic Algorithm, 约束优化建模
- **数值仿真**：有限差分法（Finite Difference Method）

## 简历项目描述

**PINN 一维非稳态热传导建模与数据分析**
- 基于 PyTorch 自动微分实现 Physics-Informed Neural Network，将一维非稳态热传导方程的控制方程、边界条件、初始条件转化为联合损失函数进行训练。
- 推导并实现级数解析解作为 ground truth，对 PINN 数值解在多个时间切片下进行定量误差对比验证。
- 产出训练损失收敛曲线、解析解/数值解对比图、二维等高线图与三维曲面图等完整可视化分析。

**YOLOv8 铝型材表面缺陷检测模型构建与训练优化**
- 设计 LabelMe 标注到 YOLO 格式的自动化数据转换流程，完成 9 类工业表面缺陷数据集的标准化处理。
- 基于 YOLOv8 微调训练检测模型，系统对比 100/300/500 epoch 与不同初始学习率（0.002/0.005/0.01）下的 Precision/Recall/mAP，确定最优训练配置。
- 封装批量推理脚本，将检测框与置信度结构化输出为 CSV，支撑工业质检场景的落地应用。

**基于遗传算法的最低温度分布优化项目**
- 将 Volume-to-Point 热传导拓扑优化问题建模为带约束的组合优化问题，设计遗传算法的编码、适应度、修复算子。
- 适应度函数中嵌入有限差分稳态热传导求解器，实现"优化算法 + 数值仿真"联合求解。
- 实现材料用量与连通性约束的自动修复机制，并提供有/无工具箱依赖的两套等价算法实现。

**底盘大数据 Agent（车辆底盘故障分析）**
- 设计端到端数据管道：多源数据接入 → 清洗（缺失/异常/重复处理并落盘清洗报告）→ 基于业务键关联成分析宽表。
- 构建可配置规则评分引擎（权重/阈值/健康分层通过 YAML 配置，不写死在代码中），输出风险分、健康分与健康状态。
- 实现规则驱动的中文自然语言问答 Agent（仅基于已计算结果回答、不编造数据）与零 CDN 依赖的离线可视化看板，并封装 Streamlit 工作台。

## 面试讲解地图

| 项目 | 适合展示的能力 |
|---|---|
| PINN 热传导建模 | 深度学习基础原理理解（自动微分、损失函数设计）、PDE 数值方法、AI for Science 建模能力、严谨的对比验证思维 |
| YOLOv8 缺陷检测 | 完整目标检测项目落地能力（数据处理→训练→调参→部署）、超参数实验设计、工业视觉应用场景理解 |
| 遗传算法温度优化 | 启发式优化算法设计、工程约束建模与算法编码转化、数值仿真与优化算法结合的复合能力 |
| 底盘大数据 Agent | 数据产品/数据分析全流程设计能力、规则引擎与 Agent 问答系统搭建、智能汽车数据场景的业务理解 |
