# BlogLink Indexer

BlogLink Indexer 是一个面向技术博客与知识库的链接聚合与索引系统，专为需要系统化整理、检索和归档大量技术文章链接的开发者、技术写作团队及知识管理爱好者设计。该项目不提供文章内容存储，而是以轻量级索引层的方式，将分散在技术博客平台上的文章链接按照既定规则进行结构化收录，并提供分类导航、快速检索与状态监控能力。

BlogLink Indexer 的核心定位是成为技术博客外链的“黄页系统”。它通过自动化脚本定期抓取链接可达性，利用元数据标签对文章类型进行粗粒度划分，最终生成可供静态站点或 CLI 工具查询的索引数据库。项目本身不依赖数据库服务，所有索引数据以 JSON 和 Markdown 双格式输出，既便于人工浏览，也适合被其他工具链集成。

## 功能概览

**链接批量导入与归一化**：支持从 CSV、JSON 或纯文本列表批量导入文章 URL，自动进行协议归一化（保留原始协议头）、去重与格式校验，确保每条链接符合 RFC 标准。

**周期性可达性检测**：内置基于 HTTP 状态码与响应时间的健康检查模块，可配置周期（默认每 24 小时）对索引内所有链接发起 HEAD 请求，标记异常链接并生成报告。

**分类标签系统**：允许用户为每个链接打上最多五个自定义标签（如“后端”、“数据库”、“DevOps”），并支持基于标签的快速过滤与统计。

**多格式索引输出**：每次索引更新后自动生成 JSON 结构化数据文件、Markdown 表格视图以及 HTML 静态导航页面，满足不同使用场景的展示需求。

**查询 CLI 工具**：提供轻量级命令行接口，支持按关键词、标签、域名或文章 ID 进行精确或模糊检索，结果以表格或纯文本列表输出。

**历史快照与回滚**：每次索引变更自动保存历史快照（保留最近 30 个版本），允许用户回退到任意历史状态，防止误操作或数据损坏。

**开放 API 接口**：基于 Flask 提供 RESTful 查询接口，支持第三方工具通过 HTTP 请求获取索引数据，便于嵌入更大规模的文档平台或知识中台。

## 应用场景

技术博客聚合站运营者可以使用 BlogLink Indexer 将不同作者、不同专题的文章链接统一纳入索引，通过标签系统进行分类，并生成可公开访问的导航页，方便读者按主题浏览。运营者还可以利用健康检查功能定期清理失效链接，保证导航站的质量。

企业内部技术团队的知识库管理员可以将团队内部技术博客、项目文档、设计文档的链接统一录入系统，利用 CLI 工具快速检索特定主题的相关文章，减少在多个书签或文档中反复查找的时间成本。

开源项目维护者可以将项目相关的教程、案例、FAQ 文章链接通过 BlogLink Indexer 进行整理，并将生成的 Markdown 索引表直接嵌入项目的 README 或 Wiki 页面，让社区成员更容易找到学习资料。

个人开发者可以将自己收藏的技术文章链接统一归档，利用标签系统构建个人知识体系，并通过历史快照功能追踪自己阅读兴趣的变化趋势。

## 快速开始

以下命令演示了从克隆仓库到启动索引服务的完整流程。

```bash
# 克隆仓库
git clone https://github.com/your-org/bloglink-indexer.git

# 进入项目目录
cd bloglink-indexer

# 安装依赖（推荐使用 Python 虚拟环境）
python -m venv venv
source venv/bin/activate  # Linux/macOS
# venv\Scripts\activate   # Windows
pip install -r requirements.txt

# 执行初始索引构建（使用示例数据）
python indexer.py --init --source sample_links.json

# 启动 Web 查询服务（默认端口 5000）
python app.py --port 5000
```

## 安装要求

