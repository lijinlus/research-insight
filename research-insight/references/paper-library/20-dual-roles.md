# 20. Beyond the Final Actor: Modeling the Dual Roles of Creator and Editor for Fine-Grained LLM-Generated Text Detection

ACL 2026 · Outstanding Paper · 核对日期：2026-10-16

[论文页面](https://aclanthology.org/2026.acl-long.235/) · [本次阅读PDF](https://aclanthology.org/2026.acl-long.235.pdf) · [官方奖项依据](https://2026.aclweb.org/program/best_papers/) · [返回索引](index.md)

首轮结构阅读：PDF pp.1–2；§2.2；Fig.1–2说明。版本：conference/open-access PDF; see source URL and SHA-256。以下为主线与写法分析，非逐段翻译或完整技术审计。


- **引言如何推进**：先说明二分类无法处理人机合作文本，再指出单一混合类仍混淆了创作者与编辑者的先后作用；由流程差异引出四类设定。
- **主张如何组织**：用修辞结构刻画内容组织、语义单元刻画表面表达，分别对应creator与editor。
- **证据如何接上**：先做修辞关系的动机分析，再给模型；主结果之外检查低误报、消融和解析器稳健性。
- **可迁移的研究操作（分析者归纳）**：先弄清对象的生成过程，再确定标签粒度与特征，而非只扩分类头。
- **使用边界（分析者判断）**：角色解释依赖所用数据与编辑流程；结构特征差异不等于普遍的人类或LLM本质属性。

## 论证细读（2026-10-17）

**本轮读取**：会议PDF pp.2–9，§§2–6、Tables 1–6及Limitations；严格group-aware结果仅定位到附录入口，未在本轮核读其表。下述是对论证的分析，不代表复现结果或逐行核验全部证明。

### 从真实流程重定义分类对象
RACE区分human、LLM、LLM-polished human、humanized LLM四类，以creator决定逻辑组织、editor影响表面表达为建模假说。§2先分析同一source及其编辑版本的RST频率相似性，§3用EDU、关系节点、RGCN和root readout实现结构特征。它不是首创四分类；引言及相关工作承认已有相邻任务，增量在角色建模与结构利用。

### 观察—设计的连接与边界
Table 1/Fig.2支持HART内编辑后结构特征部分保留，不能推出人类普遍“更有逻辑”、LLM普遍仅局部扩写。RST parser本身也可能带域或风格偏差。低维projection称information bottleneck是一种设计解释，未通过信息论量直接证明只保留creator信息。

### 把所需工作点写进指标
Table 2重点TPR@1%FPR，而非只追平均准确率：误报警代价使其有用途意义。RACE平均低FPR召回领先，但AUROC未最高；同一方法在不同指标下排序不同。Table 3消融关系类型、RGCN、CL、bottleneck、basis；整体平均收益不等于每类与每seed均改善。Table 4换parser检查鲁棒性，Table 6 leave-one-domain-out显示Writing低FPR指标并未领先，说明迁移有边界。

### 最需要核查的是切分单位
HART官方只有validation/test，作者重分70/20/10。若同一原文的多个编辑版本跨split，可泄漏source内容；正文另指向附录B.2严格group-aware切分。主表与严格分组结果需分别标注，本轮未核读后者，不将其视为已确认等效。人工反复编辑、其他语言、新生成器不在单HART范围内。

低FPR工作点还需要足够多独立negative和可靠阈值校准；检测器的类别分数不能作为实际作者身份定论。原文也明确不应无人工检查直接采取后续行动。

### 可迁移操作
从生成/编辑流程定义标签与依赖组，再选择真正重要的工作点；不把多次变体当独立样本。金融新闻、因子表达式的模板变体也应按基础事件/表达式家族分组留出。

**对skill的启发**：先识别派生样本的共同祖先；指标对应决策工作点；提出角色解释后仍需检查它是否只是数据/解析器的统计特征。
