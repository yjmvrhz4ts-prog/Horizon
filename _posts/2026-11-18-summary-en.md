---
layout: default
title: "Horizon Summary: 2026-11-18 (EN)"
date: 2026-11-18
lang: en
---

> From 40 items, 17 important content pieces were selected

---

**Technology News**
1. [Critical unauthenticated RCE disclosed in Nginx HTTP/2](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenAI releases GPT-6.2 Astra and Sol with lower Astra pricing](#item-tech-news-2) ⭐️ 8.0/10
3. [Xint discloses NGINX2Root chain reaching host root](#item-tech-news-3) ⭐️ 8.0/10
4. [Quad9 Leaves France, Raising Doubts About DNS-Level Piracy Blocking](#item-tech-news-4) ⭐️ 7.0/10
5. [Microsoft announces seven price-performance AI models, including MAI Code 2](#item-tech-news-5) ⭐️ 7.0/10
6. [Energy-Based Reasoners claims 385x inference efficiency](#item-tech-news-6) ⭐️ 7.0/10
7. [curl Maintainer Contrasts AI Rust Rewrite With 200+ Upstream Bugfixes](#item-tech-news-7) ⭐️ 7.0/10
8. [Prime Radiant releases external sandboxes for coding agents](#item-tech-news-8) ⭐️ 7.0/10
9. [CVE-2026-114938: Java4Shell RCE Reported in Recent Java](#item-tech-news-9) ⭐️ 7.0/10
10. [Voyager 1 becomes first human-made object one light-day from Earth](#item-tech-news-10) ⭐️ 7.0/10

**Technology Blog**
1. [FlyDSL MonoKernels Cut vLLM Decode Latency on AMD GPUs](#item-tech-blog-1) ⭐️ 8.0/10

**Financial News**
1. [Fed minutes show officials expect further rate hikes and flag AI inflation risk](#item-finance-news-1) ⭐️ 9.0/10
2. [Fed&\#x27;s Waller says central bank may need half-point rate hike in December](#item-finance-news-2) ⭐️ 7.0/10
3. [Banks Pause $480 Million ByteDance-Linked GPU Loan After US Chip Rules](#item-finance-news-3) ⭐️ 7.0/10
4. [Tencent reports Q3 2026 revenue miss as AI capex surges](#item-finance-news-4) ⭐️ 7.0/10
5. [China and South Korea Wrap Up FTA Services and Investment Talks](#item-finance-news-5) ⭐️ 7.0/10
6. [China Proposes Integrated Vehicle-Battery Scrapping for NEVs](#item-finance-news-6) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Critical unauthenticated RCE disclosed in Nginx HTTP/2](https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities) ⭐️ 8.0/10

A critical unauthenticated remote code execution vulnerability in Nginx&\#x27;s HTTP/2 handling has been disclosed, with the item linking CVE-2026-123633 and CVE-2026-123007. The available source does not state affected Nginx versions, a fixed release, or evidence that the flaw has been exploited, so operators running HTTP/2-enabled Nginx should rely on the CVE records and vendor advisory for patch and mitigation details. HTTP/2 is not enabled by default, but the discussion cites W3Techs data that 12% of servers use it—still a large population at internet scale.

hackernews · speedping · Nov 18, 15:19 · [Discussion](https://news.ycombinator.com/item?id=50547374)

**「Background」** The flaws are in NGINX&\#x27;s own HTTP/2 code rather than in the applications it serves, so sites and APIs can be exposed even when their own code is secure. Xint.io&\#x27;s advisory lists affected official releases from nginx 1.9.5 through 1.31.8 and says the vulnerable code was still present in master as of November 10, 2026.

**「Operator action」** Because the flaws are in NGINX itself, sites and APIs remain exposed even when their application code is secure. Disabling HTTP/2 on affected listening ports blocks CVE-2026-123633 and CVE-2026-123007, but not the three other NGINX vulnerabilities described in the same disclosure; those require disabling HTTP/3, avoiding dynamic upstream address resolution during the request phase, and restricting public access to the mail proxy.

**「Community discussion」** Commenters focused on disclosure timing and exposure: one claimed the fix appeared in the open-source repository about a week before broader disclosure, creating a window for attackers who monitor commits, and another noted HTTP/2 is not default and cited W3Techs&\#x27; 12% server share. A separate exchange questioned the recurring assumption that newer software is automatically safer.

<details><summary>References</summary>
<ul>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root: New Remote Code Execution Vulnerabilities in nginx ...</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>
<li><a href="https://www.ox.security/blog/nginx2root-five-critical-nginx-flaws-expose-web-servers-to-remote-code-execution/">NGINX 2 Root: 5 Critical NGINX RCE Vulnerabilities &amp; CVE Fixes</a></li>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root: New Remote Code Execution Vulnerabilities in nginx ...</a></li>

</ul>
</details>

**Tags**: `#nginx`, `#HTTP/2`, `#remote code execution`, `#CVE`, `#security`

---

<a id="item-tech-news-2"></a>
### [OpenAI releases GPT-6.2 Astra and Sol with lower Astra pricing](https://simonwillison.net/2026/Nov/17/gpt62-astra-and-sol/) ⭐️ 8.0/10

OpenAI released GPT-6.2 Astra, a frontier model, and GPT-6.2 Sol, an efficiency-focused model, available in the API as \`gpt-6.2-astra\` and \`gpt-6.2-sol\`; Simon Willison added support in LLM 0.38. Astra costs $8 per million input tokens and $40 per million output tokens, 80% of GPT-6 Astra&\#x27;s $10/$50, with cached input at $0.40 per million versus $1 for the older model, while Sol stays at $2/$10, the same as GPT-6.1 Sol and half the price of GPT-5.6 Sol. Willison&\#x27;s informal pelican and Yonkers animation tests did not establish a clear capability jump: neither new model morphed Yonkers into a mech as well as Claude Fable 5.2 or Gemini 4 Carbon in his comparison. He also reports mixed early reactions, including claims that Astra trails Fable 5.2 on various benchmarks and complaints about confusing communication style on long agentic tasks.

rss · Simon Willison · Nov 17, 22:38

**「Background」** OpenAI’s 6.2 release updates product lines already split between a higher-priced frontier Astra tier and a lower-priced Sol tier. The source notes that GPT-6 Astra and Claude Fable 5.2 were both priced at $10 per million input tokens and $50 per million output tokens, while earlier Sol releases were priced at $2/$10.

**「Cost and tooling effects」** The clearest measurable gain is for long-running agentic sessions: cached input on \`gpt-6.2-astra\` costs $0.40/MTok versus $1/MTok for 6 Astra, while standard input/output stay at $8/$40 per MTok. Developers driving these models through Simon Willison&\#x27;s LLM CLI need version 0.38 or later to use the \`gpt-6.2-astra\` and \`gpt-6.2-sol\` model IDs, and should treat early reports with caution — Willison notes Astra 6.2 is not scoring as high as Claude Fable 5.2 on various benchmarks, and Theo Browne&\#x27;s pre-release feedback describes long tasks stalling on questions about internal implementation details the user cannot answer.

**Tags**: `#OpenAI`, `#GPT-6.2 Astra`, `#GPT-6.2 Sol`, `#LLM pricing`, `#API models`

---

<a id="item-tech-news-3"></a>
### [Xint discloses NGINX2Root chain reaching host root](https://nginx2root.com/) ⭐️ 8.0/10

Security researcher Xint has disclosed NGINX2Root, a chain of five nginx vulnerabilities plus a Linux kernel flaw that is reported to take an attacker from an nginx visitor to host root. The chain includes CVE-2026-123007, an HTTP/2 flow-control memory-corruption bug that can execute commands in a worker without authentication. nginx 1.30.7 and 1.31.9, released November 18, fix 10 CVEs; Rapid7 has published a PoC, and no in-the-wild exploitation has been reported. Operators who cannot upgrade should disable externally exposed HTTP/2, the disclosure says.

telegram · zaihuapd · Nov 18, 16:21

**「Background」** The HTTP/2 flaw at the center of the chain, CVE-2026-123007, is not a recent regression: Xint says the vulnerable code dates to nginx&\#x27;s 2015 HTTP/2 introduction and appears in every official release from 1.9.5 through 1.31.8, including the master branch as of Nov. 10, 2026. Wiz rates it and CVE-2026-123633 Critical at CVSS 4.0 9.2, noting the flaws are in nginx itself, so secure application code does not remove exposure. The chain also uses a Linux kernel SCTP flaw to lift a worker foothold to host root, according to Astra.

**「Impact」** Operators running nginx 1.9.5 through 1.31.8 with HTTP/2 reachable must upgrade to 1.30.7 or 1.31.9, or disable external HTTP/2 if they cannot upgrade. A public Rapid7 proof-of-concept is already available, so an exposed, unpatched worker should be treated as remotely testable even though the source reports no in-the-wild exploitation yet.

<details><summary>References</summary>
<ul>
<li><a href="https://xint.io/blog/nginx2root-remote-code-execution">NGINX 2 Root : New Remote Code Execution Vulnerabilities in nginx ...</a></li>
<li><a href="https://www.wiz.io/blog/nginx-http2-rce-vulnerabilities">Unauthenticated Remote Code Execution in NGINX ... | Wiz Blog</a></li>
<li><a href="https://www.getastra.com/blog/security-advisory/nginx2root/">nginx 2 root : Five nginx RCE Flaws and a Kernel Bug...</a></li>
<li>nginx security advisories</li>
<li>nginx2root: Critical nginx RCE vulnerabilities and how to fix them</li>

</ul>
</details>

**Tags**: `#nginx`, `#vulnerability disclosure`, `#HTTP/2`, `#remote code execution`, `#Linux kernel`

---

<a id="item-tech-news-4"></a>
### [Quad9 Leaves France, Raising Doubts About DNS-Level Piracy Blocking](https://techstackups.com/articles/quad9-leaves-france-dns-blocking/) ⭐️ 7.0/10

Quad9 has withdrawn from France rather than comply with DNS blocking orders tied to piracy enforcement, and TechStackUps argues the episode shows why public resolvers are the wrong place to fight piracy. The report characterizes DNS-level filtering as both contentious and possibly ineffective, since it removes a privacy-focused resolver from the French market without establishing that blocking at the DNS layer actually stops piracy. The dispute also turns on whether courts are correctly applying a flawed law or overreaching, a distinction the article treats as central.

hackernews · ritzaco · Nov 18, 13:18 · [Discussion](https://news.ycombinator.com/item?id=50545958)

**「Background」** DNS resolvers translate domain names into IP addresses, which makes them a central chokepoint that courts and regulators can order to block sites without touching the underlying content. Quad9 is a Swiss nonprofit that runs a free public recursive resolver with malware filtering and no logging of users&\#x27; IP addresses; according to Cloudflare and TechPassion, it withdrew from France rather than comply with a DNS-level blocking order.

**「Impact」** French users who relied on Quad9 lose a public, privacy-oriented DNS option, and the withdrawal illustrates the compliance choice facing other resolver operators that receive similar blocking orders: implement the ordered filtering or stop serving the country.

**「Community discussion」** Hacker News commenters disagreed over where responsibility lies: skrebbel asked whether judges were misapplying a defensible law or lawmakers had written a bad one, while trentnix argued that non-prosecution piracy enforcement is a backdoor to suppressing disfavored speech. AppalachianEng contended that piracy enforcement is moot when AI companies have already consumed copyrighted material, and CommanderData expected continued pressure on intermediaries such as Cloudflare.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Quad9">Quad 9 - Wikipedia</a></li>
<li><a href="https://blog.cloudflare.com/quad9-withdrawal-from-france/">Quad 9 ’s withdrawal from France : A canary in the... | Cloudflare Blog</a></li>
<li><a href="https://www.techpassion.net/internet/quad9-leaves-france-dns-blocking/2169/">Quad 9 leaves France : DNS blocking order explained - TechPassion</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet censorship`, `#privacy`, `#internet governance`, `#Quad9`

---

<a id="item-tech-news-5"></a>
### [Microsoft announces seven price-performance AI models, including MAI Code 2](https://microsoft.ai/news/microsoft-ignite-2026/) ⭐️ 7.0/10

Microsoft announced seven new AI models at Ignite 2026, including MAI Code 2, positioned around scalable price-performance. The supplied material gives no concrete benchmarks, licensing terms, or availability details, so the price-performance claim is vendor positioning rather than an independently measured result. It also does not specify which models are available to developers or how they compare with prior Microsoft offerings.

hackernews · gmays · Nov 18, 16:08 · [Discussion](https://news.ycombinator.com/item?id=50548021)

**「Background」** Microsoft Ignite is the company&\#x27;s annual enterprise technology conference, where it presents cloud and AI platform direction to customers and developers. This item identifies MAI Code 2 as one of the models discussed, but it does not provide benchmarks, licensing terms, or details on how the seven models relate to earlier Microsoft releases.

**「Practical impact」** Teams evaluating coding assistants now have a claimed lower-cost option: Microsoft says MAI Code 2 targets complex, multi-file, project-scale programming, and MAI Cyber 2 Flash is aimed at vulnerability discovery at &quot;less than 2% of the cost per task&quot; of GPT-6 Astra on the CyberGymE 2 benchmark. That figure is Microsoft&\#x27;s own comparison on a single benchmark, and the supplied material gives no licensing, open-weight, or hosting details, so buyers should re-test the models on their own workloads and confirm deployment terms before substituting them for Claude or GPT-based tooling.

**「Community Discussion」** One commenter reported testing MAI Code 2 and found it good for usual work, saying they would not argue much with claims that it is on par with Opus or Sol and crediting Microsoft for starting from scratch. Others argued Microsoft should release some models as open source or open weight to win market share, warning that otherwise it risks repeating Windows Phone, and criticized the keynote and broader ecosystem as lacking innovation or appeal outside existing customers.

<details><summary>References</summary>
<ul>
<li><a href="https://microsoft.ai/news/microsoft-ignite-2026/">Seven new world class models at scalable... | Microsoft AI</a></li>
<li><a href="https://forklog.com/en/microsoft-unveils-ai-models-for-coding-and-cybersecurity/">Microsoft unveils AI models for coding and cybersecurity | ForkLog</a></li>
<li><a href="https://finance.yahoo.com/markets/article/microsoft-ignite-focuses-on-ai-models-for-specific-tasks-lowering-costs-for-enterprise-203433266.html">Microsoft &#x27;s AI pitch at Ignite : Cheaper models as business &#x27;token...</a></li>

</ul>
</details>

**Tags**: `#Microsoft`, `#AI models`, `#MAI Code 2`, `#model release`, `#price-performance`

---

<a id="item-tech-news-6"></a>
### [Energy-Based Reasoners claims 385x inference efficiency](https://energy-based-reasoners.github.io/) ⭐️ 7.0/10

A Hacker News submission links to a project page for Energy-Based Reasoners claiming 385x more efficient inference. The supplied material does not include the underlying paper or independent measurements, so the 385x figure remains a project claim rather than a verified result. Commenters describe energy-based models as strong validators that are very hard to train and often niche-specific, raising doubts about scaling beyond constrained puzzle-like tasks.

hackernews · frenchmajesty · Nov 18, 09:29 · [Discussion](https://news.ycombinator.com/item?id=50543989)

**「Background」** Energy-based models learn a scalar function that assigns an energy value to a candidate prediction, and reasoning can then be framed as searching for lower-energy candidates rather than emitting tokens left to right. A related commercial effort, Logical Intelligence&\#x27;s Kona 1.0, has been described as the first commercial energy-based model for reasoning, with Turing Award winner Yann LeCun joining as founding chair of its technical research board. The project page&\#x27;s efficiency claim therefore lands in a field where proponents see a route to self-correcting reasoning, while practitioners in the discussion caution that EBMs remain hard to train and often narrow in scope.

**「Impact」** For researchers evaluating EBMs, the practical concern is whether inference savings can survive training and scaling: commenters report that EBMs are difficult to train and have worked mainly on narrow tasks, so the 385x claim would need evidence on larger, less constrained problems before it supports adoption.

**「Community discussion」** One commenter pointed to Logical Intelligence, described as chaired by Yann LeCun, as a source of EBM examples and argued the approach has potential where LLMs struggle. Another commenter, citing a year of work on EBMs, called them impressive validators but “insanely hard to train” and very niche-specific, while a separate thread questioned what the learned scalar energy function’s codomain is and whether “energy” is just a synonym for real numbers.

<details><summary>References</summary>
<ul>
<li><a href="https://www.mexc.co/news/527319">Logical Intelligence Introduces First Energy - Based Reasoning AI...</a></li>
<li><a href="https://paperlens.io/idea/kona-1/">Kona 1: Energy - Based Reasoning | PaperLens</a></li>
<li><a href="https://www.wired.com/story/logical-intelligence-yann-lecun-startup-chart-new-course-agi/">A Yann LeCun –Linked Startup Charts a New Path to AGI | WIRED</a></li>

</ul>
</details>

**Tags**: `#energy-based models`, `#AI reasoning`, `#inference efficiency`, `#machine learning`

---

<a id="item-tech-news-7"></a>
### [curl Maintainer Contrasts AI Rust Rewrite With 200+ Upstream Bugfixes](https://simonwillison.net/2026/Nov/18/daniel-stenberg/) ⭐️ 7.0/10

curl maintainer Daniel Stenberg wrote that AI agents converted 185,000 lines of curl&\#x27;s C code into 340,000 lines of Rust over a little more than three weeks, while the actual curl project merged more than 300 commits in that period. Those commits included a little over 200 bugfixes that none of the Rust rewrites have, plus a few vulnerability fixes, according to Stenberg. He added that the upstream project produced another 200 bugfixes in the following month and asked whether the clones would keep up.

rss · Simon Willison · Nov 18, 15:58

**「Background」** Curl is a widely used C-based command-line tool and library for transferring data. Its maintainer, Daniel Stenberg, has long received repeated requests and questions about rewriting curl in Rust, sometimes as a joke and sometimes seriously. In November 2026, two AI-generated Rust rewrites of curl—urlx and another project claiming $8,600 in spend—drew attention and prompted Stenberg to compare their output with the ongoing maintenance work in the actual curl project.

**「Impact」** Developers evaluating an AI-generated curl port should not assume it includes the bug and security fixes landing upstream: Stenberg&\#x27;s account says the Rust rewrites lacked more than 200 fixes made during the rewrite window.

<details><summary>References</summary>
<ul>
<li>Actual #curl rewrites in #rust… - Post by daniel:// stenberg - Mastodon</li>
<li>Actual curl rewrites in rust - proomt</li>

</ul>
</details>

**Tags**: `#curl`, `#Rust`, `#AI code generation`, `#open source maintenance`, `#security`

---

<a id="item-tech-news-8"></a>
### [Prime Radiant releases external sandboxes for coding agents](https://simonwillison.net/2026/Nov/17/external-sandboxes-for-coding-agents/) ⭐️ 7.0/10

Simon Willison and Prime Radiant have released three implementations of an &quot;external sandbox&quot; pattern in which an AI coding agent runs outside a dedicated sandbox while the code it generates executes inside it. The backends are external-sandbox-v86, a Node.js server that runs Alpine Linux in WebAssembly via v86; external-sandbox-container, a Python server using an Apple Containers instance; and external-sandbox-quicksand, a Python server built on Microsoft&\#x27;s Quicksand library, which bundles QEMU and Alpine Linux. All expose the same localhost API, allowing Pi, Claude Code, or Codex to send execution requests to the sandbox, and each includes an optional HTTP/HTTPS allow-list proxy with credential replacement so the agent&\#x27;s code can make authenticated calls without receiving the secret. Willison frames the work as a way to test local models with less risk from mistakes or prompt injection.

rss · Simon Willison · Nov 17, 22:52

**「Background」** Coding agents such as Claude Code, Codex, and Pi can execute model-generated commands on the machine where they run, so a model error or prompt-injection attack can affect local files or reach credentials. The external sandbox pattern separates the agent from the execution environment: the agent stays outside, while the code it runs is confined to a dedicated sandbox server.

**「Impact」** For developers already using Pi, Claude Code, or Codex, the practical path is to point the agent at the sandbox&\#x27;s localhost API and choose a VM, container, or Quicksand backend; because the API is shared, the agent-side integration can stay the same across backends. The network allow-list and credential substitution are the controls to review first, since they determine which external services generated code can reach and what it can authenticate to without holding the original secret.

**Tags**: `#AI coding agents`, `#sandboxing`, `#security`, `#prompt injection`, `#developer tools`

---

<a id="item-tech-news-9"></a>
### [CVE-2026-114938: Java4Shell RCE Reported in Recent Java](https://censys.com/advisory/cve-2026-114938/) ⭐️ 7.0/10

A Telegram relay of a Censys advisory reports CVE-2026-114938, an unauthenticated remote code execution flaw in recent Java versions with a CVSS 4.0 score of 9.2, reportedly latent for nearly four years. The reported affected range is Java 17 from 17.0.6 onward and Java 21, 25, and 27; standard Java 8 and 11 are generally unaffected, except Oracle Java 8 Performance Pack. The flaw is said to affect only x86-64 server processors with AVX-512 VBMI—roughly Intel Ice Lake and newer Xeon \(2021+\) and AMD Zen 4 and newer EPYC/Ryzen \(2022+\)—with ARM64 unaffected, but the relay provides no independent confirmation, exploit status, or mitigation detail.

telegram · zaihuapd · Nov 18, 03:55

**「Background」** At the code level, CVE-2026-114938 is a heap-based buffer overflow in OpenJDK HotSpot&\#x27;s hardware-accelerated Base64 decoder, which relies on AVX-512 vector instructions. That decoder path is why exposure is limited to x86-64 machines with AVX-512 VBMI support rather than all Java installations.

**「Who has to act」** The exposure is workload- and hardware-specific: because the flaw is reported to sit in OpenJDK&\#x27;s AVX-512 Base64 decoder, the deployments needing an inventory pass and patch tracking are recent JDK 17/21/25/27 instances running on Ice Lake-era Xeon or Zen 4 and later machines, while Java 8/11 and non-AVX-512 or ARM64 hosts fall outside the reported range. With no fixed version or workaround in the source, administrators cannot yet assess interim mitigations — watchTowr&\#x27;s FAQ still labels CVE-2026-114938 a &quot;reported&quot; RCE and says it is being updated as details emerge.

<details><summary>References</summary>
<ul>
<li><a href="https://thehackernews.com/2026/11/java4shell-cve-2026-114938-enables-pre.html">Java 4 Shell Flaw ( CVE - 2026 - 114938 ) Enables Pre-Auth RCE in Jira...</a></li>
<li><a href="https://github.com/arkrwn/PoC-CVE-2026-114938-CrashLeak">GitHub - arkrwn/PoC- CVE - 2026 - 114938 -CrashLeak...</a></li>
<li>Java4Shell: Remote Code Execution in OpenJDK (CVE-2026-114938)</li>
<li>Java4Shell (Java CVE-2026-114938) FAQ - watchTowr</li>

</ul>
</details>

**Tags**: `#Java`, `#CVE-2026-114938`, `#remote code execution`, `#security advisory`, `#AVX-512`

---

<a id="item-tech-news-10"></a>
### [Voyager 1 becomes first human-made object one light-day from Earth](https://www.cnn.com/2026/11/18/science/voyager-1-light-day) ⭐️ 7.0/10

NASA&\#x27;s Voyager 1 has become the first human-made object to reach roughly one light-day from Earth, arriving about 26 billion kilometers away after 49 years of flight. A radio signal now takes about 24 hours to reach the spacecraft, so a round-trip communication takes about two days. NASA says it can still send and receive signals, and only two science instruments remain operating.

telegram · zaihuapd · Nov 18, 14:41

**「What a light-day means here」** A light-day is the distance light travels in 24 hours, roughly 26 billion kilometers, so Voyager 1&\#x27;s distance from Earth and its one-way radio travel time are two expressions of the same measurement. The milestone comes after about 49 years of flight, during which the spacecraft has kept operating while NASA manages its limited power supply.

**「Impact」** A recent power adjustment is expected to save about 10 watts and extend the mission by roughly two and a half years, according to NASA. The two-day round-trip latency also means commands and responses are heavily delayed, a constraint for operating the remaining instruments.

**Tags**: `#Voyager 1`, `#NASA`, `#space exploration`, `#deep-space communications`, `#power management`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [FlyDSL MonoKernels Cut vLLM Decode Latency on AMD GPUs](https://vllm.ai/blog/2026-11-18-flydsl-monokernels) ⭐️ 8.0/10

rss · vLLM Blog · Nov 18, 00:00

**「Background」** Interactive agents put decode on the critical path: each action must finish before the next tool call, so low-concurrency serving prizes per-user responsiveness. At small batch sizes decode still runs a chain of dependent GPU kernels whose dispatch, startup, and drain costs are not removed by HIP graphs.

**「Solution」** The AMD/vLLM authors address this with FlyDSL MonoKernels: a few author-scheduled persistent launches replace many dependent kernels. Thread blocks are reused across stages, weights are prefetched during earlier work, and tagged mailboxes let consumers start when their inputs are ready; DeepSeek-V4.1-Flash&\#x27;s K2 also performs both TP all-reduces inside the kernel. Boundaries are model-specific—DeepSeek uses K1+K2, while MiniMax-M3 initially fuses only the FFN. In vLLM, mono decode is opt-in via --monokernel, model-owned, chosen per layer and step by plan\(\), and falls back to stock layers for prefill or oversized steps while preserving KV cache, sampling, speculative decoding, and HIP graphs. Reported gains include DeepSeek-V4.1-Flash rising from 318.1 to 429.1 tok/s/user at TP2 concurrency 1, an MI325X layer dropping from 32 kernels/320 µs to 2/115 µs, and GLM-5.2 batch-1 time per token falling from 13.70 to 5.92 ms; tested accuracy deltas were within noise. Limits remain: gains shrink at higher concurrency, step widths are capped, MI300X/MI325X may need weight copies, and some baselines or accuracy evaluations are incomplete.

**「Takeaway」** The authors conclude that MonoKernels accelerate low-concurrency decode by removing kernel-boundary overhead rather than just speeding individual operators, producing 1.20×–2.26× interactivity or TPOT gains across five merged AMD models. It is a targeted latency specialization, not a general throughput win.

**Tags**: `#LLM inference`, `#GPU kernels`, `#vLLM`, `#kernel fusion`, `#AMD ROCm`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed minutes show officials expect further rate hikes and flag AI inflation risk](https://www.cnbc.com/2026/11/18/fed-minutes-october-2026.html) ⭐️ 9.0/10

Federal Reserve meeting minutes released Wednesday showed officials expect further rate increases will be needed to return broad-based inflation to the 2% target, after the FOMC voted 10-2 to hold its benchmark rate at 3.75%–4%, with both dissents favoring a quarter-point hike. Officials also identified AI-related demand as a material inflation risk and warned that complex AI-related financing could amplify losses.

rss · CNBC Finance · Nov 18, 19:41

**「Background」** The minutes document the Fed’s Oct. 28 decision to hold its benchmark rate at 3.75%-4%, leaving policy unchanged as officials assessed whether inflation was slowing enough to return to their 2% target.

<details><summary>References</summary>
<ul>
<li>Federal Reserve issues FOMC statement</li>

</ul>
</details>

**Tags**: `#Federal Reserve`, `#monetary policy`, `#inflation`, `#AI risk`, `#interest rates`

---

<a id="item-finance-news-2"></a>
### [Fed&\#x27;s Waller says central bank may need half-point rate hike in December](https://www.cnbc.com/2026/11/18/federal-reserve-governor-christopher-waller.html) ⭐️ 7.0/10

Federal Reserve Governor Christopher Waller said the Fed may need to &quot;shock people&quot; with a half-point rate hike at its Dec. 8-9 meeting and should reverse the three quarter-point cuts made in 2025, arguing inflation is headed &quot;in the wrong direction.&quot;

rss · CNBC Finance · Nov 18, 15:13

**「Background」** The Fed raised rates in September for the first time in more than three years and held them in October, while most inflation readings remained above 3%, versus its 2% target, after energy prices rose following U.S. and Israeli strikes on Iran in late February. Futures markets fully price a quarter-point December hike and anticipate another in January, according to CME Group&\#x27;s FedWatch.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#Christopher Waller`

---

<a id="item-finance-news-3"></a>
### [Banks Pause $480 Million ByteDance-Linked GPU Loan After US Chip Rules](https://www.bloomberg.com/news/articles/2026-11-17/banks-pause-480-million-chip-loan-tied-to-china-s-bytedance) ⭐️ 7.0/10

Five banks reportedly paused a $480 million loan intended to fund ByteDance-linked purchases of advanced Nvidia GPUs for a data center in Malaysia after new U.S. AI chip rules. The borrower is Singapore cloud provider Aolani Cloud, with DBS as lead arranger; some banks are discussing exiting the financing over compliance concerns.

telegram · zaihuapd · Nov 18, 05:11

**「Background」** The pause follows Washington’s tightening of chip-export rules for Southeast Asian data centers, which requires operators in countries such as Malaysia and Singapore to obtain licenses for advanced AI chips while exempting American cloud providers. ByteDance’s planned Malaysian compute relied on accessing Nvidia Blackwell GPUs through Aolani Cloud under cloud-style agreements rather than direct ownership.

**「Impact」** The financing pause leaves ByteDance&\#x27;s planned Malaysia data-center GPU purchases without that funding, and analysts expect the tighter US export rules to raise costs and delay data-center projects across Southeast Asia, with US cloud providers exempt.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/18/nvidia-us-ai-chip-export-controls-data-centers-.html">New U . S . chip curbs put Southeast Asia&#x27;s data center boom at risk</a></li>
<li><a href="https://hyper.ai/en/stories/5bfbcca4f7ab5077ec580e8fd791dc5c">ByteDance to access 36,000 Blackwell GPUs via Malaysia ; Nvidia ...</a></li>
<li><a href="https://www.zerohedge.com/ai/first-domino-falls-us-ai-chip-crackdown-freezes-480-loan-linked-chinas-bytedance">First Domino Falls: US AI Chip Crackdown Freezes $ 480 MM Loan ...</a></li>
<li><a href="https://tech-insider.org/bytedance-nvidia-b200-chips-malaysia-ai-deal/">ByteDance Nvidia B200 Deal: 36,000 Chips, $2.5B — Full Price and...</a></li>
<li><a href="https://www.cnbc.com/2026/11/18/nvidia-us-ai-chip-export-controls-data-centers-.html">New U . S . chip curbs put Southeast Asia&#x27;s data center boom at risk</a></li>

</ul>
</details>

**Tags**: `#US AI chip controls`, `#ByteDance`, `#GPU financing`, `#data center financing`, `#Malaysia`

---

<a id="item-finance-news-4"></a>
### [Tencent reports Q3 2026 revenue miss as AI capex surges](https://api3.cls.cn/share/article/2537922?os=android&amp;amp;sv=8.8.5&amp;amp;app=cailianpress&amp;amp;selected=) ⭐️ 7.0/10

Tencent reported third-quarter 2026 revenue of 207.3 billion yuan, up 8% year on year and below market expectations, with net profit attributable to shareholders up 0.8% to 63.6 billion yuan. Capital expenditure reached 81.4 billion yuan, far above the 55.4 billion yuan market estimate, free cash flow was negative 69.1 billion yuan, and Tencent said its WorkBuddy app had the highest daily token usage among domestic large-language-model products at over 100 trillion tokens a day.

telegram · zaihuapd · Nov 18, 09:20

**「Background」** WorkBuddy is Tencent&\#x27;s AI office agent, part of a push beyond chatbots into “agentic” AI that can carry out tasks on its own; token consumption measures how much text and task data its models process.

<details><summary>References</summary>
<ul>
<li><a href="https://www.workbuddy.ai/">WorkBuddy - AI Agent for Everyday Office Work</a></li>
<li><a href="https://www.appeconomyinsights.com/p/micron-demand-goes-vertical">While Meta and Tencent push deeper into the AI stack</a></li>

</ul>
</details>

**Tags**: `#Tencent`, `#earnings`, `#AI capex`, `#free cash flow`, `#China tech`

---

<a id="item-finance-news-5"></a>
### [China and South Korea Wrap Up FTA Services and Investment Talks](https://x.com/Jaemyung_Lee/status/2122988472994791476) ⭐️ 7.0/10

China and South Korea announced on November 18 the substantive conclusion of follow-up negotiations to their free trade agreement on services and investment, with China committing most-favored-nation treatment for Korean film and games and wider opening in tourism, legal, construction and finance. The two sides also agreed to expand audiovisual co-production from film to television, animation, variety shows and documentaries; the talks began in March 2018 and lasted 8 years and 8 months, with some technical matters still to be settled at the working level and the deal not yet signed or ratified.

telegram · zaihuapd · Nov 18, 10:02

**「Background」** The two countries&\#x27; original free-trade agreement entered into force in 2015, and formal follow-up negotiations on services and investment began in March 2018 under agreed guidelines.

**「Who is affected」** Korean film, game, and audiovisual producers would gain because the commitments would put them on the same market-access footing as other foreign suppliers in China, and co-production status would extend from film to TV dramas, animation, variety shows, and documentaries — though the terms are not yet a signed or ratified agreement.

<details><summary>References</summary>
<ul>
<li><a href="https://english.motir.go.kr/eng/article/EATCLdfa319ada/2484/view">The First Korea – China FTA Services and Investment Follow - up ...</a></li>

</ul>
</details>

**Tags**: `#China-South Korea FTA`, `#services and investment`, `#trade policy`, `#media and games`, `#market access`

---

<a id="item-finance-news-6"></a>
### [China Proposes Integrated Vehicle-Battery Scrapping for NEVs](https://wallstreetcn.com/articles/3786200) ⭐️ 7.0/10

China’s Commerce Ministry and eight other departments proposed on Nov. 17 revising scrapped-vehicle recycling rules to require new energy vehicles to be scrapped together with their power batteries, and said they are studying a digital battery ID system. The proposal is not yet final, and detailed rules remain pending.

telegram · zaihuapd · Nov 18, 12:22

**「Background」** In April, interim rules already treated a scrapped NEV without its power battery as an incomplete vehicle; the proposed revision would add integrated vehicle-battery recycling requirements and study a battery digital ID system.

**「Impact」** If finalized, the change would affect NEV owners, dismantlers and battery recyclers by making battery handover and traceability part of scrapping.

**Tags**: `#新能源汽车`, `#动力电池回收`, `#报废机动车`, `#监管政策`, `#电池数字身份证`

---