| 依赖 | 必需 | 说明 |
|------|------|------|
| Python 3.9+ | 是 | 核心运行环境，3.8 及以下版本不兼容异步特性 |
| requests >= 2.28.0 | 是 | 用于 HTTP 健康检查与链接可达性探测 |
| Flask >= 2.2.0 | 否 | Web API 服务依赖，仅在使用 app.py 启动服务时需要 |
| click >= 8.0.0 | 是 | CLI 命令行交互框架，用于解析子命令与参数 |
| pytest >= 7.0.0 | 否 | 单元测试框架，仅在开发或运行测试套件时需要 |
| ruff >= 0.1.0 | 否 | 代码静态检查工具，用于提交前自动格式校验 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 用户手册 | docs/user-guide.md | 如何导入链接、配置标签、生成索引、使用 CLI 查询？ |
| 运维指南 | docs/ops-guide.md | 如何部署健康检查定时任务、配置输出路径、备份快照？ |
| API 参考 | docs/api-reference.md | RESTful 接口的端点列表、请求参数格式、返回数据结构？ |
| 开发文档 | docs/developer-guide.md | 项目的模块划分、扩展新数据源的接口规范、贡献代码流程？ |

## 资源列表

以下为项目第 31/280 批次收录的全部原始链接，按类别分组展示。所有 URL 均按原始形式原样列出，未做任何协议补全或域名规范化处理。

技术文章类（编号 485111 至 137905）

