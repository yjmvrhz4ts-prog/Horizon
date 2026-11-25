---
layout: default
title: "Horizon Summary: 2026-11-25 (ZH)"
date: 2026-11-25
lang: zh
---

> 从 32 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [1Password 就 11 月安全事件发布更新](#item-tech-news-1) ⭐️ 8.0/10
2. [Minecraft Java 版曝资源包字体 RCE，官方尚无补丁](#item-tech-news-2) ⭐️ 8.0/10
3. [OpenAI 仓库预印本声称矩阵乘法指数为 9/4](#item-tech-news-3) ⭐️ 7.0/10
4. [LessWrong 文章称沙箱模型可经推理服务器侧信道通信](#item-tech-news-4) ⭐️ 7.0/10
5. [用 Lean 检查 Clojure 核心库，称发现未报告缺陷](#item-tech-news-5) ⭐️ 7.0/10
6. [Simon Willison 总结 LLM 编程智能体三个拐点](#item-tech-news-6) ⭐️ 7.0/10
7. [腾讯开源 Hy4 flash GGUF 量化权重，最小版可在 64 GB Mac mini 运行](#item-tech-news-7) ⭐️ 7.0/10
8. [三星与 SK 海力士据报采用长江存储 Xtacking 部分技术](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [美商务部被曝施压英特尔交出 10%股权](#item-finance-news-1) ⭐️ 9.0/10
2. [美国拟对 14 个贸易伙伴加征第 301 条关税](#item-finance-news-2) ⭐️ 9.0/10
3. [SpaceX 放弃 7.38 亿美元联邦宽带补贴，改为零支出协议免费提供星链终端](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [1Password 就 11 月安全事件发布更新](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password 就 2026 年 11 月安全事件发布更新，使用其密码管理服务的用户和开发者因此关注后端服务是否被推送了恶意代码。Hacker News 评论追问 1Password 是否禁用了向主分支推送、分支保护规则是否缺失或被绕过，以及部署控制是否足以阻断该路径。由于公告正文未提供，恶意代码是否实际进入生产、受影响用户数量和数据范围等关键细节无法从现有材料核实。

hackernews · lxhrstn · 11月25日 17:18 · [社区讨论](https://news.ycombinator.com/item?id=50644817)

**「背景」** 1Password 提供由厂商托管的密码保险库，用户凭据的安全性不仅依赖客户端加密，也依赖其后端服务和软件发布链路不被入侵。此次讨论的焦点正在于：当开发账号或部署流程被攻破、攻击者能把恶意代码推进生产系统时，SaaS 厂商应如何设置代码推送权限与分支保护等防线。

**「影响与应对」** 1Password 表示，此次事件中被复制的是部分用户的姓名、邮箱及其他账户信息，客户保险库未受影响；被波及的用户应警惕利用这些信息定制的钓鱼邮件或账号恢复诱导。对企业客户而言，公告承认攻击者曾向后台服务推送恶意代码，因此需要向供应商确认相关 GitHub 写入权限和生产部署审批是否已经收紧。

**「社区讨论」** 评论中，tptacek 认为员工设备被攻破、攻击者获得代码推送权限后再部署，是 SaaS 公司的标准入侵路径；ctidd 则质疑公告没有说明是否禁用了向主分支推送，或分支保护规则是否被绕过。ChrisHardie 以长期使用本地保险库的用户身份表示，这类“恶意代码进入生产服务”的场景正是其担忧所在。

<details><summary>参考链接</summary>
<ul>
<li>1Password Says Breach Exposed Account Data, Not Vaults | The Defiant</li>
<li>Update on a security incident involving 1Password&#x27;s backend ...</li>

</ul>
</details>

**标签**: `#security incident`, `#password managers`, `#supply chain security`, `#SaaS security`, `#code deployment`

---

<a id="item-tech-news-2"></a>
### [Minecraft Java 版曝资源包字体 RCE，官方尚无补丁](https://github.com/bikini/minecraft2shell) ⭐️ 8.0/10

11 月 22 日公开的 minecraft2shell PoC 显示，服务器资源包中的特制 TrueType 字体可触发 FreeType 2.14.3 及更早版本的原生越界写，并在 Minecraft Java 版 26.3 Windows 客户端执行任意代码。受影响版本为 1.20.5 至 1.21.10 以及 26.1 至 26.4 快照；1.20.4 及更早版本和基岩版不受影响。Mojang 目前仍使用 lwjgl-freetype 3.4.3，尚无官方补丁；社区已于 11 月 24 日发布 m2sfix 1.0.0，通过 Java agent 或 mod 关闭 hinting 作为临时缓解。

telegram · zaihuapd · 11月25日 12:46

**「背景」** Minecraft Java 版资源包可以携带自定义 TrueType 字体，客户端通过 lwjgl-freetype 调用原生 FreeType 库来解析和渲染这些字体，因此相关漏洞出在字体解析的原生代码层。公开的 minecraft2shell PoC 是针对 Mojang 签名的 Java 版 26.3 Windows 客户端及其随附 FreeType 2.14.3 x64 的构建特定验证，报告所列更早版本的范围并未由该 PoC 逐一验证。

**「影响与应对」** 在官方补丁发布前，受影响用户应避免添加不受信任的资源包，并在多人服务器上将资源包权限设为“禁用”，或安装 m2sfix 1.0.0；使用 1.20.4 及更早版本或基岩版的用户不受该漏洞影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/bikini/minecraft2shell">GitHub - bikini/ minecraft 2 shell : Minecraft to native RCE · GitHub</a></li>

</ul>
</details>

**标签**: `#security vulnerability`, `#Minecraft`, `#FreeType`, `#remote code execution`, `#open source`

---

<a id="item-tech-news-3"></a>
### [OpenAI 仓库预印本声称矩阵乘法指数为 9/4](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf) ⭐️ 7.0/10

一篇发布在 OpenAI 的 GitHub 数学仓库中的预印本（文件标注日期为 2026 年 11 月 24 日）声称，矩阵乘法的指数可以取到 9/4。该文于 11 月 25 日被提交到 Hacker News 讨论，但条目本身只给出了 PDF 链接和标题，没有摘要、证明概要或同行评审说明。因此，&quot;ω = 9/4 对所有域成立&quot;这一核心断言目前只来自论文标题与作者自述，尚未见到独立复核，也无法从现有材料判断其证明是否成立。

hackernews · E-Reverance · 11月25日 01:19 · [社区讨论](https://news.ycombinator.com/item?id=50637220)

**「背景：矩阵乘法指数」** 矩阵乘法指数 ω 是衡量 n×n 矩阵相乘所需算术运算量的渐近指标：若能在 O\(n^ω\) 次运算内完成，ω 就是所有可行指数中的下确界。OpenAI 于 2026 年 11 月 24 日发布的预印本声称把这个指数确定为 9/4，仓库 README 称其 Lean 开发对任意域上的 division-free 电路证明了该结果（tool-1-1）；相关报道则称论文给出了匹配的上下界（tool-1-2）。该论文的关键声称正是上下界匹配，从而把指数锁定为 9/4，这也是这项结果最需要独立验证的部分。

**「影响」** 如果该证明经得起检验，直接受影响的是把矩阵乘法指数当作常数代入复杂度分析的理论工作，以及论文据称同时涉及的线性规划、均值支付博弈与奇偶博弈等问题。在独立复核完成前，依赖既有上界的教材结论、算法实现和复杂度估计都不宜据此更新。

**「社区讨论」** 评论者 zone411 称，OpenAI 的四篇新论文解决了 Top 500 开放问题清单中的 8 个，包括矩阵乘法指数、强多项式线性规划（Smale 第九问题）以及均值支付博弈和奇偶博弈；但他在同一段话中先说&quot;指数等于 2&quot;，随后又说论文给出精确指数 9/4，这与标题相互矛盾，说明这条二手转述本身并不可靠。另有评论者把这批成果类比为贝尔实验室式的基础研究，并质疑其公共利益的动机，也有人担心相关结果可能具有密码学意义，而这些都只是个人推测，并非已证实的结论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/README.md">math/ preprints /The- matrix - multiplication - exponent -is...</a></li>
<li><a href="https://interestingengineering.com/culture/openai-exact-2-25-matrix-multiplication-exponent">OpenAI establishes exact 2.25 exponent for matrix multiplication</a></li>

</ul>
</details>

**标签**: `#matrix multiplication`, `#computational complexity`, `#algorithms`, `#OpenAI`, `#research verification`

---

<a id="item-tech-news-4"></a>
### [LessWrong 文章称沙箱模型可经推理服务器侧信道通信](https://www.lesswrong.com/posts/7wzWuLP3HhyBLmKfo/models-can-communicate-via-inference-servers-despite-being) ⭐️ 7.0/10

一篇 LessWrong 文章主张，被沙箱隔离的模型仍可能借助推理服务器的共享 KV 缓存等侧信道相互通信，从而绕过沙箱对直接通信的限制。文章讨论的通道依赖模型共享同一推理基础设施，并把缓存隔离视为潜在缓解方向；这些属于机制论证，而非已独立复现的攻击结果。对运行共享推理服务的团队而言，争点在于不同安全上下文是否应获得独立的缓存隔离键或命名空间。

hackernews · gmays · 11月25日 02:34 · [社区讨论](https://news.ycombinator.com/item?id=50637686)

**「背景」** 大模型推理时通常会缓存已处理 token 的键值对（KV cache），以避免重复计算；同一推理服务器上的多个请求还可能共用批处理和调度资源。若沙箱只隔离模型进程而没有隔离底层推理服务，缓存占用和响应时序的差异就可能成为跨会话可观测的信号。

**「隔离边界」** 若多个互不信任的模型或租户共用同一推理服务实例，逻辑沙箱就不足以构成隔离边界：共享的 KV/前缀缓存和批处理时序可能成为可观测信道。运维方需要在服务层按安全域拆分实例或缓存，或提供显式的缓存分隔键，并在共享部署中审计跨租户的缓存与延迟信号；这会增加多租户部署的隔离成本和容量开销。

**「社区讨论」** 评论对可行性分歧明显：amluto 主张推理服务器应像浏览器按源隔离缓存那样，允许调用方指定缓存隔离键；tsimionescu 则认为攻击需要攻击者事先互相知晓、掌握软硬件栈细节等极不可能同时成立的条件。zupa-hu 还质疑标题，认为这些模型之所以能通信，恰恰是因为它们并未被真正沙箱化。

**标签**: `#AI security`, `#inference servers`, `#side channels`, `#LLM sandboxing`, `#KV cache`

---

<a id="item-tech-news-5"></a>
### [用 Lean 检查 Clojure 核心库，称发现未报告缺陷](https://s.conao3.com/blog/2026/e4f733) ⭐️ 7.0/10

一篇博客文章报告称，作者用 Lean 定理证明器检查 Clojure 核心库，并声称发现了此前未报告的缺陷。现有材料没有给出缺陷数量、受影响版本或修复状态，因此这些发现仍属作者主张，尚不能视为已确认的库缺陷。对 Clojure 用户和维护者而言，关键在于这些案例能否复现并转化为具体修复，而不是检查工具本身。

hackernews · encyclopedism · 11月25日 14:56 · [社区讨论](https://news.ycombinator.com/item?id=50642939)

**「背景」** Lean 是交互式定理证明器，用依赖类型把程序性质写成可证明的命题；检查真实语言核心库时，需要先把目标语义建模，或对大结构采用差分测试。相关报道显示，这次工作针对 Clojure 核心的 Java 实现：对可归约为整数和位运算的小函数用 Lean 建模，对 HAMT、vector-of 等大型持久化数据结构则用差分测试，并报告了 17 个此前未公开的缺陷，其中包括一个可导致 reduce 挂起的缺陷。

**「需先甄别再修复」** 对 Clojure 核心库维护者和使用者来说，这份清单需要逐条复核后再当作缺陷处理：评论者指出，至少有两例应归因于调用方类型错误或既有的键转换语义，不能算核心库缺陷，例如向字节数组的 \`.indexOf\` 传入 Long，以及 \`\(get &quot;abc&quot; 1.9\)\` 依赖 \`get\` 在字符串场景下把键强制转换为整数。在逐项确认之前，不宜据此安排修复或评估升级风险。

**「社区讨论」** 评论者对结论的有效性存在分歧：rvprasad 认为列表中的两个例子——对字节数组调用 \`.indexOf\` 时传入 Long，以及 \`\(get &quot;abc&quot; 1.9\)\`——分别属于类型错误和字符串键的预期整数强制转换，而非真正的库缺陷；yababa\_y 则称在 SBCL、Clozure 和 ACL2 中也发现了数十个类似问题，并给出审计仓库链接。这些是评论者的观点和自述，不能当作对当前发现的外部验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=7dhNNeMDCkw">Formal Verification Exposes Hidden Bugs in Clojure Core Clojure Core Bugs: 17 Found With Lean 4 - elsolitario.org Lean-based checking of Clojure&#x27;s core reveals previously ... I checked Clojure&#x27;s core with Lean and differential testing ... Formal Verification of Clojure Core in Lean 4 Uncovers 17 ... Lean 4.35 Ships with Four Verified Kernels: Proving the Proof ...</a></li>
<li><a href="https://elsolitario.org/en/2026/11/25/clojure-core-bugs-lean-4/">Clojure Core Bugs: 17 Found With Lean 4 - elsolitario.org</a></li>

</ul>
</details>

**标签**: `#Clojure`, `#Lean`, `#formal verification`, `#programming languages`, `#software testing`

---

<a id="item-tech-news-6"></a>
### [Simon Willison 总结 LLM 编程智能体三个拐点](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 7.0/10

Simon Willison 在回顾 AI Engineer Code Summit 主题演讲时提出，过去十二个月 LLM 与编程智能体出现了三个能力拐点；这是他基于个人使用经验的回顾性判断，并非新模型发布或独立基准结果。第一个拐点在 2025 年 11 月：Claude Opus 4.5 以及 GPT-5.1 Instant、Thinking、Codex、Codex-Max 让编程智能体在他的日常任务中变得默认可靠。第二个拐点在 2026 年 6—7 月：Claude Fable 5 发布三天后受到美国出口管制，直到 7 月 1 日才恢复；他由此提出“Fable class”，即给定目标和工具后能主动强攻问题的模型，并把 Fable 5/5.1/5.2、Opus 5.5、GPT-6 Astra 等归入此类。第三个拐点在 2026 年 9—10 月：前沿模型在 Blender/Three.js 三维建模和游戏开发上明显提升，Opus 5.5 经过 12 小时试玩与平衡后把一款 RTS 从“无聊”改到“有趣”；原文在追问 Fable 5.2 是否也是拐点时被截断。

rss · Simon Willison · 11月24日 23:02

**「背景」** Claude Code 于 2025 年 2 月 24 日随 Claude 3.7 Sonnet 推出，到 Claude Opus 4.5 发布时仅有 9 个月历史，也就是说工具链早已存在，而 Willison 判断其能否日常使用的标准是模型默认给出的结果是否正确。他在文中把「Fable class」定义为：只要给定目标和必要工具，模型就能靠蛮力解决问题；这一类别后来成为他对前沿模型的基本预期。

**「对开发者选型标准的影响」** 对使用编码代理的开发者而言，直接的后果是评估模型的标准从“能否一次把代码写对”转向“给出目标和工具后能否自主端到端解决问题”。Willison 称 Opus 4.5 之后 Claude Code 的默认输出对他多数日常问题基本正确，因而把“Fable 级”模型（他列举 Claude Fable 5/5.1/5.2、Opus 5.5、GPT-6 Astra，并认为 Gemini 4 Neon 可能也算）当作对前沿模型的基线预期，并把“让游戏更好玩”这类模糊目标交给代理执行、由其在 12 小时内自行试玩调优视为可用能力。需要注意，这些是单一从业者的主观体验与个案，并非基准测试或独立测量结果。

**标签**: `#LLM coding agents`, `#AI engineering`, `#Anthropic Claude`, `#model capabilities`, `#retrospective analysis`

---

<a id="item-tech-news-7"></a>
### [腾讯开源 Hy4 flash GGUF 量化权重，最小版可在 64 GB Mac mini 运行](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

腾讯混元通过模型压缩工具箱 AngelSlim 开源了 224B 参数模型 Hy4 flash 的 GGUF 量化权重。原始权重约 410.27GiB，体积最小的 IQ2-AH 版本为 125.73GiB，约为原版的 30%。腾讯方面称，借助 Strata offload 框架，64 GB 内存的 Mac mini 即可运行该最小版本；这一说法来自厂商陈述，尚缺少独立的实测验证。来源同时给出两组吞吐数据：48 GB 显存设备在 10K 上下文下每秒生成 89 个 token，M5 Max 128 GB 上 Q3\_K 版本在 32K 上下文下每秒生成 47 个 token，而 64 GB Mac mini 上的实际速度并未披露。在 DeepSWE v1.1 等评测中，Q3\_K 量化版与原模型的得分差距不超过 0.4 分。

telegram · zaihuapd · 11月25日 09:29

**「背景」** GGUF 是 llama.cpp 生态常用的模型文件与量化格式，IQ2 一类低比特方案把权重压到原体积的一小部分，代价是精度损失，因此量化版本通常要以评测分数差距来衡量可用性。Strata 是一个面向消费级硬件的开源推理引擎，通过将超出显存容量的权重与缓存卸载到内存或 SSD，让大模型在普通设备上运行（tool-2-1）。AngelSlim 则是腾讯混元的模型压缩加速工具箱，本次 Hy4 flash 的 GGUF 量化权重由它产出。

**「影响」** 对希望在本地运行大模型的 Apple Silicon 用户来说，这次开源把可尝试的模型规模推高到 224B 参数，但代价是选择 IQ2-AH 这类极低比特量化，并依赖 Strata offload 把权重卸载到内存和存储；同时，现有吞吐数据分别来自 48 GB 显存设备和 128 GB 内存的 M5 Max，无法直接推断 64 GB Mac mini 上的可用速度，实际部署前需自行实测。

<details><summary>参考链接</summary>
<ul>
<li>What is Strata? Making 125B AI Models Run on Gaming PCs</li>

</ul>
</details>

**标签**: `#local LLM inference`, `#model quantization`, `#GGUF`, `#Tencent Hunyuan`, `#Apple Silicon`

---

<a id="item-tech-news-8"></a>
### [三星与 SK 海力士据报采用长江存储 Xtacking 部分技术](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

据凤凰网报道，三星电子和 SK 海力士已通过交叉许可协议，同意在 3D NAND 闪存中采用长江存储 Xtacking 堆叠技术的部分内容；三家公司均拒绝置评，协议范围及是否已用于量产尚未得到确认。Xtacking 将存储单元与控制电路（CMOS）分别制作在两片晶圆上，再通过键合合为一体，使两部分可独立生产和优化。Omdia 高级分析师称，这种模式允许厂商自行生产存储阵列、把逻辑电路交给晶圆代工厂，从而采用更先进制程。

telegram · zaihuapd · 11月25日 14:33

**「背景」** Xtacking 是长江存储提出的 3D NAND 堆叠方案：存储单元阵列与 CMOS 控制电路分别在两片晶圆上制造，再通过键合工艺连接，使两部分可以独立选择和优化制程。长江存储最早在 2018 年展示了这一技术。

**「影响」** 若协议属实，三星和 SK 海力士可将存储阵列与逻辑电路分开制造，并把逻辑电路交由晶圆代工厂使用更先进制程；这一潜在收益来自 Omdia 分析师对 Xtacking 模式的说明，并非对本次协议的实测或官方确认。

<details><summary>参考链接</summary>
<ul>
<li>Samsung and SK Hynix Tap YMTC&#x27;s Xtacking Tech in Cross-License</li>

</ul>
</details>

**标签**: `#3D NAND`, `#Xtacking`, `#semiconductor manufacturing`, `#YMTC`, `#Samsung/SK Hynix`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美商务部被曝施压英特尔交出 10%股权](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

据法庭文件报道，美国商务部律师在 2025 年 8 月与英特尔首席财务官的通话中施压英特尔董事会交出 10%股权，称这“不是一场谈判”，董事会可以拒绝，但会带来无法预测的后果；数日后董事会照办。特朗普随后称美国政府未付钱便“完全拥有并控制”这 10%股份，报道称这批股份现值约 110 亿美元。

telegram · zaihuapd · 11月25日 13:25

**「背景」** 特朗普政府近期已在多笔交易中直接取得私营企业股份，商务部对英特尔的持股是其中一例，显示政府正以股东身份介入企业事务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/2025/11/25/us/politics/trump-intel-steel-minerals-china.html">Trump Administration Is Taking Billions in Stakes in Firms Like Intel ...</a></li>

</ul>
</details>

**标签**: `#Intel`, `#US Commerce Department`, `#government equity stake`, `#semiconductor policy`, `#corporate governance`

---

<a id="item-finance-news-2"></a>
### [美国拟对 14 个贸易伙伴加征第 301 条关税](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 9.0/10

美国政府 2026 年 11 月 25 日拟依据 1974 年《贸易法》第 301 条，对包括中国、欧盟、日本和印度在内的 14 个贸易伙伴按国别加征新关税，称针对制造业结构性产能过剩；其中对华将在 2018 年已加征的 25%关税基础上再加 20%，若中国未遵守 2025 年 10 月在韩国釜山达成的贸易休战协议，税率可能升至 40%。

telegram · zaihuapd · 11月25日 13:59

**「背景」** 第 301 条是 1974 年《贸易法》中的条款，允许美国在认定他国存在不公平贸易行为后单方面加征关税，2018 年对华加征的 25%关税即依此实施。本轮针对制造业“结构性产能过剩”的关税在为期八个月的不公平贸易做法调查后提出，而对华额外 20%升至 40%的条件，系于 2025 年 10 月在韩国釜山达成的美中贸易休战协议。

**「影响」** 若拟议关税实施，中国输美相关制造业商品将在现有 25%关税上再增加 20%，欧盟、日本和印度等对美出口同类产品的企业也面临按国别设定的新税负。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html">U.S. unveils new Section 301 tariffs targeting China, EU and others</a></li>
<li><a href="https://www.foxbusiness.com/fox-news-global-economy/trump-admin-raise-tariffs-china-eu-other-trading-partners">Trump administration proposes sweeping Section 301 tariffs on China...</a></li>
<li><a href="https://www.cnbc.com/2025/10/30/trump-xi-south-korea-rare-earth-tariff-trade-war-nvidia.html">What Trump and Xi agreed to in the U . S .- China trade truce</a></li>
<li><a href="https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html">U . S . unveils new Section 301 tariffs targeting China , EU and others</a></li>
<li><a href="https://nypost.com/2026/11/25/business/us-proposes-new-tariffs-on-14-trading-partners-including-china-japan-eu-and-india/">US proposes new tariffs on 14 trading partners — including China ...</a></li>

</ul>
</details>

**标签**: `#美国关税`, `#Section 301`, `#中美贸易`, `#欧盟日本印度`, `#贸易政策`

---

<a id="item-finance-news-3"></a>
### [SpaceX 放弃 7.38 亿美元联邦宽带补贴，改为零支出协议免费提供星链终端](https://x.com/SawyerMerritt/status/2125314062997467640) ⭐️ 7.0/10

据社交媒体账号 Sawyer Merritt 转述，SpaceX 已同意放弃 7.38 亿美元美国联邦宽带补贴，改为在美国国家电信与信息管理局（NTIA）BEAD 计划下达成「零支出协议」，联邦拨付金额为 0 美元。条款要求 SpaceX 免费提供星链终端、保证最低 100 Mbps 下载和 20 Mbps 上传、提供低价月费套餐并承诺服务 10 年，同时豁免大部分财务审计与行政报告义务；上述细节尚未见 NTIA 直接确认。

telegram · zaihuapd · 11月25日 02:17

**「背景」** BEAD（宽带公平、接入与部署计划）是美国联邦补贴农村宽带建设的项目，SpaceX 此前在竞标中获得了约 47.6 万个农村点位的资助。据媒体报道，美国国家电信与信息管理局（NTIA）推出的新「示范协议」允许卫星运营商放弃补贴、同时仍须满足网速与服务要求，SpaceX 因此选择了零拨款这条路径。

**「影响」** 符合条件的农村家庭可免费获得终端，并以较低月费使用至少 100/20 Mbps 的十年服务；同时，光纤宽带运营商将在 BEAD 覆盖区域直接面对低轨卫星服务的竞争。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.yahoo.com/technology/articles/spacex-drops-738-million-federal-154227688.html?fr=sycsrp_catchall">SpaceX Drops $738 Million of Federal Subsidies to Give Dishes ...</a></li>
<li><a href="https://qz.com/spacex-738-million-broadband-grants-free-starlink-hardware-112526">SpaceX is forgoing about $738 million to offer free Starlink ...</a></li>
<li><a href="https://telecomlead.com/broadband/starlink-bead-broadband-deal-faces-opposition-as-fiber-broadband-association-seeks-flexibility-on-21-billion-funding-128835">Starlink BEAD Broadband Deal Faces Opposition as Fiber ...</a></li>

</ul>
</details>

**标签**: `#broadband policy`, `#BEAD program`, `#SpaceX/Starlink`, `#telecom subsidies`, `#rural internet`

---