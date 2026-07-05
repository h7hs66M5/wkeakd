# LinkHub CMS

LinkHub CMS 是一个面向技术内容聚合场景的轻量级文章链接管理与导航系统。项目定位于为开发者、技术博主以及内容运营者提供一套标准化的外链资源归集与展示方案，解决分散在各个平台的技术文章难以统一检索、归类与分享的问题。

LinkHub CMS 本身不存储文章正文，而是通过结构化的链接条目、分类标签、来源站点与发布时间等元数据，构建一个高可读性的技术资源导航站。目标用户包括个人博客站长、开源项目文档维护者、技术社区运营人员以及需要批量管理学习资料的后端开发者。

## 功能概览

**批量链接导入**：支持从 CSV、JSON 及 Markdown 列表批量导入文章链接，自动解析 URL 中的站点、路径与扩展名信息。

**自动分类与标签推荐**：基于链接中的目录结构（如 /Article/details/）与数字 ID 模式，自动归类到预设的技术栈或主题分组。

**多维度检索过滤**：按来源域名、ID 范围、导入批次（如第 64/280 批）等条件过滤链接列表，支持正则表达式高级搜索。

**链接状态健康检查**：周期性对已收录链接发起 HEAD 请求，标记不可达或响应超时的条目，输出异常报告。

**只读展示模式**：生成静态只读的资源导航页面，可直接部署到任何静态托管服务，无需数据库支持。

**数据快照导出**：将当前链接集合导出为 SQLite 数据库文件或 JSON 结构化数据，便于离线备份与二次开发。

## 应用场景

技术博客的友情链接或推荐阅读页面：个人技术博主可以使用 LinkHub CMS 整理自己常读的优质文章列表，生成一个整洁的推荐阅读页面供访客浏览。

开源项目文档的外部资源附录：开源项目维护者可以在项目 Wiki 或文档站中嵌入 LinkHub CMS 生成的链接列表，集中列出相关的社区教程、视频讲解或扩展阅读材料。

技术社群的知识库建设：技术交流群或社区运营人员可将群内分享过的优质文章链接统一归集到 LinkHub CMS 中，形成可积累、可检索的社群知识库。

个人学习路径的链接备忘：开发者可以将自己在学习某个技术领域（如后端架构、前端工程化）过程中查阅的文章链接全部导入，按主题分类后作为个人学习索引。

## 快速开始

以下步骤帮助你在本地环境中快速启动 LinkHub CMS 服务。

```bash
# 1. 克隆项目仓库
git clone https://github.com/linkhub-cms/linkhub-core.git
cd linkhub-core

# 2. 安装依赖（使用 Python 3.9+ 与 pip）
pip install -r requirements.txt

# 3. 初始化本地数据库与配置
python manage.py init --db sqlite:///linkhub.db

# 4. 导入示例链接数据（包含当前批次）
python manage.py import --source ./data/sample_links.json

# 5. 启动开发服务器
python manage.py runserver --host 0.0.0.0 --port 8080
```

访问 http://localhost:8080 即可查看本地的资源导航页面。生产环境部署请参考后续的文档导航章节。

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.9 或更高 | 核心运行环境，推荐使用 3.11 |
| SQLite | 3.35 或更高 | 默认嵌入式数据库，无需额外安装 |
| pip | 22.0 或更高 | Python 包依赖管理工具 |
| virtualenv | 20.0 或更高 | 推荐用于创建独立的 Python 虚拟环境 |
| curl | 7.68 或更高 | 用于链接健康检查中的 HTTP 探测 |
| git | 2.25 或更高 | 用于克隆项目源码和版本管理 |
| make | 3.82 或更高 | 辅助执行常用开发命令（可选） |
| pytest | 7.0 或更高 | 仅开发测试时需要，生产环境可不安装 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 入门指南 | docs/quickstart.md | 如何 5 分钟内完成安装并导入第一批链接数据 |
| 数据导入 | docs/import.md | 支持哪些导入格式、如何自定义字段映射 |
| 分类配置 | docs/categories.md | 如何新增、修改或合并链接分类规则 |
| 部署运维 | docs/deployment.md | 如何部署到生产服务器、如何配置反向代理 |
| API 参考 | docs/api_reference.md | 对外提供的 RESTful API 端点及参数说明 |
| 性能调优 | docs/performance.md | 当链接数超过 10 万条时如何优化查询速度 |

