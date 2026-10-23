# Research Insight · 研究思路与亮点

一个面向科研思路的通用 Codex skill：从模糊 idea、已有方案或实验结果中，提升研究立意与技术洞察，组织有证据支撑的研究主线，并设计下一步验证。

**关注问题、创新性与证据设计，不做语法润色。**

Research ideas, defensible contributions, and falsifiable experiments. A Chinese-first agent skill with 35 annotated paper cases, grounded in primary sources.

[Skill 正文](research-insight/SKILL.md) · [35 篇论文索引](research-insight/references/paper-library/index.md) · [跨论文归纳](research-insight/references/paper-library/synthesis.md) · [v0.2.0 下载](https://github.com/lijinlus/research-insight/releases/tag/v0.2.0)

## 未发布修改

当前工作树精简了默认入口，让探索、判断、结果理解与论文组织随讨论切换；研究操作按需要选用，范式名称保留为辅助标签。思路停滞时可以浏览案例索引，再选择相关卡片，跨论文归纳不再是前置阅读。

这轮修改旨在减少重复要求与过早收敛，尚未进行独立行为对照，不能据此声称减少了锚定或提高了研究效果。多轮对照准备见 [评测方案](evals/research-insight/multiturn-plan.md)。下方 `v0.2.0` 下载与安装链接仍指向已发布版本，不包含这些未发布修改。

## 它帮你做什么

| 你的阶段 | Skill 的工作 | 主要交付 |
| --- | --- | --- |
| 只有主题或类比 | 展开不同立意、技术联想与候选洞察 | 候选角度、潜在增量、技术草图；按需比较与选择验证项 |
| 已有 idea / proposal | 保留有潜力的亮点，诊断近邻差异、技术思路与证据链 | 补强方向、修订定位、实验/证明/反例等适合的验证方案 |
| 已有结果或草稿 | 判断结果支持的洞察，组织论证 | 主张—证据关系、补证项、关键图与研究主线 |
| 想学习优秀论文 | 拆解原文的立意、技术转折与论证 | 叙事如何接上证据、边界与可迁移操作 |

它会检查：你想改善什么、需要保留什么、允许付出什么成本，以及最接近的工作是否已经解释了这个结果。具体领域的假设、可用信息和评价惯例从当前任务获取，不预设应用领域。

支持方法、理论、资源、评测、系统和可靠负结果等贡献形式；不要求每篇论文都套用“发现现象—解释根因—提出方法”的结构。

讨论力度随阶段调整：早期探索允许大胆猜想、技术草图与尚不完整的候选；需要取舍、确认主张或投入资源时，再细化近邻比较和验证方案。可以围绕一个直觉或卡点持续讨论，篇幅与结构随问题调整，事实与假设始终分清。

## 四个维度与六种范式

找亮点时，先从当前问题、观察和约束发展候选。需要打开角度时，再借助**主题立意、技术洞察、证据设计、研究叙事**等入口。[研究操作库](research-insight/references/research-moves.md)提供可执行操作，并保留六种范式的原名作为对照标签：根因手术刀、反直觉重构、理论照亮经验、新基准暴露失效、社会价值叙事、极简统一美学。

[研究叙事](research-insight/references/research-story.md)进一步说明如何形成工作定位、让方法由洞察导出、安排关键图，以及将重要增量放进标题与引言前部。这些是生成和提高研究角度的启发，不是获奖门槛，也不要求一个选题套齐六种范式。

最新发布版本为 `v0.2.0`，包括通用科研定位、按阶段展开的讨论，以及原则与案例分层。未发布修改另列于 [CHANGELOG](CHANGELOG.md)。

## 默认上下文与可选案例

`v0.2.0` 采用“先分析当前材料，再按具体问题选择资料”的路径。`SKILL.md` 及三份按需参考只保留原则，不嵌入固定论文结论、特定应用选题或开发示范答案。四维与六种范式继续用于生成和提高研究角度，允许其他贡献路径。

35 篇卡片与跨论文归纳保留在可选案例库。当前工作树也允许在思路停滞时浏览索引寻找启发，再按相关性选择卡片；借用时说明操作与条件差异。核验当前课题的近邻原文仍照常进行。

校准题移到仓库级 [evals/research-insight](evals/research-insight/README.md)，任务和评估标准分开。普通 skill 安装仅取 `research-insight/`，不包含这些评分材料；整仓下载仍包含评测文件，需要独立上下文和可见文件控制才能形成更强隔离。这个设计减少默认案例暴露，尚未证明消除了锚定或提高了研究效果。

## 安装

### 在 Codex 中安装

给 Codex 发送下面这句话，使用内置的 `skill-installer` 安装固定版本：

```text
$skill-installer 安装 https://github.com/lijinlus/research-insight/tree/v0.2.0/research-insight
```

如果已有同名 skill，先检查现有版本，再决定如何更新。

### 手动安装

从 [Releases](https://github.com/lijinlus/research-insight/releases/tag/v0.2.0) 下载 `research-insight-v0.2.0.zip`，解压后将整个 `research-insight` 文件夹放入以下任一位置：

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
研究主题：【任务或现象】
已有材料：【观察、相关工作或初步结果】
实际约束：【可用数据、实现基础、时间与计算预算】
请提出少量有依据的研究角度，说明核心洞察与潜在知识增量，
比较价值和验证成本，推荐一个最先检验的问题。
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

回答随当前问题组织：可以只澄清概念、发展一个假设、解释一项结果，或给出有依据的投入建议。无需每次交付完整研究方案。

## 35 篇案例库

案例来自一篇文章推荐的 35 篇论文，涉及 CVPR、ECCV、ICLR、ICML、AAAI 和 ACL 2026。**这是推荐样本，不是这些会议的完整获奖名单。**

选题入口：[原始推荐文章](https://mp.weixin.qq.com/s/mnU8PE-6DZ38rJqHeOiSfQ)。本仓库的论文分析以原论文为依据，逐篇链接实际阅读版本和官方奖项来源；不将二手文章的概括直接作为技术证据。

每张卡片包含：

- 引言怎样收窄问题，贡献如何组织，证据怎样接上；
- 关键定义、方法、结果和对照能支持到哪一层；
- 未排除的解释、适用边界与可迁移的研究操作；
- 实际阅读章节/页码、版本和一手来源。

需要学习案例时，可读[跨论文归纳](research-insight/references/paper-library/synthesis.md)，或按具体问题进入[逐篇索引](research-insight/references/paper-library/index.md)。普通研究分析先理解当前任务，不默认读取案例库或归纳。

我们没有把“单一 claim”“一句话机制”或“有惊艳现象”设为所有好论文的必要条件。案例分析也不等同于官方给出的获奖原因。

## 内容结构

```text
research-insight/
├── SKILL.md                      # 核心流程与交付要求
├── agents/openai.yaml            # Codex 展示名称与默认提示
└── references/
    ├── research-moves.md         # 产生与诊断研究思路的操作
    ├── research-story.md         # 研究定位、六种论证路线、关键图与引言
    ├── evidence-design.md        # 主张、测量、比较与实验设计
    └── paper-library/
        ├── index.md
        ├── synthesis.md
        ├── manifest.json        # 来源、版本、PDF 哈希与读取范围
        └── 01-*.md … 35-*.md

evals/research-insight/           # 仓库维护材料，不随 skill 安装
├── README.md                    # 角色与评测隔离约定
├── prompts.jsonl                # 不含预期答案的开发任务
├── rubric.md                    # 评估者使用的验收标准
└── multiturn-plan.md            # 未运行的真实多轮对照方案
```

Skill 本身不依赖额外 Python 包、API key 或特定 GPU。核验新论文和创新性需要可用的检索/阅读工具；无法取得原文时应明确保留判断，不能编造文献或实验。它不会自动启动模型训练。

## 验证与边界

`v0.2.0` 已通过 skill 格式、展示元数据、包内链接、35 条论文记录与卡片一致性，以及安装包解压与逐文件比对检查。安装包仅包含 `research-insight/`，不包含开发任务和评分材料。

首版做过 7 个场景的人工自查；A–P 来自首版验收规范，Q–T 为后续补充。全部 20 题及评分标准保存在仓库级 `evals/`，属于开发回归规格，不是已运行的独立评测。尚未形成隐藏留出集，也未进行独立行为评测。

论文卡片读取了引言、核心方法或形式定义、主结果、关键对照与讨论，并按需检查部分附录；**没有复现实验，也没有逐行审完所有证明和附录**。具体范围以各卡片和 manifest 为准。

案例库和 skill 的整理包含 AI 辅助分析，可能仍有遗漏。尚未证明它能提高论文录用率，不能仅凭获奖样本推断某种写法导致获奖。对新课题的创新性判断仍须检索当前近邻工作。

PDF、论文全文提取、临时缓存、本地工作日志均不在发布包内。Manifest 中 `cache_*` 字段是构建时的相对缓存位置，不是发布包中应存在的文件。

## 反馈与许可

欢迎通过 [Issues](https://github.com/lijinlus/research-insight/issues) 提交论文解读纠错或使用反馈。解读纠错请附一手来源、章节/页码和需要修改的结论；使用反馈请提供脱敏输入、实际输出及预期差异。请勿提交未授权公开的稿件、数据或个人信息。

原创 skill 指令与分析采用 [MIT License](LICENSE)。引用的论文、图表、文章及其他第三方材料保留各自版权与许可；本仓库的 MIT 许可不适用于它们。本项目与相关会议或 OpenAI 无隶属关系。
