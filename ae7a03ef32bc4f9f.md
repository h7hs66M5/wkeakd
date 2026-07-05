# CMCVRR 技术文章索引与导航系统

CMCVRR 是一个面向开发者与技术研究人员的结构化文章索引项目，旨在对 blog.cmcvrr.cn 平台上的大量技术博文进行系统性梳理、分类与快速导航。本项目不直接托管文章内容，而是提供一套清晰的引用框架，帮助用户在海量历史文章中精准定位所需信息。

项目核心定位为“技术文章外链导航站”，服务于日常开发查资料、技术选型参考、历史方案复盘等场景。通过统一的目录结构、标签体系和快速启动脚本，用户可在本地搭建起一个可检索、可扩展的文章索引环境，极大提升信息获取效率。

## 功能概览

**结构化文章索引**：基于文章ID与分类标签，建立多维度检索路径，支持按技术领域、发布时间、热度排序。

**快速本地部署**：提供一键克隆、依赖安装与启动脚本，五分钟内即可在本地运行索引服务。

**全文元数据缓存**：对每篇文章的标题、摘要、发布时间、关键词进行本地缓存，实现离线检索与快速过滤。

**标签与分类系统**：内置自动标签生成逻辑，可根据文章URL特征与ID区间进行初步归类，并支持手动调整。

**RESTful 查询接口**：提供标准的HTTP API，支持按ID、标签、时间范围等条件查询文章索引记录。

**静态站点生成模式**：支持将索引数据导出为静态HTML文件，便于部署到任意Web服务器或CDN。

**扩展钩子机制**：允许用户编写自定义Python脚本，对新增文章进行自动抓取、解析与索引更新。

## 应用场景

**日常技术查阅**：开发者在遇到特定技术问题时，可通过本地索引快速定位 blog.cmcvrr.cn 上相关的历史文章，无需逐页翻找。

**技术选型参考**：团队在进行框架、库或工具选型时，可借助本索引系统批量查阅相关主题的多篇文章，综合对比不同方案的优劣。

**知识库沉淀**：技术团队可将本索引作为内部知识库的一部分，定期同步更新，沉淀团队关注的技术文章资源。

**离线文档备份**：在网络受限的环境中，用户可提前通过索引缓存文章元数据，并结合第三方下载工具对重要文章进行本地归档。

## 快速开始

以下命令将项目克隆至本地、安装依赖并启动开发服务器。

```bash
# 克隆项目仓库
git clone https://github.com/cmcvrr-index/cmcvrr-navigator.git

# 进入项目目录
cd cmcvrr-navigator

# 安装Python依赖（推荐使用虚拟环境）
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# 初始化本地索引缓存（首次运行需同步元数据）
python manage.py init-index

# 启动开发服务器（默认监听8000端口）
python manage.py runserver
```

启动成功后，访问 http://127.0.0.1:8000 即可使用本地索引查询服务。

## 安装要求

| 依赖 | 必需 | 说明 |
|------|------|------|
| Python 3.8 或更高版本 | 是 | 核心运行环境，用于执行索引管理与API服务 |
| pip 21.0+ | 是 | Python包管理工具，用于安装项目依赖 |
| SQLite 3.35+ | 是 | 本地轻量级数据库，存储文章索引元数据 |
| requests 2.28+ | 是 | 用于发送HTTP请求，获取文章页面信息 |
| beautifulsoup4 4.11+ | 是 | 解析文章HTML，提取标题、正文摘要等元数据 |
| lxml 4.9+ | 是 | 作为BeautifulSoup的解析引擎，提高解析效率 |
| markdown 3.4+ | 否 | 用于将文章摘要渲染为Markdown格式输出 |
| flask 2.2+ | 否 | 若使用Web界面模式，需要Flask框架支持 |
| pytest 7.0+ | 否 | 运行单元测试与集成测试 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|------|------|------------|
| 用户手册 | docs/user-guide.md | 如何使用索引查询、如何添加自定义标签、如何导出静态站点 |
| 开发指南 | docs/developer-guide.md | 如何扩展抓取器、如何修改索引排序逻辑、如何贡献代码 |
| API参考 | docs/api-reference.md | 各REST接口的请求参数、响应格式与状态码说明 |
| 运维手册 | docs/operations.md | 如何定期同步索引、如何备份SQLite数据库、如何迁移至PostgreSQL |
| 常见问题 | docs/faq.md | 文章ID解析失败、标签生成不准确、索引更新速度慢等问题的解决方案 |

