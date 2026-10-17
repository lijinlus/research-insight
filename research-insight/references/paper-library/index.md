# 35 篇论文：研究主线与论证写法索引

范围：用户提供文章推荐的 35 篇，按文章顺序编号；这不是 2026 年全部最佳论文的完整名单。35 篇已定位到原文、完成结构阅读，并于2026-10-17逐篇补充论证细读。奖项与完整题目对照官方来源核对日期：2026-10-16。

**阅读深度**：首轮看引言与结构；本轮逐篇读取核心方法/形式定义、主结果与关键对照、讨论或局限，并对部分相关附录追加检查。每张卡片先给结构摘要，再给具体论证分析及来源章节/页码。未复现实验，没有逐行审完全部证明与附录；个别提取异常或未取得的补充材料已标明。

先看[跨论文归纳：怎样产生idea与组织证据](synthesis.md)，再按下表进入逐篇分析。

**来源与版本**：优先采用会议开放版本；部分使用作者公开的 arXiv 版本，不把不同版本视为完全相同。每篇都链接实际阅读 PDF、官方奖项页；[manifest.json](manifest.json) 记录版本标识、来源、SHA-256 与本地缓存路径。Lychee-FD 的列表题名与 PDF 首页题名不同，已在第 22 篇注明。缓存位于项目 tmp/pdfs/35-papers，未纳入 Git。

**如何读这些卡片**：先找与自己问题相近的“研究操作”，再打开对应论文。卡片讨论作者如何建立论证，不因论文获奖就默认所有因果解释或泛化主张成立。“可迁移操作”和“使用边界”是分析者的判断。

| 编号 | 论文卡片 | 会议 | 主要研究操作 |
| --- | --- | --- | --- |
| 01 | [D4RT](01-d4rt.md) | CVPR 2026 | 统一问题接口 |
| 02 | [HKTex](02-hktex.md) | ECCV 2026 | 更换表示空间 |
| 03 | [Transformers are Inherently Succinct](03-succinct.md) | ICLR 2026 | 更换理论比较尺度 |
| 04 | [LLMs Get Lost](04-lost.md) | ICLR 2026 | 使用场景与评测错位 |
| 05 | [The Flexibility Trap](05-flexibility.md) | ICML 2026 | 拆分被捆绑的优势 |
| 06 | [High-Accuracy Sampling](06-sampling.md) | ICML 2026 | 精确提出未解复杂度问题 |
| 07 | [Global Human Opinion](07-global-opinion.md) | AAAI 2026 | 将模糊价值问题拆成研究轴 |
| 08 | [Model Change](08-model-change.md) | AAAI 2026 | 用例子递进引出新形式对象 |
| 09 | [CaDyT](09-cadyt.md) | AAAI 2026 | 打通两条各有缺口的路线 |
| 10 | [ReconVLA](10-reconvla.md) | AAAI 2026 | 可视化诊断到训练目标 |
| 11 | [High-Pass / HyperSheaflets](11-high-pass.md) | AAAI 2026 | 理论分析驱动频谱设计 |
| 12 | [LLM2CLIP](12-llm2clip.md) | AAAI 2026 | 把整合难点提前讲清 |
| 13 | [PlantTraitNet](13-planttraitnet.md) | AAAI 2026 | 数据资源到实际产品验证 |
| 14 | [Slum / GRAM](14-gram.md) | AAAI 2026 | 让应用约束决定技术路线 |
| 15 | [Imperfective Paradox](15-imperfective.md) | ACL 2026 | 用最小语言反例定义能力 |
| 16 | [Resource-Rational Encoding](16-memory.md) | ACL 2026 | 把认知约束操作化 |
| 17 | [Local Attention Expressivity](17-local-attention.md) | ACL 2026 | 反常经验到形式预测再回实验 |
| 18 | [MauBERT](18-maubert.md) | ACL 2026 | 把任务质量与数据效率同时定义 |
| 19 | [Evolutionary Guided Decoding](19-evolutionary.md) | ACL 2026 | 从估计分布错位解释算法瓶颈 |
| 20 | [Creator–Editor / RACE](20-dual-roles.md) | ACL 2026 | 从真实流程改写分类对象 |
| 21 | [Lying with Truths](21-lying-truths.md) | ACL 2026 | 用威胁模型对比建立新问题 |
| 22 | [Lychee-FD](22-lychee-fd.md) | ACL 2026 | 两个诊断对应两个设计 |
| 23 | [Mind the (DH) Gap](23-dh-gap.md) | ACL 2026 | 借用成熟受控范式研究新对象 |
| 24 | [MediEval](24-medieval.md) | ACL 2026 | 将被混为一谈的能力拆成坐标轴 |
| 25 | [PALU](25-palu.md) | ACL 2026 | 把干预范围作为研究对象 |
| 26 | [GeoRA](26-geora.md) | ACL 2026 | 目标优化机制与实现效率双约束 |
| 27 | [CURE](27-cure.md) | ACL 2026 | 从部署时闭环反推训练能力 |
| 28 | [Forms–Meanings Systematicity](28-forms-meanings.md) | ACL 2026 | 连接两种已有解释框架 |
| 29 | [STEER](29-steer.md) | ACL 2026 | 统一解释既有干预再导出方法 |
| 30 | [GISP](30-gisp.md) | ACL 2026 | 从优化目标与真实任务错位切入 |
| 31 | [PolyGloss](31-polygloss.md) | ACL 2026 | 以使用者反馈组织贡献清单 |
| 32 | [CAR-bench](32-car-bench.md) | ACL 2026 | 把不可完成与不确定纳入任务定义 |
| 33 | [ViLL-E](33-vill-e.md) | ACL 2026 | 用能力版图提出统一需求 |
| 34 | [CxMP](34-cxmp.md) | ACL 2026 | 让语言理论决定控制变量 |
| 35 | [CIG](35-cig.md) | ACL 2026 | 先验证构念再自动化测量 |


