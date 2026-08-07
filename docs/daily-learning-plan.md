# KiwiTech Insights — 42 天学习驱动开发计划

这份计划的目标不是“刷完视频”，而是每天把视频中的一个知识点变成 KiwiTech Insights 中可运行、可测试、可解释的代码。

## 三条课程线

| 技术线 | 课程 | 在本项目中的用途 |
|---|---|---|
| Java | [Java 零基础上部](https://www.bilibili.com/video/BV17F411T7Ao/) | 领域模型、集合、字符串处理、排序和面向对象设计 |
| Spring Boot | [Spring Boot 6 小时入门](https://www.bilibili.com/video/BV1Lq4y1J77x/) | REST API、配置、测试、数据库和部署 |
| React | [React 18 入门到实战](https://www.bilibili.com/video/BV1ZB4y1Z7o8/) | TypeScript 仪表盘、筛选、表格、图表和 API 集成 |

> 课程较旧，项目实现以 Java 17、当前稳定版 Spring Boot、Spring Data JPA、Vite、React 和 TypeScript 为准。Spring 课程中的 MyBatis 只理解整合思路，本项目改用 JPA；Redis、自定义 starter、Spring Boot Admin 暂不进入 MVP；React 课程中的 CRA 改用 Vite。

## 每天的固定节奏（严格控制在 120 分钟）

1. 看指定分集，最多 35 分钟；使用 1.25–1.5 倍速，只记“概念、何时使用、一个疑问”。
2. 关掉视频，用 15 分钟独立复现最小例子。
3. 用 50 分钟把知识点用于本项目；每天只追求一个可验收成果。
4. 用 15 分钟写测试并运行当天相关检查。
5. 用 5 分钟做英文口述：做了什么、为什么这样做、另一个方案及取舍。只在每周复习日更新一次项目总结，不写每日学习日志。

完成标准：代码可运行、至少一项自动检查通过，并且能够回答上述四个问题。到 120 分钟立即停止；未完成项留到下一个学习日，不通过熬夜追回进度。

### 考试优先规则

- 这 120 分钟是上限，不是必须耗满的最低时长。
- 考试前 14 天可切换到维护模式：每次 30 分钟，只复习旧代码、修一个小问题或补一个测试，不开启新阶段。
- 考试前 3 天暂停项目；考试结束后从上次未完成的任务恢复，不重新计算天数。
- 表格中的视频分集是知识范围，不要求逐秒观看。已经掌握的内容快进；当天 35 分钟看不完就只看与项目任务直接相关的小节。
- 每周复习日优先清理顺延任务。清不完时缩小功能范围，不占用考试复习时间。

## 第 1 周：Java 最小基础与领域模型

| 天 | 看什么 | 项目任务 | 当天验收 |
|---|---|---|---|
| 1 | Java P1、P6–P8、P15–P16；已装好 JDK 可快进 P7 | 确认 CSV 字段；建立一份 8–10 行样例数据，包含 2 行故意错误数据 | `java -version` 为 17+；能解释 JDK/JRE/JVM；CSV 契约写入文档 |
| 2 | P17–P26（变量、数据类型、输入） | 定义 `JobListing` 所需字段及类型，写字段选择理由 | 能指出哪些字段必填；能解释字符串、整数、日期为何使用相应类型 |
| 3 | P39–P48（判断和循环） | 写不依赖框架的行校验逻辑：缺标题、缺公司、非法日期 | 有效行通过、无效行返回明确原因；至少 3 个测试案例 |
| 4 | P54–P61（数组）和 P63–P70（方法） | 把 CSV 表头解析与字段校验拆成小方法 | 每个方法职责单一；边界案例可重复运行 |
| 5 | P81–P86（类、封装、构造器） | 建立 `JobListing`、`Skill`、`ImportError`、`ImportResult` 领域对象 | 无效对象不能被随意构造；能解释封装的价值 |
| 6 | P96–P106（String、StringBuilder） | 规范化职位描述和技能名：trim、大小写、别名 | `Spring boot`、`spring-boot` 可归一；测试覆盖空白和大小写 |
| 7 | 不看新课 | 复做本周最难功能；整理英文讲解；补测试与 README | 从空白复现核心逻辑；本周测试全部通过 |

## 第 2 周：集合、算法与可替换设计

| 天 | 看什么 | 项目任务 | 当天验收 |
|---|---|---|---|
| 8 | P111–P115（ArrayList） | 用 `List` 保存导入行和错误；生成首个内存版导入结果 | accepted/rejected 数量正确 |
| 9 | P121–P125（static、继承概念） | 提取无状态的规范化工具；避免为了复用而滥用继承 | 能解释工具方法为何可/不可设为 static |
| 10 | P129–P139（多态、抽象类、接口） | 定义 `SkillExtractor` 接口和关键词实现 | 可替换实现；调用方不依赖具体类；有单元测试 |
| 11 | P155、P159–P160（Object、Objects） | 为 `Skill` 定义基于规范化名称的相等性 | `Set<Skill>` 正确去重；测试 `equals/hashCode` 契约 |
| 12 | P177–P183（查找、排序、Arrays、lambda） | 实现技能计数和降序排名；同频率按名称排序 | 固定输入产生稳定排名；能说明时间复杂度 |
| 13 | P185–P193（Collection、List、泛型） | 把聚合结果建模为泛型或强类型结果；比较 List/Set/Map | 能解释三种集合在项目里的选择 |
| 14 | 不看新课 | 第一次小演示：读取内存数据 → 提取技能 → 输出 Top 5 | 一条命令运行；测试通过；录下 3 分钟英文讲解 |

## 第 3 周：文件导入与 Spring Boot 后端

Java 上部课程没有完整覆盖异常、文件 IO、Stream、JUnit。这周先通过项目实践补齐；遇到概念不清时再查 Java 下部课程，而不是阻塞主线。

| 天 | 看什么 | 项目任务 | 当天验收 |
|---|---|---|---|
| 15 | Java：复习 P63–P73；补读 Java 文件 IO 基础 | 用 try-with-resources 读取 CSV；区分文件错误与行错误 | 文件可靠关闭；坏行不导致整批数据静默失败 |
| 16 | Java：复习 P185–P193；补读 Map/Stream 基础 | 用 Stream 或清晰循环完成按地点、资历聚合 | 两种实现任选其一并说明可读性取舍 |
| 17 | Spring P1–P6（导学、概述、快速入门、起步依赖） | 创建后端工程；提供 `/api/health` | 应用启动；health 返回 200；提交首个 Spring 测试 |
| 18 | Spring P7–P11（YAML 与配置读取） | 配置数据库连接和 `skills.aliases`；用类型安全配置读取 | 测试配置与开发配置分离；配置可被测试验证 |
| 19 | Spring P12–P14（profiles 与加载顺序） | 建立 dev/test profile；记录敏感配置规则 | 测试使用 H2；仓库不含真实密码 |
| 20 | Spring P15（JUnit） | 为服务层补 JUnit；添加一次 controller 测试 | 正常、空输入、异常路径都有证据 |
| 21 | 不看新课 | 整理后端结构和运行文档 | 新开发者按 README 可启动并运行测试 |

## 第 4 周：数据库、CSV API 与分析 API

| 天 | 看什么 | 项目任务 | 当天验收 |
|---|---|---|---|
| 22 | Spring P17（MyBatis，只看“框架如何接数据库”） | 使用 Spring Data JPA 建 `JobListingEntity`、`SkillEntity` 与关系 | H2 集成测试可保存并查询一条 listing |
| 23 | Spring：复习 P3–P5；学习 REST controller 基本注解 | 实现 CSV multipart 上传端点 | 有效/无效行计数与错误详情 JSON 正确 |
| 24 | 无新视频 | 增加事务边界和重复导入策略 | 失败不会留下半批数据；重复规则有测试 |
| 25 | 无新视频 | 实现职位列表 API：location、seniority、skill 筛选 | 每个筛选及组合筛选均有集成测试 |
| 26 | Java P177–P183 复习 | 实现 `/api/analytics/skills` 排名 API | 排名、并列顺序、空数据结果稳定 |
| 27 | 无新视频 | 实现 location/seniority 分组与技能组合 API | 统计结果可从样例 CSV 人工复算 |
| 28 | Spring P31–P32（Actuator） | 开启必要 health/info；完成后端端到端演示 | 导入 → 查询 → 分析整条链路通过 |

## 第 5 周：React 基础并连接后端

| 天 | 看什么 | 项目任务 | 当天验收 |
|---|---|---|---|
| 29 | React P1–P13（环境、JSX、列表、条件、事件、组件、state） | 用 Vite + React + TypeScript 创建前端；渲染静态技能榜 | loading/empty/data 三种状态可见 |
| 30 | React P19–P29（表单、props、组件通信、context） | 构建 location/seniority/skill 筛选组件 | 受控表单正确；筛选状态有唯一来源 |
| 31 | React P30–P37（effect、自定义 Hook、请求封装） | 获取后端数据；封装 `useSkillAnalytics` | 请求只在依赖变化时触发；错误可见且可重试 |
| 32 | React P52–P59（Router） | 建立 Dashboard、Listings、Import 三个页面 | 直接访问 URL、导航和 404 都正常 |
| 33 | React P105–P107（ECharts 与 API 模块） | 增加技能 Top 10 图表，并保留可访问数据表 | 图表与表格来自同一数据；图表有文本替代 |
| 34 | React P117–P123（表格、筛选、分页、删除仅看思路） | 完成职位表格、筛选和分页；MVP 不做删除 | 过滤后页码正确重置；空结果有提示 |
| 35 | 不看新课 | 前后端纵向演示与可访问性检查 | 键盘可操作；错误提示清晰；生产构建通过 |

## 第 6 周：TypeScript、导入体验与作品集交付

| 天 | 看什么 | 项目任务 | 当天验收 |
|---|---|---|---|
| 36 | React P146–P153（React + TS） | 收紧 API、props、state 类型，消除可避免的 `any` | 类型检查通过；错误响应有明确类型 |
| 37 | React P158–P164（Axios + TS、列表与详情） | 统一 API client；增加职位详情页 | API 错误被统一转换；详情刷新仍可加载 |
| 38 | React P108–P116（上传思路） | 实现 CSV 拖放/选择、上传进度和错误行展示 | 用户能看到 accepted/rejected 及逐行原因 |
| 39 | Spring P34（部署）+ React P129–P131（构建、懒加载、体积分析） | 完成前后端生产构建；记录环境变量 | 两端 build 成功；部署配置不含秘密 |
| 40 | 无新视频 | 加 GitHub Actions：后端测试、前端测试/类型检查/build | 本地用同样命令全部通过 |
| 41 | 无新视频 | 更新架构图、API 示例、运行说明、设计取舍 | README 从克隆到演示无缺步 |
| 42 | 不看新课 | 最终演示：问题 → CSV → API → Dashboard → 洞察；准备面试回答 | 5 分钟 demo；回答 5 个项目问题；列出下一迭代 |

## 明确跳过的内容

- Java P2–P5 的 Windows/CMD 细节：当前是 macOS，只需会终端基础。
- Java 拼图阶段项目 P144–P154：和本项目目标无关。
- Spring Redis P16、自动配置深挖 P18–P30、Admin P33：MVP 完成后再学。
- React 美团/记账本整套复刻、登录 token、文章发布：只在项目需要相同模式时选看。
- React class component P140–P142：理解遗留代码即可，新代码使用函数组件。

## 每日协作方式

每天开始时告诉 Codex：`开始第 N 天`。Codex 应先检查前一天证据，再给出当天三个层次的帮助：

1. 先让学习者说明思路或写第一版；
2. 针对错误给提示、测试和小范围修改；
3. 完成后运行验证；每周复习日再统一更新项目总结。

Codex 不应直接代写整天任务。卡住超过 20 分钟时，可以提供最小可运行骨架，但学习者必须补测试并用自己的话解释。

## 每周项目总结模板

```md
# Week N — Project Progress

- Features built:
- Java/Spring/React concepts applied:
- Tests and verification:
- Technical problem solved:
- Design decision and trade-off:
- Demo evidence:
- Next milestone:
```
