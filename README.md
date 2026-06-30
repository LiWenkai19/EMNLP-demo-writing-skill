# emnlp-demo-writing

一个 [Claude Code](https://docs.claude.com/en/docs/claude-code) **Agent Skill**，用于高效写作 EMNLP / ACL / NAACL **System Demonstrations（demo track）** 投稿论文。

它把 EMNLP 2023+2024 共 106 篇 demo 论文的真实结构、4 篇代表作的章节骨架、以及官方征稿要求，归纳成一套可操作的写作指导——帮助在短周期内写出符合规范、不被 desk reject 的 demo 论文。

## 能做什么

- **全流程写作**：标准 6 段骨架、各章节英文填空模板、引言四步公式
- **Evaluation 设计**：针对交互类 demo 的轻量评估方案（SUS/NPS、人工评测、路径正确性核查）
- **论文图表**：系统架构图（TikZ/Mermaid/Graphviz）、数据图表（matplotlib）、界面截图的模板与指导
- **LaTeX 排版**：ACL 官方模板用法 + 可直接套用的 demo 论文 .tex 骨架
- **投稿前自检**：官方 8 个核心问题对照 + desk-reject 规避清单

指导语言为中文，论文模板句式给英文（可直接用进投稿）。

## 目录结构

```
emnlp-demo-writing/
├── SKILL.md                        # 主文件：触发条件 + 写作流程指导
└── templates/
    ├── paper-skeleton.md           # 6 段骨架 + 篇幅分配 + 写作顺序
    ├── section-templates.md        # 各章节英文模板句式
    ├── evaluation-playbook.md      # Evaluation 方案手册
    ├── figures-guide.md            # 论文图表制作（架构图/截图/数据图）
    ├── latex-formatting.md         # ACL 官方 LaTeX 排版规范 + 论文骨架
    └── checklist.md                # 投稿前自检清单
```

## 安装

把整个 `emnlp-demo-writing/` 目录放到 Claude Code 的 skills 目录下：

- **用户级（全局生效）**：`~/.claude/skills/emnlp-demo-writing/`
  （Windows：`C:\Users\<你>\.claude\skills\` 或你的 `.claude` 所在盘）
- **项目级（仅当前项目）**：`<项目>/.claude/skills/emnlp-demo-writing/`

例如：

```bash
git clone https://github.com/<your-name>/emnlp-demo-writing-skill.git
mkdir -p ~/.claude/skills
cp -r emnlp-demo-writing-skill ~/.claude/skills/emnlp-demo-writing
```

> 注意：skills 目录下的子目录名需与 `SKILL.md` 中的 `name: emnlp-demo-writing` 一致。

## 使用

安装后，在写 demo 论文时它会自动触发；也可以主动唤起，例如：

- “帮我写 demo 论文的 introduction”
- “我的 evaluation 该怎么设计”
- “帮我画系统架构图 Figure 1”
- “投稿前帮我按官方 8 问检查一下”

## 证据来源

- [EMNLP 2026 Call for Demonstrations](https://2026.emnlp.org/calls/demos/)
- [EMNLP 2024 System Demonstrations (ACL Anthology)](https://aclanthology.org/events/emnlp-2024/)
- [EMNLP 2023 System Demonstrations (ACL Anthology)](https://aclanthology.org/events/emnlp-2023/)

## License

MIT
