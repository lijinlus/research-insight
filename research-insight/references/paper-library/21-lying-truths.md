# 21. Lying with Truths: Open-Channel Multi-Agent Collusion for Belief Manipulation via Generative Montage

ACL 2026 · Outstanding Paper · 核对日期：2026-10-16

[论文页面](https://aclanthology.org/2026.acl-long.270/) · [本次阅读PDF](https://aclanthology.org/2026.acl-long.270.pdf) · [官方奖项依据](https://2026.aclweb.org/program/best_papers/) · [返回索引](index.md)

首轮结构阅读：PDF pp.1–2；§5.3入口；Fig.1–2说明。版本：conference/open-access PDF; see source URL and SHA-256。以下为主线与写法分析，非逐段翻译或完整技术审计。


- **引言如何推进**：从叙事连贯性可能诱发虚假因果切入；把隐蔽通道串谋与公开真实碎片下的认知操纵对照，再定义新的威胁模型。
- **主张如何组织**：将局部真实、整体误导作为需要同时满足的约束，并用模拟环境研究受害者判断和下游传播。
- **证据如何接上**：先对比新旧威胁，再形式化目标与构造；实验区分跨模型有效性、下游后果和组件作用。
- **可迁移的研究操作（分析者归纳）**：安全研究先说明旧威胁假设遗漏了什么，再让实验严格匹配新威胁约束。
- **使用边界（分析者判断）**：模拟攻击结果不能直接推出真实社交传播规模；“更会推理更脆弱”也应保留所测条件。

## 论证细读（2026-10-17）

**本轮读取**：会议PDF pp.3–9，§§3–7、Tables 1–3、Figures 2–4与Limitations；未执行攻击或访问任何真实平台。下述是对论证的分析，不代表复现结果或逐行核验全部证明。

### 题目怎样准确提出一个新威胁面
局部真实的信息经选择与排列后，可诱导不真实的整体因果叙事。§3区分Local Truth与Global Lie，§4将证据组织、叙事优化和下游传播放在同一模拟中，§5再检查局部核查无法覆盖的结论错误。这比“Agent可能被误导”更具体：安全属性是每片事实真实，失效对象是跨片段推断。

### 形式化有用，但不是动力学证明
Bayesian posterior是概念模型，实验主要用回答与自报告confidence操作化belief；Eq.11写出的极限趋1和“deterministically converges”并非本轮所见证明或长期实验保证。现有表格能支持模拟设定下错误接受率高，不能推出真实社交系统必然收敛到谎言。

### 数据真值是最关键的审查点
CoPHEME从PHEME改造：true/non-rumor作事实池，false/**unverified**作目标。non-rumor不天然等于已核实事实，unverified也不天然等于假；必须额外核查实例是否真的满足LT/GL定义。叙事重写还可能引入新暗示或事实细节，原始tweet标签不足以替代对最终片段的真实性审计。

### 实验能回答什么
Table 1六事件、多模型、每目标五victims，报告ASR、自信度及高自信ASR；事件宏平均与实例加权平均应分清。Table 2的CoT比较只在一个事件/两模型，不能概括为“推理越强越危险”的普遍因果规律。Table 3去debate/editor/单Agent支持所测系统组件有用，但单Agent若预算不同，不能单独证明协作分工必不可少。

Fig.3下游vote/judge接受表明共同来源错误可传播，多名victims读同一证据并不产生独立信息。§6防御是讨论和未来方向，不能写成已验证方案。所有研究在模拟中，未覆盖平台推荐、自然反叙事、真实人群与现实行为后果。

### 可迁移操作
把系统局部保证与全局用途分开验证，检查全局输出是否引入证据未支持的关系。

**对skill的启发**：构念定义要回到实例真值；相关输入下的共识不是独立证据；概念概率与实际confidence量必须区别。
