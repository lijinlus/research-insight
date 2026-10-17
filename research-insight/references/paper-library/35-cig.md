# 35. CIG: Measuring Conversational Information Gain in Deliberative Dialogues with Semantic Memory Dynamics

ACL 2026 · Outstanding Paper · 核对日期：2026-10-16

[论文页面](https://aclanthology.org/2026.acl-long.2203/) · [本次阅读PDF](https://aclanthology.org/2026.acl-long.2203.pdf) · [官方奖项依据](https://2026.aclweb.org/program/best_papers/) · [返回索引](index.md)

首轮结构阅读：PDF pp.1–2；Table 1与Table 5相邻分析；Fig.1说明。版本：conference/open-access PDF; see source URL and SHA-256。以下为主线与写法分析，非逐段翻译或完整技术审计。


- **引言如何推进**：先说明文明程度和结构形式未必意味着讨论有信息进展；定义新颖性、相关性、影响范围，再引入表示既有知识的语义记忆。
- **主张如何组织**：让每条发言相对于既有对话记忆接受评价，先验证人工判定，再检查自动评估与紧凑上下文；记忆中保留的说话者主张不等同于群体共同信念。
- **证据如何接上**：先给评分准则和标注，再做同信息条件的人机对比、记忆替代历史的检查及下游案例。
- **可迁移的研究操作（分析者归纳）**：先建立概念的可判定性，再评估LLM能否可靠自动化；信息状态必须纳入测量。
- **使用边界（分析者判断）**：评分来自特定讨论语境；语义记忆操作与信息增益的相关性不等于普遍因果机制。

## 论证细读（2026-10-17）

**本轮读取**：会议PDF pp.2–10，§§3–9及Limitations、Tables 1–7与Figures 1–3。下述是对论证的分析，不代表复现结果或逐行核验全部证明。

### 先验证构念，再建立自动化
CIG把讨论信息增益定义为相对既有知识与主题的认识推进，提出Novelty、Relevance、Implication Scope。§4用claim extraction和NLI memory更新提供历史上下文；§5收人类标签，§6检验哪些维度解释总体CIG，§7才自动评测和探索聚合，§8用主持人行为作案例。这是度量论文的完整研究主线。

### 没有命中的维度也保留在结果里
Table 4的ordinal模型控制字数，用AIC比较：Novelty/Relevance最有用，Scope贡献有限、部分语料去掉更好。作者将它改解释为讨论风格，而非信息量的单调驱动。可学习的是据证据修订最初框架；不能因为文章介绍三个维度，就把“普遍性越高越有价值”固化进skill。

CIG是1–4人类感知量，不是Shannon信息、互信息或因果知识增量；重复和协调可低CIG但仍对对话有价值。移植到新闻信息论研究必须重新定义对象和真值。

### 自动评测验证的是哪种一致性
人类在同一topic+memory summary+短窗口下打分，GPT-5与平均人类标签的MAE可比human LOO（Table 5）。LOO的目标均值、annotator筛除及信息限制影响结果，不能直接叫“超过人类判断能力”。Table 6换full/memory/short/no context时参照是GPT-5_summary，测模型不同上下文一致性，不是独立full-history人类效度。

Table 7 memory counts与人类CIG相关略高于长度/TF-IDF；共享summary生成会有优势，长句也可增加claim数。需条件/留出分析区分内容增量与长度，不能仅凭相关排名宣布语义memory是根因。Fig.2遍历聚合算子后min最好属探索性发现，与§6 Scope弱预测结果的关系仍需留出复核，不是“任何研究都取最弱维度”的普遍法则。

### 语义记忆的具体局限
抽取会去掉hedging，可能改变命题承诺；同speaker整合保留不同说话者分歧，但不代表已知共同信念。top-k检索遗漏、每claim最多更新一个历史项等限制也会影响novelty。数据是两种英语主持讨论、80segments，排除敏感主题；主持行为后的CIG变化是观察性，未隔离主持人何时选择介入的混杂，不能直接作因果策略建议。

**可迁移操作**：用专家/人类构念检验决定哪些维度保留，再评自动化；把参考标签本身与候选方法是否共享信息来源列明。

**对skill的启发**：研究框架要允许维度被数据否定；一致性不等于效度；探索得到的聚合规则需新留出验证。
