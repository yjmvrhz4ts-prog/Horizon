---
layout: default
title: "Horizon Summary: 2026-11-22 (EN)"
date: 2026-11-22
lang: en
---

> From 26 items, 7 important content pieces were selected

---

**Technology News**
1. [OpenRouter discloses inference-provider data-processing incidents](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenAI Examines Perplexity as a Model-Intelligence Measure](#item-tech-news-2) ⭐️ 7.0/10
3. [Graham Dumpleton&\#x27;s Muru targets ASGI/WSGI serving in Rust](#item-tech-news-3) ⭐️ 7.0/10
4. [FT Alleges Prince Group Figures Tied to Nvidia Chip Smuggling to China](#item-tech-news-4) ⭐️ 7.0/10

**Technology Blog**
1. [Good Programming Is Mostly About Avoiding Blunders](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [Nasdaq Falls 5.28% as Asian Markets Roll Out Stabilization Measures](#item-finance-news-1) ⭐️ 9.0/10
2. [China Urges U.S. to Withdraw FCC Phone-Number Access Curbs](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenRouter discloses inference-provider data-processing incidents](https://openrouter.ai/blog/announcements/data-processing-incidents-on-inference-providers/) ⭐️ 8.0/10

OpenRouter has published an incident disclosure about data-processing incidents involving inference providers, affecting users of its LLM routing and API service and raising questions about how prompts are routed upstream and whether zero-data-retention assurances hold. The supplied source text is unavailable, so the announcement&\#x27;s specific providers, affected request volumes, and remediation terms cannot be verified here. Commenters describing the notice say it concerns prompts being forwarded to an upstream lab and providers rerouting traffic, but those specifics remain community accounts.

hackernews · sdko · Nov 22, 02:14 · [Discussion](https://news.ycombinator.com/item?id=50595554)

**「What ZDR means in a multi-provider router」** OpenRouter aggregates many third-party inference providers behind one API, forwarding each request to whichever provider it selects, so a prompt can be processed by a company the customer never picked. Zero Data Retention \(ZDR\) is the per-endpoint designation OpenRouter attaches to providers that agree not to store prompts, and it has been the main privacy assurance available to API customers too small to negotiate direct agreements with providers. The disclosure follows canary-token research — decoy URLs embedded in requests and monitored for access — which detected prompt forwarding and led OpenRouter to off-board three providers and remove 125 endpoints from ZDR eligibility.

**「ZDR settings only bind the endpoint that gets chosen」** OpenRouter&\#x27;s Zero Data Retention controls let an account restrict routing to non-retaining endpoints globally, per model group, per guardrail, or per request, and enabling the guardrail filters the catalog to ZDR-compliant providers. Because such a setting constrains only the endpoint OpenRouter selects, teams that must keep prompts with a specific vetted provider need to narrow the allowed provider set itself rather than rely on default routing to pick a compliant endpoint.

**「Community discussion」** Commenters who received the notice describe MiniMax reading decoy prompts and providers such as AtlasCloud, Novita, and StreamLake rerouting requests to it, while others question OpenRouter&\#x27;s provider vetting and say the incident has ended their consideration of the service. A separate thread argues that direct zero-data-retention agreements with inference providers are preferable, though even those ultimately depend on trusting the provider&\#x27;s documentation and behavior.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/blog/announcements/data-processing-incidents-on-inference-providers/">Data Processing Incidents on Inference Providers</a></li>
<li><a href="https://thehackernews.com/2026/11/openrouter-drops-3-providers-after.html">OpenRouter Drops 3 Providers After Researchers Catch Months of...</a></li>
<li><a href="https://openrouter.ai/docs/guides/features/zdr">Zero Data Retention - How OpenRouter gives you control over your...</a></li>
<li><a href="https://headsupai.io/updates/openrouter-adds-one-click-zero-data-retention-enforce-enterprise-privacy">OpenRouter Adds One-Click Zero Data Retention to Enforce...</a></li>

</ul>
</details>

**Tags**: `#AI privacy`, `#inference providers`, `#data retention`, `#LLM security`, `#OpenRouter`

---

<a id="item-tech-news-2"></a>
### [OpenAI Examines Perplexity as a Model-Intelligence Measure](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI&\#x27;s post examines pretraining perplexity as a measure of model intelligence and connects it to model capability, prompting discussion about benchmarking and reasoning-focused training. Commenters note that GPT-4.5 appears as a discontinuity: the larger model performed worse than chain-of-thought-trained o1 and o3 on benchmarks despite a potentially stronger base-model perplexity. The debate questions whether perplexity is a portable capability benchmark, since training-set composition and task-specific training can shift scores.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「Background」** Perplexity is the exponentiated cross-entropy loss a language model incurs when predicting held-out text; it measures next-token predictability rather than task accuracy directly. OpenAI&\#x27;s analysis connects that pretraining metric to model capability, while the surrounding discussion contrasts it with post-training methods such as chain-of-thought and reinforcement learning used in reasoning models.

**「Impact」** For teams using perplexity as a screening metric, the discussion implies that scores should be paired with task benchmarks and documented training-set composition, because commenters identify both as confounders that can make a model look more capable or more predictable than it is in downstream use.

**「Community Discussion」** Commenters disagreed over whether pretraining perplexity is a useful capability benchmark: some welcomed it as a refreshingly simple signal, while others cited GPT-4.5&\#x27;s benchmark results and training-set composition as evidence that it is not portable. Several also questioned claims that abilities &\#x27;emerge&\#x27; at specific perplexity levels, noting that math-specialized smaller models can have higher general perplexity.

**Tags**: `#LLM evaluation`, `#perplexity`, `#benchmarking`, `#pretraining`, `#OpenAI`

---

<a id="item-tech-news-3"></a>
### [Graham Dumpleton&\#x27;s Muru targets ASGI/WSGI serving in Rust](https://simonwillison.net/2026/Nov/21/muru/) ⭐️ 7.0/10

Graham Dumpleton, who started mod\_wsgi 20 years ago, has introduced Muru, an AI-assisted Rust server intended to provide tooling for running ASGI and WSGI Python applications in both development and production. Alongside the project, Dumpleton has published a detailed series of engineering posts covering workers, import-once/fork-many behavior, HTTPS in development, combined WSGI/ASGI support, releases without restarts, canaries, Kubernetes integration, scaling to zero, and a development toolbar with tracing. The source presents Muru as an early-stage effort and gives no released version, compatibility matrix, or measured performance figures, so its production readiness remains unestablished.

rss · Simon Willison · Nov 21, 23:56

**「Background」** Muru comes from Graham Dumpleton, who began the mod\_wsgi project 20 years ago and has since been considering the ideal way to serve Python web applications in production. Muru targets both ASGI and WSGI applications, the two interfaces Python web apps use to communicate with a server.

**Tags**: `#Python`, `#ASGI/WSGI`, `#Rust`, `#web servers`, `#open source`

---

<a id="item-tech-news-4"></a>
### [FT Alleges Prince Group Figures Tied to Nvidia Chip Smuggling to China](https://www.ft.com/content/f3ad8a81-3890-4a8a-8853-ff0a94b08ba9?syn-25a6b1a6=1) ⭐️ 7.0/10

The Financial Times, citing people familiar with the matter, reported that Hu Xiaowei — whom the US Treasury has identified as the &quot;number two&quot; figure at Cambodia&\#x27;s Prince Group — is alleged to have taken part in moving Nvidia chips into China. Trade data cited by the paper puts the declared value of goods imported by Megaspeed&\#x27;s Malaysian subsidiary at roughly $4.6 billion between December 2024 and December 2025, with some of those chips allegedly ending up in China&\#x27;s black market. Prince Group denied that Hu ever worked for the company and said the allegations about an illegal network and smuggling by private jet lack any factual basis. The claims rest on unnamed sources, the underlying evidence has not been independently verified, and the parties deny wrongdoing.

telegram · zaihuapd · Nov 22, 04:34

**「Context」** US export controls restrict sales of Nvidia&\#x27;s most advanced AI accelerators to China, which has pushed demand toward intermediaries and transshipment routes in third countries. The FT report focuses on whether corporate structures in Southeast Asia and underground financing channels were used to route hardware around those restrictions.

**「Why it matters」** The report points to third-country subsidiaries and shell-company structures as the pressure point for enforcement, which means distributors and cloud or hardware buyers operating in Malaysia and nearby markets face sharper scrutiny of where Nvidia accelerators originate and where they are ultimately used. Because the central allegations are denied and unverified, the $4.6 billion figure should be read as a declared import value cited by the newspaper, not as a confirmed volume of diverted chips.

**Tags**: `#Nvidia`, `#芯片走私`, `#出口管制`, `#AI硬件`, `#供应链合规`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Good Programming Is Mostly About Avoiding Blunders](https://seangoedecke.com/to-code-well-avoid-blunders/) ⭐️ 6.0/10

rss · Sean Goedecke · Nov 22, 00:00

**「Background」** Sean Goedecke argues that in large commercial codebases, writing good code depends less on brilliant abstractions than on avoiding catastrophic mistakes, because unlike basketball, one blunder can turn an elegant codebase into a janky one.

**「Solution」** Drawing analogies to chess and tennis, he says consistently avoiding errors beats occasional brilliance. He names parallel systems, duplicate sources of truth, turning safe synchronous operations into delicate asynchronous ones, adding subtle failure points, and complicating key interfaces as blunders. The cardinal sins are inconsistency and unnecessary requirements: inconsistency destroys trust and forces engineers to hunt for surprises, while requirements are sticky because later readers assume they are necessary, and they interact combinatorially, making large codebases hard to change. The author&\#x27;s remedy is to fit work as normally as possible into the existing codebase and trim the task to the smallest requirement set. A thought like “I could implement it with this clever pattern” is a warning sign of distraction. He scopes the advice to large commercial teams and notes that it applies to AI agents too, though he says current agents are worse at avoiding unnecessary requirements.

**「Takeaway」** Goedecke&\#x27;s thesis is that great programming does not require cleverness and may even be hindered by it; attention to detail and a focus on consistency and minimal requirements matter more. The larger point is that avoiding blunders, not discovering beautiful abstractions, is the main skill in durable commercial software work.

**Tags**: `#software engineering`, `#code quality`, `#maintainability`, `#engineering judgment`, `#large codebases`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Nasdaq Falls 5.28% as Asian Markets Roll Out Stabilization Measures](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

U.S. AI technology stocks sold off sharply on Friday, with the Nasdaq falling 5.28% in a day and the Philadelphia Semiconductor Index down nearly 11%, prompting mainland China, South Korea and Taiwan to announce market-stabilization measures.

telegram · zaihuapd · Nov 22, 13:24

**「Background」** Margin financing lets investors borrow to buy shares, so mainland China’s cut in the minimum ratio to 80% allows more leverage, while South Korea and Taiwan adjusted share-buyback and short-selling rules to limit downward pressure.

**「Impact」** The measures directly affect leveraged buyers in mainland China and short sellers in Taiwan, while South Korea’s three-month relaxation of daily buyback limits gives listed companies more room to repurchase shares.

**Tags**: `#US tech selloff`, `#Asian market stabilization`, `#margin rules`, `#short-selling restrictions`, `#semiconductor stocks`

---

<a id="item-finance-news-2"></a>
### [China Urges U.S. to Withdraw FCC Phone-Number Access Curbs](https://www.bloomberg.com/news/articles/2026-11-22/china-objects-to-us-curbs-on-telecoms-access-to-phone-numbers) ⭐️ 7.0/10

China’s Commerce Ministry on Nov. 22 urged the U.S. to withdraw an FCC measure adopted Nov. 19 that restricts China Mobile, China Telecom and China Unicom’s direct access to U.S. phone numbers, calling it discriminatory and disputing the national-security rationale.

telegram · zaihuapd · Nov 22, 06:44

**「Background」** The objection follows the FCC’s Nov. 19 vote to bar China Mobile, China Telecom and China Unicom from directly accessing U.S. phone numbers on national-security grounds, using the agency’s Covered List of equipment and services deemed risky to U.S. networks.

<details><summary>References</summary>
<ul>
<li>FCC bans Chinese firms from direct access to US phone numbers in bid to curb robocalls</li>

</ul>
</details>

**Tags**: `#US-China relations`, `#telecom regulation`, `#FCC`, `#Chinese carriers`, `#policy dispute`

---