---
layout: default
title: "Horizon Summary: 2026-11-26 (ZH)"
date: 2026-11-26
lang: zh
---

> 从 43 条内容中筛选出 9 条重要资讯。

---

**科技新闻**
1. [FCC 批准 SpaceX 最多 100 万颗 Starmind 数据中心卫星](#item-tech-news-1) ⭐️ 8.0/10
2. [Minipg：把 PostgreSQL 打包为单个可执行文件](#item-tech-news-2) ⭐️ 7.0/10
3. [谷歌将让 AI 代理使用 Workspace MCP，Gmail 服务器不能发邮件](#item-tech-news-3) ⭐️ 7.0/10
4. [华为拟公布新款 HBM 芯片，论文称数据引脚密度翻倍](#item-tech-news-4) ⭐️ 7.0/10
5. [Neuralink 获 FDA 批准启动渐冻症脑机接口关键试验](#item-tech-news-5) ⭐️ 7.0/10
6. [阿斯麦 CEO：反对全面断供中国](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [德意志银行：半导体出口额首次超越石油与天然气](#item-finance-news-1) ⭐️ 8.0/10
2. [英伟达据报暂停向马来西亚、新加坡、泰国、印尼发运 AI 服务器](#item-finance-news-2) ⭐️ 8.0/10
3. [荷兰大臣称不接受美国限制 ASML 对华销售的法案](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [FCC 批准 SpaceX 最多 100 万颗 Starmind 数据中心卫星](https://www.geekwire.com/2026/fcc-clears-spacex-million-satellites-starmind-data-center/) ⭐️ 8.0/10

美国联邦通信委员会（FCC）批准 SpaceX 在 500 至 1002 公里高度的轨道上部署最多 100 万颗卫星，用于构建 Starmind 的在轨数据处理网络；FCC 称，这是美国首次批准太空数据中心星座。该授权附带通信备份、定期提交进展和轨道碎片减缓详细方案等条件，并要求首颗卫星不晚于 2033 年投入运行，整个星座在 2040 年前全部运行。FCC 在审批中驳回了亚马逊、Viasat 和美国天文学会的反对意见；这属于监管授权，并不等于 100 万颗卫星已开始部署，实际规模和时间仍取决于后续发射与建设。

telegram · zaihuapd · 11月26日 04:45

**「背景」** Starmind 是 SpaceX 规划的在轨数据处理星座，其卫星在轨道上承担数据处理任务，而不只是提供通信链路。FCC 在 11 月 25 日的文件中称，这是美国历史上首个太空数据中心星座授权；该授权是条件性的，要求分阶段部署并提交轨道碎片减缓方案，首颗卫星须不晚于 2033 年投入运行、整个星座须在 2040 年前全部运行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.fcc.gov/public/attachments/DOC-427572A1.pdf">FCC Authorizes 1 Million Satellites for Data Centers in Space</a></li>
<li><a href="https://arstechnica.com/space/2026/11/the-fcc-has-authorized-spacex-to-deploy-1-million-satellites/">The FCC has authorized SpaceX to deploy 1 million satellites</a></li>

</ul>
</details>

**标签**: `#FCC approval`, `#SpaceX`, `#space data centers`, `#satellite constellations`, `#orbital debris`

---

<a id="item-tech-news-2"></a>
### [Minipg：把 PostgreSQL 打包为单个可执行文件](https://progrium.github.io/minipg/) ⭐️ 7.0/10

Minipg 将 PostgreSQL 打包成一个可执行文件，面向希望像使用 SQLite 那样以 CLI 方式运行轻量 SQL 数据库、而不是部署 Docker 或完整服务器的开发者。作者在讨论中强调，SQLite 可以理解为嵌入式 SQL 引擎，也可以理解为 CLI 友好的简单数据库，Minipg 主要针对后者。与嵌入式库 PGlite 相比，作者称 PGlite 只支持单连接模式，而应用有时会在事务中执行其他查询；评论者还指出，Minipg 复用 PostgreSQL 的 Alpine 镜像但无需 Docker，并依赖较新的嵌入式 hypervisor h9。

hackernews · rguiscard · 11月26日 03:00 · [社区讨论](https://news.ycombinator.com/item?id=50650892)

**「背景」** Minipg 并未重新编译 PostgreSQL，而是把 Docker Hub 的 postgres:18-alpine 镜像封装进单个可执行文件，再交给 Zig 库 h9 运行：h9 的 Linux 兼容层直接执行 Alpine 的 PostgreSQL 二进制，由 Plan 9 内核接管系统调用，因此不需要启动 Linux 内核、虚拟机镜像或 Docker。作者明确将其定位为本地单用户程序的轻量选择，而不是云上部署、多副本或多连接正式 PostgreSQL 的替代品。

**「适用边界与依赖风险」** 对需要在单次会话中并发发起查询或嵌套事务的开发者而言，Minipg 针对的是 PGlite 的实际限制：PGlite 基于 PostgreSQL 的 single user mode 构建，同一时刻只支持一个连接。采用前还需权衡它依赖 h9 这一尚属年轻的嵌入式 hypervisor，其成熟度与兼容性会直接影响部署可靠性；而只用官方镜像加 podman 做测试的场景，社区反馈常规 PostgreSQL 启动约 800 毫秒，未必需要引入这一层。

**「社区讨论」** 有评论者认为 Minipg 的独立用例不够清晰，因为 PGlite 已覆盖嵌入式或进程内场景，embedded-postgres 也能提供无需 Docker 的临时测试实例；也有人认为它对小型自托管应用有用，并称单元测试只需 podman 加官方镜像，常规 PostgreSQL 约 800 毫秒即可启动。作者回应说，Minipg 的定位更接近 CLI 友好的 SQL 数据库，而不是嵌入式 SQL 引擎。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://progrium.github.io/minipg/">minipg: PostgreSQL as a single executable - progrium.github.io</a></li>
<li><a href="https://progrium.xyz/articles/2026/single-binary-postgres">How I Got Postgres into a Single Binary · progrium</a></li>
<li><a href="https://github.com/electric-sql/pglite">GitHub - electric-sql/pglite: Embeddable Postgres with real ...</a></li>

</ul>
</details>

**标签**: `#PostgreSQL`, `#embedded databases`, `#single-binary deployment`, `#database tooling`, `#open source`

---

<a id="item-tech-news-3"></a>
### [谷歌将让 AI 代理使用 Workspace MCP，Gmail 服务器不能发邮件](https://techstackups.com/articles/google-workspace-ai-agents-mcp/) ⭐️ 7.0/10

据报道，谷歌将让 AI 代理通过 MCP 服务器调用 Google Workspace 的能力，面向希望让代理操作 Workspace 的开发者；但其中的 Gmail MCP 服务器无法发送邮件。现有信息没有说明上线时间、覆盖哪些 Workspace 服务，以及该限制是否适用于所有开发者，因此这仍是报道中的平台计划，而非已完整验证的产品能力。对构建代理的开发者而言，关键限制在于官方 Gmail 路径不能完成发信动作。

hackernews · ritzaco · 11月26日 09:44 · [社区讨论](https://news.ycombinator.com/item?id=50653477)

**「背景」** MCP（Model Context Protocol）是让 AI 代理以标准化方式调用外部工具、读取数据的协议；Google 官方文档称，Gmail MCP 服务器可为代理提供搜索邮件、读取邮件串和列出标签等读取能力。另有第三方报道指出，Google 已把 Workspace 的 MCP 服务器开放为公开开发者预览，Gmail 工具覆盖起草、搜索和读写操作，因此“能否发送邮件”成为外界判断其能力边界的关键细节。

**「影响」** 对通过官方 MCP 服务器接入 Gmail 的代理开发者，自动发信流程无法只靠该服务器完成，需要另行设计发送环节，不能把该 MCP 服务器视为覆盖 Gmail 全部操作的接口。

**「社区讨论」** 评论者质疑这一限制究竟出于安全还是商业考量：perdy 指出 MCP 的 elicitation 机制可以在工具调用前要求用户确认，因此把发信能力设为仅合作伙伴可用更像商业决定；Schnitz 则认为用户会改用浏览器自动化来发信，流程会更繁琐。也有评论者怀疑这是围绕 Gemini 的封闭生态安排，但这属于推测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developers.google.com/workspace/gmail/api/guides/configure-mcp-server">Configure the Gmail MCP server | Google for Developers</a></li>
<li><a href="https://www.getmailbird.com/ai-email-agents-what-they-can-actually-do-today/">AI Email Agents : What They Can Actually Do Today | Mailbird</a></li>

</ul>
</details>

**标签**: `#Google Workspace`, `#MCP`, `#AI agents`, `#Gmail`, `#platform strategy`

---

<a id="item-tech-news-4"></a>
### [华为拟公布新款 HBM 芯片，论文称数据引脚密度翻倍](https://www.bloomberg.com/news/articles/2026-11-26/huawei-teases-next-gen-ai-memory-chip-to-take-on-samsung-hynix) ⭐️ 7.0/10

据彭博社报道，华为技术有限公司计划公布一款新型高带宽内存（HBM）芯片的细节；其研究论文标题显示，这款 HBM 的数据引脚密度是三星电子和 SK 海力士量产产品的两倍，理论上可大幅提升内存带宽。华为计划于明年 2 月在旧金山的一场会议上发表这篇研究论文。华为正推动 HBM 在中国本土投产，而该部件目前受美国制裁限制。现有信息仅来自论文标题与会议安排，尚无产品规格、良率、产能数据或独立验证结果。

telegram · zaihuapd · 11月26日 05:30

**「背景」** HBM 通过垂直堆叠 DRAM 晶粒并用硅通孔互连，以远宽于传统内存的接口为 AI 加速器提供带宽；数据引脚密度越高，单位封装可引出的位宽和潜在带宽越大。该市场长期由三星电子和 SK 海力士主导，而先进 HBM 受美国出口限制，促使华为推动本土制造。

**标签**: `#HBM`, `#Huawei`, `#semiconductor memory`, `#AI hardware`, `#US sanctions`

---

<a id="item-tech-news-5"></a>
### [Neuralink 获 FDA 批准启动渐冻症脑机接口关键试验](https://www.bloomberg.com/news/articles/2026-11-25/neuralink-gets-clearance-for-brain-implant-trial-in-als-patients?srnd=phx-technology) ⭐️ 7.0/10

Neuralink 宣布已获美国 FDA 批准，将在美国启动名为 LINK 的植入式脑机接口关键临床试验，面向渐冻症（ALS）患者招募，目标是将大脑信号直接转化为计算机控制指令。公司称这是美国首个获批的此类关键试验，试验数据将用于支持未来的医疗器械上市申请。此前，Neuralink 在早期研究中已为全球超过 30 名瘫痪患者植入设备；目前公布的信息未包含 LINK 的招募规模、试验站点、时间表或临床结果。

telegram · zaihuapd · 11月26日 07:15

**「背景」** 在美国医疗器械审批路径中，关键临床试验产生的数据通常直接用于支持上市许可申请；因此，此次 LINK 试验被视为 Neuralink 从早期安全验证迈向商业化审批的一步。在进入这一阶段前，Neuralink 已通过早期研究在全球为超过 30 名瘫痪患者植入设备。

**「影响」** 对符合条件的渐冻症患者而言，LINK 提供了一个参与研究性植入设备试验的潜在通道，但该设备尚未获批上市，疗效与安全性仍需关键试验数据验证；在招募细则公布前，患者无法据此判断实际可及性。

**标签**: `#Neuralink`, `#brain-computer interface`, `#FDA approval`, `#ALS`, `#clinical trials`

---

<a id="item-tech-news-6"></a>
### [阿斯麦 CEO：反对全面断供中国](https://www.semafor.com/article/11/25/2026/asml-makes-the-case-for-selling-chips-to-china) ⭐️ 7.0/10

阿斯麦 CEO 富凯在 Semafor《Future Proof》节目中表示，出口管制应只保护最先进技术，若把中国完全排除在光刻机供应之外，反而会促使中国在自研设备上“加倍甚至三倍投入”。他称，阿斯麦对华销售的设备比最先进制程落后十多年，维持这一代差可让中国继续依赖西方设备；过去近 30 年，阿斯麦在中国光刻机市场的份额接近 100%。此番表态正值美国推动 MATCH 法案，拟把限制从 EUV 扩大到浸没式 DUV 和维护服务，荷兰政府与阿斯麦均表示反对。

telegram · zaihuapd · 11月26日 12:19

**「背景」** 光刻机是芯片制造中决定线宽的核心设备，ASML 长期主导全球高端光刻机市场；其中 EUV 用于最先进制程，浸没式 DUV 则覆盖更成熟但量大的产能。美国此前已限制 EUV 对华出口，当前讨论中的 MATCH 法案拟把限制延伸到浸没式 DUV 及维护服务，这正是富凯上述表态的政策背景。

**「影响」** 若美国把维护服务纳入管制，中国晶圆厂现有浸没式 DUV 设备的维护安排将受影响；阿斯麦与荷兰政府已明确反对这一扩大方案。

**标签**: `#export-controls`, `#semiconductors`, `#ASML`, `#China`, `#lithography`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [德意志银行：半导体出口额首次超越石油与天然气](https://www.cnbc.com/2026/11/26/semiconductor-chips-are-the-new-oil-heres-why.html) ⭐️ 8.0/10

德意志银行基于国际贸易中心数据的分析显示，按四季度滚动合计计算，2026 年第一季度半导体出口额首次超过石油和天然气，约为 1.61 万亿美元，而石油和天然气出口额为 1.53 万亿美元。该行表示，第二季度这一差距进一步扩大，半导体出口约为 1.60 万亿美元，石油和天然气出口约为 1.47 万亿美元；霍尔木兹海峡石油运输受扰也助推了这一差距。

rss · CNBC Finance · 11月26日 17:52

**「背景」** 过去几十年，石油出口国把大量石油贸易顺差投入美国国债等资产，形成所谓“石油美元”循环；德意志银行因此提出，亚洲芯片出口国的贸易顺差可能更多回流美国科技股、初创企业和数据中心，从而改变全球资金流向。

**「影响」** 若德意志银行的判断成立，亚洲芯片出口国的贸易顺差可能更多回流美国科技股、初创企业和数据中心，而非像石油美元那样主要买入美国国债，从而改变全球资本流向并推高企业债和政府债的收益率。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Petrodollar_recycling">Petrodollar recycling - Wikipedia</a></li>

</ul>
</details>

**标签**: `#semiconductors`, `#global trade`, `#AI investment`, `#market volatility`, `#macro-financial flows`

---

<a id="item-finance-news-2"></a>
### [英伟达据报暂停向马来西亚、新加坡、泰国、印尼发运 AI 服务器](https://www.ft.com/content/7838a715-07d4-4605-aa60-21f5af2b2370) ⭐️ 8.0/10

据《金融时报》报道，英伟达已要求主要制造伙伴暂停向马来西亚、新加坡、泰国和印度尼西亚发运 AI 服务器，戴尔、美超微等组装厂商已通知四国买家相关订单无法出厂。三名知情人士称，这次冻结与美国新一轮出口管制有关，是否属于临时措施尚不清楚；美国商务部上周发布新规，要求区域云服务商在 90 天内取得出口许可，并核实客户不含受限的中国实体。

telegram · zaihuapd · 11月26日 07:38

**「背景」** 美国商务部此前出台临时规则，要求可能为中国等受限国家提供算力的 AI 芯片和服务器出口申请许可（政府批准），区域云服务商须在 90 天内取得许可；马来西亚、新加坡、泰国和印度尼西亚是中国 AI 公司获取英伟达最先进处理器的中转地，这些芯片不得直接出口中国大陆。

**「影响」** 戴尔、美超微等整机组装商以及马来西亚、新加坡、泰国和印度尼西亚的云服务商与 AI 买家将直接受影响：相关订单已被通知不能出厂，而美国商务部新规还要求区域云服务商在 90 天内取得出口许可并核实客户。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcrunch.com/2026/11/16/us-tightens-ai-chip-export-controls-to-deter-chinese-companies-from-accessing-compute-remotely/">US tightens AI chip export controls to deter Chinese ... | TechCrunch</a></li>
<li><a href="https://www.ft.com/content/7838a715-07d4-4605-aa60-21f5af2b2370?syn-25a6b1a6=1">Nvidia halts chip shipments to south-east Asia</a></li>
<li><a href="https://www.theguardian.com/business/live/2026/nov/26/nvidia-chip-shipments-south-east-asia-stock-dentists-live-updates">Nvidia reportedly halts chip shipments to south-east... | The Guardian</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#US export controls`, `#AI servers`, `#Southeast Asia`, `#semiconductor supply chain`

---

<a id="item-finance-news-3"></a>
### [荷兰大臣称不接受美国限制 ASML 对华销售的法案](https://www.bloomberg.com/news/articles/2026-11-26/netherlands-plans-to-fight-rollout-of-proposed-us-curbs-on-asml) ⭐️ 7.0/10

荷兰外贸与发展合作大臣 Sjoerdsma 11 月 26 日在议会表示，荷兰不会接受美国进一步限制 ASML 对华销售，反对 MATCH Act 的域外管辖效力，并正与欧盟委员会协调、联合德国和法国游说，争取将该法案从美国年度国防政策法案中剔除。中国约占 ASML 今年销售额的 20%，外界预计美国国会 12 月中旬表决，通过可能性较大。

telegram · zaihuapd · 11月26日 14:56

**「背景」** MATCH Act 由美国两党议员提出，要求荷兰、日本等盟友收紧对华半导体设备出口，否则美方将单方面限制这些设备。荷兰政府今年 5 月已对该提案提出书面异议，此次大臣在议会表态是把反对立场再次公开化，并试图借美国年度国防法案的表决程序将其剔除。

**「影响」** 如果 MATCH Act 通过并生效，而荷兰未在 150 天内与美方管制对齐，ASML 约 20% 的对华销售额可能受到美方单边限制的波及，其中国客户和半导体设备供应链将承受压力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reuters.com/world/asia-pacific/dutch-government-objects-proposed-us-law-restricting-asmls-china-exports-2026-05-14/">Dutch government objects to proposed US law restricting ASML ...</a></li>
<li><a href="https://nltimes.nl/2026/11/26/netherlands-draws-line-us-plan-restrict-asml-exports-china">Netherlands draws line over U.S. plan to restrict ASML ...</a></li>
<li><a href="https://www.thedefensenews.com/US-Pushes-Bill-to-Compel-Netherlands-to-Halt-Remaining-ASML-Machine-Sales-and-Service-to-China/">US Pushes Bill to Compel Netherlands to Halt Remaining ASML ...</a></li>

</ul>
</details>

**标签**: `#semiconductor export controls`, `#ASML`, `#Netherlands-EU trade policy`, `#US-China tech restrictions`, `#MATCH Act`

---