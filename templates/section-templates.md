# 各章节英文模板句式

填空式模板，`<...>` 替换成你的系统信息。句式提炼自 EMNLP 2024 代表作，可直接用进投稿。

---

## Abstract（最后写）

```
<Field/task> has <recent progress with LLMs>. However, <pain point / gap>.
To address this, we present <SystemName>, a(n) <open-source> <toolkit/framework/
platform/system> for <core function>. <SystemName> <key capability 1>, and
<key capability 2>. <Evaluation result in one sentence>. Our code is available
at <github>, with a live demo at <demo url> and a video at <video url>.
```

参考 MarkLLM 摘要：introduce X → unified extensible framework → user-friendly →
visualization → 12 evaluation tools → code at GitHub。

---

## 1 Introduction（引言四步公式）

**第1步 背景**（1–2 句，现在完成时）：
```
<Large language models (LLMs)> have <achieved remarkable progress / demonstrated
impressive capabilities> in <a wide range of tasks>, including <t1>, <t2>, and <t3>.
```

**第2步 转折点题**（However 引出痛点）：
```
However, <the existing solutions fail to / current systems lack / it remains
challenging to> <specific gap>. This <hinders / limits / undermines> <consequence>.
```

**第3步 亮出系统**：
```
To address <this/these issues>, we present <SystemName>, a(n) <type> that <one-line
definition>. <SystemName> enables <target users> to <key action>.
```

**第4步 贡献点**（bullet，2–4 条）：
```
Our main contributions are:
- We <build/release> <SystemName>, the first <category> that <novelty>.
- <SystemName> provides <unified framework / interactive interface / visualization>.
- We <open-source the system under the <license> license> and provide a live demo.
```

---

## 2 Related Work（反衬必要性）

```
<Category> systems such as <A> (cite), <B> (cite), and <C> (cite) have <what they do>.
However, they <limitation 1> and <limitation 2>. In contrast, <SystemName> <how we
differ / what we add>. To the best of our knowledge, <SystemName> is the first to
<unique angle>.
```

---

## 3 System / Architecture（核心，配 Figure 1）

```
Figure 1 shows the overall architecture of <SystemName>, which consists of <N>
components: <C1>, <C2>, and <C3>.

[3.1 Frontend / Module A]
The <frontend / module A> <does what>, built with <tech>. Users <interact how>.

[3.2 Backend / Module B]
The <backend> <handles what>. We <design choice> to <achieve what>. <SystemName>
adopts a <pluggable LLM backend>, supporting both <API> and <local models>.

[3.3 Walkthrough / Data flow]
Given <user input>, <SystemName> first <step 1>, then <step 2>, and finally <output>.
```

> 提示：若系统调用 LLM，强调后端「可插拔（pluggable）」，把创新点落在系统设计而非「调了某个 API」。

---

## 4 Usage / Walkthrough（demo 特色，配截图）

```
We illustrate a typical usage scenario (Figure 2). A user <step 1: clicks/inputs>.
<SystemName> then displays <what user sees>. The user can further <interaction 2>,
which <result>. This requires no <programming / setup>, making it accessible to
<non-expert target users>.
```

---

## 5 Evaluation（必需）

```
We evaluate <SystemName> from <N> perspectives: <P1> and <P2>.

[Setup] We recruited <N> participants / used <dataset>. <metric> measures <what>.

[Results] <SystemName> achieves <number> on <metric>, <comparison vs baseline>.
A usability study (<N> users) yields a <SUS score / NPS> of <value>, indicating
<interpretation>. These results demonstrate that <SystemName> is <effective/usable>.
```

---

## 6 Conclusion + Limitations

```
We presented <SystemName>, a(n) <type> for <function>. <One-sentence impact>.
<SystemName> is open-sourced under <license> at <github>; a live demo and video
are available at <urls>. In future work, we plan to <extension>.

Limitations: <SystemName> currently <limitation 1> and <limitation 2>. <Honest
note on scope / evaluation scale>.
```
