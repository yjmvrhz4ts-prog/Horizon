---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 36 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [英伟达董事会恢复黄仁勋 CEO 职务，称获美国政府意见](#item-tech-news-1) ⭐️ 9.0/10
2. [Anthropic 仓库称证明 VP ≠ VNP 对所有域成立](#item-tech-news-2) ⭐️ 9.0/10
3. [Ladybird 浏览器发布首个 Alpha 版](#item-tech-news-3) ⭐️ 8.0/10
4. [Z.ai 发布 GLM-5.4：首个循环 Transformer 模型](#item-tech-news-4) ⭐️ 8.0/10
5. [谷歌据称用 Mirror Dimension 测试 Chrome AI 代理](#item-tech-news-5) ⭐️ 7.0/10
6. [Windows Server 2028 默认移除 WoW64，32 位应用需手动装回](#item-tech-news-6) ⭐️ 7.0/10
7. [Codex2api 疑似遭供应链投毒，v3.1.11 被指移除鉴权](#item-tech-news-7) ⭐️ 7.0/10
8. [Meta AI 负责人称超级智能将至、控制堪忧](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [Anthropic 创纪录 IPO 后 AI 股遭抛售，DeepSeek 与月之暗面的上市计划因此蒙上阴影](#item-finance-news-1) ⭐️ 8.0/10
2. [纽约联储威廉姆斯：通胀仍高，未来可能需进一步加息](#item-finance-news-2) ⭐️ 7.0/10
3. [蚂蚁集团领投 Simplexity Robotics 1 亿美元 pre-A 轮](#item-finance-news-3) ⭐️ 7.0/10
4. [上海地铁 12 月起调整票价并推出计次票](#item-finance-news-4) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [英伟达董事会恢复黄仁勋 CEO 职务，称获美国政府意见](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 9.0/10

英伟达董事会已恢复黄仁勋的首席执行官职务，推翻此前将其迅速免职的决定。董事会声明称，在作出这一决定的过程中，董事会收到了美国联邦政府高级别官员的意见，并基于这些意见确信黄仁勋复职不构成国家安全风险。此次提供的 CNBC 报道正文被截断，因此免职的具体缘由、相关指控的性质以及复职是否附带条件，在现有材料中仍不清楚。

hackernews · jaz · 11月23日 14:00 · [社区讨论](https://news.ycombinator.com/item?id=50611576)

**「背景」** 这次复职逆转了不到两周前的一次突然人事变动：黄仁勋此前被解除 CEO 职务，而 11 月 23 日董事会一致投票，让他即刻恢复总裁、CEO 及董事身份，并表示在作出决定前与黄本人进行了一系列讨论。董事会声明还称，决策过程中收到了美国联邦政府高层人士的意见。

**「影响」** 复职声明把人事决定与“不构成国家安全风险”的政府判断直接绑定，使英伟达高层变动与对华芯片出口管制政策明确纠缠在一起。对依赖英伟达 GPU 的 AI 基础设施客户和合作伙伴而言，现实问题是战略连续性：同一董事会在短时间内推翻自身决定，而公开可见的材料未说明免职依据，外部各方难以判断出口合规安排和公司路线是否还会再次变化。

**「社区讨论」** 多位评论者认为声明中最关键的是董事会“收到美国政府高级别意见”这一句，认为这等于把政府干预写进了公司治理；也有人反驳称，若真存在犯罪证据，早已从泄密渠道流出，政府介入并不必然意味着掩盖。另有评论者批评董事会在免职阶段沟通不清、造成不必要的动荡，并质疑在 ASML 和日本芯片企业被要求遵守对华制裁的同时，英伟达却获得白宫方面的“祝福”，属于双重标准。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://nvidianews.nvidia.com/news/nvidia-board-reinstates-jensen-huang-as-president-ceo-and-board-director">NVIDIA Board Reinstates Jensen Huang as President, CEO and ...</a></li>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Board-Reinstates-Jensen-Huang-as-President-CEO-and-Board-Director/default.aspx">NVIDIA Corporation - NVIDIA Board Reinstates Jensen Huang as ...</a></li>

</ul>
</details>

**标签**: `#Nvidia`, `#AI hardware`, `#semiconductor policy`, `#corporate governance`, `#US-China tech restrictions`

---

<a id="item-tech-news-2"></a>
### [Anthropic 仓库称证明 VP ≠ VNP 对所有域成立](https://github.com/anthropics/formal-math/tree/main/vp-vnp) ⭐️ 9.0/10

托管在 Anthropic formal-math 仓库中的 vp-vnp 项目发布了一份论文与形式化材料，声称证明了 VP ≠ VNP 对所有域成立。该材料尚未经过同行评审，论文本身还表示“尚未分析其与相对化和代数化的关系”，因此这仍是一项待验证的声明，而非已确立的代数复杂性结果。

hackernews · mikeryan52 · 11月23日 22:09 · [社区讨论](https://news.ycombinator.com/item?id=50620102)

**「背景：VP 与 VNP 的由来」** 1979 年，Leslie Valiant 把 P vs NP 的二分法移植到代数复杂性中：VP 指可以由多项式规模的算术电路计算的多项式，VNP 指其系数可以被高效“验证”的多项式；这两类是否真的不同，至今仍未解决。该问题常被视为 P vs NP 在代数侧的对应版本，而 P vs NP 本身仍是计算复杂性理论中最著名的开放问题之一。

**「影响」** 如果该证明通过独立复核，它将给出 VP 与 VNP 在所有域上不同的结论；在复核完成前，研究者的实际关注点应是检查形式化脚本的假设、重新运行仓库中的验证，并处理论文尚未分析的相对化与代数化问题。

**「社区讨论」** 评论者 fons 报告自己重新运行了检查，并称这些定理可推出对原声明的“盲式重述”，同时链接到一个独立检查仓库；这属于外部复核者的经验报告，而非同行评审结论。其他评论则把此事放在 Anthropic 与 OpenAI 的竞赛以及 AI 对数学研究生选题的冲击下讨论，这些是个人判断而非已证实事实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Arithmetic_circuit_complexity">Arithmetic circuit complexity - Wikipedia</a></li>
<li><a href="https://www.kipuhub.com/en/article/algebraic-complexity-vp-vnp/">Algebraic Complexity: VP vs VNP – The Determinant vs the ...</a></li>

</ul>
</details>

**标签**: `#VP vs VNP`, `#algebraic complexity`, `#formal verification`, `#AI for mathematics`, `#computational complexity`

---

<a id="item-tech-news-3"></a>
### [Ladybird 浏览器发布首个 Alpha 版](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird 项目发布了首个 alpha 版，macOS 和 Linux 用户现在可以直接下载安装，无需自行编译。它采用自研的 HTML 解析、CSS、布局、JavaScript 和 WebAssembly 引擎，只复用 HarfBuzz、Skia、FFmpeg 与 SQLite 等外部组件。官方说明这是 alpha，部分网站无法使用且可能崩溃；用户可从浏览器内提交损坏站点报告，并在崩溃后选择是否发送崩溃报告。早期试用中，基于 WebAssembly 的 ffmpeg 和 Pyodide 工具可以运行，但依赖 Service Worker 的 Datasette Lite 因 navigator.serviceWorker.startMessages 未实现而报错。

hackernews · janvdberg · 11月23日 16:13 · [社区讨论](https://news.ycombinator.com/item?id=50614249)

**「背景」** Ladybird 源自 SerenityOS 项目，长期坚持从零实现浏览器核心组件。项目在 2026 年 2 月宣布借助 AI 编程代理将部分 LibJS 从 C++ 移植到 Rust；10 月的月度更新又报告了样式与布局移至独立线程、新 JavaScript JIT、替换 WebAssembly 引擎后在 JetStream 3 上提升 7 倍，以及 Web 平台测试通过数增加 75,650 项。

**「影响」** 对想在 macOS 或 Linux 上试用的用户，当前最实际的限制是至少 Service Worker 的部分接口尚未实现：Datasette Lite 已因缺少 navigator.serviceWorker.startMessages 而无法启动，源代码中也有对应 FIXME。依赖这类能力的应用应先在 Ladybird 中验证，而不是把它当作现有浏览器的完整替代。

**「社区讨论」** 多位试用者称赞兼容性，称新闻站点、Proxmox 乃至 NoVNC 都能正常或流畅渲染，但也有人提到页面滚动略显卡顿。另有评论提醒复杂 JavaScript 站点可能性能不佳，并称其 JS 引擎没有 JIT；这一说法与项目 10 月更新中“已落地新 JavaScript JIT”的表述并不一致。

**标签**: `#browsers`, `#ladybird`, `#open-source`, `#web-engines`, `#software-engineering`

---

<a id="item-tech-news-4"></a>
### [Z.ai 发布 GLM-5.4：首个循环 Transformer 模型](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai 发布 GLM-5.4，这是其首个采用循环 Transformer 架构的模型。据 Z.ai 描述，该架构让一组共享权重的层在一次前向传播中迭代多次并细化隐藏状态，从而在不增加参数量的情况下加深网络；这是厂商对架构的说明，推理效率收益尚待独立验证。该模型目前未开放权重，也不能通过常规 API 套餐调用，需订阅 Coding Plan；有测试者发现，Coding Plan 的 API key 可在 z.ai 的 OpenAI 兼容 Responses API 上访问新模型。在其鹈鹕 SVG 测试中，GLM-5.4 与 GLM-5.3 的生成质量相近，未表现出明显提升。

hackernews · foohis · 11月23日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50609685)

**「背景」** 标准 Transformer 在一次前向传播中每层只计算一次；而循环 Transformer 让一组共享权重的层反复运行多轮，对上一轮的隐藏状态继续精炼，从而在不增加参数量的情况下获得更深的有效网络。GLM-5.4 是智谱首个采用该架构的模型，此前 Thinking Machines Lab 在 11 月 20 日发布的 Inkling 2 Mini 也采用循环结构，其中间层对每个 token 运行三次。GLM 系列上一代是 GLM-5.3，来源提到其生成质量与 5.4 相近。

**「影响」** 想通过 z.ai 官方 API 试用 GLM-5.4 的开发者目前需要改用 Coding Plan 订阅；其 API key 仍走 OpenAI 兼容的 Responses API，因此现有兼容客户端可沿用接入方式，但需切换订阅和模型名。第三方插件 llm-zai 尚未适配新模型，测试者因此另发布了 llm-glm 插件。

**「社区讨论」** 有评论者赞赏 Z.ai 披露架构细节，认为循环 Transformer 是显而易见的探索方向，并解释其可减少逐层搬运权重带来的内存带宽瓶颈；也有用户抱怨这类模型“马拉松式思考”过于冗长，即使简单任务也反复自我检查，完成时间明显高于前沿模型。

**标签**: `#loop transformers`, `#LLM architecture`, `#coding models`, `#inference efficiency`, `#Zhipu AI`

---

<a id="item-tech-news-5"></a>
### [谷歌据称用 Mirror Dimension 测试 Chrome AI 代理](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

据蓝点网报道，谷歌为 Chrome 的 AI 代理搭建了名为 Mirror Dimension 的模拟互联网，让代理在隔离环境中执行打开网站、搜索浏览、登录、加购和完成任务等操作。报道称该环境包含数千个模拟网站，每名工程师使用独立隔离的测试环境，每天运行超过 1000 个测试案例，重点防御恶意网页的提示词注入攻击。上述细节来自二手报道，谷歌未在给定材料中确认，也没有关于该测试环境上线时间、部署范围或防护效果的信息。

telegram · zaihuapd · 11月23日 01:30

**「背景」** Chrome 的 AI 代理（即 auto browse）可以代替用户打开网站、搜索、登录并完成操作，因此网页正文、图片或 HTML 中隐藏的指令可能构成“间接提示词注入”，诱导代理偏离用户意图。Mirror Dimension 这类合成网络环境的作用，是在不触碰真实网站和账户的前提下复现此类攻击路径，用于评估代理的防御能力。

**「影响」** 若该测试方式属实，Chrome AI 代理在接触真实网页前会先在隔离的模拟站点中接受提示词注入防护测试，恶意网页内容因此成为其上线前的主要安全检验项之一；但报道未给出测试结果，无法据此判断实际防护效果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/security/mirror-dimension-for-agents/">Mirror Dimension for Agents: Evaluating Browser-Use Agents ...</a></li>
<li><a href="https://indianexpress.com/article/technology/artificial-intelligence/google-mirror-dimension-explained-fake-internet-ai-agents-10975011/">What is Google’s ‘Mirror Dimension’, the fake internet built ...</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#browser security`, `#prompt injection`, `#Chrome`, `#testing`

---

<a id="item-tech-news-6"></a>
### [Windows Server 2028 默认移除 WoW64，32 位应用需手动装回](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

微软在 Ignite 2026 宣布，计划于 2027 年秋季随 Windows 11 27H2 发布的 Windows Server 2028 将默认不包含 WoW64 兼容子系统，因此开箱无法运行 32 位应用。需要时可通过“按需功能”（FoD）重新安装 WoW64，在 Server Core 上通常使用 PowerShell 或 DISM 添加。微软称此举旨在缩小攻击面、阻止 32 位恶意软件；Windows 11 目前仍保留 WoW64，且微软未公布移除计划。

telegram · zaihuapd · 11月23日 03:03

**「背景」** WoW64 是 Windows 中负责在 64 位系统上运行 32 位应用的兼容层，微软此次的做法是把这一子系统改为可选的按需功能。按来源所述，Server Core 环境通常通过 PowerShell 或 DISM 添加该功能，因此现有 32 位软件并非彻底无法运行，而是需要管理员额外启用。

**「对运维的影响」** 企业 IT 需要在 Windows Server 2028 上线前盘点仍依赖 32 位组件的应用与代理，并在部署镜像或首次配置阶段通过 PowerShell 或 DISM 添加 WoW64 按需功能；否则在 Server Core 等默认环境中，这些程序将在装回该功能前无法启动。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.neowin.net/news/windows-server-2028-dropping-support-for-32-bit-apps-wow64-will-be-available-as-fod/">Windows Server 2028 dropping support for 32-bit apps (WoW64 ...</a></li>
<li><a href="https://windowsreport.com/microsoft-is-dropping-32-bit-app-support-by-default-in-windows-server-2028/">Microsoft Is Dropping 32-Bit App Support by Default in ...</a></li>
<li><a href="https://wccftech.com/microsoft-is-removing-32-bit-app-support-by-default-in-windows-server-2028-but-windows-11-remains-unaffected/">Microsoft Is Removing 32-Bit App Support By Default In ...</a></li>

</ul>
</details>

**标签**: `#Windows Server`, `#WoW64`, `#32-bit compatibility`, `#Microsoft`, `#enterprise IT`

---

<a id="item-tech-news-7"></a>
### [Codex2api 疑似遭供应链投毒，v3.1.11 被指移除鉴权](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

据 Telegram 频道转述的事件复盘，Codex2api 作者账号疑似被入侵，攻击者绕过 main 分支推送 tag，使 Release 构建出带后门的版本；其中 v3.1.11 被指移除鉴权，可无密码远程执行命令。报告还称有 workflow 将仓库的 16 个 GitHub Actions secrets 外传，波及同一账号下至少 21 个仓库。该报告建议安装或更新过 3.1.10–3.1.12 的用户立即停用并回退到 3.1.9，同时轮换 GitHub token、SSH key、数据库和 DeepSeek 等相关密钥；目前这些说法来自单一 Telegram 来源，尚未见独立确认。

telegram · zaihuapd · 11月23日 11:21

**「背景」** 这类供应链投毒的关键在发布链路，而不只是 main 分支：账号被黑后，攻击者可以推送 tag，让自动化流程基于被污染的代码生成 Release 构建。GitHub Actions 工作流可被配置为读取仓库 secrets；一旦工作流被篡改，这些凭据就可能被发往外部，因此受影响的不仅是单个发布包，还可能包括同一账号下的其他仓库。

**「影响」** 报告称外传涉及 16 个 Actions secrets、波及同账号至少 21 个仓库，因此受影响范围可能不止 Codex2api 项目本身；使用这些仓库的组织应按报告建议轮换 GitHub token、SSH key、数据库和 DeepSeek 等相关密钥。

**标签**: `#supply-chain-attack`, `#GitHub-Actions`, `#security-incident`, `#secrets-exfiltration`, `#remote-code-execution`

---

<a id="item-tech-news-8"></a>
### [Meta AI 负责人称超级智能将至、控制堪忧](https://thenextweb.com/news/metas-ai-chief-says-superintelligence-is-arriving-and-control-is-at-risk) ⭐️ 7.0/10

Meta 首席 AI 官、超级智能实验室负责人 Alexandr Wang 在 X 发长文称，超级智能已不再是“未来某天”的议题。他以数学家 Levent Alpöge 借助 Anthropic 的 Claude 完成、并于周六经 Lean 与 Mathlib 社区机器校验的黎曼猜想证明为例，称 AI 与顶尖人类的差距只剩具体知识、工程整合与实验三块。Wang 警告人类很难继续掌控可无限自我改进、或比自己聪明 1000 倍的系统，呼吁紧急投入安全、对齐与防护研究。该证明目前尚无人类可读版本，来源摘要也未提供独立确认。

telegram · zaihuapd · 11月23日 12:49

**「背景」** 黎曼猜想自 1859 年提出以来一直未被证明，是数学中最著名的未解问题之一；而 Lean 这类证明助手配合 Mathlib 数学库，能把证明拆成机器可逐条核验的形式化步骤，但机器校验通过只意味着被形式化的陈述得到了证明，仍需人类可读的说明来确认它对应的正是原命题。据《每日电讯报》报道，此次宣称给出证明的 Levent Alpöge 是 Anthropic 员工，这也是 Claude 的角色成为讨论焦点的原因。

**「对验证流程与安全投入的影响」** 对数学研究者和 AI 安全团队而言，这一案例的直接后果是：证明的有效性可能先于人类可读的说明而成立——据 tool-3-2，该证明由 Lean 与 Mathlib 机器校验，MIT 的独立检查还覆盖了 Dirichlet L 函数，但至今没有人类可读版本（据 Guardian 报道，Alpöge 称借助 Claude 耗时约六周完成），因此同行评审与形式化验证社区需要处理“证书已通过、论证尚未被理解”的审查缺口。与此同时，Wang 所呼吁的紧急安全、对齐与防护研究投入，落点正是他本人领导的 Meta 超级智能实验室的资源分配。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://tech.yahoo.com/ai/meta-ai/articles/why-one-math-proof-ai-211603503.html">Why One Math Proof Has AI Experts Warning Humans Might Soon ...</a></li>
<li><a href="https://www.telegraph.co.uk/business/2026/11/23/humans-risk-losing-control-to-superintelligent-ai-warns-met/">‘Hard to imagine’ humans staying in control of AI, warns Meta</a></li>
<li><a href="https://kingy.ai/blog/levent-alpoge-claude-riemann-hypothesis-proof/">Riemann hypothesis proof verified in Lean</a></li>
<li><a href="https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai">Two groups verify mathematician’s claim that Claude ... | The Guardian</a></li>

</ul>
</details>

**标签**: `#AI safety`, `#superintelligence`, `#Lean theorem proving`, `#Riemann hypothesis`, `#Meta AI`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [Anthropic 创纪录 IPO 后 AI 股遭抛售，DeepSeek 与月之暗面的上市计划因此蒙上阴影](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

Anthropic 完成 1195 亿美元创纪录 IPO 后，全球 AI 股加速下跌，中国科技股自 6 月底以来累计蒸发 1.7 万亿美元市值。这轮抛售令正在筹备或考虑上市的 DeepSeek、月之暗面和阶跃星辰面临更不明朗的发行前景。

telegram · zaihuapd · 11月23日 09:31

**「背景」** Anthropic 的 1195 亿美元首次公开募股（IPO）被称为美股史上最大 IPO，但上市后并未提振 AI 板块，反而成为全球 AI 股抛售的导火索。中国科技股自 6 月底以来累计蒸发 1.7 万亿美元，智谱较 6 月高点跌逾 85%，令筹备上市的 AI 公司面对更冷的融资环境。

**「影响」** 已上市的中国 AI 公司同样承压：智谱较 6 月高点跌超 85%，而此前半年曾涨 2000%；MiniMax 本月跌破发行价。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/19/anthropic-ipo-ai-stocks-selloff.html">Anthropic IPO fails to lift AI stocks - CNBC</a></li>

</ul>
</details>

**标签**: `#AI selloff`, `#China tech stocks`, `#IPOs`, `#Anthropic`, `#market volatility`

---

<a id="item-finance-news-2"></a>
### [纽约联储威廉姆斯：通胀仍高，未来可能需进一步加息](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

纽约联储主席威廉姆斯 11 月 23 日表示，通胀仍高于美联储 2%的目标，未来可能需要“随着时间推移”进一步加息。美联储 12 月 8 日至 9 日会议前，市场已完全计入一次 25 个基点的加息，当前联邦基金利率目标区间为 3.75%-4%。

rss · CNBC Finance · 11月23日 21:02

**「背景」** 联邦公开市场委员会（FOMC）负责制定利率，下次会议在 12 月 8 日至 9 日；威廉姆斯预计通胀到 2027 年更接近 2%、随后一年达到目标，并认为关税带来的价格压力已“基本消退”。

**标签**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#U.S. economy`

---

<a id="item-finance-news-3"></a>
### [蚂蚁集团领投 Simplexity Robotics 1 亿美元 pre-A 轮](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

彭博报道，中国具身智能公司 Simplexity Robotics 完成 1 亿美元 pre-A 轮融资，由蚂蚁集团领投，投后估值 16 亿美元。公司董事长兼联合创始人 Wang Kai 向彭博确认，阿里巴巴、腾讯、HongShan 和蓝驰创投等老股东跟投。

telegram · zaihuapd · 11月23日 02:02

**「背景」** Simplexity Robotics 于 2025 年 7 月在杭州成立，2026 年 3 月曾披露：成立半年内完成五轮融资，累计融资 20 亿元人民币，投后估值超过 10 亿美元；因此在本轮 pre-A 融资前，它已是一家估值逾 10 亿美元的初创公司。

**「影响」** 对宇树、优必选等已具备出货规模的中国人形机器人厂商而言，Simplexity 明确表示这笔 1 亿美元融资将用于与它们争夺市场，意味着竞争压力上升；据市场研究机构 Smart Analytics Global 数据，2026 年上半年中国厂商占全球人形机器人出货量超 97%，其中宇树与智元合计约 75%。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://equalocean.com/news/2026030921780">Five Rounds, RMB 2B: Simplexity Robotics Emerges... | EqualOcean</a></li>
<li><a href="https://www.donews.com/article/detail/9020/109637.html">donews.com/article/detail/9020/109637.html</a></li>

</ul>
</details>

**标签**: `#具身智能`, `#人形机器人`, `#风险融资`, `#蚂蚁集团`, `#中国科技`

---

<a id="item-finance-news-4"></a>
### [上海地铁 12 月起调整票价并推出计次票](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

据新华社报道，上海轨道交通票价将时隔 21 年首次调整，12 月 1 日起实行 3 元起乘、0—4 公里起步并按里程递增的新票价，同时推出计次票和同一支付渠道当月累计满 90 元享 9 折等优惠。

telegram · zaihuapd · 11月23日 10:45

**「背景」** 上海地铁上一次系统性票价调整是在 2005 年，起步价由 2 元调至 3 元；据市发改委及相关部门，随着线网扩张，人工、维修和电费等成本持续上升，目前票务收入覆盖定价成本的比例约为 55%，这构成此次调价的背景。

**「影响」** 高频通勤者将同时受到新里程票价和优惠措施影响；报道指出，计次票与满额优惠的主要目的是减少调价对这部分人群的冲击。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bilibili.com/video/BV1hy3W6SEZb/?spm_id_from=333.788.recommend_more_video.6">上 海 地 铁 要 调 价 了！ 9月7日召开听证会，这是自 2005 ... | 哔哩哔哩</a></li>
<li><a href="https://hot.online.sh.cn/content/2026-09/09/content_10485162.htm">时隔 21 ...</a></li>

</ul>
</details>

**标签**: `#Shanghai metro`, `#public transit fares`, `#fare adjustment`, `#commuter discounts`, `#China transport policy`

---