## 资源列表

以下为第 64/280 批次收录的全部原始链接，按站点域名分组归集。所有 URL 均保留用户提供的原始格式，未作任何协议、域名或路径改写。

站点主域：http://www.blog.hcbezg.cn

Article 路径下的全部链接：

http://www.blog.hcbezg.cn/Article/details/7318.sHtML
http://www.blog.hcbezg.cn/Article/details/153629.sHtML
http://www.blog.hcbezg.cn/Article/details/83461.sHtML
http://www.blog.hcbezg.cn/Article/details/5106.sHtML
http://www.blog.hcbezg.cn/Article/details/7811.sHtML
http://www.blog.hcbezg.cn/Article/details/6096.sHtML
http://www.blog.hcbezg.cn/Article/details/58195.sHtML
http://www.blog.hcbezg.cn/Article/details/06110.sHtML
http://www.blog.hcbezg.cn/Article/details/223662.sHtML
http://www.blog.hcbezg.cn/Article/details/981837.sHtML
http://www.blog.hcbezg.cn/Article/details/9066.sHtML
http://www.blog.hcbezg.cn/Article/details/0083781.sHtML
http://www.blog.hcbezg.cn/Article/details/472483.sHtML
http://www.blog.hcbezg.cn/Article/details/8414.sHtML
http://www.blog.hcbezg.cn/Article/details/1099.sHtML
http://www.blog.hcbezg.cn/Article/details/9440626.sHtML
http://www.blog.hcbezg.cn/Article/details/362892.sHtML
http://www.blog.hcbezg.cn/Article/details/5952018.sHtML
http://www.blog.hcbezg.cn/Article/details/1755084.sHtML
http://www.blog.hcbezg.cn/Article/details/55812.sHtML
http://www.blog.hcbezg.cn/Article/details/2630.sHtML
http://www.blog.hcbezg.cn/Article/details/426245.sHtML
http://www.blog.hcbezg.cn/Article/details/8036033.sHtML
http://www.blog.hcbezg.cn/Article/details/20436.sHtML
http://www.blog.hcbezg.cn/Article/details/4602.sHtML
http://www.blog.hcbezg.cn/Article/details/5951045.sHtML
http://www.blog.hcbezg.cn/Article/details/3280937.sHtML
http://www.blog.hcbezg.cn/Article/details/3737.sHtML
http://www.blog.hcbezg.cn/Article/details/967554.sHtML
http://www.blog.hcbezg.cn/Article/details/321367.sHtML
http://www.blog.hcbezg.cn/Article/details/9555655.sHtML
http://www.blog.hcbezg.cn/Article/details/32253.sHtML
http://www.blog.hcbezg.cn/Article/details/93374.sHtML
http://www.blog.hcbezg.cn/Article/details/3356876.sHtML
http://www.blog.hcbezg.cn/Article/details/914658.sHtML
http://www.blog.hcbezg.cn/Article/details/74628.sHtML
http://www.blog.hcbezg.cn/Article/details/0309242.sHtML
http://www.blog.hcbezg.cn/Article/details/7118569.sHtML
http://www.blog.hcbezg.cn/Article/details/90038.sHtML
http://www.blog.hcbezg.cn/Article/details/0990530.sHtML
http://www.blog.hcbezg.cn/Article/details/2972020.sHtML
http://www.blog.hcbezg.cn/Article/details/8427.sHtML
http://www.blog.hcbezg.cn/Article/details/1589804.sHtML
http://www.blog.hcbezg.cn/Article/details/0717708.sHtML
http://www.blog.hcbezg.cn/Article/details/1164.sHtML
http://www.blog.hcbezg.cn/Article/details/09942.sHtML
http://www.blog.hcbezg.cn/Article/details/5666.sHtML
http://www.blog.hcbezg.cn/Article/details/508586.sHtML
http://www.blog.hcbezg.cn/Article/details/0356177.sHtML
http://www.blog.hcbezg.cn/Article/details/581018.sHtML
http://www.blog.hcbezg.cn/Article/details/3986.sHtML
http://www.blog.hcbezg.cn/Article/details/99096.sHtML
http://www.blog.hcbezg.cn/Article/details/15553.sHtML
http://www.blog.hcbezg.cn/Article/details/41421.sHtML
http://www.blog.hcbezg.cn/Article/details/3495.sHtML
http://www.blog.hcbezg.cn/Article/details/4167157.sHtML
http://www.blog.hcbezg.cn/Article/details/2375.sHtML
http://www.blog.hcbezg.cn/Article/details/861614.sHtML
http://www.blog.hcbezg.cn/Article/details/58299.sHtML
http://www.blog.hcbezg.cn/Article/details/9642875.sHtML
http://www.blog.hcbezg.cn/Article/details/7809.sHtML
http://www.blog.hcbezg.cn/Article/details/00823.sHtML
http://www.blog.hcbezg.cn/Article/details/9637796.sHtML
http://www.blog.hcbezg.cn/Article/details/99523.sHtML
http://www.blog.hcbezg.cn/Article/details/7963.sHtML
http://www.blog.hcbezg.cn/Article/details/698445.sHtML
http://www.blog.hcbezg.cn/Article/details/506749.sHtML
http://www.blog.hcbezg.cn/Article/details/98471.sHtML
http://www.blog.hcbezg.cn/Article/details/6405.sHtML
http://www.blog.hcbezg.cn/Article/details/138775.sHtML
http://www.blog.hcbezg.cn/Article/details/235268.sHtML
http://www.blog.hcbezg.cn/Article/details/8357867.sHtML
http://www.blog.hcbezg.cn/Article/details/2947.sHtML
http://www.blog.hcbezg.cn/Article/details/5208.sHtML
http://www.blog.hcbezg.cn/Article/details/77530.sHtML
http://www.blog.hcbezg.cn/Article/details/676236.sHtML
http://www.blog.hcbezg.cn/Article/details/4765042.sHtML
http://www.blog.hcbezg.cn/Article/details/968389.sHtML
http://www.blog.hcbezg.cn/Article/details/32375.sHtML
http://www.blog.hcbezg.cn/Article/details/2407.sHtML
http://www.blog.hcbezg.cn/Article/details/4266984.sHtML
http://www.blog.hcbezg.cn/Article/details/2931415.sHtML
http://www.blog.hcbezg.cn/Article/details/5101.sHtML
http://www.blog.hcbezg.cn/Article/details/5687.sHtML
http://www.blog.hcbezg.cn/Article/details/279583.sHtML
http://www.blog.hcbezg.cn/Article/details/3325.sHtML
http://www.blog.hcbezg.cn/Article/details/0985573.sHtML
http://www.blog.hcbezg.cn/Article/details/81891.sHtML
http://www.blog.hcbezg.cn/Article/details/390490.sHtML
http://www.blog.hcbezg.cn/Article/details/56368.sHtML
http://www.blog.hcbezg.cn/Article/details/0707533.sHtML
http://www.blog.hcbezg.cn/Article/details/3941233.sHtML
http://www.blog.hcbezg.cn/Article/details/6872099.sHtML
http://www.blog.hcbezg.cn/Article/details/085595.sHtML
http://www.blog.hcbezg.cn/Article/details/0993487.sHtML
http://www.blog.hcbezg.cn/Article/details/0307429.sHtML
http://www.blog.hcbezg.cn/Article/details/192450.sHtML
http://www.blog.hcbezg.cn/Article/details/7578.sHtML
http://www.blog.hcbezg.cn/Article/details/6134551.sHtML
http://www.blog.hcbezg.cn/Article/details/96043.sHtML
http://www.blog.hcbezg.cn/Article/details/2211166.sHtML
http://www.blog.hcbezg.cn/Article/details/136900.sHtML
http://www.blog.hcbezg.cn/Article/details/9586.sHtML
http://www.blog.hcbezg.cn/Article/details/98577.sHtML
http://www.blog.hcbezg.cn/Article/details/419118.sHtML
http://www.blog.hcbezg.cn/Article/details/000576.sHtML
http://www.blog.hcbezg.cn/Article/details/298418.sHtML
http://www.blog.hcbezg.cn/Article/details/0490460.sHtML
http://www.blog.hcbezg.cn/Article/details/7688.sHtML
http://www.blog.hcbezg.cn/Article/details/094981.sHtML
http://www.blog.hcbezg.cn/Article/details/2437686.sHtML
http://www.blog.hcbezg.cn/Article/details/3300754.sHtML
http://www.blog.hcbezg.cn/Article/details/05996.sHtML
http://www.blog.hcbezg.cn/Article/details/76943.sHtML
http://www.blog.hcbezg.cn/Article/details/7324.sHtML
http://www.blog.hcbezg.cn/Article/details/1076.sHtML
http://www.blog.hcbezg.cn/Article/details/3815.sHtML
http://www.blog.hcbezg.cn/Article/details/456724.sHtML
http://www.blog.hcbezg.cn/Article/details/1834.sHtML
http://www.blog.hcbezg.cn/Article/details/2489705.sHtML
http://www.blog.hcbezg.cn/Article/details/901514.sHtML
http://www.blog.hcbezg.cn/Article/details/1437.sHtML
http://www.blog.hcbezg.cn/Article/details/430340.sHtML
http://www.blog.hcbezg.cn/Article/details/53473.sHtML
http://www.blog.hcbezg.cn/Article/details/6299.sHtML
http://www.blog.hcbezg.cn/Article/details/27318.sHtML
http://www.blog.hcbezg.cn/Article/details/21589.sHtML
http://www.blog.hcbezg.cn/Article/details/025045.sHtML
http://www.blog.hcbezg.cn/Article/details/9796.sHtML
http://www.blog.hcbezg.cn/Article/details/917783.sHtML
http://www.blog.hcbezg.cn/Article/details/89848.sHtML
http://www.blog.hcbezg.cn/Article/details/132626.sHtML
http://www.blog.hcbezg.cn/Article/details/9616.sHtML
http://www.blog.hcbezg.cn/Article/details/6348.sHtML
http://www.blog.hcbezg.cn/Article/details/7831.sHtML
http://www.blog.hcbezg.cn/Article/details/0975.sHtML
http://www.blog.hcbezg.cn/Article/details/9052134.sHtML
http://www.blog.hcbezg.cn/Article/details/3482147.sHtML
http://www.blog.hcbezg.cn/Article/details/89038.sHtML
http://www.blog.hcbezg.cn/Article/details/657335.sHtML
http://www.blog.hcbezg.cn/Article/details/303728.sHtML
http://www.blog.hcbezg.cn/Article/details/9606.sHtML
http://www.blog.hcbezg.cn/Article/details/19357.sHtML
http://www.blog.hcbezg.cn/Article/details/3498860.sHtML
http://www.blog.hcbezg.cn/Article/details/0294.sHtML
http://www.blog.hcbezg.cn/Article/details/91923.sHtML
http://www.blog.hcbezg.cn/Article/details/2650.sHtML
http://www.blog.hcbezg.cn/Article/details/6869271.sHtML
http://www.blog.hcbezg.cn/Article/details/42260.sHtML
http://www.blog.hcbezg.cn/Article/details/658460.sHtML
http://www.blog.hcbezg.cn/Article/details/6340107.sHtML
http://www.blog.hcbezg.cn/Article/details/9146.sHtML
http://www.blog.hcbezg.cn/Article/details/07915.sHtML
http://www.blog.hcbezg.cn/Article/details/047046.sHtML
http://www.blog.hcbezg.cn/Article/details/9476.sHtML
http://www.blog.hcbezg.cn/Article/details/39840.sHtML
http://www.blog.hcbezg.cn/Article/details/6675.sHtML
http://www.blog.hcbezg.cn/Article/details/68909.sHtML
http://www.blog.hcbezg.cn/Article/details/743041.sHtML
http://www.blog.hcbezg.cn/Article/details/42926.sHtML
http://www.blog.hcbezg.cn/Article/details/2026.sHtML
http://www.blog.hcbezg.cn/Article/details/7841.sHtML
http://www.blog.hcbezg.cn/Article/details/99582.sHtML
http://www.blog.hcbezg.cn/Article/details/152089.sHtML
http://www.blog.hcbezg.cn/Article/details/87703.sHtML
http://www.blog.hcbezg.cn/Article/details/1934.sHtML
http://www.blog.hcbezg.cn/Article/details/7893.sHtML
http://www.blog.hcbezg.cn/Article/details/0925536.sHtML
http://www.blog.hcbezg.cn/Article/details/141154.sHtML
http://www.blog.hcbezg.cn/Article/details/86852.sHtML
http://www.blog.hcbezg.cn/Article/details/39930.sHtML
http://www.blog.hcbezg.cn/Article/details/996978.sHtML
http://www.blog.hcbezg.cn/Article/details/4272.sHtML
http://www.blog.hcbezg.cn/Article/details/1693029.sHtML
http://www.blog.hcbezg.cn/Article/details/4130.sHtML
http://www.blog.hcbezg.cn/Article/details/3138.sHtML
http://www.blog.hcbezg.cn/Article/details/498489.sHtML
http://www.blog.hcbezg.cn/Article/details/71781.sHtML
http://www.blog.hcbezg.cn/Article/details/5844.sHtML
http://www.blog.hcbezg.cn/Article/details/788123.sHtML
http://www.blog.hcbezg.cn/Article/details/89470.sHtML
http://www.blog.hcbezg.cn/Article/details/01219.sHtML
http://www.blog.hcbezg.cn/Article/details/049769.sHtML
http://www.blog.hcbezg.cn/Article/details/1087741.sHtML
http://www.blog.hcbezg.cn/Article/details/6780148.sHtML
http://www.blog.hcbezg.cn/Article/details/139092.sHtML
http://www.blog.hcbezg.cn/Article/details/390590.sHtML
http://www.blog.hcbezg.cn/Article/details/0952328.sHtML
http://www.blog.hcbezg.cn/Article/details/4983370.sHtML
http://www.blog.hcbezg.cn/Article/details/536402.sHtML
http://www.blog.hcbezg.cn/Article/details/7968240.sHtML
http://www.blog.hcbezg.cn/Article/details/417720.sHtML
http://www.blog.hcbezg.cn/Article/details/7315231.sHtML
http://www.blog.hcbezg.cn/Article/details/2358936.sHtML
http://www.blog.hcbezg.cn/Article/details/6473257.sHtML
http://www.blog.hcbezg.cn/Article/details/527773.sHtML
http://www.blog.hcbezg.cn/Article/details/527278.sHtML
http://www.blog.hcbezg.cn/Article/details/3173.sHtML
http://www.blog.hcbezg.cn/Article/details/2211409.sHtML
http://www.blog.hcbezg.cn/Article/details/55063.sHtML
http://www.blog.hcbezg.cn/Article/details/91863.sHtML
http://www.blog.hcbezg.cn/Article/details/1217999.sHtML
http://www.blog.hcbezg.cn/Article/details/4831976.sHtML
http://www.blog.hcbezg.cn/Article/details/4909.sHtML
http://www.blog.hcbezg.cn/Article/details/1203895.sHtML
http://www.blog.hcbezg.cn/Article/details/3582733.sHtML
http://www.blog.hcbezg.cn/Article/details/1291.sHtML
http://www.blog.hcbezg.cn/Article/details/6182.sHtML
http://www.blog.hcbezg.cn/Article/details/4085.sHtML
http://www.blog.hcbezg.cn/Article/details/840218.sHtML
http://www.blog.hcbezg.cn/Article/details/74740.sHtML
http://www.blog.hcbezg.cn/Article/details/2135.sHtML
http://www.blog.hcbezg.cn/Article/details/351163.sHtML
http://www.blog.hcbezg.cn/Article/details/56375.sHtML
http://www.blog.hcbezg.cn/Article/details/382696.sHtML
http://www.blog.hcbezg.cn/Article/details/3250417.sHtML
http://www.blog.hcbezg.cn/Article/details/232357.sHtML
http://www.blog.hcbezg.cn/Article/details/234453.sHtML
http://www.blog.hcbezg.cn/Article/details/1309277.sHtML
http://www.blog.hcbezg.cn/Article/details/406114.sHtML
http://www.blog.hcbezg.cn/Article/details/040697.sHtML
http://www.blog.hcbezg.cn/Article/details/2307878.sHtML
http://www.blog.hcbezg.cn/Article/details/04583.sHtML
http://www.blog.hcbezg.cn/Article/details/7271.sHtML
http://www.blog.hcbezg.cn/Article/details/6804014.sHtML
http://www.blog.hcbezg.cn/Article/details/38827.sHtML
http://www.blog.hcbezg.cn/Article/details/6880.sHtML
http://www.blog.hcbezg.cn/Article/details/454844.sHtML
http://www.blog.hcbezg.cn/Article/details/3017014.sHtML
http://www.blog.hcbezg.cn/Article/details/400563.sHtML
http://www.blog.hcbezg.cn/Article/details/781111.sHtML
http://www.blog.hcbezg.cn/Article/details/17568.sHtML
http://www.blog.hcbezg.cn/Article/details/24068.sHtML
http://www.blog.hcbezg.cn/Article/details/5058207.sHtML
http://www.blog.hcbezg.cn/Article/details/2142048.sHtML
http://www.blog.hcbezg.cn/Article/details/8925.sHtML
http://www.blog.hcbezg.cn/Article/details/5360262.sHtML
http://www.blog.hcbezg.cn/Article/details/58619.sHtML
http://www.blog.hcbezg.cn/Article/details/976860.sHtML
http://www.blog.hcbezg.cn/Article/details/1820.sHtML
http://www.blog.hcbezg.cn/Article/details/1326.sHtML
http://www.blog.hcbezg.cn/Article/details/229485.sHtML
http://www.blog.hcbezg.cn/Article/details/9372.sHtML
http://www.blog.hcbezg.cn/Article/details/2742.sHtML
http://www.blog.hcbezg.cn/Article/details/6322711.sHtML
http://www.blog.hcbezg.cn/Article/details/449929.sHtML
http://www.blog.hcbezg.cn/Article/details/320014.sHtML
http://www.blog.hcbezg.cn/Article/details/20540.sHtML
http://www.blog.hcbezg.cn/Article/details/82919.sHtML
http://www.blog.hcbezg.cn/Article/details/2923954.sHtML

