---
layout: default
title: "Horizon Summary: 2026-11-18 (ZH)"
date: 2026-11-18
lang: zh
---

> 从 40 条内容中筛选出 17 条重要资讯。

---

**科技新闻**
1. [Nginx HTTP/2 曝两个未认证 RCE 漏洞](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenAI 发布 GPT-6.2 Astra 与 GPT-6.2 Sol](#item-tech-news-2) ⭐️ 8.0/10
3. [Xint 披露 NGINX2Root：五个 nginx 漏洞可获取主机 root](#item-tech-news-3) ⭐️ 8.0/10
4. [Quad9 退出法国：DNS 层反盗版封锁再引争议](#item-tech-news-4) ⭐️ 7.0/10
5. [微软 Ignite 2026 发布七款新 AI 模型，主打可扩展性价比](#item-tech-news-5) ⭐️ 7.0/10
6. [能量基推理器宣称推理效率提升 385 倍](#item-tech-news-6) ⭐️ 7.0/10
7. [curl 维护者：AI Rust 重写缺少上游修复](#item-tech-news-7) ⭐️ 7.0/10
8. [编码智能体的外部沙箱模式与三个实现](#item-tech-news-8) ⭐️ 7.0/10
9. [Java 曝出 CVE-2026-114938 远程代码执行漏洞](#item-tech-news-9) ⭐️ 7.0/10
10. [旅行者 1 号抵达距地一光日，约 260 亿公里](#item-tech-news-10) ⭐️ 7.0/10

**科技博客**
1. [FlyDSL MonoKernel 降低 vLLM 交互式解码延迟](#item-tech-blog-1) ⭐️ 8.0/10

**财经新闻**
1. [美联储会议纪要：官员预计还需加息，并担忧 AI 推高通胀](#item-finance-news-1) ⭐️ 9.0/10
2. [美联储理事沃勒称可能需在 12 月加息 50 个基点](#item-finance-news-2) ⭐️ 7.0/10
3. [美国芯片新规后五家银行暂停 4.8 亿美元字节跳动相关 GPU 贷款](#item-finance-news-3) ⭐️ 7.0/10
4. [腾讯三季度营收 2073 亿元，资本开支升至 814.33 亿元](#item-finance-news-4) ⭐️ 7.0/10
5. [中韩宣布自贸协定服务与投资后续谈判实质性结束](#item-finance-news-5) ⭐️ 7.0/10
6. [九部门拟推动新能源汽车“车电一体报废”](#item-finance-news-6) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Nginx HTTP/2 曝两个未认证 RCE 漏洞](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 8.0/10

据 Wiz 博客，Nginx 的 HTTP/2 实现中被披露两个可导致未认证远程代码执行的漏洞，编号为 CVE-2026-123633 和 CVE-2026-123007。当前公开材料只给出漏洞类别和 CVE 记录，未说明受影响版本、触发条件或修复版本。对运行 Nginx 且启用 HTTP/2 的站点而言，这是需要优先核查暴露面并跟进补丁的安全问题。

hackernews · speedping · 11月18日 15:19 · [社区讨论](https://news.ycombinator.com/item?id=50547374)

**「背景」** Xint 的公告称，CVE-2026-123007 的漏洞代码存在于 nginx 1.9.5 至 1.31.8 的所有官方发布版本中，2026 年 11 月 10 日的 master 分支也仍包含该代码。Astra 针对 CVE-2026-123007 与 CVE-2026-123633 给出的缓解建议是在受影响端口关闭 HTTP/2：1.25.1 及以后使用 \`http2 off;\`，更早版本从 \`listen\` 指令中移除 \`http2\`，但这会使依赖原生 gRPC 的服务受影响。

**「影响与缓解」** 对暴露在公网且启用 HTTP/2 的 NGINX 站点和 API，这两个漏洞（CVE-2026-123633、CVE-2026-123007，CVSS 4.0 评分 9.2）可让攻击者无需认证执行代码，即使应用自身代码安全也无法挡住。临时缓解措施是在受影响的监听端口关闭 HTTP/2；但这只能阻断这两个漏洞，不能覆盖同一批披露中的另外三个 NGINX 漏洞，因此不能替代升级。

**「社区讨论」** 评论者指出，HTTP/2 在 Nginx 中并非默认启用，但仍有约 12% 的服务器开启，在互联网规模下暴露面不小；也有人称修复提交比更广泛披露早一周出现在开源仓库，且提交信息包含报告者线索，认为这段修复先于披露的窗口可能被利用。另有评论借 Apache 与 Nginx 的对比，批评“新软件一定更安全”的惯性看法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root: New Remote Code Execution Vulnerabilities in nginx ...</a></li>
<li><a href="https://www.getastra.com/blog/security-advisory/nginx2root/">nginx 2 root: Five nginx RCE Flaws and a Kernel Bug...</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>
<li><a href="https://www.ox.security/blog/nginx2root-five-critical-nginx-flaws-expose-web-servers-to-remote-code-execution/">NGINX 2 Root: 5 Critical NGINX RCE Vulnerabilities &amp; CVE Fixes</a></li>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root: New Remote Code Execution Vulnerabilities in nginx ...</a></li>

</ul>
</details>

**标签**: `#nginx`, `#HTTP/2`, `#remote code execution`, `#CVE`, `#security`

---

<a id="item-tech-news-2"></a>
### [OpenAI 发布 GPT-6.2 Astra 与 GPT-6.2 Sol](https://simonwillison.net/2026/Nov/17/gpt62-astra-and-sol/) ⭐️ 8.0/10

OpenAI 推出 GPT-6.2 Astra 和 GPT-6.2 Sol，前者定位为处理最难项目的前沿模型，后者定位为面向日常工作的高效通用模型；API 名称分别为 \`gpt-6.2-astra\` 和 \`gpt-6.2-sol\`，Simon Willison 的 LLM 0.38 已支持这两个模型。Astra 定价为每百万 token 输入 8 美元、输出 40 美元，是 GPT-6 Astra（10/50）的 80%，缓存输入价格从每百万 token 1 美元降至 0.40 美元；Sol 维持每百万 token 2/10 美元，与 6.1 Sol、6 Sol 相同，是 GPT-5.6 Sol（4/20）的一半。Willison 指出，外界对这两款模型的评价不一：Astra 在多项基准上不及 Claude Fable 5.2，且有用户抱怨其沟通方式令人困惑；他让两款模型生成“Yonkers 变机甲”动画的测试，也未能达到 Fable 5.2 和 Gemini 4 Carbon 的效果。

rss · Simon Willison · 11月17日 22:38

**「背景」** OpenAI 目前的模型线分为两档：Astra 面向高难度任务的旗舰模型，Sol 则是面向日常工作的低成本、通用型号，两者按代际版本号迭代（此前已有 6 Astra、6.1 Sol 和 6 Sol）。在这类 API 定价中，命中缓存的输入 token 单独计价，通常远低于未缓存输入；因此缓存价格的下调对需要反复携带长上下文的智能体式长任务影响最直接，本次 Astra 的缓存输入价从每百万 token 1 美元降至 0.40 美元。

**「对开发者的影响」** 已使用 6 Astra 的开发者可以把 API 模型名改为 gpt-6.2-astra，并通过 LLM 0.38 接入；输入和输出价格分别降至每百万 token 8 美元和 40 美元，缓存命中价降至 0.40 美元，这对长时间运行的代理会话成本影响最直接。但作者实测和 Theo Browne 的反馈显示，Astra 在部分基准上不如 Claude Fable 5.2，长任务中还可能因追问内部实现细节而阻塞，升级前应针对自身工作流验证。

**标签**: `#OpenAI`, `#GPT-6.2 Astra`, `#GPT-6.2 Sol`, `#LLM pricing`, `#API models`

---

<a id="item-tech-news-3"></a>
### [Xint 披露 NGINX2Root：五个 nginx 漏洞可获取主机 root](https://nginx2root.com/) ⭐️ 8.0/10

据 Xint 披露，NGINX2Root 攻击链串联 5 个 nginx 漏洞和 1 个 Linux 内核缺陷，可将权限从 nginx 访客提升至主机 root。其中 CVE-2026-123007 是 HTTP/2 流控内存破坏，未认证即可在 worker 进程中执行命令。nginx 1.30.7 与 1.31.9 已于 11 月 18 日修复共 10 个 CVE；Rapid7 已发布 PoC，目前暂无在野利用，无法升级的部署应关闭对外 HTTP/2。

telegram · zaihuapd · 11月18日 16:21

**「背景」** nginx 自 2015 年引入 HTTP/2 支持，Xint 称从 1.9.5 到 1.31.8 的官方版本都包含 CVE-2026-123007 的脆弱代码，甚至 2026 年 11 月 10 日的主分支仍包含该代码。Wiz 将 CVE-2026-123007 与 CVE-2026-123633 一并评为 CVSS 4.0 9.2 的严重级别，并指出漏洞位于 nginx 本身，即使网站或 API 的应用代码安全也可能暴露。

**「影响与处置」** 对于启用了 HTTP/2 并使其对外可达的 nginx 运维者，CVE-2026-123007 影响 1.9.5 至 1.31.8：攻击者可导致 worker 进程崩溃、破坏内存，并可能远程执行代码；应升级到 1.30.7+ 或 1.31.9+，无法升级时关闭对外 HTTP/2。由于完整的 NGINX2Root 利用链还串联了 Linux 内核缺陷，除升级 nginx 外还需核查内核侧修复，不能把 nginx 升级视为消除到主机 root 路径的唯一措施。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root : New Remote Code Execution Vulnerabilities in nginx ...</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>
<li>nginx security advisories</li>
<li>NGINX ngx_http_v2_module vulnerability CVE-2026-123007</li>
<li>nginx2root: Critical nginx RCE vulnerabilities and how to fix them</li>

</ul>
</details>

**标签**: `#nginx`, `#vulnerability disclosure`, `#HTTP/2`, `#remote code execution`, `#Linux kernel`

---

<a id="item-tech-news-4"></a>
### [Quad9 退出法国：DNS 层反盗版封锁再引争议](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

公共 DNS 解析器 Quad9 已退出法国，事件围绕法国要求 DNS 解析器对盗版相关域名实施封锁展开。TechStackUps 的文章认为，DNS 解析器不是合适的执法点：它只能让域名无法解析，无法移除内容，用户还可通过更换解析器、DoH 或 VPN 绕过。对法国用户而言，这意味着少了一个公共解析器选项；文章没有给出受影响用户规模或封锁名单的具体范围。

hackernews · ritzaco · 11月18日 13:18 · [社区讨论](https://news.ycombinator.com/item?id=50545958)

**「背景」** Quad9 是一家总部位于瑞士的非营利公共递归 DNS 解析器，提供免费、注重隐私的服务，并内置恶意软件和钓鱼域名过滤。DNS 解析器负责把域名转换为 IP 地址，因此要求解析器屏蔽特定域名，会把版权执法变成对互联网基础解析层的统一过滤；Cloudflare 的评论文章将 Quad9 被迫退出法国视为这种 DNS 层强制封禁风险的例证。

**「影响」** 在法国依赖 Quad9 的用户和网络管理员需要改用其他解析器，相关配置也要迁移。把封锁要求施加在递归解析器上，会让原本中立的域名解析服务承担内容执法角色，并促使服务商在合规与保持中立之间做出退出或妥协的选择。

**「社区讨论」** 有评论者认为，不以起诉盗版者为核心的反盗版措施只是压制言论的后门；也有人认为执法具有选择性，商业规模侵权并未被同等追究。另一组讨论则追问，荒唐结果应归咎于法官错误解释法律，还是归咎于立法者制定了荒唐法律。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Quad9">Quad 9 - Wikipedia</a></li>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad 9 ’s withdrawal from France : A canary in the... | Cloudflare Blog</a></li>
<li><a href="https://www.techpassion.net/internet/quad9-leaves-france-dns-blocking/2169/">Quad 9 leaves France : DNS blocking order explained - TechPassion</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet censorship`, `#privacy`, `#internet governance`, `#Quad9`

---

<a id="item-tech-news-5"></a>
### [微软 Ignite 2026 发布七款新 AI 模型，主打可扩展性价比](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 7.0/10

微软在 Ignite 2026 上宣布推出七款新 AI 模型，以可扩展的性价比为主要卖点。目前提供的材料没有给出基准测试数据、定价、许可条款或具体可用性，因此无法独立判断这一性价比主张。有评论者称已测试 MAI Code 2，认为其表现与 Opus 或 Sol 大致相当，但这只是单个用户反馈，并非可验证的基准结果。

hackernews · gmays · 11月18日 16:08 · [社区讨论](https://news.ycombinator.com/item?id=50548021)

**「背景」** 这批模型以微软自有的 MAI 品牌发布，共七个，官方给出的定位是“可扩展的性价比”；其中 MAI Code 2 是代码模型，名称中的“2”表明它属于该系列的第二代产品。发布场合是微软 Ignite 2026 大会，这是微软面向企业与开发者集中公布产品更新的年度活动。

**「对开发与安全团队的影响」** 对成本敏感的编码和安全团队而言，微软给出的具体卖点是：MAI Cyber 2 Flash 在 CyberGymE 2 基准上以不到 GPT-6 Astra 单任务成本 2% 的水平达到其质量，MAI Code 2 则面向跨文件、整项目级编程；这会促使团队把这两类任务纳入模型选型对比。不过这些“同级质量、极低成本”的数字来自微软自述，采用前应在自有代码库和安全任务上复测，并核实商用许可和现有开发工具链的接入方式。

**「社区讨论」** 有评论者称已试用 MAI Code 2，认为其表现相当不错、与 Opus 或 Sol 大致相当；另一位评论者则主张微软应把部分模型开源或开放权重以争取市场份额，并警告否则可能重演 Windows Phone 的处境。另有评论批评 Ignite 主题演讲缺乏技术深度、微软云与生态对初创公司吸引力不足，但这些属于个人观感，并非可验证结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world class models at scalable... | Microsoft AI</a></li>
<li><a href="https://forklog.com/en/microsoft-unveils-ai-models-for-coding-and-cybersecurity/">Microsoft unveils AI models for coding and cybersecurity | ForkLog</a></li>
<li><a href="https://finance.yahoo.com/markets/article/microsoft-ignite-focuses-on-ai-models-for-specific-tasks-lowering-costs-for-enterprise-203433266.html">Microsoft &#x27;s AI pitch at Ignite : Cheaper models as business &#x27;token...</a></li>

</ul>
</details>

**标签**: `#Microsoft`, `#AI models`, `#MAI Code 2`, `#model release`, `#price-performance`

---

<a id="item-tech-news-6"></a>
### [能量基推理器宣称推理效率提升 385 倍](https://energy-based-reasoners.github.io/) ⭐️ 7.0/10

一个名为 Energy-Based Reasoners 的项目页面在 Hacker News 上被分享，声称能量基模型（EBM）推理器能实现 385 倍更高效的推理。这是项目方给出的说法，所给材料中没有独立复现或同行评审细节，因此尚不能视为已确认的突破。讨论者把这一成果限定在特定逻辑谜题任务上：有人认为这类方法在数独等小规模问题上有效，但质疑它能否扩展到更大规模；也有人追问页面是否明确定义了「能量」这一标量函数的取值域，因为文中只说明它为「给定输入下的候选预测赋予能量」。

hackernews · frenchmajesty · 11月18日 09:29 · [社区讨论](https://news.ycombinator.com/item?id=50543989)

**「背景：能量模型与 Kona 1.0」** 能量模型（EBM）学习一个标量函数，为给定输入下的每个候选预测赋予“能量”值，推理过程就是寻找低能量解，因此模型可以逐步自我纠错，而不是一次性生成答案。据 PaperLens 介绍，Logical Intelligence 已发布其称为首个商用能量推理模型的 Kona 1.0，图灵奖得主 Yann LeCun 以技术研究委员会创始主席身份加入；评论中提到的正是这一背景。

**「实际影响」** 对考虑采用该方法的开发者而言，关键约束在训练端而非推理端：有评论者称自己投入约一年训练 EBM，结论是它们堪称「出色的验证器」，但「极难训练」且高度依赖具体任务。这意味着 385 倍的推理加速未必能抵消训练与调参成本，评估时应先确认目标任务是否落在该方法已验证的小规模逻辑谜题范围内。

**「社区讨论」** 评论者提到由 Yann LeCun 等人担任主席的 Logical Intelligence，认为 EBM 在 LLM 传统上表现较弱的领域（如小学水平的算术与计数）有潜力；但同一批讨论者也质疑其数独求解器无法扩展，并要求看到任意规模数独的演示。另有评论从实现角度给出按「能量」优先修改冲突格子的数独思路，也有人认为该方法目前只在非常特定的逻辑谜题集合上效果良好，并对后续论文表示关注。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://paperlens.io/idea/kona-1/">Kona 1: Energy - Based Reasoning | PaperLens</a></li>
<li><a href="https://www.wired.com/story/logical-intelligence-yann-lecun-startup-chart-new-course-agi/">A Yann LeCun –Linked Startup Charts a New Path to AGI | WIRED</a></li>

</ul>
</details>

**标签**: `#energy-based models`, `#AI reasoning`, `#inference efficiency`, `#machine learning`

---

<a id="item-tech-news-7"></a>
### [curl 维护者：AI Rust 重写缺少上游修复](https://simonwillison.net/2026/Nov/18/daniel-stenberg/) ⭐️ 7.0/10

curl 维护者 Daniel Stenberg 表示，AI 代理将 18.5 万行 C 代码转换为 34 万行 Rust 代码期间，真实 curl 项目在三个多星期内合并了 300 多个提交，其中略多于 200 个是缺陷修复，还修复了若干漏洞。他指出这些 Rust 重写版没有包含上述修复，并反问这些克隆项目能否跟上 curl 上游持续进行的修复。

rss · Simon Willison · 11月18日 15:58

**「背景」** curl 维护者 Daniel Stenberg 曾多次收到将 curl 重写为 Rust 的请求或询问，这些提议有时是玩笑，有时是认真的。2026 年 11 月出现了两个由 AI 生成的 Rust 重写版本，其中一个项目声称花费 8,600 美元；Stenberg 的文章正是对这些“克隆”能否跟上上游维护工作的回应。

**「影响」** 对打算采用这些 AI 生成 Rust 重写版的人来说，代码规模更大并不等于与上游同步；若用于生产，需要自行补上 curl 上游这 200 多个缺陷修复和漏洞修复，或确认重写项目已经跟进。

<details><summary>参考链接</summary>
<ul>
<li>Actual #curl rewrites in #rust… - Post by daniel:// stenberg - Mastodon</li>
<li>Actual curl rewrites in rust - proomt</li>

</ul>
</details>

**标签**: `#curl`, `#Rust`, `#AI code generation`, `#open source maintenance`, `#security`

---

<a id="item-tech-news-8"></a>
### [编码智能体的外部沙箱模式与三个实现](https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/) ⭐️ 7.0/10

Simon Willison 与 Prime Radiant 发布了“外部沙箱”模式：编码智能体本身运行在沙箱外，它生成的代码被送入专用沙箱执行，以降低试用本地模型时因误操作或提示注入而造成破坏的风险。此次同时发布三个服务端实现——基于 v86 在 WebAssembly 中运行 Alpine Linux 的 Node.js 服务、在 Apple Containers 中运行 Alpine Linux 的 Python 服务，以及使用 Microsoft Quicksand（打包 QEMU 与 Alpine Linux）的 Python 服务。三者提供相同的 localhost API，可配置 Pi、Claude Code 或 Codex 将代码执行请求转发到沙箱；它们还附带可选的 HTTP/HTTPS 主机允许列表代理和凭据替换机制，使智能体无需持有真实密钥即可发起已认证 API 调用。

rss · Simon Willison · 11月17日 22:52

**「背景」** 本地运行编码代理时，代理会执行其生成的代码；一旦模型出错或遭到提示注入，就可能在机器上执行破坏性操作。外部沙箱模式据此把代理留在沙箱之外，只把需要执行的代码送进独立沙箱，并通过 localhost API 与沙箱通信。这样可以用虚拟机或容器隔离代码的影响范围，同时由沙箱侧的代理控制其网络访问。

**「影响」** 对需要运行编码智能体所生成代码的开发者而言，这一模式把执行环境与智能体进程分离，并允许按主机限制网络出口；采用时需确保允许列表和代理覆盖代码的实际依赖，否则安装依赖或访问外部 API 可能被拦截。凭据替换机制则让智能体在不接触真实密钥的情况下完成已认证请求。

**标签**: `#AI coding agents`, `#sandboxing`, `#security`, `#prompt injection`, `#developer tools`

---

<a id="item-tech-news-9"></a>
### [Java 曝出 CVE-2026-114938 远程代码执行漏洞](https://censys.com/advisory/cve-2026-114938/) ⭐️ 7.0/10

一则 Telegram 帖子援引 Censys 公告称，Java 存在无需认证的远程代码执行漏洞 CVE-2026-114938，CVSS 4.0 评分为 9.2，并称该漏洞已潜伏近四年。据该公告，影响范围包括 Java 17（17.0.6 及之后全部 17 线）、21、25、27；标准 Java 8/11 通常不受影响，但 Oracle Java 8 Performance Pack 例外。漏洞仅影响搭载 AVX-512 VBMI 指令集的 x86-64 服务器处理器，大致对应 2021 年及以后发布的 Intel 处理器（Ice Lake 及更新世代 Xeon）和 2022 年及以后发布的 AMD 处理器（Zen 4 及更新 EPYC/Ryzen）；ARM64 架构不受影响。目前这只是对 Censys 公告的转述，尚无独立确认，也未提供利用状态或缓解措施。

telegram · zaihuapd · 11月18日 03:55

**「背景」** 该漏洞的根源在于 OpenJDK HotSpot 的硬件加速 Base64 解码器：GitHub 上的漏洞说明将其描述为堆缓冲区溢出，并指出触发该漏洞的代码路径依赖 AVX-512。AVX-512 VBMI 是 x86-64 处理器的一项指令集特性，因此是否受影响不仅取决于 Java 版本，还取决于服务器 CPU 是否支持该特性；这也解释了为何 ARM64 以及不支持 AVX-512 VBMI 的机器不在影响范围内。

**「影响与应对」** 受影响的是在支持 AVX-512 VBMI 的 x86-64 服务器上运行 OpenJDK 17.0.6 及以上 17 线、21、25 或 27 的部署：攻击者无需认证即可触发 OpenJDK AVX-512 Base64 解码器中的内存破坏，进而可能执行任意代码，而 ARM64 主机以及标准 Java 8/11 部署不在范围内。运维方应优先清点 JDK 版本与 CPU 指令集，按厂商修复版本升级；在补丁到位前，可评估禁用 AVX-512 加速路径，并跟踪 watchTowr 持续更新的 FAQ，以获取受影响范围与缓解措施的变化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/java4shell-cve-2026-114938-enables-pre.html">Java 4 Shell Flaw ( CVE - 2026 - 114938 ) Enables Pre-Auth RCE in Jira...</a></li>
<li><a href="https://github.com/arkrwn/PoC-CVE-2026-114938-CrashLeak">GitHub - arkrwn/PoC- CVE - 2026 - 114938 -CrashLeak...</a></li>
<li>Java4Shell: Remote Code Execution in OpenJDK (CVE-2026-114938)</li>
<li>Java4Shell (Java CVE-2026-114938) FAQ - watchTowr</li>
<li>Java4Shell RCE: Affected Versions &amp; Fix (CVE-2026-114938)</li>

</ul>
</details>

**标签**: `#Java`, `#CVE-2026-114938`, `#remote code execution`, `#security advisory`, `#AVX-512`

---

<a id="item-tech-news-10"></a>
### [旅行者 1 号抵达距地一光日，约 260 亿公里](https://www.cnn.com/2026/11/18/science/voyager-1-light-day) ⭐️ 7.0/10

据科技圈茶馆转述 CNN 报道，旅行者 1 号于美东时间 11 月 18 日凌晨 5 时 16 分后到达距地球约 260 亿公里处，飞行约 49 年，成为首个距地球一个光日的人造物体。无线电信号从地球单程抵达探测器需 24 小时，NASA 仍能与探测器收发信号，但一次往返通信约需两天。目前探测器上仅两台科学仪器仍在工作；NASA 近期调整了设备供电，预计可节省约 10 瓦电力，使任务延长约两年半。

telegram · zaihuapd · 11月18日 14:41

**「背景知识」** “光日”是光在真空中运行 24 小时所经过的距离，约 260 亿千米；因此，当旅行者 1 号抵达这一距离时，它发出的无线电信号单程需要约 24 小时才能到达地球。旅行者 1 号于 1977 年发射，已在太空中飞行约 49 年。这次抵达一个光日的距离，是它持续远离太阳系过程中的一个新节点。

**「影响」** 对任务运行而言，一条指令要一天后才能到达探测器，确认执行结果又要再等一天，因此异常处置和操作排序都必须按天级节奏规划；同时，10 瓦的供电节省直接换算成约两年半的运行时间，供电预算实际上决定了哪些仪器还能继续开机。

**标签**: `#Voyager 1`, `#NASA`, `#space exploration`, `#deep-space communications`, `#power management`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [FlyDSL MonoKernel 降低 vLLM 交互式解码延迟](https://vllm.ai/blog/2026-11-18-flydsl-monokernels) ⭐️ 8.0/10

rss · vLLM Blog · 11月18日 00:00

**「背景」** 编码 agent 等交互式应用把解码放在任务关键路径上，低并发服务更看重单用户响应速度而非总吞吐。一次解码步骤要依次启动投影、注意力、专家计算等一连串 GPU kernel；小 batch 下每个 kernel 工作量很小，却仍要付出 GPU 侧的调度、启动与收尾开销，依赖关系又限制了重叠，HIP graph 只能省掉 CPU 启动开销。

**「方案」** 作者用 AMD 的 FlyDSL（Python DSL 与 MLIR 编译器）把多个依赖算子阶段合并进单次 persistent kernel 启动：固定网格的线程块跨阶段复用，提前预取后续权重，用带标签的 mailbox 按消费者所需粒度传递就绪数据，并在 kernel 内完成 TP all-reduce。融合边界必须按模型定制——DeepSeek-V4.1-Flash 把标准层拆成 K1（注意力前段与 KV cache 插入）和 K2（注意力后段、FFN 与两次 all-reduce），MiniMax-M3 则只融合 FFN 部分。在 vLLM 中它作为“特化解码”接入：默认关闭、由 --monokernel 开启，不支持的部署在启动时报错并列出全部原因，调度器、KV cache、投机解码与 HIP graph 均不变，每步由 plan\(\) 决定哪些层走 mono。作者报告 MI355X TP2 上 DeepSeek-V4.1-Flash 并发 1 的 P90 交互性从 318.1 升到 429.1 tok/s/user；MI325X 移植把单个解码层从 32 个 kernel/320 µs 降到 2 个/115 µs，并发 1 交互性 182.25→411.26 tok/s/user；GLM-5.2 的 RFC 测量把一步从约 2459 个 kernel 降到约 210 个，batch 1 每 token 时间 13.70→5.92 ms。精度方面作者称各模型差异在噪声范围内（GPQA-Diamond 85.3→85.1），但 TP8 等配置仍在评估。局限也很明确：收益随并发升高递减，步宽受限（DeepSeek 48 行、MiniMax/Kimi 16 行），MI300X/MI325X 因缺少低精度矩阵指令还需保留额外权重副本。

**「启示」** 作者的核心论点是：低并发解码的大量时间耗在 kernel 边界之间，由 kernel 作者显式设计调度的 MonoKernel 能把这段空隙转成可重叠的工作；但它是针对特定模型、TP 规模与步宽的定点优化，并不能替代面向吞吐的通用批处理路径。

**标签**: `#LLM inference`, `#GPU kernels`, `#vLLM`, `#kernel fusion`, `#AMD ROCm`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美联储会议纪要：官员预计还需加息，并担忧 AI 推高通胀](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 9.0/10

美联储 10 月会议纪要显示，官员们认为通胀压力“广泛存在”，几乎所有人都判断为进一步加息可能是合适的，因此以 10 票赞成、2 票反对将基准利率维持在 3.75%-4%区间；两位反对者主张加息 25 个基点。纪要还把人工智能相关需求列为“重要的通胀风险来源”，并提到 AI 相关债务快速增长带来的金融稳定风险。

rss · CNBC Finance · 11月18日 19:41

**「背景」** 10 月 28 日结束的美联储议息会议决定将联邦基金利率目标区间维持在 3.75%至 4%，周三公布的会议纪要则披露了官员们当时对通胀和后续加息的讨论。

<details><summary>参考链接</summary>
<ul>
<li>Federal Reserve issues FOMC statement</li>
<li>Fed rate decision October 2026 - CNBC</li>

</ul>
</details>

**标签**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#AI risk`, `#interest rates`

---

<a id="item-finance-news-2"></a>
### [美联储理事沃勒称可能需在 12 月加息 50 个基点](https://www.cnbc.com/2026/11/18/federal-reserve-governor-christopher-waller.html) ⭐️ 7.0/10

美联储理事克里斯托弗·沃勒 11 月 18 日表示，为应对通胀，央行可能需要在 12 月 8 日至 9 日的联邦公开市场委员会会议上加息 50 个基点（0.5 个百分点），并逆转 2025 年的三次降息（每次 25 个基点）。这是沃勒的个人主张，并非美联储已作出的决定。

rss · CNBC Finance · 11月18日 15:13

**「背景」** 美联储 9 月实施了三年多来首次加息，10 月维持利率不变；期货市场目前完全计入 12 月加息 25 个基点，而多数通胀读数仍高于 3%，也高于美联储 2%的目标。

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#Christopher Waller`

---

<a id="item-finance-news-3"></a>
### [美国芯片新规后五家银行暂停 4.8 亿美元字节跳动相关 GPU 贷款](https://www.bloomberg.com/news/articles/2026-11-17/banks-pause-480-million-chip-loan-tied-to-china-s-bytedance) ⭐️ 7.0/10

据彭博社报道，美国最新的 AI 芯片管制出台后，五家银行暂停推进一笔 4.8 亿美元贷款，该贷款原计划为字节跳动在马来西亚数据中心采购英伟达先进 GPU 提供融资。借款方新加坡云服务商 Aolani Cloud 表示，正与监管机构和融资伙伴评估新规；部分银行则在讨论退出该融资。

telegram · zaihuapd · 11月18日 05:11

**「背景」** 美国新规要求新加坡、马来西亚等东南亚国家的数据中心运营商在采购先进 AI 芯片前先取得许可证。据 ZeroHedge 报道，相关芯片的物理位置虽在马来西亚，但由当地实体 Aolani Cloud 持有，字节跳动以类似云服务的方式使用这些算力。

**「影响」** 据 CNBC 报道，分析师预计，美国收紧对东南亚数据中心的芯片出口将导致当地数据中心建设和运营延迟、成本上升，而不是终止该地区的 AI 建设热潮——这直接压向在当地租用算力的云服务商与数据中心开发商。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.zerohedge.com/ai/first-domino-falls-us-ai-chip-crackdown-freezes-480-loan-linked-chinas-bytedance">First Domino Falls: US AI Chip Crackdown Freezes $ 480 MM Loan ...</a></li>
<li><a href="https://tech-insider.org/bytedance-nvidia-b200-chips-malaysia-ai-deal/">ByteDance Nvidia B200 Deal: 36,000 Chips, $2.5B — Full Price and...</a></li>
<li><a href="https://www.cnbc.com/2026/11/18/nvidia-us-ai-chip-export-controls-data-centers-.html">New U . S . chip curbs put Southeast Asia&#x27;s data center boom at risk</a></li>

</ul>
</details>

**标签**: `#US AI chip controls`, `#ByteDance`, `#GPU financing`, `#data center financing`, `#Malaysia`

---

<a id="item-finance-news-4"></a>
### [腾讯三季度营收 2073 亿元，资本开支升至 814.33 亿元](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

腾讯公布 2026 年第三季度财报，营收 2073 亿元人民币，同比增长 8%，低于市场预期；归母净利润 636 亿元，同比增长 0.8%。当季资本开支 814.33 亿元，远超市场预估的 554 亿元，单季自由现金流为负 691 亿元；腾讯同时称其 AI 产品 WorkBuddy 日均 Token 用量超过 100 万亿，为国内大语言模型产品最高（该说法由公司披露，未经独立验证）。

telegram · zaihuapd · 11月18日 09:20

**「背景」** WorkBuddy 是腾讯面向办公场景推出的 AI Agent，可自主拆解并完成报告、幻灯片等任务，属于腾讯从聊天机器人转向“代理式 AI”的产品之一。

**「影响」** 资本开支大幅超出预期，意味着腾讯当季用于算力等基础设施的支出显著抬升；自由现金流为负则表明当季经营现金不足以覆盖投资支出，可能压缩其回购与分红的操作空间。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.workbuddy.ai/">WorkBuddy - AI Agent for Everyday Office Work</a></li>
<li><a href="https://www.appeconomyinsights.com/p/micron-demand-goes-vertical">While Meta and Tencent push deeper into the AI stack</a></li>

</ul>
</details>

**标签**: `#Tencent`, `#earnings`, `#AI capex`, `#free cash flow`, `#China tech`

---

<a id="item-finance-news-5"></a>
### [中韩宣布自贸协定服务与投资后续谈判实质性结束](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

中韩 11 月 18 日宣布自贸协定服务与投资后续谈判实质性结束，中方承诺在电影、游戏等领域给予韩国最惠国待遇，并扩大旅游、法律、建筑和金融等领域开放；双方还将视听共同制作范围从电影扩至电视剧、动画、综艺和纪录片。谈判自 2018 年 3 月启动、历时 8 年 8 个月，目前并非最终签署或批准，部分技术事项仍留待工作层协商。

telegram · zaihuapd · 11月18日 10:02

**「背景」** 中韩自贸协定于 2015 年生效，但服务和投资领域的开放需另行谈判，双方因此于 2018 年 3 月启动后续谈判，至今已进行多轮正式磋商。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://english.motir.go.kr/eng/article/EATCLdfa319ada/2484/view">The First Korea – China FTA Services and Investment Follow - up ...</a></li>

</ul>
</details>

**标签**: `#China-South Korea FTA`, `#services and investment`, `#trade policy`, `#media and games`, `#market access`

---

<a id="item-finance-news-6"></a>
### [九部门拟推动新能源汽车“车电一体报废”](https://wallstreetcn.com/articles/3786200) ⭐️ 7.0/10

中国商务部等九部门 11 月 17 日提出修订《报废机动车回收管理办法实施细则》，拟推动新能源汽车“车电一体报废”回收拆解，并研究制定动力电池数字身份证管理制度；相关办法仍待制定。

telegram · zaihuapd · 11月18日 12:22

**「背景」** 今年 4 月施行的暂行办法已规定，报废新能源汽车若缺失动力电池，应认定为车辆缺失；新规拟在此基础上进一步明确回收环节要求。

**「影响」** 若最终实施，报废新能源汽车将需连车带电池一并交售，回收拆解和动力电池回收企业还需记录电池流转信息。

**标签**: `#新能源汽车`, `#动力电池回收`, `#报废机动车`, `#监管政策`, `#电池数字身份证`

---