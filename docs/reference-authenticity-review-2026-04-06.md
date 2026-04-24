# 论文参考文献真实性复核报告

复核日期：2026-04-06

复核范围：`main.bbl` 中实际进入论文文后参考文献表的 24 条参考文献。

复核方法：

- 优先核对 DOI 对应的官方落地页或 Crossref 元数据。
- ACL / NeurIPS / ICLR / NIST 等会议或机构文献，优先核对官网页面。
- 中文法规、标准与中文期刊文章，优先核对政府网站、国家标准全文公开系统和期刊官网页面。

## 结论概览

- 已证实真实存在：24/24。
- 未发现“标题、作者、刊名/会议名均无法对应官方来源”的明显伪造条目。
- 建议进一步规范或留痕说明的条目：6 条。

## 建议重点关注

1. `robertson2009bm25`
   当前条目写作 `2009, 3(4): 333-389`。这与 IR Anthology 等文章级来源一致；但 DOI `10.1561/1500000019` 在部分解析链路中会跳到整册级页面，容易看到 `4(1-2): 1-174` 一类元数据。该条不判定为假，但答辩或查重抽检时建议保留文章级来源作为佐证。
2. `policyrag2025`
   期刊官网页面可核实题名、作者、卷期页码与 DOI，真实性没有问题；但该 DOI 通过 Crossref API 返回 `404`，因此不能仅凭 Crossref 未收录就判定为假文献。
3. `asai2024selfrag`
   官方 OpenReview 页面存在访问限制，直接抓取时可能返回拒绝访问；建议以 ICLR 2024 proceedings 页面作为备查链接。
4. `ni2025trustworthyrag`
   该条为 arXiv 预印本，真实存在，但不是正式期刊或会议终版。若学院要求优先引用正式发表版本，建议后续再确认是否已有可替换的正式版本。
5. `genai_measures2023`
   政府官网可核实真实性；当前条目只有年份，若按规范严格著录，可补充发布日期等信息。
6. `gbt22239_2019`
   国家标准官网可核实真实性；当前条目只有年份，若按规范严格著录，可补充发布日期 `2019-05-10`、实施日期 `2019-12-01` 等信息。

## 全量复核结果

| Key | 复核结论 | 说明 | 官方或权威来源 |
| --- | --- | --- | --- |
| `feuerriegel2024generative` | 已核实 | 题名、刊名、年份、卷期页码一致 | https://doi.org/10.1007/s12599-023-00834-7 |
| `zhang2025hallucination` | 已核实 | 题名、刊名、年份、卷期页码一致 | https://doi.org/10.1145/3703155 |
| `genai_measures2023` | 已核实 | 政府官网可核实题名与发布主体；建议补充发布日期 | https://www.gov.cn/zhengce/zhengceku/202307/content_6891752.htm |
| `oleary2024km` | 已核实 | 题名、刊名、年份、卷期页码一致 | https://doi.org/10.1109/MIS.2024.3366648 |
| `salton1975vectorspace` | 已核实 | 题名、刊名、年份、卷期页码一致 | https://doi.org/10.1145/361219.361220 |
| `karpukhin2020dpr` | 已核实 | ACL Anthology 可核实会议名、年份与页码 | https://aclanthology.org/2020.emnlp-main.550/ |
| `robertson2009bm25` | 已核实，需说明 | 当前 `3(4):333-389` 与文章级来源一致；DOI 解析链路可能出现整册级元数据 | https://ir.webis.de/anthology/2009.ftir_journal-ir0anthology0volumeA3A4.0/ |
| `johnson2021faiss` | 已核实 | 题名、刊名、年份、卷期页码一致 | https://doi.org/10.1109/TBDATA.2019.2921572 |
| `lewis2020rag` | 已核实 | NeurIPS 官网可核实题名与年份 | https://proceedings.neurips.cc/paper/2020/hash/6b493230205f780e1bc26945df7481e5-Abstract.html |
| `gao2023hyde` | 已核实 | ACL Anthology 可核实会议名、年份与页码 | https://aclanthology.org/2023.acl-long.99/ |
| `jiang2023flare` | 已核实 | ACL Anthology 可核实会议名、年份与页码 | https://aclanthology.org/2023.emnlp-main.495/ |
| `asai2024selfrag` | 已核实，建议保留 proceedings 链接 | OpenReview 直连可能受限，ICLR 2024 官方 proceedings 可核实题名与年份 | https://proceedings.iclr.cc/paper_files/paper/2024/hash/25f7be9694d7b32d5cc670927b8091e1-Abstract-Conference.html |
| `rahman2025comparative` | 已核实 | 题名、刊名、年份、卷号与文章号一致 | https://doi.org/10.1109/ACCESS.2025.3632404 |
| `oleary2024enterprise` | 已核实 | 题名、刊名、年份、卷期页码一致 | https://doi.org/10.1109/MIS.2023.3345591 |
| `wang2025buildingkm` | 已核实 | 题名、刊名、年份、卷号与文章号一致 | https://doi.org/10.1016/j.jobe.2025.112189 |
| `rubio2025industrialkm` | 已核实 | 题名、刊名、年份、卷号与文章号一致 | https://doi.org/10.1016/j.csi.2025.103995 |
| `policyrag2025` | 已核实，需说明 | 期刊官网可核实题名、作者、卷期页码与 DOI；Crossref API 未收录 | https://manu44.magtech.com.cn/Jwk_infotech_wk3/CN/10.11925/infotech.2096-3467.2024.0670 |
| `zhang2024raglab` | 已核实 | ACL Anthology 可核实会议名、年份与页码 | https://aclanthology.org/2024.emnlp-demo.43/ |
| `zhang2025flexrag` | 已核实 | ACL Anthology 可核实会议名、年份与页码 | https://aclanthology.org/2025.acl-demo.60/ |
| `vogelsang2025ragva` | 已核实 | 题名、刊名、年份、卷号与文章号一致 | https://doi.org/10.1016/j.jss.2025.112436 |
| `ni2025trustworthyrag` | 已核实，属预印本 | arXiv 页面可核实题名与年份；尚属预印本 | https://arxiv.org/abs/2502.06872 |
| `liu2024lostmiddle` | 已核实 | 题名、刊名、年份、卷号与页码一致 | https://doi.org/10.1162/tacl_a_00638 |
| `sandhu2000nist` | 已核实 | NIST 官方页面与 ACM DOI 均可核实 | https://www.nist.gov/publications/nist-model-role-based-access-control-towards-unified-standard |
| `gbt22239_2019` | 已核实 | 国家标准官网可核实标准号与标准名称；建议补充发布日期与实施日期 | https://openstd.samr.gov.cn/bzgk/gb/newGbInfo?hcno=BAFB47E8874764186BDB7865E8344DAF |

## 额外说明

- 若只从 BibTeX key 命名看，个别条目如 `zhang2025hallucination`、`rahman2025comparative`、`rubio2025industrialkm`、`vogelsang2025ragva` 与首作者姓氏并不一致，但这属于条目标识命名问题，不影响编译后的参考文献真实性。
- 当前复核重点是“文献是否真实存在、题名与来源是否可对应、核心著录项是否匹配”。若你下一步要做的是送审前格式统一，还可以继续对 GB/T 7714 的文献类型标识、发布日期、访问日期、预印本标注等做一轮格式性修订。
