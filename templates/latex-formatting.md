# ACL/EMNLP 官方 LaTeX 排版规范

EMNLP/ACL/NAACL 投稿统一用 ACL 官方模板（`acl.sty` + `acl_natbib.bst`）。
本文件给出排版要点 + 一份可直接套用的 demo 论文 LaTeX 骨架。

官方模板来源（Overleaf，CC BY 4.0）：
https://www.overleaf.com/latex/templates/association-for-computational-linguistics-acl-conference/jvxskxpnznfj
GitHub: https://github.com/acl-org/acl-style-files

## 模板包含的文件

| 文件 | 作用 |
|------|------|
| `acl_latex.tex` | 主源文件（示例文档）|
| `acl.sty` | ACL 样式文件 |
| `acl_natbib.bst` | 参考文献样式 |
| `custom.bib` | 你自己的参考文献 |
| `anthology.bib` | ACL Anthology 全库（可选引入）|

## 核心：三种编译模式（投稿/终稿切换）

```latex
\documentclass[11pt]{article}
\usepackage[review]{acl}   % 投稿评审版（demo track 是单盲，但 review 选项加行号便于评审）
% \usepackage{acl}          % 终稿 camera-ready（去掉 review）
% \usepackage[preprint]{acl}% 预印本：非匿名 + 带页码
```

- **demo track 是单盲**（作者不匿名），但投稿时仍建议用 `review`（带行号方便评委引用）。
- 录用后改成 `\usepackage{acl}` 出 camera-ready。
- 字体默认 Times Roman 11pt：`\usepackage{times}`（或 `newtx`）。
- 推荐 pdfLaTeX；非拉丁字符（如中文示例）用 XeLaTeX/LuaLaTeX。

## 常用命令速查

**引用（基于 natbib + ACL 扩展）：**
| 输出 | 命令 |
|------|------|
| author (year) | `\citet{key}` |
| (author, year) | `\citep{key}` |
| author, year | `\citealp{key}` |
| author's (year) | `\citeposs{key}`（ACL 专属）|

参考文献：`\bibliography{custom}` 或 `\bibliography{anthology,custom}`（含全库）。

**作者多单位：** `\and`（同单位换行）/ `\And`（不同单位）/ `\AND`（新作者行）。

**图（单栏 / 跨双栏）：**
```latex
\usepackage{graphicx}
\begin{figure}[t]
  \includegraphics[width=\columnwidth]{fig1}
  \caption{...}\label{fig:arch}
\end{figure}

\begin{figure*}[t]   % 跨双栏，放多张截图
  \includegraphics[width=0.48\linewidth]{a}\hfill
  \includegraphics[width=0.48\linewidth]{b}
  \caption{...}
\end{figure*}
```

**附录：** 正文末加 `\appendix` 后再写 section（编号自动转字母）。
**禁止：** 改默认 caption 字号、改页边距、超页数。

## 可直接套用的 Demo 论文骨架（复制即用）

```latex
\documentclass[11pt]{article}
\usepackage[review]{acl}
\usepackage{times}
\usepackage{graphicx}
\usepackage{latexsym}
\usepackage[T1]{fontenc}
\usepackage[utf8]{inputenc}
% 若有中文示例：改用 XeLaTeX 并 \usepackage{ctex}

\title{MedPath-TCM: A Knowledge-Grounded Interactive Learning System\\
       for Traditional Chinese Medicine Beginners}

\author{First Author \\ Affiliation \\ \texttt{email} \\\And
        Second Author \\ Affiliation \\ \texttt{email}}

\begin{document}
\maketitle

\begin{abstract}
% 背景痛点 → We present X → X 做了什么 → 评估结论 → demo/视频/代码链接
\end{abstract}

\section{Introduction}
% 背景 → However 痛点 → We present MedPath-TCM → 贡献点(bullet)
% 末尾给三个链接的脚注：demo / video / code

\section{Related Work}
% 已有 TCM 信息化 / KG 可视化 / 教育工具的不足，反衬本系统

\section{System Architecture}
\label{sec:system}
% 配 Figure 1 总览图；核心 novelty(PD-KGC) 重点讲；其余组件简述

\section{Usage / Walkthrough}
% 配界面截图(figure*)；用户点什么、看到什么

\section{Evaluation}
% 可用性问卷(SUS/NPS) + 路径正确性人工核查，报告 N 与数字

\section{Conclusion}
% 收尾 + 未来工作

\section*{Limitations}
% 诚实写局限（ACL 要求，不计入正文页数限制）

\section*{Ethics Statement}
% 健康类系统：声明非诊断、数据隐私、免责（不计页数）

\bibliography{custom}

\appendix
\section{Appendix}
% 补充材料，最多 2 页
\end{document}
```

## 页数红线（再次提醒）

- 正文 ≤ 6 页（录用后 +1 页）
- References / Limitations / Ethics Statement **不计入**正文页数
- Appendix ≤ 2 页

## 健康/医疗类 demo 的特别注意

- **Ethics Statement 几乎必写**：明确「非临床诊断、不替代就医」、数据来源与隐私、面向教育用途。
- 体质/健康声明要谨慎措辞，避免被判定为医疗建议导致 ethical concern。
