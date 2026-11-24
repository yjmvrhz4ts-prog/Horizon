---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 35 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [百度开源文心 5.5 Flash Preview：280B MoE、Apache 2.0](#item-tech-news-1) ⭐️ 8.0/10
2. [Ternary Bonsai 2.5 27B 三值量化模型发布](#item-tech-news-2) ⭐️ 7.0/10
3. [Quad9 因法国法律限制停用当地 DNS 服务](#item-tech-news-3) ⭐️ 7.0/10
4. [Check Point 安全管理服务器遭在野入侵，攻击者伪造管理员会话](#item-tech-news-4) ⭐️ 7.0/10
5. [Brendan Gregg 启发的性能分析：确定性 VM 与火焰图之争](#item-tech-news-5) ⭐️ 7.0/10
6. [Simon Willison 回顾 LLM 十二个月的三个拐点](#item-tech-news-6) ⭐️ 7.0/10
7. [Z.ai 发布 GLM-5.4：首个循环 Transformer 编程模型](#item-tech-news-7) ⭐️ 7.0/10
8. [黄循财称新加坡不会充当规避美芯片管制通道](#item-tech-news-8) ⭐️ 7.0/10
9. [vCenter 曝 9.8 分免鉴权漏洞，Broadcom 发布补丁](#item-tech-news-9) ⭐️ 7.0/10

**科技博客**
1. [vLLM 为 ERNIE 5.5 Flash Preview 提供 Day-0 插件支持](#item-tech-blog-1) ⭐️ 6.0/10
2. [vLLM-GR：生成式推荐推理框架](#item-tech-blog-2) ⭐️ 5.0/10

**财经新闻**
1. [小米三季度经调整净利同比下降 56.8%，汽车交付超 10 万辆](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [百度开源文心 5.5 Flash Preview：280B MoE、Apache 2.0](https://x.com/Baidu_Inc/status/2125077484442190137) ⭐️ 8.0/10

百度于 11 月 24 日通过官方 X 账号宣布，文心 5.5 Flash Preview 以 Apache 2.0 协议在 Hugging Face 和 ModelScope 开放权重，开发者可用 vLLM 或 SGLang 部署并微调。该模型采用 MoE 架构，总参数 280B、每 token 激活 14B，上下文长度为 1M token；百度称其是基于 ERNIE 5.5 Flash Base 训练的首个后训练模型。流传的基准图表显示 Terminal-Bench 4.0 为 46.5 分、DeepSWE v1.1 为 71.2 分，但百度未说明这些结果是否经过第三方独立验证，且该版本仍属 Preview。

telegram · zaihuapd · 11月24日 07:32

**「背景」** 文心 5.5 Flash Preview 采用混合专家（MoE）架构：总参数 280B 指全部专家权重的规模，而每个 token 仅激活其中 14B，因此推理成本更接近中小模型，同时保留较大的容量。据百度说明，该模型是基于 ERNIE 5.5 Flash Base 训练的首个后训练模型，此次以 Apache 2.0 开放的正是这一后训练版本的权重。

**「影响」** 对希望本地部署或微调长上下文模型的开发者而言，Apache 2.0 权重和 vLLM、SGLang 支持降低了许可与工具链门槛；但 Preview 状态和未经独立验证的基准意味着生产选型仍需自行复测。

**标签**: `#open-source LLM`, `#Baidu ERNIE`, `#mixture-of-experts`, `#Apache 2.0`, `#long context`

---

<a id="item-tech-news-2"></a>
### [Ternary Bonsai 2.5 27B 三值量化模型发布](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 7.0/10

Ternary Bonsai 2.5 27B 是一款面向本地推理的 27B 三值量化模型，社区用户已在其 Q2 GGUF 版本上做了实际测试。一位用户在 24GB 内存的 Mac Mini M5 Pro 上报告生成速度约 22—25 token/s、首 token 约 2.12 秒，并能较轻松地容纳 128k 上下文。另有用户称该模型在 SWE-bench Verified 上的表现与 Opus 4.6 相当，但这一说法尚未经过独立验证，评测配置也未说明。目前公开细节主要来自社区讨论，官方基准和完整规格仍有限。

hackernews · b0m · 11月24日 20:08 · [社区讨论](https://news.ycombinator.com/item?id=50633922)

**「背景」** Bonsai 系列的核心做法是三值权重量化：权重只存 \{-1, 0, +1\} 而非 16 位浮点，从而把 27B 参数模型（有分析指出 Bonsai 2 基于 Qwen3.8）从约 54 GB 压到约 7.67 GB。2026 年 9 月发布的 Bonsai 2 27B 相比全精度版本体积缩小 9 倍以上，仍保留 98.2% 的综合基准性能，2.5 版本延续的正是这条以体积换部署便利的压缩路线。

**「本地部署的实际影响」** 对打算在单机上跑长上下文 agent 的开发者来说，直接后果是硬件门槛落在消费级内存上：社区用户在 24GB 内存的 Mac Mini 上运行该模型的 Q2 GGUF，实测生成速度约 22–25 tok/s、首 token 约 2.1 秒，并称 128k 上下文可常驻内存，因此有望用于批量 agent 编码任务。不过，同一讨论中有人追问除 FPGA 外是否存在三元权重的专用硬件加速，这表明当前吞吐主要来自常规量化推理路径，不能把速度归因于三元计算硬件。在把这套配置接入实际 agent 流程前，应先用自己的任务验证工具调用与长上下文表现，而不是仅凭基准分数决定。

**「社区讨论」** 评论者对小型模型的进展表示兴奋，但对 SWE-bench 等价说法持保留态度，认为这可能同时来自基准针对性优化、基准本身变化，以及小模型滞后约半年接近前沿水平。也有人要求与同尺寸的 Q1/Q2 量化模型直接对比，并询问除 FPGA 外是否已有三值权重的硬件加速支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://prismml.com/news/bonsai-2-27b">PrismML — Introducing Bonsai 2 27B: Near-Lossless Compression ...</a></li>
<li><a href="https://www.mindstudio.ai/blog/ternary-bonsai-2-27b-benchmarks">Bonsai 2 27B Benchmarks: Does Ternary Quantization Actually ...</a></li>

</ul>
</details>

**标签**: `#ternary quantization`, `#local LLM inference`, `#small language models`, `#GGUF`, `#agentic coding`

---

<a id="item-tech-news-3"></a>
### [Quad9 因法国法律限制停用当地 DNS 服务](https://quad9.net/news/blog/quad9-service-deactivation-in-france/) ⭐️ 7.0/10

Quad9 已停用其在法国的 DNS 解析服务，法国用户经 9.9.9.9 等地址发起的查询会失败。社区用户 11 月 24 日实测显示，查询返回 REFUSED，并带有 EDE 18（Prohibited），表明原因是法国法律限制；Quad9 官方博客确认了撤出，但现有材料未说明具体法律依据。作为应对，有用户搭建了转发至 Quad9 的公共代理，支持 DoH、DoT 和 Do53。

hackernews · farrokhi · 11月24日 08:33 · [社区讨论](https://news.ycombinator.com/item?id=50625384)

**「背景」** 公共递归 DNS 负责把域名解析为 IP 地址，用户可通过 9.9.9.9 这类固定地址直接调用，而不必自行运行解析器；Quad9 就是提供此类服务的公共解析器之一。社区评论称，法国用户在 2026 年 11 月 24 日已看到对 9.9.9.9 的查询返回 REFUSED，并带有 EDE 18（Prohibited）及“因法国法律限制服务不可用”的说明。

**「实际影响」** 对法国的个人、企业和公共部门用户来说，继续把 Quad9 解析器作为递归 DNS 将不再可用；Quad9 已在 2026 年 11 月 24 日停用法国服务。依赖其统一 DNS 配置的机构需要改配其他解析器，并重新检查转发链路，否则相关域名查询会失败。

**「社区讨论」** 有评论者为法国境内用户搭建了缓存并转发至 Quad9 的公共 DNS 代理，称支持 DoH、DoT、Do53 的 UDP/TCP 以及 IPv4/IPv6，可作为“基本可直接替换”的方案；另有评论者质疑为何不自行运行 Unbound 等解析器，并询问公共解析器在规模上的优势。上述可用性与替代方案的说法来自评论者，尚未经独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://quad9.net/news/blog/quad9-service-deactivation-in-france/">Quad 9 Service Deactivation in France | Quad 9</a></li>
<li><a href="https://www.commentcamarche.net/applis-sites/39161-quad9-fin-france/">Ce DNS gratuit et populaire refuse de bloquer les sites pirates...</a></li>

</ul>
</details>

**标签**: `#DNS`, `#internet infrastructure`, `#privacy`, `#France`, `#legal policy`

---

<a id="item-tech-news-4"></a>
### [Check Point 安全管理服务器遭在野入侵，攻击者伪造管理员会话](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 7.0/10

据 GreyNoise 博文，一场针对 Check Point 安全管理服务器的在野入侵活动正在进行：攻击者反复请求 HFS 的 loginSrp1 登录端点，收集 JavaScript Math.random\(\) 的输出，重建 Node.js V8 PRNG 的内部状态，进而恢复 HFS 会话 Cookie 的签名密钥并伪造管理员会话。该攻击链的核心是可预测随机数导致的会话 Cookie 伪造，而非单纯的漏洞扫描。现有信息未说明受影响版本、修复状态或攻击者归因。

hackernews · louiereederson · 11月24日 16:32 · [社区讨论](https://news.ycombinator.com/item?id=50630594)

**「背景」** 这一攻击的关键前提是会话 Cookie 的 \`sid\` 由 JavaScript 的 \`Math.random\(\)\` 生成：评论中引述的报告称，攻击者反复请求 HFS 的 \`loginSrp1\` 端点，收集足够多的输出后重建 Node.js V8 PRNG 的内部状态，进而恢复 Cookie 签名密钥并伪造管理员会话。换言之，问题不只是某个登录端点被绕过，而是随机数输出可预测，使原本用于防伪的签名机制可以被离线推算和伪造。

**「影响」** 对暴露在互联网上的 Security Management Server 和多域管理服务器（MDS）而言，SmartConsole 登录流程中的 CVE-2026-16232 可让未认证的远程攻击者取得完整管理员权限。运维方应依据 Check Point 公告修补相关组件，并限制管理界面的公网访问。

**「社区讨论」** 评论中，有人将此事视为 PRNG 老问题的重演，并认为应修复 Math.random 这类默认随机数接口，而不是逐个修补误用它的应用；也有人质疑初始访问方式，推测 CVE-2026-16232 是入口，并追问受影响组织是否都把管理服务器暴露在互联网上。上述均为评论者的判断或疑问，现有材料未给出确认。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.rapid7.com/blog/post/ra-check-point-smartconsole-authentication-bypass-technical-analysis-cve-2026-16232/">Check Point SmartConsole Authentication Bypass Technical Analysis...</a></li>
<li><a href="https://digital.nhs.uk/cyber-alerts/2026/cc-4820">Check Point Releases Security Update for Critical Authentication...</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#Check Point`, `#active exploitation`, `#session forgery`, `#PRNG predictability`

---

<a id="item-tech-news-5"></a>
### [Brendan Gregg 启发的性能分析：确定性 VM 与火焰图之争](https://fzakaria.com/2026/11/12/worshipping-at-the-altar-of-brendan-gregg) ⭐️ 7.0/10

一篇受 Brendan Gregg 启发的性能分析文章在 Hacker News 上引发讨论，焦点包括确定性虚拟机、火焰图（flamegraph）的适用边界，以及多线程和异步工作负载的关键路径分析。由于文章正文未提供，现有信息主要来自评论：有评论者提到曾看到该 VM 是单线程的，并质疑其在高吞吐多线程流水线中的分析能力；也有人表示火焰图难以推断跨线程依赖。另有评论者指出，异步代码（如 C++ 协程、fiber、future）的关键路径分析可能需要修改框架代码，嵌入请求上下文来关联不同线程上的续接任务。

hackernews · kqr · 11月24日 10:50 · [社区讨论](https://news.ycombinator.com/item?id=50626413)

**「背景」** 火焰图把采样得到的调用栈按耗时聚合，适合定位 CPU 热点，却不容易直接显示跨线程依赖和异步任务之间的因果关系。文章页面的摘要则把确定性虚拟机（如 Rewind）描述为可重复重放的调试与优化环境，作者称已用它排查 heisenbugs、让 profile-guided optimization 可复现，并让 Nix 构建达到 bit-reproducible。

**「社区讨论」** 评论者把确定性 VM 与 Antithesis、rr 等记录-回放工具作类比；aidanhs 认为单线程设计可能削弱高吞吐多线程分析，并称自己已对用火焰图做多线程性能分析失去热情，uvdn7 则追问这类方法能否处理 C++ 协程、fiber、future 等异步负载，认为不修改框架、嵌入请求上下文就很难找到关键路径。hungryhobbit 还介绍了 Nvidia 的“speed of light”思路：先估算去掉一切阻碍后的理论上限，再定位瓶颈。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://fzakaria.com/2026/11/12/worshipping-at-the-altar-of-brendan-gregg">Worshipping at the altar of Brendan Gregg - fzakaria.com</a></li>

</ul>
</details>

**标签**: `#performance analysis`, `#profiling`, `#flame graphs`, `#deterministic VM`, `#record-replay`

---

<a id="item-tech-news-6"></a>
### [Simon Willison 回顾 LLM 十二个月的三个拐点](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 7.0/10

Simon Willison 在 11 月 24 日的回顾中，以 Claude Opus 4.5 发布一周年为参照，总结过去十二个月 LLM 与编码智能体的三个拐点。第一个拐点出现在 2025 年 11 月：他称 Opus 4.5 让 Claude Code 的默认结果通常正确，达到可日常使用的程度；OpenAI 同月发布的 GPT-5.1 Instant、GPT-5.1 Thinking、GPT-5.1-Codex 和 GPT-5.1-Codex-Max 也让 Codex 对许多编码任务可靠有用。第二个拐点出现在 2026 年 6–7 月，即“Fable 类模型”：Claude Fable 5 发布三天后因出口管制被实际禁用，直到 7 月 1 日恢复；Willison 将 Fable 5、5.1、5.2 和 Claude Opus 5.5 等归入此类，其特点是只要给出目标和工具，就能自行穷举解决问题。第三个拐点出现在 2026 年 9–10 月，前沿模型在 3D 建模和游戏开发上明显跃升，9 月 22 日发布的 Opus 5.5 被他称为首个似乎理解“乐趣”的模型；这些判断来自他的个人使用经验和主题演讲，而非独立基准测试。

rss · Simon Willison · 11月24日 23:02

**「背景」** Claude Code 于 2025 年 2 月 24 日随 Claude 3.7 Sonnet 推出，到 Opus 4.5 发布时只有九个月历史。作者此前没有把它当作日常主力，因为结果经常需要人工纠正；2025 年 11 月 24 日发布的 Opus 4.5 改变了他的使用体验，也成为这篇回顾的时间锚点。

**「影响」** 对使用这些模型的开发者，实际操作的重点从“代码补全质量”转向“给定目标和工具后能否端到端完成任务”：Willison 描述 Fable 会自行搭建截图与本地日志工具来排查 Safari 显示问题，Opus 5.5 则用 12 小时试玩和重平衡把一款 RTS 从无聊改到有趣。

**标签**: `#LLM agents`, `#coding agents`, `#AI engineering`, `#Claude Opus`, `#industry analysis`

---

<a id="item-tech-news-7"></a>
### [Z.ai 发布 GLM-5.4：首个循环 Transformer 编程模型](https://simonwillison.net/2026/Nov/23/glm-54/) ⭐️ 7.0/10

Z.ai 发布 GLM-5.4，这是其首个采用循环 Transformer（looped transformer）架构的模型，主打通用编程能力。该架构让一组共享权重的层在一次前向传播中多次迭代、细化隐藏状态，从而在不增加参数量的情况下加深网络。模型目前尚未开放权重，Z.ai 表示将在完成必要的安全加固后“负责任地”开源；现阶段只能通过 Coding Plan 订阅使用，常规 API 尚不可访问，两者共用位于 https://api.z.ai/api/v1 的 OpenAI 兼容 Responses API。Simon Willison 的试用显示，GLM-5.4 在 pelican 测试中的生成质量与 GLM-5.3 相近，风格更接近 OpenAI 或 Anthropic 的模型，但源内容未提供基准测试或独立评测数据。

rss · Simon Willison · 11月23日 23:40

**「背景：循环 Transformer」** 循环 Transformer 的基本思路是让一组共享权重的层在一次前向传播中重复运行多次，每一轮基于上一轮的隐藏状态继续细化，从而在不增加参数量的情况下加深有效计算。GLM-5.4 之前，Z.ai 的 GLM 系列已迭代到 5.3；同一周内，Thinking Machines Lab 的 Inkling 2 Mini 也采用了循环结构，并称其中间层会对每个 token 运行三次。

**「对开发者的实际影响」** 对开发者来说，GLM-5.4 目前既不在常规 API 上提供，也没有开放权重：想试用只能订阅 Z.ai 的 Coding Plan，该套餐的 key 可用于 https://api.z.ai/api/v1 的 OpenAI 兼容 Responses 接口，而官方尚未公布基准数据和 API 定价（据第三方报道，该模型于 11 月 23 日上线 Coding Plan，支持视觉并附带 50% 的周配额提升）。这也意味着现有工具链需要适配——作者原本使用的 llm-zai 插件尚不支持新模型，他因此临时发布了 llm-glm 插件，并打算在 llm-zai 跟上后停用自己的版本；在官方基准缺失的情况下，选型评估目前只能依赖这类实际试用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://thenextweb.com/news/zai-glm-5-4-loop-transformer-coding-model">Z . ai ’s GLM - 5 . 4 runs its layers twice to rival 2T-parameter models</a></li>
<li><a href="https://www.orcarouter.ai/blog/glm-5-4-release-what-we-know">GLM - 5 . 4 Arrives on Z . ai &#x27;s Coding Plan: No Benchmarks Yet</a></li>

</ul>
</details>

**标签**: `#looped transformers`, `#GLM-5.4`, `#AI model releases`, `#coding models`

---

<a id="item-tech-news-8"></a>
### [黄循财称新加坡不会充当规避美芯片管制通道](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

新加坡总理黄循财表示，新加坡不会成为企业规避美国芯片出口管制的通道，当局正在调查 Megaspeed 采购英伟达芯片的交易。此前一天，美国商务部将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单；《联邦公报》称这些企业存在向未获授权用户转移先进计算产品的“重大风险”，名单包括其在马来西亚和泰国的关联实体。路透社报道，阿里巴巴新加坡子公司 Apex Enterprise Solutions 同样在列，阿里称从未转移受管制的先进计算芯片。

telegram · zaihuapd · 11月24日 05:03

**「背景」** 美国对先进计算芯片的出口管制通过出口许可和实体清单等机制执行：被列入清单的企业在采购美国技术或产品时须申请许可，并通常面临严格审查。此次争议的核心在于，第三国是否会被用作受管制芯片流向未授权用户的中间环节。

**「实际影响」** 被列入实体清单后，Megaspeed、其马来西亚子公司 Speedmatrix 以及阿里巴巴新加坡子公司 Apex Enterprise Solutions 在获取受美国出口管制的物项时须先申请许可证，美国供应商向这些实体出货同样需要获得许可，因此并不是一律禁止交易。阿里巴巴方面称 Apex“从未转移受美国出口限制的先进计算芯片”，并认为将其列入清单是错误的；因此这些实体的实际业务影响将取决于许可证审批结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://uz.kursiv.media/en/2026-11-24/us-blacklist-megaspeed-alice-huang/">US blacklists Megaspeed , once led by China spy suspect Alice Huang</a></li>
<li><a href="https://www.straitstimes.com/world/united-states/us-blacklists-megaspeed-chip-firm-linked-to-nvidia-scandal">US blacklists Megaspeed , Alibaba unit amid Nvidia scandal</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/us-blacklists-alibaba-owned-company-014536273.html">US Blacklists Alibaba -Owned Company in Setback to AI Ambitions</a></li>

</ul>
</details>

**标签**: `#semiconductor export controls`, `#AI chips`, `#Singapore`, `#Nvidia`, `#US-China tech`

---

<a id="item-tech-news-9"></a>
### [vCenter 曝 9.8 分免鉴权漏洞，Broadcom 发布补丁](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 7.0/10

Broadcom 为 VMware 产品线发布涵盖 23 个漏洞的补丁，其中 vCenter 目录服务（vmdir）的鉴权绕过 CVE-2026-123903 被评为 9.8 分。该漏洞允许能访问 vCenter 的攻击者绕过认证直接进入系统。所给摘要称，该漏洞在补丁发布前几天曾被作为零日利用；但这条 Telegram 转述未提供受影响版本、修复版本或独立验证。

telegram · zaihuapd · 11月24日 14:50

**「背景」** vCenter 是 VMware 的集中管理平台，其目录服务 vmdir 承载身份与目录数据；一旦攻击者能访问 vCenter，这类鉴权绕过便可能让其无需账号进入管理面。就在本次补丁发布前数日，已有报道称另一个 vCenter 鉴权绕过漏洞 CVE-2026-123890 需要紧急修补，并提到有安全厂商将攻击活动归因于一个疑似中国背景的团伙；本次的 CVE-2026-123903 是同一产品上另一起编号不同的漏洞，两者不应混淆。

**「影响」** 对可访问 vCenter 的管理员而言，应优先限制访问 vCenter 的网络范围，并核对 Broadcom 公告以确认修复版本；在免鉴权绕过的前提下，只依赖账户口令或外围访问控制不足以降低风险。

<details><summary>参考链接</summary>
<ul>
<li>VMware vCenter CVE-2026-123890: Fixed Builds and What to Do</li>
<li>CVE-2026-123890: vCenter authentication-bypass vulnerability</li>
<li>Broadcom fixes critical CVE-2026-123890 in VMware ...</li>

</ul>
</details>

**标签**: `#vCenter`, `#VMware`, `#authentication bypass`, `#zero-day`, `#CVE-2026-123903`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [vLLM 为 ERNIE 5.5 Flash Preview 提供 Day-0 插件支持](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 6.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** ERNIE 5.5 Flash Preview 是 280B 总参数、每 token 激活 14B 的稀疏 MoE 模型，支持 1M 上下文并面向长程 Agent；在发布日接入 vLLM 是主要部署挑战。

**「方案」** 百度 ERNIE 团队与 vLLM 用独立 vLLM-ERNIE 插件实现 Day-0 支持：在 vllm==0.32.0 环境中装入插件，vLLM 经 vllm.general\_plugins 自动加载，且只在 config 指定 ERNIE 架构时导入模型代码。插件复用 vLLM 的注意力、KV cache、投机解码、并行与服务端能力，前缀缓存、chunked prefill、CUDA graph、PD 分离等可直接使用。针对 VHA 跨头混合、Multi-Router Latent MoE、MultiMax 输出头和门控注意力，作者设计融合 kernel，并在加载时预折叠权重、融合 FP8 量化，称相对逐算子实现有 1.55× 至 6.53× 的单 kernel 加速。模型采用 MXFP4 路由专家（W4A8 QAT）、其余 FP8 与 FP8 KV cache；FlashIndexer 用动态头路由和阈值预过滤降低稀疏索引开销，作者称 1M 上下文下约 1.4× 加速；3 层 DSpark 草稿模型每步最多提议 7 个 token，平均接受长度超过 4.0。这些数字来自厂商博文，未附完整测量条件或独立复现。

**「启示」** 文章的核心是“模型代码与专用 kernel 放进插件、通用推理能力交给 vLLM”的集成路径，使新模型能在发布日进入生产栈而无需维护 fork。其价值取决于读者是否部署该模型，以及厂商声明的加速能否在自身负载上复现。

**标签**: `#vLLM`, `#ERNIE 5.5 Flash`, `#MoE inference`, `#kernel fusion`, `#speculative decoding`

---

<a id="item-tech-blog-2"></a>
### [vLLM-GR：生成式推荐推理框架](https://vllm.ai/blog/2026-11-24-vllm-gr-announcement) ⭐️ 5.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** 生成式推荐要在单次请求的延迟预算内，把用户的长交互历史转化为一组可展示的候选物品。以 OneRec 为例，模型生成语义 ID（SID），服务端则需探索多条候选路径，同时避免为每个候选重复处理同一段历史。

**「方案」** vLLM-GR 在 vLLM 的调度、模型执行和分页 KV cache 之上加入贯穿整个搜索过程的 beam session：EngineCore 管理会话，调度器下发 prefill/decode，模型 runner 为下一 token 打分，beam 选择记录存活路径的分数与父索引，下一步 decode 据此读取对应 KV。多个 beam 共享 prompt KV，目录约束把生成限制在真实物品的 SID 上；在 PDD 流水线中，主机准备下一阶段与加速器执行当前阶段重叠。作者报告了覆盖 NVIDIA 与 Ascend 六种加速器、beam 宽度 256/128 和 batch 1/4/8 的 P99 测试：W=256、B=4/8 时 vLLM-GR 在六种硬件上均最低，H20 上 B=8、W=256 为 369.4 ms，对比 SGLang 的 1280.1 ms 和 NVIDIA SID-GR 的 428.1 ms。但 B=1 时并非总是领先，RTX PRO 6000 上 SID-GR 为 28.25 ms、vLLM-GR 为 29.21 ms；且各图来自计时定义、样本数和后端设置不同的独立运行，部分后端版本未记录，属于厂商自测。

**「启示」** 作者认为，把 beam search、共享 KV 和目录约束直接做进推理引擎，可降低宽候选生成的尾延迟；但现有证据仍限于特定栈的自报基准，更广模型支持与生成、排序统一服务仍在路线图中。

**标签**: `#vLLM`, `#generative recommendation`, `#beam search`, `#KV cache`, `#inference serving`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [小米三季度经调整净利同比下降 56.8%，汽车交付超 10 万辆](https://ir.mi.com/static-files/3d372aaa-8ff8-4e33-ba01-68c8d7975a0b) ⭐️ 7.0/10

小米集团公布 2026 年第三季度财报，经调整净利润为 48.84 亿元，同比下降 56.8%，但仍略高于市场预期的 47.46 亿元；总营收 1072.4 亿元，同比下降 5.2%。当季新车交付 100,975 辆，公司称存储芯片等元器件涨价与研发投入加码使盈利短期承压，研发支出 92.4 亿元，综合毛利率 20.2%。

telegram · zaihuapd · 11月24日 10:09

**「背景」** 小米将业务划分为“手机×AIoT”和“新能源汽车及 AI 等创新业务”两大分部，前者仍是主要收入来源，汽车则是近年新增的增长板块；本季度存储芯片等核心元器件涨价推高了成本。

**标签**: `#小米`, `#财报`, `#电动汽车`, `#智能手机`, `#中国科技`

---