## 资源列表

本部分列出项目中引用的全部原始文章链接。按文章ID区间进行分组展示，便于快速浏览。

技术基础与综述类

http://www.blog.cmcvrr.cn/Article/details/3255863.sHtML
http://www.blog.cmcvrr.cn/Article/details/6720.sHtML
http://www.blog.cmcvrr.cn/Article/details/2775244.sHtML
http://www.blog.cmcvrr.cn/Article/details/17578.sHtML
http://www.blog.cmcvrr.cn/Article/details/681287.sHtML
http://www.blog.cmcvrr.cn/Article/details/8778.sHtML
http://www.blog.cmcvrr.cn/Article/details/46741.sHtML
http://www.blog.cmcvrr.cn/Article/details/71908.sHtML
http://www.blog.cmcvrr.cn/Article/details/54595.sHtML
http://www.blog.cmcvrr.cn/Article/details/4347591.sHtML
http://www.blog.cmcvrr.cn/Article/details/2323.sHtML
http://www.blog.cmcvrr.cn/Article/details/7901.sHtML
http://www.blog.cmcvrr.cn/Article/details/4393940.sHtML
http://www.blog.cmcvrr.cn/Article/details/7024956.sHtML
http://www.blog.cmcvrr.cn/Article/details/3906.sHtML
http://www.blog.cmcvrr.cn/Article/details/9883.sHtML
http://www.blog.cmcvrr.cn/Article/details/288903.sHtML
http://www.blog.cmcvrr.cn/Article/details/041531.sHtML

编程语言与框架专题

http://www.blog.cmcvrr.cn/Article/details/9681210.sHtML
http://www.blog.cmcvrr.cn/Article/details/67402.sHtML
http://www.blog.cmcvrr.cn/Article/details/5993.sHtML
http://www.blog.cmcvrr.cn/Article/details/8968773.sHtML
http://www.blog.cmcvrr.cn/Article/details/7985208.sHtML
http://www.blog.cmcvrr.cn/Article/details/7526.sHtML
http://www.blog.cmcvrr.cn/Article/details/4647.sHtML
http://www.blog.cmcvrr.cn/Article/details/8941729.sHtML
http://www.blog.cmcvrr.cn/Article/details/35651.sHtML
http://www.blog.cmcvrr.cn/Article/details/8922051.sHtML
http://www.blog.cmcvrr.cn/Article/details/3654440.sHtML
http://www.blog.cmcvrr.cn/Article/details/445566.sHtML
http://www.blog.cmcvrr.cn/Article/details/61456.sHtML
http://www.blog.cmcvrr.cn/Article/details/133503.sHtML
http://www.blog.cmcvrr.cn/Article/details/16767.sHtML
http://www.blog.cmcvrr.cn/Article/details/4040078.sHtML
http://www.blog.cmcvrr.cn/Article/details/40422.sHtML
http://www.blog.cmcvrr.cn/Article/details/0862.sHtML
http://www.blog.cmcvrr.cn/Article/details/1118909.sHtML

数据库与存储技术