共计收录 250 条链接，全部归属于同一来源站点。

## 项目结构

项目采用标准的 Python Web 应用布局，核心模块与目录说明如下。

```
linkhub-core/
├── manage.py                 # 统一命令行入口，集成 init/import/runserver 等子命令
├── requirements.txt          # 生产环境 Python 依赖清单（Flask, SQLAlchemy, requests）
├── requirements-dev.txt      # 开发测试额外依赖（pytest, black, mypy）
├── linkhub/                  # 核心应用包
│   ├── __init__.py           # 应用工厂函数，创建 Flask 实例
│   ├── config.py             # 配置管理（支持环境变量覆盖）
│   ├── models.py             # SQLAlchemy ORM 模型定义（Link, Category, Batch）
│   ├── schemas.py            # Pydantic / Marshmallow 序列化与校验模式
│   ├── services/             # 业务逻辑层
│   │   ├── importer.py       # 链接导入服务（支持 JSON/CSV/Markdown 解析）
│   │   ├── checker.py        # 链接健康检查异步任务
│   │   └── exporter.py       # 数据导出为 SQLite / JSON
│   ├── routes/               # HTTP 路由与视图函数
│   │   ├── index.py          # 首页与列表页
│   │   ├── detail.py         # 单条链接详情页（含元数据展示）
│   │   └── admin.py          # 管理后台（导入/分类/导出操作）
│   ├── templates/            # Jinja2 模板文件
│   │   ├── base.html         # 基础布局模板
│   │   ├── list.html         # 链接列表渲染模板
│   │   └── detail.html       # 详情页模板
│   ├── static/               # 前端静态资源（CSS / JS / 字体）
│   │   ├── css/              # 基于 Bulma 框架的定制样式
│   │   └── js/               # 前端交互（过滤、排序、分页）
│   └── utils/                # 通用工具函数
│       ├── url_parser.py     # URL 拆解与规范化工具
│       └── logger.py         # 日志配置与输出封装
├── data/                     # 数据存储目录
│   ├── sample_links.json     # 示例导入数据（含当前批次 250 条链接）
│   └── linkhub.db            # SQLite 数据库文件（运行时生成）
├── tests/                    # 单元测试与集成测试
│   ├── test_models.py        # ORM 模型测试
│   ├── test_importer.py      # 导入服务测试
│   └── test_checker.py       # 健康检查测试
├── docs/                     # 完整文档源文件（Markdown）
│   ├── quickstart.md
│   ├── import.md
│   ├── categories.md
│   ├── deployment.md
│   ├── api_reference.md
│   └── performance.md
├── scripts/                  # 运维辅助脚本
│   ├── backup.sh             # 数据库备份脚本
│   └── health_check_cron.sh  # 定时健康检查的 crontab 示例
├── .env.example              # 环境变量模板（数据库连接、秘钥等）
└── README.md                 # 本文件
```

