# Demo 论文标准骨架与篇幅分配

基于 EMNLP 2024 四篇代表作真实章节结构归纳。总正文 ≤ 6 页。

## 章节骨架（含建议篇幅）

| # | 章节 | 篇幅 | 作用 |
|---|------|------|------|
| 1 | Introduction | ~1 页 | 问题→痛点→系统→贡献。决定评委第一印象，最重要 |
| 2 | Related Work / Background | 0.5–1 页 | 已有方案不足，反衬本系统必要性 |
| 3 | System / Architecture | 1.5–2 页 | **核心**：架构、模块、数据流 + Figure 1 总览图 |
| 4 | Usage / Walkthrough | 0.5–1 页 | demo 特色：用户怎么操作 + 截图 |
| 5 | Evaluation / Experiments | 0.5–1 页 | **必需**：评估证据，否则 desk reject |
| 6 | Conclusion (+ Limitations) | ~0.25 页 | 收尾 + 局限 + license + 链接 |

## 4 篇真实章节对照（命名差异参考）

```
MarkLLM            TransAgents        OpenFactCheck          Arxiv Copilot
1 Introduction     1 Introduction     1 Introduction         1 Introduction
2 Background       2 Related Work     2 Related Work         2 Arxiv Copilot
  2.1 算法           3 System            3 System Architecture    2.1 Personalized
  2.2 评估视角        3.1 Frontend         3.1 ...                  2.2 Real-time
3 系统框架          3.2 Backend         3.2 LLMEval              2.3 Self-evolution
  3.1 统一框架        3.3 Walkthrough    4 Access & Deployment    2.4 Deployment
  3.2 可视化         4 Experiments        4.1 Python Library     3 User Guidance
  3.3 自动评估        4.1 Setup            4.2 Web Interface      4 Evaluation
4 User Examples    4.2 Automatic Eval  5 Conclusion&Future    5 Related Work
5 Experiment       4.3 Human Eval                             6 Conclusion&Future
6 Conclusion       4.4 Cost Analysis
                   5 Case Study
                   6 Conclusion
                   7 Limitations
```

观察：
- 命名可灵活（System 可叫系统名本身，如 “2 Arxiv Copilot”）。
- Related Work 可放前（多数）也可放后（Arxiv Copilot 放第 5 节）。
- System 节常拆成「前端/后端」或「若干特性子节」。
- 篇幅重心稳定落在 System(3) + Usage(4)。

## 10 天冲刺写作顺序

1. **先搭 System(3) + Usage(4)**：你对自己系统最熟，先把核心写满。
2. **再写 Evaluation(5)**：边写边补做评估（问卷可并行收集）。
3. **写 Related Work(2)**：查 5–10 篇相关 demo/工具对比。
4. **最后写 Introduction(1)**：提炼全文，套引言四步公式。
5. **Conclusion(6) + Abstract**：收尾，摘要放最后写。
6. **配图**：Figure 1 系统总览图 + Usage 截图，越早画越好。
