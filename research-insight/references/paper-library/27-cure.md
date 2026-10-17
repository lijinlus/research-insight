# 27. CURE: Critique-Driven Unified Reinforcement Learning for Test-Time Self-Improvement

ACL 2026 · Outstanding Paper · 核对日期：2026-10-16

[论文页面](https://aclanthology.org/2026.acl-long.1321/) · [本次阅读PDF](https://aclanthology.org/2026.acl-long.1321.pdf) · [官方奖项依据](https://2026.aclweb.org/program/best_papers/) · [返回索引](index.md)

首轮结构阅读：PDF pp.1–2；§4.1；Fig.1–2说明。版本：conference/open-access PDF; see source URL and SHA-256。以下为主线与写法分析，非逐段翻译或完整技术审计。


- **引言如何推进**：先区分并行采样与顺序推理，再指出可靠自我检查未被充分优化；把依赖强教师或测试时真值的问题转成自主闭环需求。
- **主张如何组织**：将求解、批评与重探索共同训练；用高层提示重启推理，避免不断携带错误答案。
- **证据如何接上**：先画训练和推理闭环，再用pilot检查重复错误；实验同时比较单次表现与多轮扩展。
- **可迁移的研究操作（分析者归纳）**：按推理阶段真正可用的信息反推训练设计，明确训练与测试的信息边界。
- **使用边界（分析者判断）**：自主推理不等于无监督训练；训练仍使用验证与奖励信息，预算比较需计入额外批评开销。

## 论证细读（2026-10-17）

**本轮读取**：会议PDF pp.2–7与10–13，§§3–5、Tables 1–3、Figures 1–2/3–5说明；p.7–9部分图中文字提取异常，未读取其原始曲线精确数值。下述是对论证的分析，不代表复现结果或逐行核验全部证明。

### 从部署闭环反推训练对象
CURE要求同一个模型会solve、verify、给hint并按hint再探索。训练可用verifier，但部署时由自己的正确性判断决定是否重试。§3不把critique仅作附加文本，而是用再解题成功率给hint延迟奖励，verification用gold判断监督，成功重探索轨迹replay回solve任务。三项能力对应三个损失与推理链中的实际环节。

### 方法中的约束有具体用途
重生成只读原问题与高层hint，不读原错误解；Fig.2的wrong-solution/hint/resampling比较支持降低重复错误的候选解释。这个设计不等于普遍证明删除历史最好。验证正负1:1是训练抽样选择，推理时真实错误先验可能不同，仍需校准。训练时给gold judgment不等于测试能使用gold。

### 有效critic怎么定义
verification准确、hint让答案改善、solver能用hint是不同能力。§4.5去verification训练后多轮曲线平，去hint优化后较早饱和，分别检验闭环瓶颈。hint奖励是后续平均成功率减初始组成功率，有采样噪声和任务难度影响；成功replay也改变训练分布，不能把全部增益只归因于hint内容。

### 预算与结果读法
基线每题8次初解，CURE 4初解+4guided并有额外critique；数量相近不代表token/计算完全相同。Table 1单次与最多8轮区分；Avg@32等是平均准确率估计，不是Pass@32。Table 2再比较majority/BoN/iterative，并承认CURE的BoN有时不如GRPO；外部reward模型分布错位是作者假说。

Table 3用总生成token与latency补充最大N/T预算，BoN还保守排除reranker延迟。MATH较少token且相似延迟，难题上的顺序loop可能更慢，不能称通用加速。条件重试可能停在自信错误，也可能改坏正确答案，需拆false-accept、false-reject、correct→wrong与wrong→correct，而不只看最后准确率。

### 可迁移操作
先画部署时哪些反馈可得，再为每个决定能否产生有效下一步的能力设置训练和单独测量。金融因子生成若没有可靠verifier，不能直接套RLVR；可先在可执行表达式正确性与留出评估上测试闭环，而不将回测噪声视为绝对真值。

**对skill的启发**：闭环贡献按决策环节而非模块数判断；训练/部署信息隔离；轮次公平还需token、延迟及停止错误。