http://www.blog.cmcvrr.cn/Article/details/85627.sHtML
http://www.blog.cmcvrr.cn/Article/details/6884398.sHtML
http://www.blog.cmcvrr.cn/Article/details/2209473.sHtML
http://www.blog.cmcvrr.cn/Article/details/333189.sHtML
http://www.blog.cmcvrr.cn/Article/details/684469.sHtML
http://www.blog.cmcvrr.cn/Article/details/395496.sHtML
http://www.blog.cmcvrr.cn/Article/details/4737.sHtML
http://www.blog.cmcvrr.cn/Article/details/8972421.sHtML
http://www.blog.cmcvrr.cn/Article/details/7805.sHtML
http://www.blog.cmcvrr.cn/Article/details/92063.sHtML
http://www.blog.cmcvrr.cn/Article/details/4343.sHtML
http://www.blog.cmcvrr.cn/Article/details/7669565.sHtML
http://www.blog.cmcvrr.cn/Article/details/1472375.sHtML
http://www.blog.cmcvrr.cn/Article/details/68465.sHtML
http://www.blog.cmcvrr.cn/Article/details/7067488.sHtML
http://www.blog.cmcvrr.cn/Article/details/592202.sHtML
http://www.blog.cmcvrr.cn/Article/details/279709.sHtML
http://www.blog.cmcvrr.cn/Article/details/82665.sHtML
http://www.blog.cmcvrr.cn/Article/details/39187.sHtML

网络与安全技术

http://www.blog.cmcvrr.cn/Article/details/94115.sHtML
http://www.blog.cmcvrr.cn/Article/details/4260.sHtML
http://www.blog.cmcvrr.cn/Article/details/113164.sHtML
http://www.blog.cmcvrr.cn/Article/details/80951.sHtML
http://www.blog.cmcvrr.cn/Article/details/4543200.sHtML
http://www.blog.cmcvrr.cn/Article/details/3784096.sHtML
http://www.blog.cmcvrr.cn/Article/details/9183232.sHtML
http://www.blog.cmcvrr.cn/Article/details/901884.sHtML
http://www.blog.cmcvrr.cn/Article/details/8645685.sHtML
http://www.blog.cmcvrr.cn/Article/details/8221433.sHtML
http://www.blog.cmcvrr.cn/Article/details/781846.sHtML
http://www.blog.cmcvrr.cn/Article/details/7336.sHtML
http://www.blog.cmcvrr.cn/Article/details/18337.sHtML
http://www.blog.cmcvrr.cn/Article/details/3551445.sHtML
http://www.blog.cmcvrr.cn/Article/details/35095.sHtML
http://www.blog.cmcvrr.cn/Article/details/2352.sHtML
http://www.blog.cmcvrr.cn/Article/details/3546.sHtML
http://www.blog.cmcvrr.cn/Article/details/6422843.sHtML

运维与DevOps实践

http://www.blog.cmcvrr.cn/Article/details/91097.sHtML
http://www.blog.cmcvrr.cn/Article/details/67686.sHtML
http://www.blog.cmcvrr.cn/Article/details/5843737.sHtML
http://www.blog.cmcvrr.cn/Article/details/7319.sHtML
http://www.blog.cmcvrr.cn/Article/details/01810.sHtML
http://www.blog.cmcvrr.cn/Article/details/7774.sHtML
http://www.blog.cmcvrr.cn/Article/details/2556337.sHtML
http://www.blog.cmcvrr.cn/Article/details/371382.sHtML
http://www.blog.cmcvrr.cn/Article/details/788680.sHtML
http://www.blog.cmcvrr.cn/Article/details/018528.sHtML
http://www.blog.cmcvrr.cn/Article/details/8633228.sHtML
http://www.blog.cmcvrr.cn/Article/details/490920.sHtML
http://www.blog.cmcvrr.cn/Article/details/822649.sHtML
http://www.blog.cmcvrr.cn/Article/details/1491364.sHtML
http://www.blog.cmcvrr.cn/Article/details/01962.sHtML
http://www.blog.cmcvrr.cn/Article/details/24759.sHtML
http://www.blog.cmcvrr.cn/Article/details/71397.sHtML
http://www.blog.cmcvrr.cn/Article/details/53962.sHtML

云计算与容器化

