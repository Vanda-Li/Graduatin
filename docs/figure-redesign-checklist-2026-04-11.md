# 论文图片重绘与重构清单

日期：2026-04-11

适用对象：当前毕业论文《基于RAG技术的智能问答系统设计与实现》中的第 2 章、第 3 章、第 4 章图片

对应工程目录：

- 论文正文：[main.tex](/home/lilu/Graduatin/main.tex)
- 需求分析：[docs/chap02.tex](/home/lilu/Graduatin/docs/chap02.tex)
- 系统设计：[docs/chap03.tex](/home/lilu/Graduatin/docs/chap03.tex)
- 系统实现：[docs/chap04.tex](/home/lilu/Graduatin/docs/chap04.tex)
- 图片目录：[image/chap02](/home/lilu/Graduatin/image/chap02)
- 图片目录：[image/chap03](/home/lilu/Graduatin/image/chap03)
- 图片目录：[image/chap04](/home/lilu/Graduatin/image/chap04)

---

## 1. 文档目标

这份清单的目标不是对现有图片做零散修补，而是把论文中的图片体系重构为一套与正文一致、图种统一、层次清晰、版式可读的正式论文配图方案。

本清单重点回答 6 个问题：

1. 每张图当前的问题是什么。
2. 哪些内容应当保留。
3. 哪些内容应当删除。
4. 应当如何重构。
5. 新图应包含哪些元素、采用怎样的布局。
6. 可以参考哪些论文中的图，以及参考的是哪一幅图。

---

## 2. 总体判断

当前图片存在三类共性问题：

1. 章节层次混用。
   第 2 章需求图混入了实现层和外部系统细节；第 3 章设计图中又直接出现了实现类名和调用链；第 4 章个别实现图没有把正文中强调的关键分支画出来。

2. 语义和正文不完全一致。
   最明显的是权限模型、公开属性表达、文档与组织标签关系、多轮会话控制逻辑、Prompt 装配和隐私治理这几部分。

3. 图面风格与论文体例不统一。
   当前图片中同时存在 UML 用例图、类流程图、产品海报式架构图、开发时序图、整屏截图缩略图；颜色语义、字体、箭头和注释风格也不统一。

---

## 3. 统一重绘原则

### 3.1 章节边界

- 第 2 章只画需求，不画实现。
- 第 3 章只画设计，不画类名和代码名。
- 第 4 章只画实现，不再重复需求定义。

### 3.2 图种边界

- 第 2 章统一为 UML 用例图。
- 第 3 章统一为架构图、活动图、控制流图、E-R 图。
- 第 4 章统一为实现流程图、时序图、界面标注图。

### 3.3 命名边界

- 图中优先使用中文术语。
- 必要时在括号中补英文，例如：`组织标签授权过滤流程图 (OrgTag Authorization Flow)`。
- 不要混用产品页面文案式英文和论文化中文。

### 3.4 版式边界

- 正文落地后图中文字不低于 8pt。
- 优先导出 `PDF/SVG` 等矢量格式。
- 尽量避免继续使用低分辨率 `PNG` 作为正式论文图。
- 不要使用黄色便签、营销卡片式阴影、渐变海报中心圆盘等会破坏论文风格的视觉元素。

### 3.5 颜色语义

建议统一如下：

- 蓝色：身份与权限
- 绿色：文档接入与入库
- 橙色：检索与排序
- 紫色：会话与生成
- 红色：隐私治理与安全控制
- 灰色：存储与基础设施

### 3.6 绘图工具建议

- draw.io / diagrams.net
- ProcessOn
- Figma
- PlantUML
- Mermaid

其中：

- UML 用例图和活动图适合用 PlantUML 或 draw.io
- 架构图、Prompt 分层图适合 draw.io 或 Figma
- E-R 图适合 draw.io 或数据库建模工具导出

---

## 4. 优先级排序

### 4.1 第一优先级，必须重画

- 图 2.1 用户与组织管理用例图
- 图 2.2 文档接入与处理用例图
- 图 2.3 检索模块用例图
- 图 2.4 会话交互用例图
- 图 3.2 系统总体架构图
- 图 3.3 权限映射关系图
- 图 3.4 权限判定与数据隔离流程图
- 图 3.5 文档处理全生命周期设计图
- 图 3.6 混合检索与安全过滤设计图
- 图 3.7 会话状态控制与生成编排设计图
- 图 4.3 文件合并实现流程图

### 4.2 第二优先级，中等改造

- 图 3.1 系统主处理链路示意图
- 图 3.8 系统 E-R 图
- 图 4.1 安全过滤链执行关系图
- 图 4.2 组织标签授权过滤流程图

### 4.3 第三优先级，以裁切和标注优化为主

- 图 4.4 用户与组织管理界面展示
- 图 4.5 知识库与会话交互界面展示
- 图 4.6 历史记录与结果追溯界面展示

### 4.4 建议新增

- Prompt 分层装配示意图
- 隐私治理链路图

---

## 5. 逐图重构清单

## 5.1 图 2.1 用户与组织管理用例图

当前图片：

