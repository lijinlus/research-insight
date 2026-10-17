# Research Insight · 研究思路与亮点

一个面向科研思路的 Codex skill：从模糊 idea、已有方案或实验结果中，提炼有依据的贡献，找出最威胁主张的缺口，并设计下一步验证。

**关注问题、创新性与证据设计，不做语法润色。**

Research ideas, defensible contributions, and falsifiable experiments. A Chinese-first agent skill with 35 annotated paper cases, grounded in primary sources.

[Skill 正文](research-insight/SKILL.md) · [35 篇论文索引](research-insight/references/paper-library/index.md) · [跨论文归纳](research-insight/references/paper-library/synthesis.md) · [v0.1.0 下载](https://github.com/lijinlus/research-insight/releases/tag/v0.1.0)

## 它帮你做什么

| 你的阶段 | Skill 的工作 | 主要交付 |
| --- | --- | --- |
| 只有主题或类比 | 探索少量可区分的研究假设 | 候选主张、价值与成本、优先验证项 |
| 已有 idea / proposal | 诊断问题、近邻差异与证据链 | 最关键缺口、修订主张、最小验证卡 |
| 已有结果或草稿 | 判断结果实际支持什么 | 主张—证据对应关系、补证项、研究主线 |
| 想学习优秀论文 | 拆解原文的知识增量与论证 | 关键证据、边界、可迁移的研究操作 |

它会检查：你想改善什么、需要保留什么、允许付出什么成本，以及最接近的工作是否已经解释了这个结果。涉及金融或量化时，还会检查时间顺序、信息可见性、选择偏差和交易成本等条件。

支持方法、理论、资源、评测、系统和可靠负结果等贡献形式；不要求每篇论文都套用“发现现象—解释根因—提出方法”的结构。

## 安装

### 在 Codex 中安装

给 Codex 发送下面这句话，使用内置的 `skill-installer` 安装固定版本：

```text
$skill-installer 安装 https://github.com/lijinlus/research-insight/tree/v0.1.0/research-insight
```

如果已有同名 skill，先检查现有版本，再决定如何更新。

### 手动安装

从 [Releases](https://github.com/lijinlus/research-insight/releases/tag/v0.1.0) 下载 `research-insight-v0.1.0.zip`，解压后将整个 `research-insight` 文件夹放入以下任一位置：

| 使用范围 | 目录 |
| --- | --- |
| 当前项目 | `<项目根目录>/.agents/skills/research-insight/` |
| 当前用户 | `~/.agents/skills/research-insight/` |

目录内应直接包含 `SKILL.md`、`agents/` 和 `references/`。若安装后未显示，重启 Codex 再试。目录与调用方式以 [OpenAI 官方 skills 文档](https://learn.chatgpt.com/docs/build-skills)为准。

这是可独立安装的 GitHub skill 包；当前尚未提交到官方插件目录。

## 使用

在请求前加上 `$research-insight`，并尽量提供研究对象、已有材料和实际约束。敏感材料可以先脱敏；不必把整个项目一次性贴入。

**探索一个想法：**

```text
$research-insight
我想研究多 Agent 是否能改善金融新闻分析。现在只有这个方向，
还没有证据证明协作有价值。请提出少量可区分的研究假设，
比较与单模型、更多采样预算等简单替代方案的差异，推荐最先做的实验。
约束：先使用已有模型和小规模数据，不训练完整系统。
```

**诊断一个方案：**

```text
$research-insight
下面是我的 proposal。请检查最接近的工作，区分已核验事实与待验证假设，
指出最可能让贡献不成立的一处，并给出可支持或推翻它的最小实验。
不要先帮我改标题。
【粘贴 proposal、已有结果及数据/预算约束】
```

**从原文学习：**

```text
$research-insight
请拆解这篇论文的问题、核心主张、关键比较和证据边界，
说明哪些研究操作可以迁移到别的课题，并标明实际读取的章节。
【论文链接或 PDF】
```

一次诊断通常会围绕“当前判断 → 最关键缺口 → 修订后的主张 → 下一步验证”展开。问题简单时只回答主要瓶颈，不强制生成长报告。

## 35 篇案例库

案例来自一篇文章推荐的 35 篇论文，涉及 CVPR、ECCV、ICLR、ICML、AAAI 和 ACL 2026。**这是推荐样本，不是这些会议的完整获奖名单。**

选题入口：[原始推荐文章](https://mp.weixin.qq.com/s/mnU8PE-6DZ38rJqHeOiSfQ)。本仓库的论文分析以原论文为依据，逐篇链接实际阅读版本和官方奖项来源；不将二手文章的概括直接作为技术证据。

每张卡片包含：

- 引言怎样收窄问题，贡献如何组织，证据怎样接上；
- 关键定义、方法、结果和对照能支持到哪一层；
- 未排除的解释、适用边界与可迁移的研究操作；
- 实际阅读章节/页码、版本和一手来源。

先读[跨论文归纳](research-insight/references/paper-library/synthesis.md)，再按问题进入[逐篇索引](research-insight/references/paper-library/index.md)。Skill 按需读取少量相关卡片，不默认把全部论文分析加入上下文。

我们没有把“单一 claim”“一句话机制”或“有惊艳现象”设为所有好论文的必要条件。案例分析也不等同于官方给出的获奖原因。

## 内容结构

```text
research-insight/
├── SKILL.md                      # 核心流程与交付要求
├── agents/openai.yaml            # Codex 展示名称与默认提示
└── references/
    ├── research-moves.md         # 产生与诊断研究思路的操作
    ├── evidence-design.md        # 主张、测量、比较与实验设计
    ├── quant-ml.md               # 金融与量化的条件检查
    ├── calibration-cases.md      # 虚构的行为验收场景
    └── paper-library/
        ├── index.md
        ├── synthesis.md
        ├── manifest.json        # 来源、版本、PDF 哈希与读取范围
        └── 01-*.md … 35-*.md
```

Skill 本身不依赖额外 Python 包、API key 或特定 GPU。核验新论文和创新性需要可用的检索/阅读工具；无法取得原文时应明确保留判断，不能编造文献或实验。它不会自动启动模型训练。

## 首版验证与边界

`v0.1.0` 已通过 skill 格式检查、包内链接检查、35 条论文记录与卡片一致性检查，以及安装包解压检查。研究流程做过 7 个场景的人工自查；校准文件中的 A–P 场景是验收规范，不是已运行的独立评测。

论文卡片读取了引言、核心方法或形式定义、主结果、关键对照与讨论，并按需检查部分附录；**没有复现实验，也没有逐行审完所有证明和附录**。具体范围以各卡片和 manifest 为准。

案例库和 skill 的整理包含 AI 辅助分析，可能仍有遗漏。尚未证明它能提高论文录用率，不能仅凭获奖样本推断某种写法导致获奖。对新课题的创新性判断仍须检索当前近邻工作。

PDF、论文全文提取、临时缓存、本地工作日志均不在发布包内。Manifest 中 `cache_*` 字段是构建时的相对缓存位置，不是发布包中应存在的文件。

## 反馈与许可

欢迎通过 [Issues](https://github.com/lijinlus/research-insight/issues) 提交论文解读纠错或使用反馈。解读纠错请附一手来源、章节/页码和需要修改的结论；使用反馈请提供脱敏输入、实际输出及预期差异。请勿提交未授权公开的稿件、数据或个人信息。

原创 skill 指令与分析采用 [MIT License](LICENSE)。引用的论文、图表、文章及其他第三方材料保留各自版权与许可；本仓库的 MIT 许可不适用于它们。本项目与相关会议或 OpenAI 无隶属关系。
