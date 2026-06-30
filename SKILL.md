---
name: emnlp-demo-writing
description: 写作或修改 EMNLP/ACL/NAACL System Demonstrations（demo track）投稿论文时使用。覆盖从论文骨架、各章节模板、引言写法、evaluation 设计、论文图表绘制（系统架构图/流程图/数据图表/界面截图，含 TikZ/Mermaid/Graphviz/matplotlib 模板）、到官方 8 个核心问题自检与投稿前 desk-reject 规避清单的全流程。当用户要写 demo 论文、起草某一章节、画论文里的图/架构图/Figure、检查 demo 论文是否合规、或问“demo 论文怎么写/结构是什么”时触发。
---

# EMNLP Demo 论文写作助手

帮助在 10 天冲刺周期内高效写出符合 EMNLP/ACL System Demonstrations track 规范、不被 desk reject 的 demo 论文。指导用中文，论文模板句式给英文（可直接用进投稿）。

本 skill 的结论来自对 EMNLP 2024 四篇代表作真实章节结构（MarkLLM、TransAgents、OpenFactCheck、Arxiv Copilot）与 EMNLP 2026 官方征稿要求的归纳。

## 触发后第一步：先判断用户在哪个阶段

- **“帮我写 demo 论文 / 从头开始”** → 走下面【全流程】，从骨架开始，逐节推进。
- **“写一下 introduction / system / evaluation 这节”** → 直接给该节模板（见 `templates/section-templates.md`），并套用用户的系统信息。
- **“检查我的论文 / 投稿前看看”** → 走【投稿前自检】，用 8 问清单 + desk-reject 清单逐条过。
- **“evaluation 不知道怎么做”** → 走【Evaluation 设计】，给适配 demo 的轻量评估方案。
- **“画图 / 帮我做 Figure 1 / 架构图 / 评估图表 / 界面截图”** → 走【图表制作】，见 `templates/figures-guide.md`，按图的类型选工具并直接生成。

不确定时，先问用户系统叫什么、解决什么问题、目标用户是谁，再动笔。

## 三条铁律（违反任何一条都可能 desk reject）

1. **必须报告某种 evaluation**——没有任何评估直接桌拒。哪怕是小规模可用性问卷也行。
2. **必须提供可运行入口**——论文里要给出在线 demo 网址或可下载安装包链接，缺失直接拒。
3. **页数**：正文 ≤ 6 页（录用 +1 页），参考文献/伦理声明不限，附录 ≤ 2 页。

配套：演示视频 ≤ 2.5 分钟；单盲（不匿名）；开源系统受青睐，需写明 license；至少一名作者到场 live demo。

## 全流程：标准 6 段骨架

demo 论文有一套高度固定的骨架，直接照搬（详见 `templates/paper-skeleton.md`）：

1. **Introduction**（~1 页，最重要）：问题 → 痛点（However）→ We present X → 2–4 条贡献。
2. **Related Work / Background**（0.5–1 页）：已有方案及其不足，反衬本系统必要性。
3. **System / Architecture**（1.5–2 页，核心）：架构、模块、数据流；配一张总览图 Figure 1。
4. **Usage / Walkthrough**（0.5–1 页，demo 特色）：用户实际怎么操作，配界面截图。
5. **Evaluation**（0.5–1 页，必需）：人工评测 / 用户研究 / 效率指标，至少一种。
6. **Conclusion (+ Limitations)**（~0.25 页）：收尾 + 诚实写局限 + license + 三个链接。

**篇幅重心在第 3、4 节**——demo 论文卖的是「系统本身 + 怎么用」，不是理论推导。

写作顺序建议（10 天冲刺最省力）：先写 System(3) 和 Usage(4)（你最熟），再写 Evaluation(5)，最后回头写 Introduction(1) 和 Related Work(2)，Conclusion(6) 收尾。Introduction 放最后写，因为它要提炼全文。

## 引言四步公式

4 篇代表作引言开头完全一致，套用这个公式（英文句式见 `templates/section-templates.md`）：

1. 背景铺垫：1–2 句讲领域大趋势。
2. 转折点题：`However / But` 引出痛点或空白。
3. 亮出系统：`We present / We introduce X` 一句话定义系统。
4. 列贡献点：bullet 或排比列 2–4 条（开源 / 统一框架 / 可视化 / 低成本 / 实时 等）。

## Evaluation 设计（demo 论文最易翻车处）

demo 的评估**不需要刷 benchmark**，但必须有。按系统类型挑一种最省力的（详见 `templates/evaluation-playbook.md`）：

- **可用性问卷**：SUS 量表 / NPS（净推荐值）——最适合交互类 demo，找 10–20 人填即可。
- **人工偏好评测**：让标注者比较系统输出 vs 基线/人工。
- **效率指标**：节省时间百分比、响应延迟、成本对比。
- **功能客观度量**：覆盖率、准确率、路径正确性人工核查。

## 图表制作

demo 论文通常需要 3 类图，本 skill 可指导并直接帮你生成（详见 `templates/figures-guide.md`）：

- **系统架构图（Figure 1，必备）**：TikZ（投稿终稿，矢量）/ Mermaid / Graphviz（快速起草）。
- **界面截图（Usage 节）**：跑 demo 浏览器截图，多张拼成跨栏 figure。
- **数据图表（Evaluation 节）**：matplotlib 生成，导出 PDF 矢量。

原则：架构图/数据图导出 PDF 矢量，截图用 ≥300dpi PNG；核心模块用一个强调色；caption 放图下方。
把系统模块信息交给 Claude，可直接生成或迭代上述任一图。

## 投稿前自检：官方 8 个核心问题

评委拿这 8 问逐条打分。提交前确认每条在文中都有明确着落（清单见 `templates/checklist.md`）：

1. 解决什么问题？　2. 为什么重要、影响何在？　3. 方法/技术新颖性？　4. 目标用户是谁？
5. 系统如何工作？　6. 与现有系统比较？　7. license 是什么？　8. 如何评估、有无用户研究？

## 风格要点（可直接套用）

- 系统命名 `Name: 一句话定位`，定位句点明类型与领域。
- 摘要固定结构：背景痛点 → We present X → X 做了什么 → 评估结论 → demo/视频/代码链接。
- 时态：背景用现在完成时，系统描述用一般现在时，实验用一般过去时。
- 正文给齐三个链接：GitHub、在线 demo、演示视频；并写明开源 license。
- 高频卖点词：open-source / unified / user-friendly / low-cost / real-time / interactive。

## 参考资料

- 章节骨架与篇幅分配：`templates/paper-skeleton.md`
- 各章节英文模板句式：`templates/section-templates.md`
- Evaluation 方案手册：`templates/evaluation-playbook.md`
- 图表制作手册（架构图/截图/数据图）：`templates/figures-guide.md`
- 投稿前自检清单：`templates/checklist.md`

证据来源（ACL Anthology / 官方征稿）：
- EMNLP 2026 Call for Demos: https://2026.emnlp.org/calls/demos/
- MarkLLM (EMNLP 2024 demo.7): https://aclanthology.org/2024.emnlp-demo.7/
- TransAgents (demo.14): https://aclanthology.org/2024.emnlp-demo.14/
- OpenFactCheck (demo.23): https://aclanthology.org/2024.emnlp-demo.23/
- Arxiv Copilot (demo.13): https://aclanthology.org/2024.emnlp-demo.13/