http://www.blog.fuvxie.cn/Article/details/485111.sHtML
http://www.blog.fuvxie.cn/Article/details/1769420.sHtML
http://www.blog.fuvxie.cn/Article/details/3475451.sHtML
http://www.blog.fuvxie.cn/Article/details/4053546.sHtML
http://www.blog.fuvxie.cn/Article/details/4409239.sHtML
http://www.blog.fuvxie.cn/Article/details/5252.sHtML
http://www.blog.fuvxie.cn/Article/details/868821.sHtML
http://www.blog.fuvxie.cn/Article/details/3924848.sHtML
http://www.blog.fuvxie.cn/Article/details/137905.sHtML
http://www.blog.fuvxie.cn/Article/details/34107.sHtML
http://www.blog.fuvxie.cn/Article/details/71916.sHtML
http://www.blog.fuvxie.cn/Article/details/8014.sHtML
http://www.blog.fuvxie.cn/Article/details/5242961.sHtML
http://www.blog.fuvxie.cn/Article/details/6718397.sHtML
http://www.blog.fuvxie.cn/Article/details/32363.sHtML
http://www.blog.fuvxie.cn/Article/details/6407839.sHtML
http://www.blog.fuvxie.cn/Article/details/5846.sHtML
http://www.blog.fuvxie.cn/Article/details/4271129.sHtML
http://www.blog.fuvxie.cn/Article/details/1910.sHtML
http://www.blog.fuvxie.cn/Article/details/2697645.sHtML
http://www.blog.fuvxie.cn/Article/details/625885.sHtML
http://www.blog.fuvxie.cn/Article/details/53443.sHtML
http://www.blog.fuvxie.cn/Article/details/3516525.sHtML
http://www.blog.fuvxie.cn/Article/details/4314574.sHtML
http://www.blog.fuvxie.cn/Article/details/304697.sHtML
http://www.blog.fuvxie.cn/Article/details/873505.sHtML
http://www.blog.fuvxie.cn/Article/details/0062.sHtML
http://www.blog.fuvxie.cn/Article/details/018565.sHtML
http://www.blog.fuvxie.cn/Article/details/0263.sHtML
http://www.blog.fuvxie.cn/Article/details/8490.sHtML
http://www.blog.fuvxie.cn/Article/details/8013.sHtML
http://www.blog.fuvxie.cn/Article/details/0646453.sHtML
http://www.blog.fuvxie.cn/Article/details/92046.sHtML
http://www.blog.fuvxie.cn/Article/details/4837.sHtML
http://www.blog.fuvxie.cn/Article/details/442124.sHtML
http://www.blog.fuvxie.cn/Article/details/776837.sHtML
http://www.blog.fuvxie.cn/Article/details/6762795.sHtML
http://www.blog.fuvxie.cn/Article/details/270236.sHtML
http://www.blog.fuvxie.cn/Article/details/5786551.sHtML
http://www.blog.fuvxie.cn/Article/details/8870.sHtML
http://www.blog.fuvxie.cn/Article/details/8051.sHtML
http://www.blog.fuvxie.cn/Article/details/9751702.sHtML
http://www.blog.fuvxie.cn/Article/details/178836.sHtML
http://www.blog.fuvxie.cn/Article/details/400309.sHtML
http://www.blog.fuvxie.cn/Article/details/787049.sHtML
http://www.blog.fuvxie.cn/Article/details/348114.sHtML
http://www.blog.fuvxie.cn/Article/details/59346.sHtML
http://www.blog.fuvxie.cn/Article/details/2181.sHtML
http://www.blog.fuvxie.cn/Article/details/51868.sHtML
http://www.blog.fuvxie.cn/Article/details/254222.sHtML
http://www.blog.fuvxie.cn/Article/details/3295614.sHtML
http://www.blog.fuvxie.cn/Article/details/3252.sHtML
http://www.blog.fuvxie.cn/Article/details/3455.sHtML
http://www.blog.fuvxie.cn/Article/details/931418.sHtML
http://www.blog.fuvxie.cn/Article/details/24758.sHtML
http://www.blog.fuvxie.cn/Article/details/220081.sHtML
http://www.blog.fuvxie.cn/Article/details/994789.sHtML
http://www.blog.fuvxie.cn/Article/details/14736.sHtML
http://www.blog.fuvxie.cn/Article/details/33807.sHtML
http://www.blog.fuvxie.cn/Article/details/890680.sHtML
http://www.blog.fuvxie.cn/Article/details/2243589.sHtML
http://www.blog.fuvxie.cn/Article/details/726556.sHtML
http://www.blog.fuvxie.cn/Article/details/5607.sHtML
http://www.blog.fuvxie.cn/Article/details/2123166.sHtML
http://www.blog.fuvxie.cn/Article/details/709893.sHtML
http://www.blog.fuvxie.cn/Article/details/7969422.sHtML
http://www.blog.fuvxie.cn/Article/details/5865537.sHtML
http://www.blog.fuvxie.cn/Article/details/6003.sHtML
http://www.blog.fuvxie.cn/Article/details/9088875.sHtML
http://www.blog.fuvxie.cn/Article/details/98675.sHtML
http://www.blog.fuvxie.cn/Article/details/888496.sHtML
http://www.blog.fuvxie.cn/Article/details/864236.sHtML
http://www.blog.fuvxie.cn/Article/details/4417678.sHtML
http://www.blog.fuvxie.cn/Article/details/5271.sHtML
http://www.blog.fuvxie.cn/Article/details/70414.sHtML
http://www.blog.fuvxie.cn/Article/details/5334141.sHtML
http://www.blog.fuvxie.cn/Article/details/06487.sHtML
http://www.blog.fuvxie.cn/Article/details/9027022.sHtML
http://www.blog.fuvxie.cn/Article/details/3687.sHtML
http://www.blog.fuvxie.cn/Article/details/5643.sHtML
http://www.blog.fuvxie.cn/Article/details/8663085.sHtML
http://www.blog.fuvxie.cn/Article/details/1296734.sHtML
http://www.blog.fuvxie.cn/Article/details/218346.sHtML
http://www.blog.fuvxie.cn/Article/details/0187.sHtML
http://www.blog.fuvxie.cn/Article/details/38859.sHtML
http://www.blog.fuvxie.cn/Article/details/3769.sHtML
http://www.blog.fuvxie.cn/Article/details/116846.sHtML
http://www.blog.fuvxie.cn/Article/details/74480.sHtML
http://www.blog.fuvxie.cn/Article/details/9455992.sHtML
http://www.blog.fuvxie.cn/Article/details/4821.sHtML
http://www.blog.fuvxie.cn/Article/details/499878.sHtML
http://www.blog.fuvxie.cn/Article/details/6953.sHtML
http://www.blog.fuvxie.cn/Article/details/09084.sHtML
http://www.blog.fuvxie.cn/Article/details/118999.sHtML
http://www.blog.fuvxie.cn/Article/details/188382.sHtML
http://www.blog.fuvxie.cn/Article/details/3497.sHtML
http://www.blog.fuvxie.cn/Article/details/6704.sHtML
http://www.blog.fuvxie.cn/Article/details/360236.sHtML
http://www.blog.fuvxie.cn/Article/details/2912.sHtML
http://www.blog.fuvxie.cn/Article/details/6428039.sHtML
http://www.blog.fuvxie.cn/Article/details/358329.sHtML
http://www.blog.fuvxie.cn/Article/details/78215.sHtML
http://www.blog.fuvxie.cn/Article/details/2752.sHtML
http://www.blog.fuvxie.cn/Article/details/7757.sHtML
http://www.blog.fuvxie.cn/Article/details/827328.sHtML
http://www.blog.fuvxie.cn/Article/details/2313.sHtML
http://www.blog.fuvxie.cn/Article/details/5566.sHtML
http://www.blog.fuvxie.cn/Article/details/4684.sHtML
http://www.blog.fuvxie.cn/Article/details/0502550.sHtML
http://www.blog.fuvxie.cn/Article/details/887429.sHtML
http://www.blog.fuvxie.cn/Article/details/8103948.sHtML
http://www.blog.fuvxie.cn/Article/details/5954.sHtML
http://www.blog.fuvxie.cn/Article/details/5466.sHtML
http://www.blog.fuvxie.cn/Article/details/01608.sHtML
http://www.blog.fuvxie.cn/Article/details/823762.sHtML
http://www.blog.fuvxie.cn/Article/details/7670.sHtML
http://www.blog.fuvxie.cn/Article/details/8544.sHtML
http://www.blog.fuvxie.cn/Article/details/52596.sHtML
http://www.blog.fuvxie.cn/Article/details/355220.sHtML
http://www.blog.fuvxie.cn/Article/details/1489.sHtML
http://www.blog.fuvxie.cn/Article/details/33685.sHtML
http://www.blog.fuvxie.cn/Article/details/1705656.sHtML
http://www.blog.fuvxie.cn/Article/details/232474.sHtML
http://www.blog.fuvxie.cn/Article/details/314498.sHtML
http://www.blog.fuvxie.cn/Article/details/2501.sHtML
http://www.blog.fuvxie.cn/Article/details/7118511.sHtML
http://www.blog.fuvxie.cn/Article/details/499772.sHtML
http://www.blog.fuvxie.cn/Article/details/2573024.sHtML
http://www.blog.fuvxie.cn/Article/details/6604836.sHtML
http://www.blog.fuvxie.cn/Article/details/5545421.sHtML
http://www.blog.fuvxie.cn/Article/details/540532.sHtML
http://www.blog.fuvxie.cn/Article/details/318849.sHtML
http://www.blog.fuvxie.cn/Article/details/66302.sHtML
http://www.blog.fuvxie.cn/Article/details/4839.sHtML
http://www.blog.fuvxie.cn/Article/details/4886636.sHtML
http://www.blog.fuvxie.cn/Article/details/7775896.sHtML
http://www.blog.fuvxie.cn/Article/details/95881.sHtML
http://www.blog.fuvxie.cn/Article/details/6494635.sHtML
http://www.blog.fuvxie.cn/Article/details/403594.sHtML
http://www.blog.fuvxie.cn/Article/details/9290136.sHtML
http://www.blog.fuvxie.cn/Article/details/5582.sHtML
http://www.blog.fuvxie.cn/Article/details/8398.sHtML
http://www.blog.fuvxie.cn/Article/details/194535.sHtML
http://www.blog.fuvxie.cn/Article/details/25970.sHtML
http://www.blog.fuvxie.cn/Article/details/6782166.sHtML
http://www.blog.fuvxie.cn/Article/details/492585.sHtML
http://www.blog.fuvxie.cn/Article/details/5052.sHtML
http://www.blog.fuvxie.cn/Article/details/69248.sHtML
http://www.blog.fuvxie.cn/Article/details/2825.sHtML
http://www.blog.fuvxie.cn/Article/details/7831.sHtML
http://www.blog.fuvxie.cn/Article/details/1433538.sHtML
http://www.blog.fuvxie.cn/Article/details/802785.sHtML
http://www.blog.fuvxie.cn/Article/details/9936044.sHtML
http://www.blog.fuvxie.cn/Article/details/02267.sHtML
http://www.blog.fuvxie.cn/Article/details/79712.sHtML
http://www.blog.fuvxie.cn/Article/details/49573.sHtML
http://www.blog.fuvxie.cn/Article/details/06449.sHtML
http://www.blog.fuvxie.cn/Article/details/817222.sHtML
http://www.blog.fuvxie.cn/Article/details/93511.sHtML
http://www.blog.fuvxie.cn/Article/details/13276.sHtML
http://www.blog.fuvxie.cn/Article/details/3472629.sHtML
http://www.blog.fuvxie.cn/Article/details/9709107.sHtML
http://www.blog.fuvxie.cn/Article/details/710160.sHtML
http://www.blog.fuvxie.cn/Article/details/206630.sHtML
http://www.blog.fuvxie.cn/Article/details/38821.sHtML
http://www.blog.fuvxie.cn/Article/details/4120949.sHtML
http://www.blog.fuvxie.cn/Article/details/46510.sHtML
http://www.blog.fuvxie.cn/Article/details/681951.sHtML
http://www.blog.fuvxie.cn/Article/details/750513.sHtML
http://www.blog.fuvxie.cn/Article/details/4315.sHtML
http://www.blog.fuvxie.cn/Article/details/67192.sHtML
http://www.blog.fuvxie.cn/Article/details/064051.sHtML
http://www.blog.fuvxie.cn/Article/details/63823.sHtML
http://www.blog.fuvxie.cn/Article/details/327460.sHtML
http://www.blog.fuvxie.cn/Article/details/7059.sHtML
http://www.blog.fuvxie.cn/Article/details/455893.sHtML
http://www.blog.fuvxie.cn/Article/details/395703.sHtML
http://www.blog.fuvxie.cn/Article/details/2410531.sHtML
http://www.blog.fuvxie.cn/Article/details/10264.sHtML
http://www.blog.fuvxie.cn/Article/details/5472.sHtML
http://www.blog.fuvxie.cn/Article/details/48323.sHtML
http://www.blog.fuvxie.cn/Article/details/2788625.sHtML
http://www.blog.fuvxie.cn/Article/details/7349847.sHtML
http://www.blog.fuvxie.cn/Article/details/1544.sHtML
http://www.blog.fuvxie.cn/Article/details/139525.sHtML
http://www.blog.fuvxie.cn/Article/details/21230.sHtML
http://www.blog.fuvxie.cn/Article/details/253475.sHtML
http://www.blog.fuvxie.cn/Article/details/01469.sHtML
http://www.blog.fuvxie.cn/Article/details/800590.sHtML
http://www.blog.fuvxie.cn/Article/details/185355.sHtML
http://www.blog.fuvxie.cn/Article/details/56071.sHtML
http://www.blog.fuvxie.cn/Article/details/29618.sHtML
http://www.blog.fuvxie.cn/Article/details/3671808.sHtML
http://www.blog.fuvxie.cn/Article/details/7665.sHtML
http://www.blog.fuvxie.cn/Article/details/3319.sHtML
http://www.blog.fuvxie.cn/Article/details/6980615.sHtML
http://www.blog.fuvxie.cn/Article/details/38180.sHtML
http://www.blog.fuvxie.cn/Article/details/10144.sHtML
http://www.blog.fuvxie.cn/Article/details/525033.sHtML
http://www.blog.fuvxie.cn/Article/details/5749.sHtML
http://www.blog.fuvxie.cn/Article/details/5739755.sHtML
http://www.blog.fuvxie.cn/Article/details/5585.sHtML
http://www.blog.fuvxie.cn/Article/details/29144.sHtML
http://www.blog.fuvxie.cn/Article/details/9980623.sHtML
http://www.blog.fuvxie.cn/Article/details/4091.sHtML
http://www.blog.fuvxie.cn/Article/details/2235.sHtML
http://www.blog.fuvxie.cn/Article/details/131448.sHtML
http://www.blog.fuvxie.cn/Article/details/415616.sHtML
http://www.blog.fuvxie.cn/Article/details/6592.sHtML
http://www.blog.fuvxie.cn/Article/details/980825.sHtML
http://www.blog.fuvxie.cn/Article/details/8803614.sHtML
http://www.blog.fuvxie.cn/Article/details/5885.sHtML
http://www.blog.fuvxie.cn/Article/details/40211.sHtML
http://www.blog.fuvxie.cn/Article/details/4819267.sHtML
http://www.blog.fuvxie.cn/Article/details/0672818.sHtML
http://www.blog.fuvxie.cn/Article/details/3771132.sHtML
http://www.blog.fuvxie.cn/Article/details/498560.sHtML
http://www.blog.fuvxie.cn/Article/details/8172933.sHtML
http://www.blog.fuvxie.cn/Article/details/286603.sHtML
http://www.blog.fuvxie.cn/Article/details/1744.sHtML
http://www.blog.fuvxie.cn/Article/details/7255.sHtML
http://www.blog.fuvxie.cn/Article/details/368449.sHtML
http://www.blog.fuvxie.cn/Article/details/57032.sHtML
http://www.blog.fuvxie.cn/Article/details/0040249.sHtML
http://www.blog.fuvxie.cn/Article/details/6054.sHtML
http://www.blog.fuvxie.cn/Article/details/9366.sHtML
http://www.blog.fuvxie.cn/Article/details/5318040.sHtML
http://www.blog.fuvxie.cn/Article/details/5926972.sHtML
http://www.blog.fuvxie.cn/Article/details/356537.sHtML
http://www.blog.fuvxie.cn/Article/details/4834.sHtML
http://www.blog.fuvxie.cn/Article/details/7083756.sHtML
http://www.blog.fuvxie.cn/Article/details/501763.sHtML
http://www.blog.fuvxie.cn/Article/details/7361749.sHtML
http://www.blog.fuvxie.cn/Article/details/4757.sHtML
http://www.blog.fuvxie.cn/Article/details/48442.sHtML
http://www.blog.fuvxie.cn/Article/details/21480.sHtML
http://www.blog.fuvxie.cn/Article/details/2897599.sHtML
http://www.blog.fuvxie.cn/Article/details/2979.sHtML
http://www.blog.fuvxie.cn/Article/details/6841401.sHtML
http://www.blog.fuvxie.cn/Article/details/92712.sHtML
http://www.blog.fuvxie.cn/Article/details/61633.sHtML
http://www.blog.fuvxie.cn/Article/details/491810.sHtML
http://www.blog.fuvxie.cn/Article/details/0571.sHtML
http://www.blog.fuvxie.cn/Article/details/173277.sHtML
http://www.blog.fuvxie.cn/Article/details/660926.sHtML
http://www.blog.fuvxie.cn/Article/details/81170.sHtML
http://www.blog.fuvxie.cn/Article/details/0557.sHtML
http://www.blog.fuvxie.cn/Article/details/1091296.sHtML
http://www.blog.fuvxie.cn/Article/details/78458.sHtML
http://www.blog.fuvxie.cn/Article/details/6779.sHtML

