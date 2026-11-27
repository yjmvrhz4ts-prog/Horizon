---
layout: default
title: "Horizon Summary: 2026-11-27 (ZH)"
date: 2026-11-27
lang: zh
---

> 从 34 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [OpenSec 披露 Linux nfsd 预认证漏洞 CVE-2026-99362](#item-tech-news-1) ⭐️ 8.0/10
2. [主流编程语言的形式化验证之争](#item-tech-news-2) ⭐️ 7.0/10
3. [热门购物网站被曝滥用 WebRTC 的信用卡盗刷脚本](#item-tech-news-3) ⭐️ 7.0/10
4. [SemiAnalysis 深评 AWS Trainium3 推理与微架构](#item-tech-news-4) ⭐️ 7.0/10
5. [纳德拉承认微软应届生招聘放缓](#item-tech-news-5) ⭐️ 7.0/10
6. [《我的世界》基岩版资源包漏洞影响 26.52–26.63，26.65 修复](#item-tech-news-6) ⭐️ 7.0/10

**科技博客**
1. [谁来判定文字由 AI 写成](#item-tech-blog-1) ⭐️ 5.0/10

**财经新闻**
1. [国常会部署资本市场稳市机制：强化“国家队”作用、优化中央汇金类“平准基金”功能](#item-finance-news-1) ⭐️ 8.0/10
2. [央行发布大额存单新规：个人认购起点降至 10 万元](#item-finance-news-2) ⭐️ 7.0/10
3. [市场监管总局约谈 15 家电动自行车企业 要求整改并召回缺陷产品](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [OpenSec 披露 Linux nfsd 预认证漏洞 CVE-2026-99362](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec 披露 Linux 内核 NFS 服务器组件 nfsd 的预认证堆溢出漏洞 CVE-2026-99362，CVSS 评分 9.8；其通告称，攻击者无需登录，仅通过一条发往 tcp/2049 的连接即可越界写入内核堆并获取 root shell。该漏洞自 2014 年的 Linux 3.16 起存在，影响启用 NFSv4.1 或 4.2 的文件服务器、NAS 和集群存储节点，CVE 于 2026 年 11 月 20 日公开。修复已在 6.12.117、6.18.61、7.3.2 和 7.4-rc1 发布，管理员需升级内核并重启；无法立即升级时可限制 tcp/2049 访问。目前仅见 OpenSec 的简短通告，未提供漏洞技术细节，相关利用效果尚未见独立验证。

telegram · zaihuapd · 11月27日 12:57

**「背景」** NFSv4.1/4.2 使用会话与槽位机制，客户端通过 SEQUENCE 操作申请槽位；上游修复提交的标题为“nfsd: preflight SEQUENCE replies before accepting a slot”，表明缺陷与 nfsd 在接受槽位前未预检回复有关。Red Hat 的安全公告同时指出，其默认 RHEL 配置不运行或不启用内核 nfsd，因此攻击面主要限于实际开启 NFS 服务的主机。

**「影响与处置」** 对运行受影响内核并启用 NFSv4.1/4.2 的文件服务器、NAS 和集群存储节点，若不能立即升级到 6.12.117、6.18.61、7.3.2 或 7.4-rc1，就应限制对 tcp/2049 的访问；该漏洞无需登录，远程客户端可借此越界写入内核堆并取得 root。修复需升级内核并重启后生效。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99362">CVE-2026-99362 - Red Hat Customer Portal</a></li>
<li><a href="https://www.ox.security/ox-radar/cve/CVE-2026-99362/">CVE-2026-99362: kernel: kernel: Out-of-bounds write in nfsd ...</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99362">CVE-2026-99362 - Red Hat Customer Portal</a></li>
<li><a href="https://watchtowr.com/intelligence/nfs2root-linux-nfs-cve-2026-99362-faq/">NFS2ROOT (CVE-2026-99362) FAQ: Linux NFS Exposure and Fix</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#NFS`, `#CVE`, `#security vulnerability`, `#remote exploit`

---

<a id="item-tech-news-2"></a>
### [主流编程语言的形式化验证之争](https://blainehansen.me/post/mainstream-verifiable-language/) ⭐️ 7.0/10

一篇随笔主张，主流编程语言需要具备可形式化验证的基础，使正确性验证能进入日常开发。Hacker News 讨论对此展开争论：有评论者以 Ada SPARK 为例，称把现有 C 代码迁移到 SPARK 子集并验证到 SPARK Silver 后，报告了整数溢出等运行时错误；也有评论者认为形式化验证只能证明实现满足规格，无法证明规格符合现实，而且规格冲突会随代码复杂度上升。

hackernews · todsacerdoti · 11月27日 05:22 · [社区讨论](https://news.ycombinator.com/item?id=50663089)

**「背景」** 形式化验证指用机器可检查的规范描述程序应满足的性质，并在模型范围内证明实现符合这些规范；它能排除某类错误，但不能自动保证规范本身正确。Ada SPARK 是面向这类工作的 Ada 子集和验证工具链，开发者用契约和类型约束表达不变量，工具可静态证明部分运行时错误不会发生。

**「影响」** 对考虑在现有代码库中引入形式化验证的团队，讨论提示需要把规格审查与实现验证分开投入：Ada SPARK 的经验显示工具能查出整数溢出等运行时错误，但规格是否符合现实无法由证明本身保证。

**「社区讨论」** ianjbutler 认为不必等待编程语言与建模语言完全统一，可以先更多使用自动机、进程代数等更形式化的概念来设计系统；spankalee 则表示自己正在开发的 Zena 语言与文中设想相近。

**标签**: `#formal verification`, `#programming languages`, `#software correctness`, `#Ada SPARK`, `#formal methods`

---

<a id="item-tech-news-3"></a>
### [热门购物网站被曝滥用 WebRTC 的信用卡盗刷脚本](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

据 Infohawk 报道，一些热门购物网站上发现了滥用 WebRTC 的信用卡盗刷脚本。现有材料没有给出受影响站点、脚本样本数量或攻击规模，因此这仍是一项有待进一步核实的发现，还不能确认它是大规模事件。对电商站点和前端团队而言，直接风险来自页面中引入的第三方脚本：当第三方脚本本身恶意或被入侵时，信用卡数据可能被收集并外传。

hackernews · scanr · 11月27日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50668145)

**「背景」** 电商结账页通常嵌入同意管理、营销像素等第三方脚本，脚本一旦被篡改或替换，就可能在结账流程中收集支付数据。工具结果显示，此次被植入的 skim 脚本在黑色星期五前一周出现在 Lascana、Samsonite、American Tourister、Revolve 和 FWRD 的在线商店，通过同意横幅设置、营销像素等途径进入，并由服务器在结账页启用，且主要针对移动设备。

**「对电商结账页的实际影响」** 对在结账页嵌入支付、客服或分析等第三方脚本的电商站点来说，实际后果是卡片数据可能在用户提交时被脚本实时外传；Magecart 类攻击正常用这类第三方脚本作为入口。评论者指出 WebRTC 并非必要条件，普通 HTTP 请求同样可行，因此站点应审计第三方脚本，并把 CSP 的 connect-src 等限制覆盖到实际使用的传输通道，而不是只针对 WebRTC 做封堵。

**「社区讨论」** 部分评论者质疑 WebRTC 在此事中的特殊性：afavour 和 kevsamuel 认为，普通 HTTP 请求同样可以完成数据外传，问题更可能出在第三方脚本或 CSP 配置上。jszymborski 则把这类事件视为支持广告拦截的理由；这些都属于评论者观点，没有提供独立证据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer">Credit card skimming scripts using WebRTC found on popular ...</a></li>
<li><a href="https://daily.dev/posts/credit-card-skimming-scripts-using-webrtc-found-on-popular-shopping-sites-mr8zgdbaf">Credit card skimming scripts using WebRTC found on...</a></li>
<li><a href="https://www.reflectiz.com/blog/magecart-attack-disguised-gtm/">Magecart attack wears GTM disguise – Reflectiz</a></li>

</ul>
</details>

**标签**: `#web security`, `#credit card skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce`

---

<a id="item-tech-news-4"></a>
### [SemiAnalysis 深评 AWS Trainium3 推理与微架构](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis 发布对 AWS Trainium3 的推理性能与微架构评测，并把 Trainium3 与 TPU 一同纳入其开源 InferenceX 基准，使其与 Nvidia GB300、Rubin NVL72、TPUv7、AMD 等加速器同表比较。文章称，在回放真实编码智能体会话的 AgentX 端到端负载中，Trainium3 搭配 PDS 与 vLLM 的每美元性能（perf/$ TCO）在整条 TCO 对 p90 交互性曲线上优于除 Vera Rubin 之外的所有加速器；在 InferenceX 上，它与 TPU 在每 token 生成成本上与 GB300 互有胜负，甚至占优。微架构层面，文章强调 Trainium 以 tile 为一等原语、从零为 ML 负载设计，而非在图形 GPU 上逐代加装 AI 单元；其 Trainium 描述符生成引擎（DGE，对标 Nvidia TMA 与 AMD MI455X 的 TDM）据称可在较小消息尺寸下达到峰值 HBM 带宽利用率，而这一点在 Nvidia GPU 上无法实现。上述数据均来自 SemiAnalysis 自建的 UBenchX 微基准（含 SRAM scratchpad 延迟/带宽、机架级带宽与延迟、attention 指数运算等），AWS Annapurna Labs 团队协助讲解架构并校验实验；文章未在可见部分给出绝对延迟或吞吐数值，相关结论应视为该机构的基准测试与厂商协助验证下的结果。

rss · Semianalysis · 11月27日 15:54

**「架构路线差异」** 理解这项评测的关键在于两家厂商的架构起点不同：Nvidia 的数据中心 GPU 源自图形渲染，从 Volta 的 Tensor Cores、Hopper 的 TMA 到 Blackwell 的 Tensor Memory，都是在原有 GPU 上逐步加入 AI 专用单元；Trainium 则从一开始就以 tile 为一等原语，为机器学习负载做整体设计。SemiAnalysis 用 UBenchX 微基准测量这些单元，并把 Trainium 的 DGE 与 Nvidia TMA、AMD MI455X TDM 放在同一层面比较。

**「采购评估影响」** 对推理团队来说，最直接的后果是采购评估中必须加入 Trainium3：SemiAnalysis 的 InferenceX 基准称，在吞吐量与 p90 交互性之间的整条 TCO 前沿上，Trainium3 + vLLM 的每美元性能优于除 Vera Rubin 之外的所有加速器。由于它已支持 vLLM，已有 vLLM 服务栈的团队不必先重写框架，但仍需验证 Neuron/PDS 工具链及自身模型的 attention 形状能否复现基准中的收益。

**标签**: `#AWS Trainium`, `#AI accelerators`, `#inference`, `#microarchitecture`, `#Nvidia`

---

<a id="item-tech-news-5"></a>
### [纳德拉承认微软应届生招聘放缓](https://www.windowslatest.com/2026/11/27/lets-add-the-next-human-satya-nadella-admits-new-grad-hiring-slowed-as-companies-rebuild-around-ai-and-says-every-company-will-add-its-next-person-after-it-burns-through-its-ai-budget/) ⭐️ 7.0/10

微软 CEO 纳德拉在 The Pragmatic Engineer 播客中承认，公司的应届生招聘已经放缓，会先把现有员工调配到合适岗位，再补招新人。他还称，AI 原生公司会“先用完 AI 预算，再招下一个人类”，并预计每家公司都会如此。截至 6 月 30 日，微软员工数为 22.3 万，一年减少 5000 人，为 2016 年以来首次年度下滑。该报道引用的 MIT 与微软研究院论文称，采用 GitHub Copilot 的企业季度技术岗招聘减少 29%，初级岗位受影响最大。

telegram · zaihuapd · 11月27日 03:03

**「背景」** 微软的校园招聘此前是纳德拉公开强调的方向：他今年年初在达沃斯曾表示“仍然相信校园招聘”。与此同时，微软的用工规模在收缩——截至今年 6 月 30 日员工数为 22.3 万，一年减少约 5000 人，为 2016 年以来首次年度下滑。此次在 The Pragmatic Engineer 播客中的表态，正与此前的说法和这份员工数据形成对照。

**「应届与初级技术岗位承压」** 对应届生和初级技术岗位求职者来说，直接后果是入口收窄：企业会先调配现有员工，并在增加编制之前优先安排 AI 预算，因此校招名额和初级岗位都会承压。微软截至 2026 年 6 月 30 日的全职员工为 22.3 万人，同比减少约 5000 人，这表明编制收缩已经发生。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://stockanalysis.com/stocks/msft/employees/">Microsoft (MSFT) Number of Employees 1990-2026 - Stock Analysis</a></li>
<li><a href="https://www.seattletimes.com/business/microsoft/microsofts-head-count-falls-for-first-time-in-a-decade/">Microsoft’s head count falls for first time in a decade</a></li>

</ul>
</details>

**标签**: `#AI labor impact`, `#Microsoft`, `#tech hiring`, `#entry-level jobs`, `#GitHub Copilot`

---

<a id="item-tech-news-6"></a>
### [《我的世界》基岩版资源包漏洞影响 26.52–26.63，26.65 修复](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

《我的世界》基岩版存在资源包漏洞：含 content.zipe 文件的资源包可改动 Ore UI 界面文件并运行隐藏脚本。附加组件开发者 8Crafter 于 11 月 15 日在 Reddit 公开该问题，称已确认影响 26.52 至 26.63 版，更早版本也可能受影响；覆盖 PC、手机和主机，Java 版不受影响。加入服务器或 Realm 时若开启资源包自动下载，玩家可能无需手动安装就收到问题文件，利用方式包括删除全部存档、获取玩家 IP，以及在 Windows 特定条件下无提示打开任意 URI 并启动资源包内批处理文件下载恶意软件；Mojang 已在 26.65 版修复，AxmBro 的 Windows 只读检测工具可查找 content.zipe，但不能判定资源包是否恶意。

telegram · zaihuapd · 11月27日 18:04

**「背景」** 在《我的世界》基岩版中，资源包可包含 content.zipe 等文件并替换游戏资源，Ore UI 则是游戏的界面框架。加入服务器或 Realm 时若开启资源包自动下载，客户端会在玩家不手动安装的情况下加载服务器推送的资源包，这构成了此次漏洞的暴露路径。

**「影响」** 仍停留在 26.52–26.63 的玩家以及服务器或 Realm 运营者应升级到 26.65；在旧版本加入开启资源包自动下载的服务器时，仍可能在没有手动安装的情况下收到问题资源包。

**标签**: `#Minecraft Bedrock`, `#security vulnerability`, `#resource packs`, `#malware`, `#gaming`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [谁来判定文字由 AI 写成](https://seangoedecke.com/who-gets-to-decide-if-something-is-written-by-ai/) ⭐️ 5.0/10

rss · Sean Goedecke · 11月27日 00:00

**「背景」** 围绕写作奖、出版合同和社交媒体推文的争议不断出现：某段文字是否由 AI 生成，往往由检测工具或社群舆论来裁决。作者认为，Pangram 等工具是否可靠、是否该扫描他人作品固然值得讨论，但冲突的根源在于谁有权做这种判定。

**「方案」** 作者把反 AI 检测的情绪解释为对权力集中的警惕：Pangram 属于不受信任的科技行业，让另一家科技公司充当守门人难以令人放心；更深层地，过去几十年从社区化、可通融的人类判断转向工具化流程，也让不少人反感“用另一个 AI 工具治理 AI”的思路。但作者自己支持 Pangram，因为在他看来，检测工具之外唯一现实的替代方案是社区自行判定，而作者认为社区并不擅长识别 AI 文本：不常用 AI 的人会把有明显 AI 痕迹的文字当成人类所写，也会因为一条推文冗长礼貌就判其为 AI，结果错误更多。因此，若真想阻止 AI 进入艺术与文化空间，就应使用最强工具，即便它本身也是 AI；若担心科技公司互相监督，则应推动开源方案或由政府自建检测平台。作者也承认读者提出的合理担忧：许多 AI 工具并不可靠，即使好工具也可能误报。

**「启示」** 作者的结论是，AI 检测之争本质上是治理权之争；拒绝工具并不会让人类空间更纯净，反而可能把判定权交给更不擅长识别 AI 的社群，从而让更多 AI 内容进入其中。

**标签**: `#AI detection`, `#AI-generated content`, `#trust and governance`, `#community moderation`, `#Pangram`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [国常会部署资本市场稳市机制：强化“国家队”作用、优化中央汇金类“平准基金”功能](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 8.0/10

11 月 27 日，国务院总理李强主持召开国务院常务会议，部署持续完善资本市场稳市机制，要求推动上市公司加大分红回购力度、加力发挥“国家队”稳市作用、进一步优化中央汇金公司的类“平准基金”功能并提供充足流动性保障，同时完善保险、企业年金、社保基金等中长期资金入市支持引导政策。会议以方向和原则要求为主，未公布增量政策的具体规模或操作细节。

telegram · zaihuapd · 11月27日 05:35

**「背景」** 中央汇金公司是国有独资投资机构，市场通常将其增持股票或 ETF 视为“国家队”直接入市；新闻稿所说的类“平准基金”功能，指通过逆向买卖提供流动性、平抑市场异常波动。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cls.cn/detail/2546318">cls.cn/detail/2546318</a></li>

</ul>
</details>

**标签**: `#国常会`, `#资本市场政策`, `#中央汇金`, `#平准基金`, `#中长期资金`

---

<a id="item-finance-news-2"></a>
### [央行发布大额存单新规：个人认购起点降至 10 万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行 11 月 27 日公布《大额存单管理办法》，将个人认购起点从 20 万元降至 10 万元、机构从 1000 万元降至 500 万元，自 2027 年 3 月 21 日起施行。同日发布的《人民币存贷款利率管理规定》要求金融机构自主确定存贷款利率、不得以高息揽储等不正当手段吸收存款，也自 2027 年 3 月 21 日起施行。

telegram · zaihuapd · 11月27日 11:36

**「背景」** 大额存单是银行面向大额资金客户的存款产品，现行门槛由 2015 年《大额存单管理暂行办法》设定，新办法将取代该暂行办法及 2016 年第 13 号公告。

**「影响」** 个人认购门槛下调后，持有 10 万元以上、不足 20 万元的储户将新具备认购资格，银行个人大额存单的适用客户范围随之扩大。

**标签**: `#央行监管`, `#大额存单`, `#存款利率`, `#零售银行`, `#中国金融政策`

---

<a id="item-finance-news-3"></a>
### [市场监管总局约谈 15 家电动自行车企业 要求整改并召回缺陷产品](https://www.news.cn/20261127/0c8c665ce70c417b9263b39fa8a519f0/c.html?hl=zh-CN) ⭐️ 7.0/10

2026 年 11 月 27 日，国家市场监管总局集中约谈雅迪、台铃、爱玛、九号、小牛等 15 家电动自行车企业，指出部分企业在 CCC 认证（强制性产品认证）飞行检查中存在质量保证能力不足、产品一致性管控不严，以及违反强制性国家标准出厂销售不合格产品等问题。监管部门要求企业抓紧整改，严格执行“一车一池一充一码”，防止不合格产品流入市场，并对确认存在缺陷的产品立即召回。

telegram · zaihuapd · 11月27日 12:06

**「背景」** 电动自行车须先通过 CCC 认证（中国强制性产品认证）并符合强制性国家标准，才能出厂销售；此次约谈提到的“一车一池一充一码”，是要求车辆、电池、充电器与编码一一对应，以便追溯并防止违规改装。监管部门是在近期对 CCC 认证进行全覆盖飞行检查（不预先通知的突击检查）后，发现部分企业存在质量保证能力欠缺、产品一致性管控不严等问题，才采取这次集中约谈。

**「影响」** 对经确认存在缺陷的产品，相关车主将受召回安排影响；这 15 家企业须承担售后和召回责任，不得推诿责任、误导消费者无牌上路，也不得以“证书很快恢复”为由拒绝退车。

**标签**: `#电动自行车监管`, `#产品质量`, `#CCC认证`, `#企业约谈`, `#消费者权益`

---