http://www.blog.cmcvrr.cn/Article/details/50289.sHtML
http://www.blog.cmcvrr.cn/Article/details/501944.sHtML
http://www.blog.cmcvrr.cn/Article/details/15753.sHtML
http://www.blog.cmcvrr.cn/Article/details/83315.sHtML
http://www.blog.cmcvrr.cn/Article/details/4113918.sHtML
http://www.blog.cmcvrr.cn/Article/details/252202.sHtML
http://www.blog.cmcvrr.cn/Article/details/818932.sHtML
http://www.blog.cmcvrr.cn/Article/details/540052.sHtML
http://www.blog.cmcvrr.cn/Article/details/906517.sHtML
http://www.blog.cmcvrr.cn/Article/details/581643.sHtML
http://www.blog.cmcvrr.cn/Article/details/7408129.sHtML
http://www.blog.cmcvrr.cn/Article/details/0875.sHtML
http://www.blog.cmcvrr.cn/Article/details/333807.sHtML
http://www.blog.cmcvrr.cn/Article/details/07674.sHtML
http://www.blog.cmcvrr.cn/Article/details/740932.sHtML
http://www.blog.cmcvrr.cn/Article/details/455883.sHtML
http://www.blog.cmcvrr.cn/Article/details/016456.sHtML
http://www.blog.cmcvrr.cn/Article/details/4330.sHtML

前端与移动端开发

http://www.blog.cmcvrr.cn/Article/details/7530821.sHtML
http://www.blog.cmcvrr.cn/Article/details/6158633.sHtML
http://www.blog.cmcvrr.cn/Article/details/2284.sHtML
http://www.blog.cmcvrr.cn/Article/details/2282559.sHtML
http://www.blog.cmcvrr.cn/Article/details/074497.sHtML
http://www.blog.cmcvrr.cn/Article/details/45128.sHtML
http://www.blog.cmcvrr.cn/Article/details/8858123.sHtML
http://www.blog.cmcvrr.cn/Article/details/1941.sHtML
http://www.blog.cmcvrr.cn/Article/details/78304.sHtML
http://www.blog.cmcvrr.cn/Article/details/71201.sHtML
http://www.blog.cmcvrr.cn/Article/details/3763573.sHtML
http://www.blog.cmcvrr.cn/Article/details/9022142.sHtML
http://www.blog.cmcvrr.cn/Article/details/3205685.sHtML
http://www.blog.cmcvrr.cn/Article/details/25965.sHtML
http://www.blog.cmcvrr.cn/Article/details/5327843.sHtML
http://www.blog.cmcvrr.cn/Article/details/0018544.sHtML
http://www.blog.cmcvrr.cn/Article/details/926685.sHtML
http://www.blog.cmcvrr.cn/Article/details/000526.sHtML

算法与数据结构

http://www.blog.cmcvrr.cn/Article/details/26563.sHtML
http://www.blog.cmcvrr.cn/Article/details/7320.sHtML
http://www.blog.cmcvrr.cn/Article/details/63338.sHtML
http://www.blog.cmcvrr.cn/Article/details/190356.sHtML
http://www.blog.cmcvrr.cn/Article/details/4650.sHtML
http://www.blog.cmcvrr.cn/Article/details/952280.sHtML
http://www.blog.cmcvrr.cn/Article/details/5707471.sHtML
http://www.blog.cmcvrr.cn/Article/details/33905.sHtML
http://www.blog.cmcvrr.cn/Article/details/25014.sHtML
http://www.blog.cmcvrr.cn/Article/details/2599.sHtML
http://www.blog.cmcvrr.cn/Article/details/4916697.sHtML
http://www.blog.cmcvrr.cn/Article/details/3354621.sHtML
http://www.blog.cmcvrr.cn/Article/details/1598.sHtML
http://www.blog.cmcvrr.cn/Article/details/5960811.sHtML
http://www.blog.cmcvrr.cn/Article/details/619155.sHtML
http://www.blog.cmcvrr.cn/Article/details/38450.sHtML
http://www.blog.cmcvrr.cn/Article/details/3514.sHtML
http://www.blog.cmcvrr.cn/Article/details/3951.sHtML

架构设计与系统分析