## 项目结构

```
bloglink-indexer/
├── indexer.py                # 主索引构建脚本，负责导入、清洗与输出
├── app.py                    # Flask Web 服务入口，提供 RESTful 查询接口
├── cli.py                    # CLI 命令行工具实现，基于 click 框架
├── config.yaml               # 全局配置文件（链接源路径、输出目录、调度周期等）
├── requirements.txt          # Python 依赖列表
├── src/                      # 核心源码模块
│   ├── __init__.py
│   ├── fetcher.py            # 链接抓取与 HTTP 健康检查模块
│   ├── parser.py             # URL 解析、归一化与校验逻辑
│   ├── storage.py            # JSON/Markdown 读写与历史快照管理
│   ├── tags.py               # 标签系统增删改查与统计
│   └── exporter.py           # 多格式导出（JSON、Markdown、HTML）
├── tests/                    # 单元测试与集成测试套件
│   ├── test_fetcher.py
│   ├── test_parser.py
│   └── test_storage.py
├── data/                     # 运行时数据目录（索引输出与快照存放）
│   ├── index.json            # 当前完整索引数据
│   ├── index.md              # Markdown 表格视图
│   └── snapshots/            # 历史快照目录（按时间戳命名）
├── docs/                     # 项目文档（用户手册、API 参考等）
│   ├── user-guide.md
│   ├── ops-guide.md
│   └── api-reference.md
└── examples/                 # 示例数据与配置文件模板
    ├── sample_links.json     # 示例链接列表（用于快速体验）
    └── custom_tags.yaml      # 自定义标签预设示例
```