- [image/chap02/user.png](/home/lilu/Graduatin/image/chap02/user.png)
- 对应正文：[docs/chap02.tex:21](/home/lilu/Graduatin/docs/chap02.tex#L21)

### 当前问题

- 用例图中混入了 `RAG 智能检索对话` 和 `大模型 API 服务`，越过了“用户与组织管理”的模块边界。
- 正文需求中的 `登出`、`当前用户信息查询`、`切换主组织` 没有体现。
- 图中对“管理员”和“普通用户”的能力边界表达不够规范。

### 应保留

- 普通用户
- 管理员
- 用户注册
- 用户登录
- 组织标签管理
- 用户管理
- 用户组织授权
- 私人组织标签初始化

### 应删除

- 关联模块用例
- `RAG 智能检索对话`
- `大模型 API 服务`
- 所有跨模块调用箭头

### 应补充

- 用户登出
- 当前用户信息查询
- 切换主组织

### 重构方式

重构为标准 UML 用例图，系统边界只保留“用户与组织管理模块”，不出现其他模块和系统服务。

### 新图元素

- Actor：普通用户、管理员
- Use Case：注册、登录、登出、当前用户信息查询、切换主组织、组织标签管理、用户管理、用户访问范围配置、私人组织标签初始化

### 新图关系

- `注册 <<include>> 私人组织标签初始化`
- 管理员通过 UML 泛化继承普通用户的基础能力

### 推荐布局

- 左侧纵向放 Actor
- 右侧放系统边界框
- 边界内部上半部分放身份相关用例
- 边界内部下半部分放组织上下文相关用例

### 文字示意图

```text
[管理员] ----> (组织标签管理)
[管理员] ----> (用户管理)
[管理员] ----> (用户访问范围配置)

[普通用户] ----> (注册)
[普通用户] ----> (登录)
[普通用户] ----> (登出)
[普通用户] ----> (当前用户信息查询)
[普通用户] ----> (切换主组织)

(注册) ..<<include>>..> (私人组织标签初始化)
```

### 可参考图源

- NIST RBAC 论文中的基础 RBAC 关系画法，可参考角色与主体的规范连接方式。
  链接：https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=916402
  可参考图：Figure 1, Figure 2

---

## 5.2 图 2.2 文档接入与处理用例图

当前图片：

- [image/chap02/text.png](/home/lilu/Graduatin/image/chap02/text.png)
- 对应正文：[docs/chap02.tex:40](/home/lilu/Graduatin/docs/chap02.tex#L40)

### 当前问题

- 正文中要求支持上传状态和处理阶段状态查询，但图中没有明确体现。
- 正文中没有定义“部门管理员”这一角色，图中却引入了额外 Actor。
- 图中出现 `系统后台服务` 和 `向量数据库` 这样的实现层参与者，不符合第 2 章需求图定位。

### 应保留

- 上传文档
- 删除文档
- 分片上传与断点续传
- 文档解析
- 内容清洗与分段
- 文本向量化
- 持久化存储

### 应删除

- 部门管理员
- 系统后台服务
- 向量数据库

### 应补充

- 格式/大小/内容合法性校验
- 合并完整性校验
- 查询上传状态
- 查询处理状态
- 异步入库

### 重构方式

不要再把图画成“系统内部流水线可视化图”，而应画成“用户能触发和查询哪些能力”的 UML 用例图。

### 新图元素

- Actor：普通用户
- Use Case：上传文档、删除文档、查询上传状态、查询处理状态、分片上传与断点续传、异步入库、格式与内容校验、完整性校验

### 新图关系

- `上传文档 <<include>> 格式与内容校验`
- `上传文档 <<include>> 分片上传与断点续传`
- `分片上传与断点续传 <<include>> 完整性校验`
- `上传文档` 之后触发 `异步入库`

### 推荐布局

- 左侧一个 Actor
- 边界内部左列放“上传接入”
- 边界内部右列放“状态与删除”

### 文字示意图

```text
[普通用户] ----> (上传文档)
[普通用户] ----> (删除文档)
[普通用户] ----> (查询上传状态)
[普通用户] ----> (查询处理状态)

(上传文档) ..<<include>>..> (格式与内容校验)
(上传文档) ..<<include>>..> (分片上传与断点续传)
(分片上传与断点续传) ..<<include>>..> (完整性校验)
(上传文档) ----> (异步入库)
```

### 可参考图源

- Lewis et al., RAG 论文的 Figure 1 可参考“检索和生成以外置组件串接”的抽象表达方式，但不要照抄其生成模型结构。
  链接：https://ar5iv.labs.arxiv.org/html/2005.11401v4
  可参考图：Figure 1

---

## 5.3 图 2.3 检索与问答用例图

当前图片：

- [image/chap02/Retrieval.png](/home/lilu/Graduatin/image/chap02/Retrieval.png)
- 对应正文：[docs/chap02.tex:60](/home/lilu/Graduatin/docs/chap02.tex#L60)

### 当前问题

- 图题为“检索模块用例图”，但正文小节是“检索与问答需求”，范围偏窄。
- 图中大量出现 BM25、Top-K、向量数据库、全文检索引擎等实现信息，不符合需求图定位。
- 正文要求“生成带来源依据的回答”和“多轮对话中每轮检索独立权限过滤”，图中没有完整体现。

### 应保留

- 自然语言检索
- 权限过滤
- 排序优化

### 应删除

- BM25
- Top-K
- 向量数据库
- 全文检索引擎
- 黄底说明便签
- 任何具体技术实现名词

### 应补充

- 生成带来源依据的回答
- 多轮追问
- 来源回溯
- 每轮检索独立权限过滤

### 重构方式

重构为“检索与问答用例图”，突出用户可见能力，而非后端技术组件。

### 新图元素

- Actor：用户
- Use Case：知识检索、权限过滤、结果排序优化、生成回答、来源回溯、多轮追问

### 新图关系

- `知识问答 <<include>> 知识检索`
- `知识检索 <<include>> 权限过滤`
- `知识检索 <<include>> 排序优化`
- `知识问答 <<include>> 来源回溯`
- `多轮追问 <<extend>> 知识问答`

### 推荐布局

- 左边用户
- 系统边界内部上层为检索
- 系统边界内部下层为回答生成

### 文字示意图

```text
[用户] ----> (知识问答)
[用户] ----> (多轮追问)

(知识问答) ..<<include>>..> (知识检索)
(知识检索) ..<<include>>..> (权限过滤)
(知识检索) ..<<include>>..> (排序优化)
(知识问答) ..<<include>>..> (来源回溯)
(多轮追问) ..<<extend>>..> (知识问答)
```

### 可参考图源

- Lewis et al., Figure 1，适合参考“检索器 + 生成器”的主链拆分方式。
  链接：https://ar5iv.labs.arxiv.org/html/2005.11401v4
  可参考图：Figure 1

---

## 5.4 图 2.4 会话交互与文档服务用例图

当前图片：

- [image/chap02/inter.png](/home/lilu/Graduatin/image/chap02/inter.png)
- 对应正文：[docs/chap02.tex:80](/home/lilu/Graduatin/docs/chap02.tex#L80)

### 当前问题

- 图内容几乎全部落在“会话生命周期管理”，没有覆盖“文档服务”。
- 正文中提到的文件列表、文本预览、带时效性的安全下载链接没有出现。
- 图中出现 `会话管理服务` 和 `读取缓存状态` 等实现性描述。

### 应保留

- 开启新会话
- 历史会话追溯
- 多轮对话连续性维护

### 应删除

- 会话管理服务
- 读取缓存状态
- 持久化检索

### 应补充

- 回答实时增量呈现
- 回答完成状态返回
- 分页读取历史
- 查看文件列表
- 预览文本内容
- 生成安全下载链接

### 重构方式

重构为“会话交互 + 文档服务”的并列用例图，而不是单一会话管理图。

### 新图元素

- Actor：普通用户
- Use Case：开启新会话、实时增量呈现、返回完成状态、历史会话回读、分页读取历史、查看文件列表、预览文本、生成下载链接

### 推荐布局

- 系统边界内部左右双栏
- 左栏为“会话交互”
- 右栏为“文档服务”

### 文字示意图

```text
[普通用户] ----> (开启新会话)
[普通用户] ----> (历史会话回读)
[普通用户] ----> (分页读取历史)
[普通用户] ----> (查看文件列表)
[普通用户] ----> (预览文本)
[普通用户] ----> (生成安全下载链接)

(开启新会话) ..<<include>>..> (实时增量呈现)
(开启新会话) ..<<include>>..> (返回完成状态)
```

### 可参考图源

- 暂无特别适合直接照搬的论文用例图。
- 建议按正文需求独立绘制，不必硬套外文论文图形。

---

## 5.5 图 3.1 系统主处理链路示意图

当前图片：

- [image/chap03/design-overview.png](/home/lilu/Graduatin/image/chap03/design-overview.png)
- 对应正文：[docs/chap03.tex:5](/home/lilu/Graduatin/docs/chap03.tex#L5)

### 当前问题

- 当前图能表达“双链路”的大意，但没有把正文强调的三条设计边界明确可视化。
- `A/B/C` 类局部标记偏草图感。

### 应保留

- 离线入库链
- 在线问答链
- 上传/问题输入/系统响应三类入口出口

### 应删除

- A/B/C 风格小标签
- 过于松散的展示稿式图标摆放

### 应补充

- 上传确认与后台处理解耦边界
- 权限过滤前置边界
- Chat Provider / Embedding Provider 抽象边界

### 重构方式

改为“双泳道主链路图”。

### 新图元素

- 离线泳道：上传确认、异步调度、解析、分块、向量化、索引写入、可检索
- 在线泳道：问题输入、查询规范化、混合检索、权限过滤、Prompt 装配、生成、流式返回
- 共享边界：Embedding Provider、Chat Provider

### 推荐布局

- 上下双泳道横向布局
- 底部单独挂两个 Provider 抽象框

### 文字示意图

```text
离线入库链:
上传确认 -> 异步调度 -> 解析 -> 分块 -> 向量化 -> 索引写入 -> Ready

在线问答链:
问题输入 -> 查询规范化 -> 混合检索 -> 权限过滤 -> Prompt装配 -> 生成 -> 流式返回

共享边界:
Embedding Provider
Chat Provider
```

### 可参考图源

- Lewis et al., Figure 1
  链接：https://ar5iv.labs.arxiv.org/html/2005.11401v4
  参考点：Retriever 与 Generator 的主链骨架

---

## 5.6 图 3.2 系统总体架构图

当前图片：

- [image/chap03/structure.png](/home/lilu/Graduatin/image/chap03/structure.png)
- 对应正文：[docs/chap03.tex:23](/home/lilu/Graduatin/docs/chap03.tex#L23)

### 当前问题

- 中心 `AI/LLM Core` 的海报式主视觉不符合论文化表达。
- 没有把正文强调的 Redis、Kafka、MySQL、MinIO、Elasticsearch、Provider 抽象边界明确表现出来。
- 用词偏产品宣传化，如“本地知识库集成”“大语言模型集成”。

### 应保留

- 前后端分层
- 用户层
- 业务服务层
- 持久化/基础设施层

### 应删除

- AI/LLM Core 中心圆盘式结构
- 过于抽象的产品化模块命名

### 应补充

- 前端四模块：知识库管理、聊天问答、组织标签管理、用户管理
- 后端接口层：认证、上传、检索、聊天、历史、文件
- 核心服务层：AuthZ、Ingestion、Retrieval、PromptAssembler、Conversation、Governance
- 基础设施层：MySQL、MinIO、Elasticsearch、Redis、Kafka
- 外部模型层：Chat Provider、Embedding Provider

### 重构方式

重构为严格分层架构图。

### 推荐布局

- 自上而下 5 层
- 最右侧外挂外部模型服务

### 文字示意图

```text
用户/管理员
    |
前端层
用户管理 | 组织标签 | 知识库 | 会话
    |
接口层
Auth | Upload | Search | Chat WS | History | File
    |
核心服务层
AuthZ | Upload/Merge | Ingestion | Retrieval | Prompt | Conversation | Governance
    |
基础设施层
MySQL | MinIO | Elasticsearch | Redis | Kafka

右侧外挂:
Chat Provider ------> DeepSeek
Embedding Provider -> DashScope
```

### 可参考图源

- RAGLAB 论文 Figure 1
  链接：https://ar5iv.labs.arxiv.org/html/2408.11381v2
  参考点：模块化、分层式、组件职责边界清晰

---

## 5.7 图 3.3 权限映射关系图

当前图片：

- [image/chap03/org.png](/home/lilu/Graduatin/image/chap03/org.png)
- 对应正文：[docs/chap03.tex:78](/home/lilu/Graduatin/docs/chap03.tex#L78)

### 当前问题

- 当前图将“公开访问”表达为 `Primary: PUBLIC`，与正文中的 `isPublic` 文档属性冲突。
- 图中混合了规则、样例文档和存储实例，语义层次不够纯净。

### 应保留

- role
- primaryOrg
- orgTags
- 层级继承
- 公开文档、私有文档、组织文档三类可见性来源

### 应删除

- `Primary: PUBLIC`
- 用样例文档盒子替代规则表达的方式

### 应补充

- `EffectiveTags(u)` 展开过程
- `owner OR isPublic OR orgTag in EffectiveTags(u)` 的显式规则

### 重构方式

改为“用户属性 -> 标签展开 -> 文档属性 -> 可见性规则 -> 可见范围”的映射图。

### 新图元素

- 用户属性
- 有效标签展开器
- 文档元数据
- 可见性规则
- 输出可见范围

### 推荐布局

- 左到右 4 列

### 文字示意图

```text
[用户属性]
role / userId / primaryOrg / directTags
        |
        v
[有效标签展开]
EffectiveTags(u)
        |
        +---------------------+
                              v
                     [文档元数据]
                     owner / orgTag / isPublic
                              |
                              v
                     [可见性规则]
ADMIN -> all
USER  -> owner OR isPublic OR orgTag in EffectiveTags(u)
                              |
                              v
                         Visible Scope V(u)
```

### 可参考图源

- NIST RBAC 论文 Figure 1, Figure 2
  链接：https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=916402
  参考点：用户、角色、权限之间的标准关系表达

---

## 5.8 图 3.4 权限判定与数据隔离流程图

当前图片：

- [image/chap03/acc.png](/home/lilu/Graduatin/image/chap03/acc.png)
- 对应正文：[docs/chap03.tex:99](/home/lilu/Graduatin/docs/chap03.tex#L99)

### 当前问题

- 图面过宽、判断路径回折严重，阅读成本较高。
- 图中把文件访问放行逻辑和检索候选过滤逻辑混在一起，但没有明确“检索场景是注入 filter，而不是直接放行”的区别。

### 应保留

- 认证
- 管理员全可见
- `owner / public / orgTag` 条件判定
- 检索前过滤

### 应删除

- 大范围跨页横向连线
- 语义不明确的总线框

### 应补充

- 检索场景输出为 metadata filter
- 文件访问场景输出为 allow / deny

### 重构方式

重构为竖向活动图。

### 新图元素

- 输入请求
- 认证是否通过
- 是否管理员
- 是否 owner
- 是否 isPublic
- 是否 orgTag in EffectiveTags(u)
- 文件访问 allow / deny
- 检索注入 metadata filter

### 推荐布局

- 上到下主流程
- 右侧附一个注释框说明“检索与文件服务输出不同”

### 可参考图源

- NIST RBAC 论文 Figure 6, Figure 7
  链接：https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=916402
  参考点：约束和控制点的分层表达

---

## 5.9 图 3.5 文档处理全生命周期设计图

当前图片：

- [image/chap03/text.png](/home/lilu/Graduatin/image/chap03/text.png)
- 对应正文：[docs/chap03.tex:108](/home/lilu/Graduatin/docs/chap03.tex#L108)

### 当前问题

- 标题写“全生命周期”，但图中没有体现删除生命周期。
- 没有显式表现“小文件直通”和“大文件异步”两条路径。
- 没有突出 `rawText / safeText / normalizedText` 三视图的生成位置。
- 当前竖向高柱式结构在 A4 页面中可读性一般。

### 应保留

- 分片上传
- 合并
- Kafka
- 解析
- 向量化
- 索引写入

### 应删除

- 过窄、过高的串联式柱状布局

### 应补充

- 小文件直通路径
- 大文件异步路径
- 阶段状态：UPLOADED / MERGED / PARSED / VECTORIZED / INDEXED / READY / FAILED
- 三视图：rawText / safeText / normalizedText
- 删除同步清理路径

### 重构方式

重构为横向阶段图，上方画主处理流程，下方画状态和恢复点。

### 文字示意图

```text
上传完成
   |
[文件大小 <= 阈值 ?] ---是---> 直通处理
   |否
   v
Kafka 异步调度
   |
解析原文
   |
安全治理
   +--> rawText
   +--> safeText
   +--> normalizedText
   |
语义分块 -> 向量化 -> 索引写入 -> Ready
   |
删除请求 -> 删除 DB / MinIO / ES
```

### 可参考图源

- Lewis et al., Figure 1
  链接：https://ar5iv.labs.arxiv.org/html/2005.11401v4
  参考点：主链路简洁化表达

---

## 5.10 图 3.6 混合检索与安全过滤设计图

当前图片：

- [image/chap03/retrieve.png](/home/lilu/Graduatin/image/chap03/retrieve.png)
- 对应正文：[docs/chap03.tex:128](/home/lilu/Graduatin/docs/chap03.tex#L128)

### 当前问题

- 当前图已经接近实现层时序图，出现了 `SearchController`、`EmbeddingClient` 等类名。
- 粉色横条式强调太强，不够论文化。
- 双阶段检索思想是对的，但图中“设计逻辑”没有充分从“实现调用顺序”中抽离出来。

### 应保留

- 双阶段检索
- 权限前置
- 候选重排
- Elasticsearch 内部重排窗口

### 应删除

- SearchController
- SecurityInterceptor
- EmbeddingClient
- 类名级实现细节

### 应补充

- Query Normalization
- metadata filter 显式定义
- normalizedText 参与数值/金额等词法匹配

### 重构方式

重构为“设计级两路召回 + 一路重排”的横向流程图。

### 新图元素

- Query
- Query Normalization
- Query Embedding
- Dense Recall
- Sparse Recall
- Candidate Window
- Rescore
- Top-K Evidence
- Metadata Filter

### 推荐布局

- 左到右
- 中段分叉，两路并行，右侧汇合

### 文字示意图

```text
Query
  |
Query Normalization -----> Sparse/BM25 ------------------+
  |                                                     |
  +--> Query Embedding -> Dense kNN + metadata filter --+--> Candidate Window
                                                         |
                                                         v
                                                   Rescore / BM25重排
                                                         |
                                                         v
                                                    Top-K Evidence
```

### 可参考图源

- Lewis et al., Figure 1
  链接：https://ar5iv.labs.arxiv.org/html/2005.11401v4
  参考点：Retriever 与 Generator 分工
- Question Rewriting for Conversational QA, Figure 3
  链接：https://ar5iv.labs.arxiv.org/html/2004.14652
  参考点：检索候选选择与重排分阶段表达

---

## 5.11 新增图：Prompt 分层装配示意图

对应正文：

- [docs/chap03.tex:148](/home/lilu/Graduatin/docs/chap03.tex#L148)

### 新图目的

当前正文只有表 3.2，没有图。对于读者而言，表格说明“有什么层”，但图更适合说明“这些层怎样自上而下装配成最终输入”。

### 应保留来源

- 直接以表 3.2 中 7 个逻辑层为准

### 新图元素

- assistant_rules
- conversation_policy
- memory_policy
- privacy_policy
- turn_summary
- memory_summary
- authorized_context
- empty-evidence placeholder

### 推荐布局

- 自上而下堆叠
- 最下方输出到 `LLM Input`

### 文字示意图

```text
+---------------------------+
| assistant_rules           |
+---------------------------+
| conversation_policy       |
+---------------------------+
| memory_policy             |
+---------------------------+
| privacy_policy            |
+---------------------------+
| turn_summary              |
+---------------------------+
| memory_summary            |
+---------------------------+
| authorized_context        |
| or empty-evidence placeholder |
+---------------------------+
            |
            v
         LLM Input
```

### 可参考图源

- 暂无强匹配论文图。
- 建议按本论文的表 3.2 独立绘制。

---

## 5.12 图 3.7 会话状态控制与生成编排设计图

当前图片：

- [image/chap03/generate.png](/home/lilu/Graduatin/image/chap03/generate.png)
- 对应正文：[docs/chap03.tex:177](/home/lilu/Graduatin/docs/chap03.tex#L177)

### 当前问题

- 正文的重点是轮次判断、历史注入策略、工作记忆、检索范围收缩与生成编排。
- 当前图却主要是 WebSocket 级时序图，更适合放在第 4 章。
- 图中几乎没有体现 `NEW_TOPIC / FOLLOW_UP / META / CLARIFICATION` 四类轮次。
- 图中没有体现 `SELECTIVE / RAW_RECENT / DISABLED` 三类历史注入策略。

### 应保留

- 授权检索
- Prompt 装配
- 生成
- 回写历史

### 应删除

- WebSocket 接口
- SessionManager
- HybridSearch
- PromptBuilder
- DeepSeek API

### 应补充

- 轮次分析器
- 四类轮次
- 三类历史注入策略
- 当前主题、活动文档、关键词、最近答案摘要
- 澄清分支
- 元问题分支

### 重构方式

重构为控制流图，而不是实现时序图。

### 新图元素

- 输入问题
- 轮次分析
- 历史策略选择
- 工作记忆
- 历史摘要
- 检索范围约束
- 授权检索
- Prompt 装配
- 输出复核
- 流式返回
- 更新历史与记忆

### 推荐布局

- 主流程上到下
- 右侧挂两个数据状态框：历史摘要、工作记忆

### 文字示意图

```text
用户问题
   |
轮次分析
   |-- NEW_TOPIC ------> 重置记忆 -> 全局检索
   |-- FOLLOW_UP ------> 读取历史摘要/活动文档 -> 限范围检索
   |-- CLARIFICATION --> 返回澄清请求 -> 结束
   |-- META -----------> 会话控制分支 -> 结束
   |
治理后 Query
   |
授权检索
   |
Prompt 装配
   |
Chat Provider
   |
输出复核
   |
流式返回
   |
写入历史 + 更新工作记忆
```

### 可参考图源

- Question Rewriting for Conversational QA, Figure 1
  链接：https://ar5iv.labs.arxiv.org/html/2004.14652
  参考点：先处理会话上下文，再接标准 QA 组件

---

## 5.13 新增图：隐私治理链路图

对应正文：

- [docs/chap03.tex:213](/home/lilu/Graduatin/docs/chap03.tex#L213)

现有可用素材：

- [image/chap03/privacy-governance-chain.puml](/home/lilu/Graduatin/image/chap03/privacy-governance-chain.puml)

### 新图目的

隐私治理是第 3 章的重点之一，但当前没有正式入文图。建议把隐私治理明确补成一张设计级流程图。

### 新图元素

- 输入文本/问题
- 敏感识别
- 脱敏处理
- 元数据标注
- 索引视图
- 外发视图
- 日志视图
- 输出复核

### 必须标注的字段

- safeText
- restricted
- externalModelAllowed
- sensitivityLevel

### 推荐布局

- 一条主链
- 中段分出三条视图使用支路

### 文字示意图

```text
输入文本/问题
   |
敏感识别
   |
脱敏处理 -> safeText
   |
元数据标注
   +--> 索引视图
   +--> 外发视图
   +--> 日志视图
   |
模型输出
   |
结果复核
   |
放行 / 拦截 / 二次脱敏
```

### 可参考图源

- 无强匹配通用论文图，建议直接根据本章文字与已有 puml 源文件重绘。

---

## 5.14 图 3.8 系统 E-R 图

当前图片：

- [image/chap03/ER.png](/home/lilu/Graduatin/image/chap03/ER.png)
- 对应正文：[docs/chap03.tex:229](/home/lilu/Graduatin/docs/chap03.tex#L229)

### 当前问题

- 图中 `file_upload` 与 `organization_tags` 被画成“多对多归属”。
- 正文表 3.4 中却将 `file_upload.org_tag` 写为单字段外键。
- 这是当前全篇最重要的“图文结构冲突”之一。

### 应保留

- users
- organization_tags
- file_upload
- chunk_info
- document_vectors

### 应删除

- “多对多归属”文字，如果实现并非如此

### 应补充

- users -> file_upload 上传关系
- organization_tags.parent_tag 自引用关系
- organization_tags.created_by -> users
- file_upload -> chunk_info 一对多
- file_upload -> document_vectors 一对多

### 重构方式

重构为标准 Crow's Foot E-R 图，字段只保留主键、外键和关键业务字段。

### 推荐布局

- 上方：users 与 organization_tags
- 中间：file_upload
- 下方：chunk_info 与 document_vectors

### 备注

如果系统真实实现确实是“文件可归属多个组织标签”，则必须同步修改：

- [docs/chap03.tex:257](/home/lilu/Graduatin/docs/chap03.tex#L257) 附近表 3.4
- 相关权限公式和文件元数据说明

---

## 5.15 图 4.1 安全过滤链执行关系图

当前图片：

- [image/chap04/filter.png](/home/lilu/Graduatin/image/chap04/filter.png)
- 对应正文：[docs/chap04.tex:31](/home/lilu/Graduatin/docs/chap04.tex#L31)

### 当前问题

- 当前图只是“类名顺序条”，不能支撑正文中对身份恢复和授权分离的说明。
- 分辨率偏低，放入论文后细节支撑力较弱。

### 应保留

- SecurityConfig
- JwtAuthenticationFilter
- OrgTagAuthorizationFilter
- Controller
- Service

### 应补充

- Request 进入链路
- SecurityContext 写入
- 组织标签缓存查询
- 授权判断输出

### 重构方式

重构为“请求语义流动图”，不是单纯横向类名链。

### 推荐布局

- 左到右主链
- 下方两个注释框说明：
  - Jwt 阶段产出：身份
  - OrgTag 阶段产出：授权结论

---

## 5.16 图 4.2 组织标签授权过滤流程图

当前图片：

- [image/chap04/orgfilter.png](/home/lilu/Graduatin/image/chap04/orgfilter.png)
- 对应正文：[docs/chap04.tex:50](/home/lilu/Graduatin/docs/chap04.tex#L50)

### 当前问题

- `公开资源或默认组织?` 这一判断把“公开资源”和“默认组织”混成了一个条件。
- 正文强调有效标签集合来自缓存层，但图中没有明确表现。

### 应保留

- 特殊接口/无需资源 ID 的快速放行
- 公开资源放行
- 身份校验
- 组织标签授权

### 应删除

- 混合语义判断：公开资源或默认组织

### 应补充

- 通过 OrgTagCacheService 获取 EffectiveTags
- 文件访问和检索场景的授权结果说明

### 重构方式

从“已认证身份”开始画，不再重复 JWT 校验内容。

### 推荐布局

- 上到下单列活动图
- 右侧外挂“缓存层”说明框

---

## 5.17 图 4.3 文件合并实现流程图

当前图片：

- [image/chap04/merge.png](/home/lilu/Graduatin/image/chap04/merge.png)
- 对应正文：[docs/chap04.tex:74](/home/lilu/Graduatin/docs/chap04.tex#L74)

### 当前问题

- 当前图是一条单向成功路径，没有画失败分支。
- 没有体现正文中明确描述的小文件同步入库和大文件 Kafka 异步入库分流。
- 没有体现 `uploadedChunks` 返回供补传重试。

### 应保留

- 校验文件记录
- 校验上传完整性
- 查询 chunk_info
- 检查 MinIO 分片对象
- composeObject 合并
- 清理 Redis
- 更新 file_upload 状态

### 应删除

- 一路成功到底、无回退的流程结构

### 应补充

- 校验失败返回 `uploadedChunks`
- 文件大小阈值判断
- 小文件 inline 入库
- 大文件投递 Kafka

### 重构方式

重构为带失败路径和分流判断的活动图。

### 文字示意图

```text
接收合并请求
   |
校验 file_upload 与 owner
   |--失败--> 拒绝
   |
校验 chunk 记录数 / 期望分片数
   |--失败--> 返回 uploadedChunks
   |
校验 MinIO 分片对象是否齐全
   |--失败--> 返回 uploadedChunks
   |
composeObject 合并
   |
清理 Redis / 更新状态为 MERGED
   |
[文件大小 <= 阈值 ?]
   |--是--> Inline 入库
   |--否--> 发送 Kafka
   |
返回确认
```

### 可参考图源

- 无强匹配标准论文图。
- 建议直接按正文实现逻辑绘制。

---

## 5.18 图 4.4 用户与组织管理界面展示

当前图片：

- [image/chap04/ui/ui_user.png](/home/lilu/Graduatin/image/chap04/ui/ui_user.png)
- [image/chap04/ui/ui-org.png](/home/lilu/Graduatin/image/chap04/ui/ui-org.png)
- 对应正文：[docs/chap04.tex:207](/home/lilu/Graduatin/docs/chap04.tex#L207)

### 当前问题

- 并排布局本身可行，但当前截图缩放后字号偏小。
- 顶部导航和大面积背景占用了图面，正文真正描述的关键信息区域比例不足。

### 应保留

- 用户概览卡片
- 筛选区域
- 表格主内容
- 行操作区
- 组织标签树形结构

### 应删除或裁掉

- 顶部导航冗余区域
- 左右边缘无信息留白
- 背景装饰大色块

### 应补充

- 编号标注
  - 1 概览统计
  - 2 筛选/分配入口
  - 3 关键表格列
  - 4 行内操作

### 重构方式

优先做“裁切 + 标注”，不要只放整屏缩略图。

### 推荐布局

- 如果裁切后仍然看不清，则改为上下排列两个子图

---

## 5.19 图 4.5 知识库与会话交互界面展示

当前图片：

- [image/chap04/ui/ui_file.png](/home/lilu/Graduatin/image/chap04/ui/ui_file.png)
- [image/chap04/ui/ui_session.png](/home/lilu/Graduatin/image/chap04/ui/ui_session.png)
- 对应正文：[docs/chap04.tex:230](/home/lilu/Graduatin/docs/chap04.tex#L230)

### 当前问题

- 文件列表字段多，但当前图缩得较小，正文提到的 `MD5`、组织标签、公开属性和操作列看不清。
- 会话图中“来源编号”是正文重点，但在当前缩略图里不易辨认。

### 应保留

- 文件管理表格区
- 会话消息区
- 输入框

### 应删除或裁掉

- 大面积无关背景
- 顶部导航重复区

### 应补充

- 会话图中的“来源编号”局部放大 inset
- 文件图中的字段区局部放大 inset

### 重构方式

改成“整图 + 关键局部放大框”的论文式界面图。

### 推荐布局

- 继续使用双子图可以，但两张图都应做内容区裁切

---

## 5.20 图 4.6 历史记录与结果追溯界面展示

当前图片：

- [image/chap04/ui/ui_history.png](/home/lilu/Graduatin/image/chap04/ui/ui_history.png)
- 对应正文：[docs/chap04.tex:256](/home/lilu/Graduatin/docs/chap04.tex#L256)

### 当前问题

- 当前图缩放后“筛选条件”和“来源编号”都较难看清。
- 宽度设置为 `0.72\textwidth` 偏保守，图的可读性不够。

### 应保留

- 用户筛选
- 时间范围筛选
- 历史问答回放
- 来源编号

### 应删除或裁掉

- 背景装饰区域
- 与正文无关的边角导航

### 应补充

- 一个局部放大框，用于强调来源追溯位置

### 重构方式

可改成上下两段式图片：

- 上段：筛选区
- 下段：历史记录回放区

### 推荐布局

- 将宽度提高至 `0.82\textwidth` 至 `0.88\textwidth`

---

## 6. 建议新增后的设计章图片目录

如果允许重新调整图号，建议第 3 章最终目录如下：

- 图 3.1 系统主处理链路示意图
- 图 3.2 系统总体架构图
- 图 3.3 权限映射与可见范围图
- 图 3.4 权限判定与候选隔离流程图
- 图 3.5 文档全生命周期设计图
- 图 3.6 混合检索设计图
- 图 3.7 Prompt 分层装配示意图
- 图 3.8 会话状态控制与生成编排设计图
- 图 3.9 隐私治理链路图
- 图 3.10 系统 E-R 图

这样第 3 章的逻辑顺序会更完整：

- 总链路
- 总架构
- 权限
- 文档接入
- 检索
- Prompt
- 会话
- 隐私
- 数据结构

---

## 7. 外部参考图源汇总

以下参考仅建议借鉴“图种与结构组织方式”，不建议直接照抄视觉样式或布局细节。

### 7.1 RAG 总链路与模块化架构

- Lewis et al., *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks*
  - 链接：https://ar5iv.labs.arxiv.org/html/2005.11401v4
  - 可参考图：Figure 1
  - 适合参考：图 3.1、图 3.6
  - 参考理由：Figure 1 用较少元素完成了“检索器 + 生成器 + top-K 文档 + 端到端训练”的主链表达。

- Zhang et al., *RAGLAB: A Modular and Research-Oriented Unified Framework for Retrieval-Augmented Generation*
  - 链接：https://ar5iv.labs.arxiv.org/html/2408.11381v2
  - 可参考图：Figure 1
  - 适合参考：图 3.2
  - 参考理由：Figure 1 强调模块化、组件边界和框架层次，适合借鉴为论文式总体架构图。

### 7.2 权限、层级与约束

- Sandhu, Ferraiolo, Kuhn, *The NIST Model for Role-Based Access Control: Towards a Unified Standard*
  - 链接：https://tsapps.nist.gov/publication/get_pdf.cfm?pub_id=916402
  - 可参考图：
    - Figure 1: Flat RBAC
    - Figure 2: Hierarchical RBAC
    - Figure 6: Constrained RBAC - Static SOD
    - Figure 7: Constrained RBAC - Dynamic SOD
  - 适合参考：图 3.3、图 3.4
  - 参考理由：这组图对“主体-角色-权限-层级-约束”关系表达非常规范，尤其适合作为权限类图的结构参考。

### 7.3 会话上下文处理与问题重写

- Vakulenko et al., *Question Rewriting for Conversational Question Answering*
  - 链接：https://ar5iv.labs.arxiv.org/html/2004.14652
  - 可参考图：
    - Figure 1
    - Figure 3
  - 适合参考：图 3.6、图 3.8（原图 3.7）
  - 参考理由：Figure 1 体现“先处理会话上下文，再接标准 QA 组件”；Figure 3 体现“候选选择 + 重排序”分阶段结构。

---

## 8. 与当前工程直接相关的补充建议

### 8.1 建议入文的现有素材

- [image/chap03/prompt.png](/home/lilu/Graduatin/image/chap03/prompt.png)
  - 建议改造后作为“Prompt 分层装配示意图”

- [image/chap03/privacy-governance-chain.puml](/home/lilu/Graduatin/image/chap03/privacy-governance-chain.puml)
  - 建议完善后作为“隐私治理链路图”

### 8.2 建议归档或不再作为正式正文图使用的素材

- [image/chap02/rag.png](/home/lilu/Graduatin/image/chap02/rag.png)
- [image/chap02/llm.png](/home/lilu/Graduatin/image/chap02/llm.png)
- [image/chap02/querry.png](/home/lilu/Graduatin/image/chap02/querry.png)
- [image/chap04/colorbar.png](/home/lilu/Graduatin/image/chap04/colorbar.png)

这些素材要么未入文，要么不再适合作为正式论文配图主图。

---

## 9. 最终执行顺序

建议按下面顺序推进，避免返工：

1. 先重画第 2 章四张需求图，彻底清掉实现层词汇。
2. 再重画图 3.2、3.3、3.4、3.5、3.6、3.7。
3. 新增 Prompt 图和隐私治理图。
4. 修正图 3.8，使其和表 3.4 一致。
5. 重画图 4.3，并同步优化图 4.1、图 4.2。
6. 最后再裁切和标注 UI 截图。

---

## 10. 结论

本次图片修改不应理解为“美化图片”，而应理解为“修正图文逻辑关系”。

当前最关键的问题不是配色和清晰度，而是：

- 第 2 章图中混入实现层
- 第 3 章图中存在概念冲突和设计缺项
- 第 4 章图中关键实现分支未画

只要先把这三个层面理顺，再做视觉统一，整篇论文的专业度会明显提升。