http://www.blog.cmcvrr.cn/Article/details/0446.sHtML
http://www.blog.cmcvrr.cn/Article/details/4510.sHtML
http://www.blog.cmcvrr.cn/Article/details/2213625.sHtML
http://www.blog.cmcvrr.cn/Article/details/1741618.sHtML
http://www.blog.cmcvrr.cn/Article/details/4107.sHtML
http://www.blog.cmcvrr.cn/Article/details/0892.sHtML
http://www.blog.cmcvrr.cn/Article/details/7305.sHtML
http://www.blog.cmcvrr.cn/Article/details/74017.sHtML
http://www.blog.cmcvrr.cn/Article/details/8608118.sHtML
http://www.blog.cmcvrr.cn/Article/details/83997.sHtML
http://www.blog.cmcvrr.cn/Article/details/073791.sHtML
http://www.blog.cmcvrr.cn/Article/details/9064.sHtML
http://www.blog.cmcvrr.cn/Article/details/16163.sHtML
http://www.blog.cmcvrr.cn/Article/details/45500.sHtML
http://www.blog.cmcvrr.cn/Article/details/72209.sHtML
http://www.blog.cmcvrr.cn/Article/details/878552.sHtML
http://www.blog.cmcvrr.cn/Article/details/1129.sHtML
http://www.blog.cmcvrr.cn/Article/details/6898015.sHtML

大数据与人工智能

http://www.blog.cmcvrr.cn/Article/details/104247.sHtML
http://www.blog.cmcvrr.cn/Article/details/3703984.sHtML
http://www.blog.cmcvrr.cn/Article/details/8346.sHtML
http://www.blog.cmcvrr.cn/Article/details/2666080.sHtML
http://www.blog.cmcvrr.cn/Article/details/591818.sHtML
http://www.blog.cmcvrr.cn/Article/details/93173.sHtML
http://www.blog.cmcvrr.cn/Article/details/021208.sHtML
http://www.blog.cmcvrr.cn/Article/details/0054.sHtML
http://www.blog.cmcvrr.cn/Article/details/8307296.sHtML
http://www.blog.cmcvrr.cn/Article/details/357746.sHtML
http://www.blog.cmcvrr.cn/Article/details/9639.sHtML
http://www.blog.cmcvrr.cn/Article/details/08893.sHtML
http://www.blog.cmcvrr.cn/Article/details/7378038.sHtML
http://www.blog.cmcvrr.cn/Article/details/25750.sHtML
http://www.blog.cmcvrr.cn/Article/details/0454609.sHtML
http://www.blog.cmcvrr.cn/Article/details/6330.sHtML
http://www.blog.cmcvrr.cn/Article/details/6915709.sHtML
http://www.blog.cmcvrr.cn/Article/details/6334265.sHtML

性能优化与调优

http://www.blog.cmcvrr.cn/Article/details/82478.sHtML
http://www.blog.cmcvrr.cn/Article/details/4334.sHtML
http://www.blog.cmcvrr.cn/Article/details/962381.sHtML
http://www.blog.cmcvrr.cn/Article/details/981730.sHtML
http://www.blog.cmcvrr.cn/Article/details/028644.sHtML
http://www.blog.cmcvrr.cn/Article/details/66251.sHtML
http://www.blog.cmcvrr.cn/Article/details/1689.sHtML
http://www.blog.cmcvrr.cn/Article/details/3741607.sHtML
http://www.blog.cmcvrr.cn/Article/details/89321.sHtML
http://www.blog.cmcvrr.cn/Article/details/61170.sHtML
http://www.blog.cmcvrr.cn/Article/details/585282.sHtML
http://www.blog.cmcvrr.cn/Article/details/5566.sHtML
http://www.blog.cmcvrr.cn/Article/details/9488891.sHtML
http://www.blog.cmcvrr.cn/Article/details/88170.sHtML
http://www.blog.cmcvrr.cn/Article/details/885791.sHtML
http://www.blog.cmcvrr.cn/Article/details/598719.sHtML
http://www.blog.cmcvrr.cn/Article/details/0012061.sHtML
http://www.blog.cmcvrr.cn/Article/details/1839884.sHtML

开源与社区生态

