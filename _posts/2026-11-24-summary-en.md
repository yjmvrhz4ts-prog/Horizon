---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 35 items, 12 important content pieces were selected

---

**Technology News**
1. [Baidu open-sources 280B ERNIE 5.5 Flash Preview under Apache 2.0](#item-tech-news-1) ⭐️ 8.0/10
2. [Ternary Bonsai 2.5 27B draws local-inference tests and benchmark skepticism](#item-tech-news-2) ⭐️ 7.0/10
3. [Quad9 deactivates DNS service in France over legal constraints](#item-tech-news-3) ⭐️ 7.0/10
4. [Check Point management servers hit by session-forgery campaign](#item-tech-news-4) ⭐️ 7.0/10
5. [Brendan Gregg-Inspired Essay Draws Debate on Deterministic VMs and Flamegraphs](#item-tech-news-5) ⭐️ 7.0/10
6. [Simon Willison names three LLM inflection points in twelve months](#item-tech-news-6) ⭐️ 7.0/10
7. [Z.ai Releases GLM-5.4, Its First Looped-Transformer Coding Model](#item-tech-news-7) ⭐️ 7.0/10
8. [Singapore&\#x27;s Wong says it won&\#x27;t be a conduit around US chip controls](#item-tech-news-8) ⭐️ 7.0/10
9. [VMware vCenter 9.8 auth bypass CVE-2026-123903 reportedly exploited as zero-day](#item-tech-news-9) ⭐️ 7.0/10

**Technology Blog**
1. [vLLM Day-0 Support for ERNIE 5.5 Flash](#item-tech-blog-1) ⭐️ 6.0/10
2. [vLLM-GR Brings Beam Search to Generative Recommendation Serving](#item-tech-blog-2) ⭐️ 5.0/10

**Financial News**
1. [Xiaomi Q3 adjusted net profit falls 56.8% as EV deliveries top 100,000](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Baidu open-sources 280B ERNIE 5.5 Flash Preview under Apache 2.0](https://x.com/Baidu_Inc/status/2125077484442190137) ⭐️ 8.0/10

Baidu announced on November 24 that it has open-sourced ERNIE 5.5 Flash Preview, a 280B-parameter mixture-of-experts model with 14B active parameters per token and a 1M-token context window. The weights are available under Apache 2.0 on Hugging Face and ModelScope and can be deployed or fine-tuned with vLLM or SGLang; Baidu describes it as the first post-trained model built on ERNIE 5.5 Flash Base. Circulating benchmark charts show Terminal-Bench 4.0 at 46.5 and DeepSWE v1.1 at 71.2, but Baidu did not say whether those results were independently verified.

telegram · zaihuapd · Nov 24, 07:32

**「Background」** Mixture-of-experts models route each token through only part of the network, so total parameter count and per-token compute can differ sharply. Baidu says this release is the first post-trained model built on ERNIE 5.5 Flash Base, making the open weights a preview model rather than a final release.

**「Impact」** Developers can download the weights and self-host or fine-tune the model under a permissive license, with vLLM and SGLang listed as supported deployment paths. The 280B total parameter count still implies substantial memory and storage requirements for hosting the full model, even though only 14B parameters are active per token.

**Tags**: `#open-source LLM`, `#Baidu ERNIE`, `#mixture-of-experts`, `#Apache 2.0`, `#long context`

---

<a id="item-tech-news-2"></a>
### [Ternary Bonsai 2.5 27B draws local-inference tests and benchmark skepticism](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 7.0/10

Ternary Bonsai 2.5 27B has been released as a 27B model using ternary quantization, and early users are testing a Q2 GGUF build for local inference. One user reports about 22.3 tokens/s generation, a 2.12 s first token, and 222.9 tokens/s prompt processing on a Mac Mini M5 Pro with 24 GB RAM and a 512 GB SSD, and says 128k context fits easily in memory. Another reports roughly 300 tokens/s prefill and 30 tokens/s generation on a MacBook through Unsloth Studio, describing the agentic calls as solid. A commenter claims SWE-bench Verified performance equivalent to Opus 4.6, but the supplied material includes no vendor benchmark data or independent confirmation.

hackernews · b0m · Nov 24, 20:08 · [Discussion](https://news.ycombinator.com/item?id=50633922)

**「Background」** Ternary Bonsai 2.5 27B follows PrismML&\#x27;s Bonsai 2 27B, a ternary-weight quantization that the company said retained 98.2% of aggregate benchmark performance while shrinking the model more than 9x versus its full-precision counterpart \(tool-2-1\). The earlier model stored weights as \{-1, 0, +1\}, cutting a roughly 54 GB model to about 7.67 GB \(tool-2-3\). An external write-up reports that the 2.5 release keeps a 5.9 GB footprint, raises SWE-bench Verified to 75.6, and ships GGUF and MLX weights for local agentic coding \(tool-2-2\).

**「What it means in practice」** For developers with consumer Apple silicon, the Q2 GGUF is reported to be usable for local agentic work: one commenter measured about 22.3 tokens/s generation \(222.9 tok/s prompt processing\) on a Mac Mini M5 Pro with 24GB RAM and said a 128k context fits easily in memory, while another reported roughly 300 tok/s prefill and 30 tok/s generation through Unsloth Studio and called the agentic calls &quot;solid.&quot; The practical caveat is whether ternary weights get real hardware acceleration on consumer GPUs outside FPGA setups — a question raised in the thread but not answered by the supplied evidence — so buyers should validate throughput on their own target hardware rather than assume a general speedup.

**「Community discussion」** Dissent centers on the benchmark claim: one commenter wonders how much of the reported SWE-bench parity with Opus 4.6 is “benchmaxxing,” benchmark drift, or genuine small-model progress, while another asks for direct comparisons with equivalently sized Q1/Q2 quantizations such as Qwen3.8. A separate question asks whether ternary weights have hardware acceleration other than FPGAs.

<details><summary>References</summary>
<ul>
<li><a href="https://prismml.com/news/bonsai-2-27b">PrismML — Introducing Bonsai 2 27B: Near-Lossless Compression ...</a></li>
<li><a href="https://explainx.ai/blog/prismml-ternary-bonsai-2-5-27b-agentic-coding-5-9gb-november-2026">PrismML Ternary Bonsai 2.5 27B: 5.9 GB Agentic Coding Model</a></li>
<li><a href="https://www.mindstudio.ai/blog/ternary-bonsai-2-27b-benchmarks">Bonsai 2 27B Benchmarks: Does Ternary Quantization Actually ...</a></li>

</ul>
</details>

**Tags**: `#ternary quantization`, `#local LLM inference`, `#small language models`, `#GGUF`, `#agentic coding`

---

<a id="item-tech-news-3"></a>
### [Quad9 deactivates DNS service in France over legal constraints](https://quad9.net/news/blog/quad9-service-deactivation-in-france/) ⭐️ 7.0/10

Quad9 has deactivated its DNS service in France, making its public resolver unavailable to users there. A community report says the change took effect on 24 November 2026, with queries to 9.9.9.9 returning REFUSED and an extended DNS error stating “Service unavailable due to French legal constraints.” The supplied material does not identify the specific legal order or establish whether all Quad9 addresses and protocols are affected.

hackernews · farrokhi · Nov 24, 08:33 · [Discussion](https://news.ycombinator.com/item?id=50625384)

**「What Quad9 is and why it is leaving」** Quad9 is a public recursive DNS resolver run by a Swiss nonprofit foundation; users point their devices at addresses such as 9.9.9.9 instead of their ISP&\#x27;s resolver, and the service offers both filtered \(malware-blocking\) and unfiltered variants. Public resolvers have increasingly been drawn into site-blocking disputes, where a legal order requires a resolver to make certain domains unreachable rather than simply look them up. According to a commenter&\#x27;s dig output, queries to Quad9 from France now come back with status REFUSED and extended DNS error 18, described as &quot;Service unavailable due to French legal constraints.&quot;

**「What French users must do now」** French users and organizations that pointed their devices or networks at 9.9.9.9 must reconfigure to another resolver or run their own, because Quad9&\#x27;s shutdown is not a graceful degradation: queries now return REFUSED with EDE code 18 citing French legal constraints. Because the withdrawal stems from beIn&\#x27;s domain-blocking demands rather than a technical failure, switching to a resolver that complies with French blocking orders is the only supported path for users who want to stay on a public resolver.

**「Community discussion」** One commenter set up a public forwarding proxy as a “fairly drop-in replacement” for French users, offering DoH, DoT, and Do53 over IPv4 and IPv6 while only caching and forwarding requests to Quad9. Another commenter said Unbound works well for home use with Pi-hole and asked whether it fails to scale or whether public resolvers such as Quad9 and 1.1.1.1 offer an advantage over running your own DNS.

<details><summary>References</summary>
<ul>
<li><a href="https://quad9.net/news/blog/quad9-service-deactivation-in-france/">Quad 9 Service Deactivation in France | Quad 9</a></li>
<li><a href="https://www.commentcamarche.net/applis-sites/39161-quad9-fin-france/">Ce DNS gratuit et populaire refuse de bloquer les sites pirates...</a></li>

</ul>
</details>

**Tags**: `#DNS`, `#internet infrastructure`, `#privacy`, `#France`, `#legal policy`

---

<a id="item-tech-news-4"></a>
### [Check Point management servers hit by session-forgery campaign](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 7.0/10

An active intrusion campaign is targeting Check Point security management servers, with attackers forging administrator session cookies after exploiting a predictable session identifier. According to the report excerpts, an HFS \`loginSrp1\` endpoint returned signed cookies whose \`sid\` came from JavaScript’s \`Math.random\(\)\`; collecting several login responses let the actor reconstruct the V8 PRNG state, recover the HFS cookie-signing key, and forge a signed admin session. The excerpts do not say how many organizations were affected or whether Check Point has issued a fix.

hackernews · louiereederson · Nov 24, 16:32 · [Discussion](https://news.ycombinator.com/item?id=50630594)

**「Background」** Check Point security management servers are the administrative control point for configuring and monitoring protected networks, so a forged administrator session cookie grants control-plane access rather than access to a single host. The technique described in the report depends on V8&\#x27;s JavaScript Math.random\(\): it is not a cryptographically secure generator, and enough consecutive outputs allow an attacker to reconstruct its internal state and thereby recover a signing key. Here the repeated POSTs to the HFS loginSrp1 endpoint each returned a signed cookie carrying a &quot;sid&quot; drawn from Math.random\(\), giving the actor the output stream needed to forge an admin cookie.

**「Exposure risk」** Any Check Point Security Management Server or Multi-Domain Security Management Server reachable from the internet is exposed to CVE-2026-16232, an authentication bypass in the SmartConsole login process that can give unauthenticated remote attackers full administrative access. Operators should apply Check Point&\#x27;s security update and restrict management interfaces to trusted networks; Check Point published its advisory for the flaw on July 22, 2026.

**「Community discussion」** Commenters focused on the Math.random/V8 PRNG weakness, with one arguing the random-number generator should be made secure rather than blaming the many applications that used it incorrectly. Another questioned initial access: the link across multiple Check Point customers suggests CVE-2026-16232, but it is unclear whether all affected organizations exposed their management servers to the internet.

<details><summary>References</summary>
<ul>
<li><a href="https://www.greenbone.net/en/blog/check-point-smartconsole-vulnerability/">Check Point SmartConsole Vulnerability : CVE - 2026 - 16232</a></li>
<li><a href="https://www.rapid7.com/blog/post/ra-check-point-smartconsole-authentication-bypass-technical-analysis-cve-2026-16232/">Check Point SmartConsole Authentication Bypass Technical Analysis...</a></li>
<li><a href="https://digital.nhs.uk/cyber-alerts/2026/cc-4820">Check Point Releases Security Update for Critical Authentication...</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#Check Point`, `#active exploitation`, `#session forgery`, `#PRNG predictability`

---

<a id="item-tech-news-5"></a>
### [Brendan Gregg-Inspired Essay Draws Debate on Deterministic VMs and Flamegraphs](https://fzakaria.com/2026/11/12/worshipping-at-the-altar-of-brendan-gregg) ⭐️ 7.0/10

A performance-analysis essay inspired by Brendan Gregg drew substantive Hacker News discussion about deterministic virtual machines, flamegraph limitations, and critical-path analysis for multithreaded and asynchronous workloads. The article body was not supplied, so its specific claims and any tools or measured results it describes could not be verified.

hackernews · kqr · Nov 24, 10:50 · [Discussion](https://news.ycombinator.com/item?id=50626413)

**「Background」** Farid Zakaria&\#x27;s essay is framed around Brendan Gregg&\#x27;s performance-analysis work, and Zakaria writes that a deterministic VM called Rewind has helped him find heisenbugs, make profile-guided optimization reproducible, and make Nix builds bit-reproducible. A deterministic VM is meant to make an execution repeatable, which is the precondition for debugging or profiling a one-off failure more than once.

**「Community Discussion」** Commenter aidanhs welcomed deterministic VMs but argued that a single-threaded VM may compromise analysis of high-throughput multithreaded pipelines, and said they had cooled on flamegraphs because cross-thread dependencies are hard to infer. Another commenter, uvdn7, doubted that deterministic VMs help async workloads, noting that finding an async critical path may require framework changes such as propagating a request context across threads.

<details><summary>References</summary>
<ul>
<li><a href="https://fzakaria.com/2026/11/12/worshipping-at-the-altar-of-brendan-gregg">Worshipping at the altar of Brendan Gregg - fzakaria.com</a></li>

</ul>
</details>

**Tags**: `#performance analysis`, `#profiling`, `#flame graphs`, `#deterministic VM`, `#record-replay`

---

<a id="item-tech-news-6"></a>
### [Simon Willison names three LLM inflection points in twelve months](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 7.0/10

In a November 24, 2026 retrospective tied to the first anniversary of Claude Opus 4.5, Simon Willison argues the past twelve months contained three inflection points for LLMs and coding agents, expanding on a keynote he gave at the AI Engineer Code Summit. The first was November 2025, when Opus 4.5 — alongside OpenAI&\#x27;s GPT-5.1 Instant, Thinking, Codex and Codex-Max — became the first model whose default output in Claude Code was generally correct and faster than fixing the problem himself; Claude Code was then nine months old, having launched with Claude 3.7 Sonnet in February 2025. The second was the June/July arrival of what he calls &quot;Fable class&quot; models: Claude Fable 5, a restricted version of Claude Mythos, which Anthropic had said in April was too dangerous to release because of its vulnerability-exploitation capability, was pulled under US export controls after three days and returned July 1; he now classes Fable 5, 5.1 and 5.2, Opus 5.5 \(&quot;cheap Fable&quot;\), GPT-6 Astra and possibly Gemini 4 Neon in that group, defined by solving a problem with brute force once given a goal and the necessary tools. The third was 3D modeling and game development in September–October, which he dates to Opus 5.5&\#x27;s release on September 22, 2026 — the first model he says responded to &quot;make it a LOT more fun&quot; by spending 12 hours playtesting and rebalancing his RTS — though the supplied excerpt is truncated before his discussion of whether Fable 5.2 is a further inflection point.

rss · Simon Willison · Nov 24, 23:02

**「Background」** Claude Code had been available for about nine months before Claude Opus 4.5, having launched alongside Claude 3.7 Sonnet in February 2025. Willison&\#x27;s account is that earlier coding-agent output needed enough correction that Claude Code was not yet a daily driver, which is the baseline against which he measures Opus 4.5&\#x27;s reliability.

**「Impact」** For developers assessing coding agents, Willison&\#x27;s practical threshold is whether a model&\#x27;s default output is usually right enough that using it beats working the problem by hand — a bar he says Opus 4.5 first cleared, after earlier Claude Code versions required enough correction to not count as an accelerant. He also notes a lag between the December holidays, when he and others experimented with the new models, and January, when they put them into actual work, suggesting evaluation time precedes production adoption.

**Tags**: `#LLM agents`, `#coding agents`, `#AI engineering`, `#Claude Opus`, `#industry analysis`

---

<a id="item-tech-news-7"></a>
### [Z.ai Releases GLM-5.4, Its First Looped-Transformer Coding Model](https://simonwillison.net/2026/Nov/23/glm-54/) ⭐️ 7.0/10

Z.ai released GLM-5.4, its first model built on a looped-transformer architecture and aimed at generalized coding. In Z.ai&\#x27;s description, a group of weight-shared layers runs for multiple iterations and refines the hidden states from the previous pass, yielding a deeper network without increasing the parameter count. The model is reachable through Z.ai&\#x27;s API, but currently only via its Coding Plan subscription rather than the regular API, although both share the same OpenAI-compatible Responses API at https://api.z.ai/api/v1. Z.ai has not released open weights, saying it plans to open-source them after safety hardening, and the account includes no published benchmarks—only informal pelican-drawing comparisons in which GLM-5.4 and GLM-5.3 looked similar in quality and closer to OpenAI or Anthropic output than the distinctive 5.1 and 5.2 generations.

rss · Simon Willison · Nov 23, 23:40

**「Background」** In a standard Transformer, each layer runs once per forward pass. Z.ai&\#x27;s looped design instead runs a group of weight-shared layers for multiple iterations, refining the hidden states from the previous pass and producing a deeper network without increasing the parameter count.

**「Access and compatibility constraints」** Developers cannot reach GLM-5.4 through Z.ai&\#x27;s regular API pricing; access requires a Coding Plan subscription, which went live on November 23 with vision support and 50% more weekly quota. Because the coding plan and the regular API share the same OpenAI-compatible Responses endpoint at https://api.z.ai/api/v1, a coding-plan key works with existing OpenAI-compatible tooling, though client plugins may lag — Willison shipped his own llm-glm plugin only because llm-zai did not yet support the new model. Teams that need self-hosting or benchmark-based comparison still have to wait, since no weights, benchmarks, or API price have been published.

<details><summary>References</summary>
<ul>
<li><a href="https://www.orcarouter.ai/blog/glm-5-4-release-what-we-know">GLM - 5 . 4 Arrives on Z . ai &#x27;s Coding Plan: No Benchmarks Yet</a></li>

</ul>
</details>

**Tags**: `#looped transformers`, `#GLM-5.4`, `#AI model releases`, `#coding models`

---

<a id="item-tech-news-8"></a>
### [Singapore&\#x27;s Wong says it won&\#x27;t be a conduit around US chip controls](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

Singapore Prime Minister Lawrence Wong said Singapore will not be used as a conduit to evade US chip export controls, and that authorities are investigating Megaspeed&\#x27;s purchases of Nvidia chips. The statement followed the US Commerce Department&\#x27;s blacklisting of Megaspeed and six other Southeast Asian firms, including affiliates in Malaysia and Thailand, over what the Federal Register described as a &quot;significant risk&quot; of diverting advanced computing products to unauthorized users. Alibaba&\#x27;s Singapore subsidiary Apex Enterprise Solutions was also listed; Alibaba said it has never transferred controlled advanced computing chips.

telegram · zaihuapd · Nov 24, 05:03

**「Background」** US export controls restrict sales of advanced Nvidia accelerators to China, and enforcement depends heavily on stopping transshipment through third countries — Singapore&\#x27;s role as a regional trading and data-center hub has made it a recurring focus of that scrutiny. Placement on the Commerce Department&\#x27;s Entity List means a company needs a US license to receive controlled technology, and the listing can extend to related entities registered in other countries, which is why the Megaspeed action named affiliates in Malaysia and Thailand.

**「Compliance fallout for suppliers」** Because the designations target Megaspeed, its Malaysian subsidiary Speedmatrix, Alibaba&\#x27;s Singapore unit Apex Enterprise Solutions and the other named firms under rules covering all items subject to US export controls, suppliers and partners must now screen these entities and obtain US licenses before shipping, with delays or denials likely. Alibaba says Apex &quot;has never diverted advanced computing chips subject to US export restrictions,&quot; leaving open whether the listing will be contested.

<details><summary>References</summary>
<ul>
<li><a href="https://uz.kursiv.media/en/2026-11-24/us-blacklist-megaspeed-alice-huang/">US blacklists Megaspeed , once led by China spy suspect Alice Huang</a></li>
<li><a href="https://www.straitstimes.com/world/united-states/us-blacklists-megaspeed-chip-firm-linked-to-nvidia-scandal">US blacklists Megaspeed , Alibaba unit amid Nvidia scandal</a></li>
<li><a href="https://finance.yahoo.com/technology/ai/articles/us-blacklists-alibaba-owned-company-014536273.html">US Blacklists Alibaba -Owned Company in Setback to AI Ambitions</a></li>

</ul>
</details>

**Tags**: `#semiconductor export controls`, `#AI chips`, `#Singapore`, `#Nvidia`, `#US-China tech`

---

<a id="item-tech-news-9"></a>
### [VMware vCenter 9.8 auth bypass CVE-2026-123903 reportedly exploited as zero-day](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 7.0/10

Broadcom has released patches for 23 VMware vulnerabilities, including a 9.8-severity authentication bypass in vCenter&\#x27;s directory service \(vmdir\) tracked as CVE-2026-123903. The flaw lets anyone who can reach vCenter bypass authentication and access the system, according to the relayed report, which says it was exploited as a zero-day shortly before the fix. The item does not list affected vCenter versions, patch build numbers, or independent verification, so the precise exposure and whether exploitation continues are unconfirmed.

telegram · zaihuapd · Nov 24, 14:50

**「Earlier vCenter bypass」** Broadcom had issued emergency updates about five days earlier for a separate critical vCenter authentication bypass, CVE-2026-123890, according to search results; that earlier flaw was also described as requiring an emergency patch. The current issue is tracked separately as CVE-2026-123903.

**「Impact」** For infrastructure and security teams, the practical priority is to identify any vCenter instance reachable from untrusted networks, since no credentials are needed beyond network access. Because the relay gives no version or patch-build details, administrators should consult Broadcom&\#x27;s advisory to confirm which releases are affected and which update remediates CVE-2026-123903 rather than assuming an existing vCenter build is covered.

<details><summary>References</summary>
<ul>
<li>VMware vCenter CVE-2026-123890: Fixed Builds and What to Do</li>
<li>Broadcom fixes critical CVE-2026-123890 in VMware ...</li>

</ul>
</details>

**Tags**: `#vCenter`, `#VMware`, `#authentication bypass`, `#zero-day`, `#CVE-2026-123903`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [vLLM Day-0 Support for ERNIE 5.5 Flash](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 6.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** ERNIE 5.5 Flash Preview is a sparse mixture-of-experts model with 280B total parameters but only 14B activated per token, a 1M-token context, and tool-calling support for long-horizon agent tasks. The deployment challenge was to make this new architecture usable on release day without maintaining a vLLM fork, custom Docker image, or nightly wheel.

**「Solution」** Baidu&\#x27;s ERNIE team and vLLM shipped support as a standalone vLLM-ERNIE plugin installed alongside the official vllm==0.32.0 wheel. vLLM discovers it through the vllm.general\_plugins entrypoint and registers ERNIE architectures lazily, so the plugin adds no overhead when serving other models. The model uses 37 Heavily Compressed Attention layers and six MLA-DSA sparse-attention layers, plus Multi-Router Latent MoE and a MultiMax output head. The authors report that dedicated fused kernels for these structures run 1.55x to 6.53x faster than naive implementations, while preserving bitwise-identical outputs in several cases. FlashIndexer routes sparse indexer heads per token and adds threshold pre-filtering; the authors report a 1.4x indexing speedup at 1M context. The default checkpoint stores routed experts in MXFP4 with W4A8 quantization-aware training and other weights in FP8, with an FP8 KV cache. A bundled three-layer DSpark draft model proposes up to seven tokens per step and is said to reach mean acceptance above 4.0 on coding and agent workloads. The plugin also supports tensor parallelism, expert parallelism, PD disaggregation over Mooncake, and CPU KV-cache offloading. These performance figures are vendor-reported and lack independent methodology.

**「Takeaway」** The plugin approach lets model-specific kernels and features ship on the model&\#x27;s schedule while inheriting vLLM&\#x27;s serving infrastructure, though the speedup and acceptance-length claims still need independent validation.

**Tags**: `#vLLM`, `#ERNIE 5.5 Flash`, `#MoE inference`, `#kernel fusion`, `#speculative decoding`

---

<a id="item-tech-blog-2"></a>
### [vLLM-GR Brings Beam Search to Generative Recommendation Serving](https://vllm.ai/blog/2026-11-24-vllm-gr-announcement) ⭐️ 5.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** Generative recommenders such as OneRec generate semantic IDs \(SIDs\) for items a viewer may watch next, but a feed needs many candidates within one request’s latency budget. Serving them requires wide candidate search constrained to the real item catalog, which generic LLM inference does not directly address.

**「Solution」** vLLM-GR, an open-source framework built on vLLM, adds a beam session to vLLM’s scheduler, model execution, and paged KV cache. EngineCore owns each session; the scheduler dispatches prefill and decode stages, while the model runner scores the next token and beam selection records each surviving path’s score and parent so the next decode reads the correct KV state. Prompt KV is shared across beams rather than copied per candidate, and the host prepares the next stage while the accelerator executes the current one. It supports full-vocabulary or catalog-constrained generation, per-stage beam widths, and per-parent limits, exposed through Python, OpenAI-compatible HTTP, and gRPC. In OneRec-1.7B BF16 tests, vLLM-GR had the lowest P99 at beam width 256 and batch sizes 4 and 8 across all six tested accelerators; on H20 at batch size 8 it measured 369.4 ms versus 1,280.1 ms for SGLang and 428.1 ms for NVIDIA SID-GR. Yet NVIDIA SID-GR was faster at batch size 1 on RTX PRO 6000 \(28.25 ms versus 29.21 ms\), the winner at beam width 128 varied, and the authors note differing timing definitions, missing backend revisions, and an unrecorded SGLang constraint setting.

**「Takeaway」** vLLM-GR’s contribution is to make wide, catalog-constrained candidate search a first-class vLLM serving workload; its benchmark lead is promising but remains provisional because the comparisons are self-reported and unevenly documented.

**Tags**: `#vLLM`, `#generative recommendation`, `#beam search`, `#KV cache`, `#inference serving`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Xiaomi Q3 adjusted net profit falls 56.8% as EV deliveries top 100,000](https://ir.mi.com/static-files/3d372aaa-8ff8-4e33-ba01-68c8d7975a0b) ⭐️ 7.0/10

Xiaomi&\#x27;s adjusted net profit fell 56.8% year on year to RMB 4.884 billion in Q3 2026, slightly above the RMB 4.746 billion market estimate; electric-vehicle deliveries reached 100,975 units.

telegram · zaihuapd · Nov 24, 10:09

**「Background」** Xiaomi&\#x27;s profit squeeze comes as prices for memory chips and other core components rise while the company spends more on research and development, pressure that outweighs its growing but still smaller electric-vehicle business.

**Tags**: `#小米`, `#财报`, `#电动汽车`, `#智能手机`, `#中国科技`

---