## 贡献指南

我们欢迎任何形式的贡献，包括但不限于代码提交、文档改进、问题报告与功能建议。请遵循以下步骤参与项目。

第一，在 GitHub 上 fork 本仓库到个人账号，并将 fork 后的仓库 clone 到本地开发环境。

第二，创建新的功能分支，分支命名采用 `feature/功能简述` 或 `fix/问题简述` 格式，避免在 main 分支上直接修改。

第三，编写或修改代码后，请确保所有现有单元测试通过，并为新增功能补充对应的测试用例。运行 `pytest tests/` 验证。

第四，提交代码时遵循约定式提交规范，使用 `feat:`、`fix:`、`docs:`、`refactor:` 等前缀，提交信息应清晰描述改动内容与动机。

第五，向本仓库的 main 分支发起 Pull Request，并在 PR 描述中关联相关 issue（如有）。PR 需要至少一位项目维护者审核通过后方可合并。

## 常见问题

Q: 导入链接时提示 "Invalid URL format"，但我的 URL 在浏览器中可以正常访问，是什么原因？

A: 导入器默认对 URL 进行严格格式校验，要求包含协议头。请检查你的数据中是否所有 URL 都以 http:// 或 https:// 开头。如果是从文本文件中复制，注意去除首尾不可见字符（如空格或换行符）。你也可以在导入命令中添加 `--strict=false` 参数关闭严格校验，此时系统会自动为缺少协议的 URL 补全 http://。

Q: 健康检查标记了大量链接为异常，但我手动访问这些链接时是正常的，如何解决？

A: 健康检查默认使用 HEAD 请求探测，部分服务器可能不支持 HEAD 方法或对 HEAD 请求返回错误状态码。你可以在配置文件中将 `CHECK_METHOD` 改为 `GET`，或者调整 `CHECK_TIMEOUT` 参数增大超时阈值（单位秒）。另外，某些站点有反爬机制，请合理设置检查间隔，避免频率过高被临时封禁。

Q: 如何将当前数据库中的数据迁移到另一台服务器上？

A: 使用导出命令 `python manage.py export --format json --output ./backup.json` 将全部链接数据导出为 JSON 文件。在目标服务器上执行 `python manage.py import --source ./backup.json --overwrite` 即可完整恢复。若使用 SQLite 数据库，也可直接复制 .db 文件到目标服务器，但需确保 SQLite 版本兼容。

## 许可证

MIT

> 外链数量: 250 | 生成时间: 2026-07-05 15:33:09