http://www.blog.cmcvrr.cn/Article/details/887344.sHtML
http://www.blog.cmcvrr.cn/Article/details/6132597.sHtML
http://www.blog.cmcvrr.cn/Article/details/6360166.sHtML
http://www.blog.cmcvrr.cn/Article/details/7216627.sHtML
http://www.blog.cmcvrr.cn/Article/details/7901554.sHtML
http://www.blog.cmcvrr.cn/Article/details/252660.sHtML
http://www.blog.cmcvrr.cn/Article/details/0651402.sHtML
http://www.blog.cmcvrr.cn/Article/details/3070.sHtML
http://www.blog.cmcvrr.cn/Article/details/1464512.sHtML
http://www.blog.cmcvrr.cn/Article/details/682461.sHtML
http://www.blog.cmcvrr.cn/Article/details/92404.sHtML
http://www.blog.cmcvrr.cn/Article/details/7056.sHtML
http://www.blog.cmcvrr.cn/Article/details/27293.sHtML
http://www.blog.cmcvrr.cn/Article/details/1743.sHtML
http://www.blog.cmcvrr.cn/Article/details/076404.sHtML
http://www.blog.cmcvrr.cn/Article/details/921638.sHtML
http://www.blog.cmcvrr.cn/Article/details/3574908.sHtML
http://www.blog.cmcvrr.cn/Article/details/435168.sHtML

测试与质量保障

http://www.blog.cmcvrr.cn/Article/details/771501.sHtML
http://www.blog.cmcvrr.cn/Article/details/68942.sHtML
http://www.blog.cmcvrr.cn/Article/details/0399.sHtML
http://www.blog.cmcvrr.cn/Article/details/0930.sHtML
http://www.blog.cmcvrr.cn/Article/details/3604.sHtML
http://www.blog.cmcvrr.cn/Article/details/032914.sHtML
http://www.blog.cmcvrr.cn/Article/details/45427.sHtML
http://www.blog.cmcvrr.cn/Article/details/837837.sHtML
http://www.blog.cmcvrr.cn/Article/details/67916.sHtML
http://www.blog.cmcvrr.cn/Article/details/4449.sHtML
http://www.blog.cmcvrr.cn/Article/details/357530.sHtML
http://www.blog.cmcvrr.cn/Article/details/1467.sHtML
http://www.blog.cmcvrr.cn/Article/details/399193.sHtML
http://www.blog.cmcvrr.cn/Article/details/87560.sHtML
http://www.blog.cmcvrr.cn/Article/details/2783.sHtML
http://www.blog.cmcvrr.cn/Article/details/0221.sHtML
http://www.blog.cmcvrr.cn/Article/details/7821757.sHtML
http://www.blog.cmcvrr.cn/Article/details/51962.sHtML

项目管理与敏捷实践

http://www.blog.cmcvrr.cn/Article/details/0751140.sHtML
http://www.blog.cmcvrr.cn/Article/details/0030.sHtML
http://www.blog.cmcvrr.cn/Article/details/7330.sHtML
http://www.blog.cmcvrr.cn/Article/details/1468.sHtML
http://www.blog.cmcvrr.cn/Article/details/959888.sHtML
http://www.blog.cmcvrr.cn/Article/details/5108788.sHtML
http://www.blog.cmcvrr.cn/Article/details/28623.sHtML
http://www.blog.cmcvrr.cn/Article/details/3499.sHtML
http://www.blog.cmcvrr.cn/Article/details/21947.sHtML
http://www.blog.cmcvrr.cn/Article/details/0977.sHtML
http://www.blog.cmcvrr.cn/Article/details/0926824.sHtML
http://www.blog.cmcvrr.cn/Article/details/7587.sHtML
http://www.blog.cmcvrr.cn/Article/details/90022.sHtML
http://www.blog.cmcvrr.cn/Article/details/52671.sHtML

## 项目结构

