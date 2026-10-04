---
name: qidao-medlit-search
description: "中英双轨医学文献检索技能，用于检索循证医学与现代中医文献（PubMed、Google Scholar、Cochrane、CNKI、万方、维普等），按证据等级分级并产出结构化成果。当用户需要为炁道智慧体系、中医导引/气功/经络/穴位/推拿相关主张搜集资料、核验临床经验与文献依据、搭建循证论证框架，或把检索结果落成体系文档（证据分级摘要 / 结构化文献清单 / 体系落地文档）时使用。"
---

# 炁道医学文献检索（Qidao Medlit Search）

## 概览

中英双轨检索循证医学与现代中医文献，按证据等级分级，输出可直接用于"炁道智慧体系"论证、教学与落地的结构化成果。核心是**核验临床经验 → 追溯文献 → 证据分级 → 体系落地**的闭环。

## 工作流

### 第 1 步：解析检索需求

先把用户的模糊请求拆成**可检索的主题与子问题**，并判定本次属于哪类任务：

- **核验型**：某个临床经验/主张（如"膏肓穴刺激与迷走神经的关系"）是否站得住 → 需要 RCT / Meta / 机制研究去验证，输出带证据等级的判断。
- **收集型**：为体系某层（理论/机制/实践/证据）系统性搜集资料 → 输出结构化文献清单。
- **落地型**：把检索结果整合进炁道智慧体系框架文档 → 输出体系落地文档。

用 PICO 思想拆解每个子问题：人群（P）、干预（I，如某种导引/取穴/手法）、对照（C）、结局（O，如心率变异性、疼痛评分）。若缺关键维度，先确认再检索。

### 第 2 步：选择来源与工具（中英双轨）

按子问题语种与证据类型选来源，详见 [references/sources.md](references/sources.md)。原则：

- 英文循证（RCT/Meta/机制）：优先 `scholar_search`、`general_search` 定位 PubMed / Cochrane / Google Scholar 条目，必要时用 `web_fetch` 精读原文。
- 中文文献（CNKI / 万方 / 维普 / 古籍）：用 `general_search` + `web_fetch` 检索摘要与条目；需全文或封闭站内检索时，用浏览器访问对应平台。
- 指南 / 药物 / 医院 / 医生类：用 `seed_medical_search`。
- 每个来源记下**来源名、年份、标题、链接**，保持可追溯。

### 第 3 步：执行检索（多关键词 × 中英双轨）

- 每个子问题至少用 **2–3 组关键词**并行检索（中英各一组），英文补 MeSH/同义词（如 qigong / daoyin / meridian / acupoint / vagus nerve / myofascial）。
- 指定合理时间窗（机制与循证优先近 5–10 年，经典理论不限年代）。
- 一次并行调用不超过 3 个 query；命中后按需 `web_fetch` 精读摘要。
- 检索词示例与体系各层的落地关键词见 [references/qidao-framework.md](references/qidao-framework.md)。

### 第 4 步：证据分级

每一条证据按 [references/evidence-grading.md](references/evidence-grading.md) 标注等级（系统综述/Meta → RCT → 队列/病例对照 → 临床观察/专家共识 → 古籍/名老中医经验）。**区分"已查证"与"一方称"**：RCT/Meta 验证过的结论明确写"经 RCT 验证"；仅古籍/临床观察支撑的写"据古籍/临床观察，待 RCT 验证"。

### 第 5 步：产出交付（按需选择形态）

- **证据分级检索摘要**：按主题聚合，每个结论标注证据等级 + 来源 + 年份，适合体系论证与教学引用。
- **结构化文献清单**：Markdown 表格，字段含 序号/标题/作者年份/来源库/证据等级/链接/一句话要点，便于批量归档。
- **体系落地文档**：按 [references/qidao-framework.md](references/qidao-framework.md) 四层结构（理论层→机制层→实践层→证据层）整合检索结果，产出完整体系文档（Word / 飞书 / HTML 按需）。

交付前回读：确认每条结论有来源、证据等级标注正确、链接可访问；汇总数字用工具核算。

## 检索主题分层框架

"炁道智慧体系"的四层检索与落地结构见 [references/qidao-framework.md](references/qidao-framework.md)。检索前先确定命中的层，再取该层的关键词模板与落地动作。

## Resources

- `references/sources.md` — 中英信源与工具映射表。
- `references/evidence-grading.md` — 现代循证 + 中医古籍证据分级规范。
- `references/qidao-framework.md` — 炁道智慧体系四层框架：检索关键词模板与体系落地动作。