## 贡献指南

1. 在 GitHub 上 Fork 本仓库，并将 Fork 后的仓库克隆到本地开发环境中。建议在 dev 分支上开展工作，避免直接修改 main 分支。

2. 运行 `make setup-dev`（或手动执行 `pip install -r requirements-dev.txt`）安装开发依赖，包括 pytest、ruff 和 pre-commit 钩子。提交前务必执行 `ruff check .` 确保代码风格符合项目规范。

3. 为新增功能或修复的缺陷编写对应的单元测试，测试文件放置在 `tests/` 目录下，命名格式为 `test_*.py`。所有测试用例需在本地通过 `pytest` 全量运行后方可提交。

4. 提交 Pull Request 时请按照模板填写说明，清晰描述改动内容、影响范围以及是否涉及破坏性变更。涉及链接处理逻辑的改动需附带至少三个实际 URL 的测试案例。

5. 文档更新与代码改动同等重要。任何涉及配置项变更、CLI 命令调整或 API 接口修改的 Pull Request，必须同步更新 `docs/` 下对应的文档文件。

## 常见问题

**Q: 项目如何处理目标博客站点反爬策略？**

A: BlogLink Indexer 仅发起轻量级 HEAD 请求用于健康检查，不抓取页面正文内容，且请求间隔默认为 500 毫秒，并支持通过 `config.yaml` 配置 `request_delay` 参数进一步降低请求频率。对于返回 403 或 429 状态码的链接，系统会自动标记为“受限”并跳过后续检测，不会对目标站点造成压力。

**Q: 索引数据是否支持外部数据库存储？**

A: 当前版本以本地文件系统为主要存储后端，输出格式为 JSON 和 Markdown。但系统设计了 `storage.py` 抽象接口，用户可通过继承 `BaseStorage` 类实现 PostgreSQL、MongoDB 或 Elasticsearch 适配器，具体示例可参考 `docs/developer-guide.md` 中的扩展章节。

**Q: 如何处理 URL 中的大小写与尾部斜杠不一致问题？**

A: 导入阶段会自动调用 `parser.normalize_url()` 方法，该方法保留协议与域名大小写，仅对路径部分进行大小写归一化（全部转为小写），并移除尾部多余的斜杠。同时，系统会记录原始 URL 与归一化后 URL 的映射关系，便于追溯。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 15:33:09