```
cmcvrr-navigator/
├── indexer/                           # 核心索引模块
│   ├── __init__.py                    # 模块初始化，导出主要类
│   ├── crawler.py                     # 文章抓取器，负责HTTP请求与HTML解析
│   ├── parser.py                      # 元数据解析器，提取标题、标签、发布时间
│   ├── indexer.py                     # 索引管理器，控制增删改查操作
│   └── tags.py                        # 自动标签生成与分类逻辑
├── api/                               # RESTful API 服务模块
│   ├── __init__.py                    # 路由注册与蓝图定义
│   ├── routes.py                      # 各API端点的路由处理函数
│   ├── serializers.py                 # 响应数据序列化与校验
│   └── middleware.py                  # 请求日志、跨域、限流等中间件
├── storage/                           # 存储适配层
│   ├── __init__.py                    # 存储工厂方法
│   ├── sqlite_store.py                # SQLite数据库实现
│   ├── memory_store.py                # 内存存储（用于测试）
│   └── schema.sql                     # 数据库表结构定义
├── static/                            # 静态站点生成输出目录
│   ├── index.html                     # 首页索引列表
│   ├── tags.html                      # 标签聚合页面
│   └── articles/                      # 每篇文章的详情页
│       └── {article_id}.html          # 按文章ID生成的静态页面
├── tests/                             # 单元测试与集成测试
│   ├── test_crawler.py                # 抓取器功能测试
│   ├── test_parser.py                 # 解析器功能测试
│   ├── test_api.py                    # API接口测试
│   └── fixtures/                      # 测试用的模拟数据
│       └── sample_article.html        # 样例HTML响应体
├── scripts/                           # 运维辅助脚本
│   ├── sync_index.py                  # 手动触发索引同步
│   ├── export_static.py               # 导出静态HTML站点
│   └── backup_db.py                   # 备份SQLite数据库文件
├── docs/                              # 项目文档（详见文档导航表格）
│   ├── user-guide.md
│   ├── developer-guide.md
│   ├── api-reference.md
│   ├── operations.md
│   └── faq.md
├── config.py                          # 全局配置文件（数据库路径、端口、超时等）
├── requirements.txt                   # Python依赖列表（锁定版本）
├── manage.py                          # 统一命令行入口（init-index, runserver, sync）
├── LICENSE                            # MIT许可证文件
└── README.md                          # 项目说明文档（本文件）
```

## 贡献指南

1.  Fork 本仓库至个人账户，并在本地 clone 已 fork 的仓库。请确保使用最新的 main 分支作为基准。

2.  创建新的功能分支（如 feature/add-tag-rule），所有开发工作均在该分支上进行，避免直接修改 main 分支。

3.  编写或修改代码后，请运行 tests 目录下的全部测试用例，确保现有功能未被破坏。新增功能需附带对应的单元测试。

4.  提交代码时，请遵循约定的提交信息格式：`<类型>: <简短描述>`，类型包括 feat、fix、docs、style、refactor、test、chore。

5.  发起 Pull Request 至本仓库的 main 分支，并在 PR 描述中清晰说明改动目的、实现方式及测试覆盖情况。PR 需至少一名维护者审核通过后方可合并。

## 常见问题

**Q: 索引同步时提示“文章ID解析失败”，应如何排查？**

A: 该问题通常源于目标文章页面结构发生变化或网络请求超时。建议首先检查网络连通性，确保可正常访问 blog.cmcvrr.cn。若网络正常，可尝试手动访问对应的文章URL，确认页面是否返回200状态码。若页面结构确有变动，请修改 indexer/parser.py 中的解析规则，并提交相应的PR。亦可临时使用 --skip-errors 参数跳过失败条目。

**Q: 本地SQLite数据库体积增长过快，如何优化？**

A: SQLite数据库体积增长主要源于文章元数据缓存及历史同步记录。可定期执行 `python manage.py vacuum` 命令进行数据库收缩。若需保留更少的历史版本，可在 config.py 中调整 `MAX_HISTORY_RECORDS` 参数，限制每个文章ID仅保留最近N条更新记录。亦可考虑迁移至PostgreSQL以支持更大数据量。

**Q: 静态站点导出后，部分文章的摘要显示不完整，如何解决？**

A: 摘要显示不完整通常是因为原始文章正文提取失败。可尝试在 indexer/parser.py 中调整正文选择器（如改为 `article` 或 `.content` 等通用类名）。对于特定异常情况，可在 `config.py` 中配置 `CUSTOM_PARSER_RULES`，为指定的文章ID或URL前缀单独设定解析规则。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 15:34:56