## 读完后的共同观察

下面是对这批材料的结构分析，没有用获奖样本推断录用的因果规律或必要条件。

1. **强主线容纳多项贡献。** D4RT、ReconVLA、PlantTraitNet、PolyGloss 都把方法、资源或验证拆成多项贡献，再连接到同一个问题。“只准 claim 一件事”不是原文的共同格式。
2. **真正有区分度的经常是比较方式。** Succinctness 换理论比较尺度；MediEval 拆开两种正确性；LLMs Get Lost 改信息呈现协议。研究价值可以来自更准确的问题与测量。
3. **引言不一定从惊艳句子开始。** 不少论文仍从领域背景写起；可学习的转折在于迅速收窄到具体缺口，并让后续设计回应该缺口。
4. **组件数不决定贡献是否清楚。** ViLL-E 有三阶段训练，LLM2CLIP 解决两项整合障碍，Lychee-FD 用两项设计回应两种诊断。要解释必要性，并验证预算与效果。
5. **关键图承担的职责不同。** 有的先展示例子，有的画能力缺口或质量—成本权衡，再有架构图。理论论文也可以依赖定义、定理和反例组织论证。
6. **结果章节适合按问题组织。** ReconVLA 直接把研究问题对应到实验小节；Global Opinion、CIG 等也以研究轴或验证阶段串起证据，而不只是模型排名。

## 按需求选案例

- 想从失败现象找可检验解释：[Lychee-FD](22-lychee-fd.md)、[STEER](29-steer.md)、[The Flexibility Trap](05-flexibility.md)。同时检查因果用语是否超过干预证据。
- 想把认知启发落成变量：[Resource-Rational Encoding](16-memory.md)、[Local Attention Expressivity](17-local-attention.md)。保留形式或认知模型的适用条件。
- 想设计新评测：[LLMs Get Lost](04-lost.md)、[MediEval](24-medieval.md)、[CxMP](34-cxmp.md)、[CIG](35-cig.md)。先学能力定义与受控比较。
- 想研究 LLM 后训练：[GeoRA](26-geora.md)、[CURE](27-cure.md)、[STEER](29-steer.md)、[PALU](25-palu.md)。分别关注更新几何、闭环能力、优化动态和干预范围。
- 想学应用约束如何改变方法：[CaDyT](09-cadyt.md)、[GRAM](14-gram.md)、[PolyGloss](31-polygloss.md)、[CAR-bench](32-car-bench.md)。先确认约束确实存在。
- 想学理论论文的主线：[Succinctness](03-succinct.md)、[High-Accuracy Sampling](06-sampling.md)、[Model Change](08-model-change.md)。先明确对象、条件和比较尺度。

## 来源范围说明

官方入口：[CVPR](https://cvpr.thecvf.com/Conferences/2026/News/Best_Papers)、[ECCV](https://eccv.ecva.net/Conferences/2026/AcceptedPapers)、[ICLR](https://blog.iclr.cc/2026/04/23/announcing-the-iclr-2026-outstanding-papers/)、[ICML](https://blog.icml.cc/2026/07/05/announcing-the-icml-2026-awards/)、[AAAI](https://aaai.org/about-aaai/aaai-awards/aaai-conference-paper-awards-and-recognition/)、[ACL](https://2026.aclweb.org/program/best_papers/)。官方奖项页只支持身份与奖项核对；逐篇结构分析依据各卡片的原文，不把二手文章的概括当作技术证据。
