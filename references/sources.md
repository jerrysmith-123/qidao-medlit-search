# 中英信源与工具映射

按"语种 × 证据类型"选择来源与工具。每个来源产出条目时必须带**来源名、年份、标题、链接**，保持可追溯。

## 英文循证源

| 来源 | 覆盖 | 推荐工具 | 说明 |
|---|---|---|---|
| PubMed (MEDLINE) | 现代医学、针灸、穴位、导引机制、RCT、系统综述 | `scholar_search` / `general_search`，需精读时 `web_fetch`（pubmed.ncbi.nlm.nih.gov） | 首选英文循证；注意 MeSH 与同义词扩展 |
| Cochrane Library | 系统综述（含针灸等干预） | `general_search` 定位条目 + `web_fetch` | 证据等级最高的干预性结论来源 |
| Google Scholar | 泛检索、引文追踪 | `scholar_search` / `general_search` | 覆盖灰色文献与早期文献，注意甄别期刊质量 |

## 中文文献源

| 来源 | 覆盖 | 推荐工具 | 说明 |
|---|---|---|---|
| CNKI 中国知网 | 中医导引/气功/经络/名老中医经验/学位论文 | `general_search` + `web_fetch` 摘要；需全文或站内检索时浏览器访问 cnki.net | 中文中医文献主力库 |
| 万方数据 | 期刊、学位论文、会议 | `general_search` + `web_fetch`（wanfangdata.com.cn） | 学位论文与会议文献较全 |
| 维普 | 中文期刊回溯 | `general_search` + `web_fetch`（cqvip.com） | 早期期刊回溯好 |

## 指南 / 专业条目

| 来源 | 覆盖 | 推荐工具 |
|---|---|---|
| 循证医学指南 / 诊疗指南 | 疾病指南、专家共识 | `seed_medical_search`（filetype:guideline） |
| 药物信息 | 用药、说明书 | `seed_medical_search`（filetype:drug） |
| 医院 / 医生 | 就医辅助 | `seed_medical_search`（filetype:hospital / doctor） |

## 古籍 / 经典

| 来源 | 覆盖 | 推荐工具 | 说明 |
|---|---|---|---|
| 《黄帝内经》《难经》《针灸大成》等经典 | 炁、经络、导引、脏腑理论 | `general_search` 检索条文与校注 | 属证据等级 5，作为理论依据而非 RCT 结论 |

## 封闭平台 / 全文获取

中文库（CNKI 等）需登录或全文时，用浏览器（browser-use）进入平台检索、下载并提取可见内容；外文库全文优先 `web_fetch`，受阻时再考虑浏览器。

## 检索纪律

- 一次并行 query 不超过 3 个；不重复检索同一信息。
- 命中条目标注证据等级后再进入产出；证据不足就补检索，不靠"应该/大概"支撑结论。
