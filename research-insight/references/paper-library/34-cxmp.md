# 34. CxMP: A Linguistic Minimal-Pair Benchmark for Evaluating Constructional Understanding in Language Models

ACL 2026 · Outstanding Paper · 核对日期：2026-10-16

[论文页面](https://aclanthology.org/2026.acl-long.2132/) · [本次阅读PDF](https://aclanthology.org/2026.acl-long.2132.pdf) · [官方奖项依据](https://2026.aclweb.org/program/best_papers/) · [返回索引](index.md)

首轮结构阅读：PDF pp.1–2引言主体；§4.1；Fig.1–2与Table 1说明。版本：conference/open-access PDF; see source URL and SHA-256。以下为主线与写法分析，非逐段翻译或完整技术审计。


- **引言如何推进**：先区分句子合语法与理解结构所含意义；指出单一构式和提示分类不利于跨模型比较；再用最小对隔离形式线索。
- **主张如何组织**：覆盖多种构式，并检查规模、目标和训练阶段下的构式理解与伪词泛化。
- **证据如何接上**：从易懂构式例子进入任务设计，再比较整体表现、学习轨迹与偏差，显示测量能揭露什么。
- **可迁移的研究操作（分析者归纳）**：先论证现有任务混入了哪项能力，再设计能跨模型使用的更干净对照。
- **使用边界（分析者判断）**：最小对仍需语义与生成质量核验；模型对似然的偏好不能无条件等同于人的理解。

## 论证细读（2026-10-17）

**本轮读取**：会议PDF pp.2–10，§§2–6及Limitations、Tables 1–2、Figures 2–8。下述是对论证的分析，不代表复现结果或逐行核验全部证明。

### 从语言理论导出可测的语义区别
CxMP不只问句子语法是否自然，而是给constructional example，再比较两个diagnostic continuation的合理性。九类构式与A/B视角、实体角色互换对应不同预测；由此把“懂构式”操作化为能随角色和关系改变判断，而不是记住常见词搭配。

### 控制变量是核心贡献的一部分
四种实体命名（普通名词、男女名、name+字母）平衡自然性与词汇偏差；swapped版本检验是否总选某个名字、最近名词或第一名词。43K pairs来自模板+GPT生成与筛查，896项三人验证，多数票96.65%、全一致83.59%；子集验证不能说所有43K已逐条人工核验，成对/模板变体也非43K独立语义。

### 通用协议仍存在测量差异
开放CLM用length-normalized logprob，MLM用pseudo-likelihood，GPT-5用prompt估计，三者并非同一种直接可比读数。construction+diagnostic整体自然度可能夹带词频、语法与world plausibility；作者Limitations主动承认likelihood法并非最大化现代LLM能力的协议。MLM与CLM比较还混架构、数据规模/来源，不是训练目标唯一因果效应。

### 好的分析让总分解释更具体
Pythia size sweep、open-sci data比较、Llama instruction/base配对给不同变化轴；不能把跨data source规模差一概归因token数。OLMo checkpoint与BLiMP对比显示两种能力发展不同，但“human acquisition-like”是类比，未证明人同样经历其训练阶段。

Fig.7 bias按组均值差定义，接近零可能是都随机或错误相互抵消，要与paired correctness和总准确率一起读。pseudoword测试降低词义线索，也改变token化/分布，仍保留词类词缀；下降支持词汇依赖候选，不是已经排除所有分布外困难。human对照来自既有实验，与当前材料未完全匹配。

### 可迁移操作
设计“语义关系改变，表面词项尽量不变”的成对任务；让互换前后的答案按预期翻转，再跨模板/词汇留出。

**对skill的启发**：总分旁加角色互换/互补视角与无关线索控制；协议通用性与能力充分激发是不同目的；低偏差不能脱离正确率解读。
