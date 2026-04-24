# 可直接用 PlantUML 的论文图片清单

日期：2026-04-13

## 可以直接给出 PlantUML 的图

- 图 2.1 用户与组织管理用例图
  源文件：[fig2-1-user-org-usecase.puml](/home/lilu/Graduatin/image/chap02/fig2-1-user-org-usecase.puml)
- 图 2.2 文档接入与处理用例图
  源文件：[fig2-2-document-ingestion-usecase.puml](/home/lilu/Graduatin/image/chap02/fig2-2-document-ingestion-usecase.puml)
- 图 2.3 检索与问答用例图
  源文件：[fig2-3-retrieval-qa-usecase.puml](/home/lilu/Graduatin/image/chap02/fig2-3-retrieval-qa-usecase.puml)
- 图 2.4 会话交互与文档服务用例图
  源文件：[fig2-4-session-doc-service-usecase.puml](/home/lilu/Graduatin/image/chap02/fig2-4-session-doc-service-usecase.puml)
- 图 3.1 系统主处理链路示意图
  源文件：[fig3-1-design-overview-swimlane.puml](/home/lilu/Graduatin/image/chap03/fig3-1-design-overview-swimlane.puml)
- 图 3.2 系统总体架构图
  源文件：[fig3-2-system-architecture-layered.puml](/home/lilu/Graduatin/image/chap03/fig3-2-system-architecture-layered.puml)
- 图 3.3 权限映射关系图
  源文件：[fig3-3-permission-mapping.puml](/home/lilu/Graduatin/image/chap03/fig3-3-permission-mapping.puml)
- 图 3.4 权限判定与数据隔离流程图
  源文件：[fig3-4-permission-decision-flow.puml](/home/lilu/Graduatin/image/chap03/fig3-4-permission-decision-flow.puml)
- 图 3.5 文档处理全生命周期设计图
  源文件：[fig3-5-document-lifecycle.puml](/home/lilu/Graduatin/image/chap03/fig3-5-document-lifecycle.puml)
- 图 3.6 混合检索与安全过滤设计图
  源文件：[fig3-6-hybrid-retrieval-design.puml](/home/lilu/Graduatin/image/chap03/fig3-6-hybrid-retrieval-design.puml)
- Prompt 分层装配示意图
  源文件：[fig3-6-prompt-layering.puml](/home/lilu/Graduatin/image/chap03/fig3-6-prompt-layering.puml)
- 图 3.7 会话状态控制与生成编排设计图
  源文件：[fig3-7-generation-orchestration.puml](/home/lilu/Graduatin/image/chap03/fig3-7-generation-orchestration.puml)
- 图 3.8 系统 E-R 图
  源文件：[fig3-8-er-diagram.puml](/home/lilu/Graduatin/image/chap03/fig3-8-er-diagram.puml)
  备注：可以先用 PlantUML 初稿，但如果学校要求标准 Crow's Foot 风格，建议再人工微调。
- 新增图：隐私治理链路图
  源文件：[privacy-governance-chain.puml](/home/lilu/Graduatin/image/chap03/privacy-governance-chain.puml)
- 图 4.1 安全过滤链执行关系图
  源文件：[fig4-1-security-filter-chain.puml](/home/lilu/Graduatin/image/chap04/fig4-1-security-filter-chain.puml)
- 图 4.2 组织标签授权过滤流程图
  源文件：[fig4-2-org-tag-filter-flow.puml](/home/lilu/Graduatin/image/chap04/fig4-2-org-tag-filter-flow.puml)
- 图 4.3 文件合并实现流程图
  源文件：[fig4-3-file-merge-flow.puml](/home/lilu/Graduatin/image/chap04/fig4-3-file-merge-flow.puml)

## 不建议直接用 PlantUML，建议你自己画或基于截图人工处理的图

- 图 4.4 用户与组织管理界面展示
  原因：这类图本质上是界面截图拼版，重点在裁切、放大、编号标注和视觉对齐，不是结构关系图。
- 图 4.5 知识库与会话交互界面展示
  原因：需要保留真实界面视觉和交互区域，适合在 Figma、PPT、draw.io 或截图标注工具中完成。
- 图 4.6 历史记录与结果追溯界面展示
  原因：需要做局部放大、来源高亮和阅读路径标注，PlantUML 不适合处理这类视觉细节。

## 可用但最好人工再润色的图

- 图 3.2 系统总体架构图
  PlantUML 可以出结构正确版，但如果你想要更均衡的层间留白、分组视觉和论文级版式，后续最好在 draw.io 再微调一次。
- 图 3.8 系统 E-R 图
  PlantUML 可以表达结构和字段关系，但若学院强制要求数据库建模工具风格或 Crow's Foot 标准外观，建议按现有字段关系手工重画。
