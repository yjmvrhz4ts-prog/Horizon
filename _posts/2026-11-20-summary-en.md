---
layout: default
title: "Horizon Summary: 2026-11-20 (EN)"
date: 2026-11-20
lang: en
---

> From 40 items, 18 important content pieces were selected

---

**Technology News**
1. [Levent Alpöge claims Claude-assisted proof of Generalized Riemann Hypothesis](#item-tech-news-1) ⭐️ 8.0/10
2. [GitHub repo claims unforced Navier–Stokes blow-up, drawing Hacker News scrutiny](#item-tech-news-2) ⭐️ 8.0/10
3. [Gemini Can Operate Mac Apps With Pause Controls](#item-tech-news-3) ⭐️ 8.0/10
4. [PHP HTTPS/FTPS stream wrappers silently disabled TLS for 20 years](#item-tech-news-4) ⭐️ 8.0/10
5. [Meta employees report Muse AI assistant mixing chats and exposing private data](#item-tech-news-5) ⭐️ 8.0/10
6. [KVM flaw lets VMs read AMD host memory with nested virtualization](#item-tech-news-6) ⭐️ 8.0/10
7. [Architect Labs Claims AI Designed and Verified Frostbite CPU](#item-tech-news-7) ⭐️ 7.0/10
8. [Paper claims language models can rewrite their own weights without training](#item-tech-news-8) ⭐️ 7.0/10
9. [Thinking Machines announces Inkling 2 Mini local MoE model](#item-tech-news-9) ⭐️ 7.0/10
10. [Terry Tao Post Reportedly Covers Navier-Stokes Singularity and GRH](#item-tech-news-10) ⭐️ 7.0/10
11. [Mozilla Post Details Why iOS Still Lacks Non-WebKit Browser Engines](#item-tech-news-11) ⭐️ 7.0/10
12. [Signal Publishes Privacy Update on AI App Chat Access](#item-tech-news-12) ⭐️ 7.0/10
13. [Ravi Vakil announces proposed Masullo proof of Generalized Riemann Hypothesis](#item-tech-news-13) ⭐️ 7.0/10
14. [UK tribunal orders public hearing in Apple encryption case](#item-tech-news-14) ⭐️ 7.0/10
15. [U.S. House panel discloses 879,868 approved AI-chip exports to China](#item-tech-news-15) ⭐️ 7.0/10
16. [US chip curbs prompt India AI compute buildout](#item-tech-news-16) ⭐️ 7.0/10

**Technology Blog**
1. [Serving Inkling 2 Mini&\#x27;s Looped Layers on vLLM](#item-tech-blog-1) ⭐️ 7.0/10

**Financial News**
1. [Fed Officials Speak More as Warsh Avoids Rate Guidance](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Levent Alpöge claims Claude-assisted proof of Generalized Riemann Hypothesis](https://alpo.ge/remark.pdf) ⭐️ 8.0/10

Levent Alpöge has posted a PDF claiming that he and Claude discovered a proof of the Riemann Hypothesis, with the method extending to the Generalized Riemann Hypothesis and, he expects, the Extended Riemann Hypothesis. He says the arguments were also formalized without assumptions. The supplied material does not independently verify the proof or the formalization, and the post itself is a claim rather than a confirmed result.

hackernews · iamronaldo · Nov 20, 14:16 · [Discussion](https://news.ycombinator.com/item?id=50574968)

**「Background」** The Riemann Hypothesis, dating to 1859 and still unproved, asserts that the nontrivial zeros of the zeta function lie on a single critical line; the Generalized Riemann Hypothesis extends that assertion to a broader class of L-functions. Alpöge&\#x27;s manuscript is written in Lean, a proof assistant that mechanically checks each step, though specialists still need to confirm that the formalization actually encodes the claimed theorem.

**「Impact」** Mathematicians and formal-verification groups would need to inspect and build the claimed Lean development before the result could be treated as established; a commenter reports that the archive is about 1.3 GB and roughly 15 million lines, making independent checking a substantial effort.

**「Community discussion」** Commenters point to a purported separate human proof and describe the four-page PDF as an abbreviated but recognizable proof skeleton that suggests the work is not crank material. Another commenter reports the Lean archive&\#x27;s size, while a separate thread criticizes framing Alpöge only as an Anthropic employee rather than as a mathematician, arguing that this shifts credit from the person to the company.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nacionale.com/en/articles/has-riemann-hypothesis-been-proved-levent-alpoge-claude-anthropic-claim-lean">Riemann hypothesis proof claimed with Claude , unverified</a></li>
<li><a href="https://www.scientificamerican.com/article/anthropic-mathematician-claims-to-prove-riemann-hypothesis-most-famous-problem-in-all-of-math/">Anthropic mathematician claims to prove Riemann hypothesis , most...</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#Riemann Hypothesis`, `#Lean`, `#formal verification`, `#unverified claim`

---

<a id="item-tech-news-2"></a>
### [GitHub repo claims unforced Navier–Stokes blow-up, drawing Hacker News scrutiny](https://github.com/tristanbuckmaster/navier-stokes/) ⭐️ 8.0/10

A GitHub repository by Tristan Buckmaster claiming finite-time blow-up for the Navier–Stokes equations reached Hacker News on November 20, 2026, where commenters described it as the unforced version of the problem rather than the forced construction they attribute to OpenAI. The submission supplied no technical detail beyond the repository title, and the claim&\#x27;s validity is not established by the available material. Commenters also connected it to a same-day generalized Riemann Hypothesis claim and to mathematician Levent Alpöge, framing the day as unusually eventful for mathematics.

hackernews · trotro · Nov 20, 15:34 · [Discussion](https://news.ycombinator.com/item?id=50576232)

**「Why the Navier–Stokes claim matters」** The Clay Mathematics Institute lists the Navier–Stokes existence and smoothness problem as one of its Millennium Prize Problems and offers US$1 million for a solution. A finite-time blow-up would mean a smooth solution develops a singularity in finite time, and this claim concerns the unforced equations, with no external force applied. Reporting describes a 79-page AI-assisted paper whose numerical certificate has not been released and whose independent verification is still pending.

**「Verification burden」** Because the submission is a bare GitHub repository rather than a peer-reviewed paper, the immediate consequence is that mathematicians and anyone citing it must treat the claimed unforced blow-up as unverified until the construction is checked by others. The community&\#x27;s distinction between this and OpenAI&\#x27;s forced construction matters here: the arXiv write-up describes OpenAI&\#x27;s manuscript as a blow-up result obtained &quot;with smooth forcing,&quot; so only an unforced proof would settle the Millennium Prize formulation as usually stated.

**「Community discussion」** Commenters focused on distinguishing this claimed unforced blow-up from the forced construction tancop attributed to OpenAI, calling the unforced version more &quot;realistic&quot; in a sense. The thread also traded in same-day speculation about a generalized Riemann Hypothesis result, an Anthropic &quot;millennium problem&quot; rumor, and Levent Alpöge potentially claiming two millennium problems in one day, none of which verifies the repository&\#x27;s claim.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_priority_controversy">Navier–Stokes priority controversy - Wikipedia</a></li>
<li><a href="https://officechai.com/ai/tristan-buckmaster-levent-alpoge-claim-proof-of-navier-stokes-millennium-prize-problem-without-forcing/">Tristan Buckmaster, Levent Alpöge Claim Proof Of Navier ...</a></li>
<li><a href="https://magica.com/news/alpoge-buckmaster-navier-stokes-unforced-blowup-claim">Alpöge and Buckmaster’s unverified Navier–Stokes claim | Magica</a></li>
<li><a href="https://cdn.openai.com/pdf/32d9f210-8b73-45e0-91bc-82a30aef8a9a/navier-stokes.pdf">FINITE TIME BLOWUP FOR NAVIER–STOKES - cdn.openai.com</a></li>
<li><a href="https://arxiv.org/abs/2609.35406">Finite-Time Blowup for Navier-Stokes with Smooth Forcing ...</a></li>

</ul>
</details>

**Tags**: `#Navier-Stokes`, `#mathematics`, `#fluid dynamics`, `#research breakthrough`, `#Hacker News`

---

<a id="item-tech-news-3"></a>
### [Gemini Can Operate Mac Apps With Pause Controls](https://www.bloomberg.com/news/articles/2026-11-19/google-s-gemini-can-now-control-mac-devices-on-users-behalf) ⭐️ 8.0/10

Google has added a “computer operation” feature to Gemini for Mac that can click, type, navigate menus, and fill forms on a user&\#x27;s behalf. The feature is available in the US to Gemini Mac users subscribed to Google AI Plus, Pro, or Ultra. Gemini runs in a separate background window while the user continues using the main screen and cursor; users can restrict which apps it can access, watch its actions in real time, pause it, and approve key steps.

telegram · zaihuapd · Nov 20, 02:51

**「Background」** Desktop-control agents act through a computer&\#x27;s graphical interface—clicking, typing, and navigating menus—rather than through an app-specific API or integration. That approach can let a model operate software that was not designed for automation, while making app-level access limits and approval before sensitive actions the main safeguards.

**「Impact」** For eligible subscribers, Gemini can now act inside app interfaces while the user keeps using the Mac, turning multi-step menu and form tasks into delegated actions rather than chat-only requests. The app-access limits, real-time view, pause control, and approval step are the concrete controls users can apply and monitor.

**Tags**: `#AI agents`, `#Google Gemini`, `#macOS automation`, `#desktop automation`, `#AI safety controls`

---

<a id="item-tech-news-4"></a>
### [PHP HTTPS/FTPS stream wrappers silently disabled TLS for 20 years](https://x.com/ljachowicz/status/2123477025268924514) ⭐️ 8.0/10

A case-sensitivity bug in PHP&\#x27;s HTTP and FTP stream wrappers reportedly meant TLS was only enabled when the fifth character of the scheme was a lowercase &quot;s&quot;, so URLs such as HTTPS://, httpS:// and FTPS:// were sent as plaintext HTTP or FTP. According to the relayed report, this exposed tokens, Basic authentication credentials, cookies, POST request bodies and FTP login details, including when a third party redirected a request to such a URL. The flaw is tracked as CVE-2026-128064 \(GHSA-f6gg-rchx-xw8j\) with a CVSS 4.0 score of 8.2, and is fixed in PHP 8.2.36, 8.3.37, 8.4.28, 8.5.13 and 8.6.0. PHP 8.1 and earlier are end-of-life and will not receive a fix, leaving lowercase normalization of URL schemes as the workaround; the claim originates from a social/Telegram relay rather than an independent advisory.

telegram · zaihuapd · Nov 20, 03:04

**「Background」** PHP&\#x27;s HTTP and FTP stream wrappers matched URL schemes case-insensitively but enabled TLS only when the scheme&\#x27;s fifth character was a lowercase &quot;s&quot;. That mismatch is what allowed variants such as HTTPS:// and httpS:// to be accepted as secure schemes while the connection itself stayed plaintext. PHP&\#x27;s changelog records the fix for &quot;Mixed-case HTTPS and FTPS URLs can expose data in plaintext&quot; under CVE-2026-128064 / GHSA-f6gg-rchx-xw8j.

**「Impact」** Operators of applications on PHP 8.1 or earlier must normalize URL schemes to lowercase themselves before passing them to the stream wrappers, since no patch is planned for those branches. Anyone who cannot upgrade immediately should audit code paths where URLs may arrive with mixed-case schemes — including redirect targets — because credentials and request bodies sent through them traveled unencrypted.

<details><summary>References</summary>
<ul>
<li><a href="https://www.php.net/ChangeLog-8.php">PHP : PHP 8 ChangeLog</a></li>

</ul>
</details>

**Tags**: `#PHP`, `#security vulnerability`, `#TLS`, `#CVE`, `#open source`

---

<a id="item-tech-news-5"></a>
### [Meta employees report Muse AI assistant mixing chats and exposing private data](https://techcrunch.com/2026/11/19/metas-ai-agent-muse-is-mixing-up-conversations-and-exposing-private-data-report-says/) ⭐️ 8.0/10

Meta employees reported in internal posts that the company&\#x27;s AI assistant Muse mixed conversations across accounts and displayed other people&\#x27;s private information, according to Reuters and TechCrunch. The reported examples included parenting requests and career advice that had not been sent or asked for, orders that had not been placed, and a weather-chat message saying, “By the way, Capital One balance $2,722.58, Charles Schwab balance $5,899.57.” Another employee said Muse reminded her on her personal phone to reply to her sister&\#x27;s Signal message even though she said she had not authorized access to other apps. The accounts come from internal employee posts rather than a public technical disclosure, and the source included no confirmation or explanation from Meta.

telegram · zaihuapd · Nov 20, 05:10

**「Background」** Muse is Meta&\#x27;s personal AI agent, announced on September 8, 2026, and rolling out in the US on iOS, Android, and muse.ai, with free core use and subscription plans. It runs on a virtual machine in Meta&\#x27;s cloud and is used through a chat interface that includes a browser the user can watch as the agent works.

**「Impact」** If confirmed, the reported cross-account leakage would mean that sensitive financial or messaging data could surface in the wrong person&\#x27;s Muse session. For users who link the assistant to other accounts or apps, the concrete concern is which third-party integrations and notification permissions Muse can access, and whether those permissions need to be reviewed or limited until Meta explains the scope.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Muse_%28AI_agent%29">Muse (AI agent) - Wikipedia</a></li>
<li><a href="https://about.fb.com/news/2026/09/introducing-muse-personal-ai-agent/">Introducing Muse: The World’s First Personal AI Agent Built ...</a></li>

</ul>
</details>

**Tags**: `#AI privacy`, `#Meta Muse`, `#data leakage`, `#AI agents`, `#security incident`

---

<a id="item-tech-news-6"></a>
### [KVM flaw lets VMs read AMD host memory with nested virtualization](https://thehackernews.com/2026/11/new-linux-kvm-flaw-cve-2026-99312-lets.html) ⭐️ 8.0/10

A Linux KVM flaw tracked as CVE-2026-99312 can let a virtual machine read host memory on AMD machines when nested virtualization is enabled; researchers reported reading about 127 GB of host memory from a VM running on DigitalOcean. An upstream fix was released on November 18 in stable Linux 7.3.5 and related stable kernels, but the report says Debian and Ubuntu kernels remain unpatched. Until distribution updates arrive, the suggested mitigation is to disable nested virtualization on affected AMD hosts.

telegram · zaihuapd · Nov 20, 14:23

**「Background」** KVM is the Linux kernel&\#x27;s hypervisor, and nested virtualization lets a guest run its own hypervisor, requiring the host to emulate low-level processor events such as INIT resets. Red Hat&\#x27;s advisory describes this flaw as arising when KVM emulates an INIT reset with paging enabled during nested virtualization and fails to reset the MMU context, which can cause memory corruption or a denial of service.

**「Operational impact」** Operators of AMD hosts with nested virtualization should disable it until a patched kernel is available, since a guest can read host memory. Debian and Ubuntu users cannot yet rely on a distribution update, although upstream Linux 7.3.5 contains the fix.

<details><summary>References</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99312">CVE-2026-99312 - Red Hat Customer Portal</a></li>

</ul>
</details>

**Tags**: `#KVM`, `#Linux kernel security`, `#CVE-2026-99312`, `#AMD virtualization`, `#cloud security`

---

<a id="item-tech-news-7"></a>
### [Architect Labs Claims AI Designed and Verified Frostbite CPU](https://architectlabs.com/blog/frostbite) ⭐️ 7.0/10

Architect Labs&\#x27; blog post claims that an AI discovered, designed, and verified a CPU architecture called Frostbite, which is based on interaction nets. The post presents the result as an AI-driven architecture effort, but the available evidence does not include independent benchmarks, fabrication results, or a reproducible verification artifact, so performance and novelty remain unconfirmed. The claim drew substantial Hacker News attention, with commenters disputing the headline&\#x27;s framing and the strength of the technical evidence.

hackernews · shioyama · Nov 20, 10:01 · [Discussion](https://news.ycombinator.com/item?id=50572503)

**「Background」** Architect Labs describes Frostbite as a general-purpose CPU built around interaction nets and says its AI systems discovered, designed, and verified the architecture end to end \[tool-1-1\]\[tool-1-3\]. The HN submitter stresses that interaction nets are a fundamentally different programming paradigm from the architecture underlying conventional CPUs, so the model itself is the relevant prerequisite. External coverage repeats the 4.59x performance-per-watt figure as a claim by Architect Labs rather than an independently verified result \[tool-1-2\].

**「Impact」** Chip architects and AI-hardware researchers should treat Frostbite as an unverified research claim until independent benchmarks and a full account of the verification method are available; the discussion specifically questions the use of an in-order CPU baseline and a small program set.

**「Community Discussion」** Hacker News commenters disputed the “AI-designed” framing: jkhdigital argued that humans supplied the insights while AI synthesized decades of research into a coherent product, and pizza234 questioned the in-order CPU baseline, the small program set, and novelty relative to WaveScalar. shioyama, who posted the item, argued that commenters should focus on interaction nets as a fundamentally different programming paradigm, while acknowledging uncertainty about whether this implementation will deliver the claimed performance.

<details><summary>References</summary>
<ul>
<li><a href="https://architectlabs.com/blog/frostbite">Introducing Frostbite: A new CPU architecture discovered ...</a></li>
<li><a href="https://www.notebookcheck.net/AMD-and-Intel-move-over-AI-designed-an-all-new-CPU-and-claims-it-is-4-6x-more-efficient.1455225.0.html">AMD and Intel, move over: AI designed an all-new CPU — and ...</a></li>
<li><a href="https://architectlabs.com/">Architect Labs</a></li>

</ul>
</details>

**Tags**: `#AI hardware design`, `#CPU architecture`, `#interaction nets`, `#formal verification`

---

<a id="item-tech-news-8"></a>
### [Paper claims language models can rewrite their own weights without training](https://arxiv.org/abs/2611.21885) ⭐️ 7.0/10

A paper posted to arXiv \(2611.21885\) and discussed on Hacker News claims a language model rewrote its own weights through its own reasoning and improved &quot;with no gradients and no training.&quot; As quoted in the discussion, the method has the model test its edits on practice problems and keep only what works, with accuracy rising across eight consecutive sessions. The supplied evidence consists of the paper&\#x27;s headline claims and reader commentary rather than an independent measurement, and commenters note the approach resembles existing training-free weight-editing work and Google&\#x27;s &quot;sleep&quot; framework, which updates weights offline using self-generated practice examples. Several readers also pressed on how the model identifies which weights to adjust, since no mechanism is described in the available material.

hackernews · lwhsiao · Nov 20, 16:29 · [Discussion](https://news.ycombinator.com/item?id=50577265)

**「Background」** The paper&\#x27;s starting point is the usual deployment pattern for language models: they are trained once, frozen, and need another training run to improve, while prompts or inference-time scaffolding do not persist after the task ends \(tool-1-1\). A related earlier line of work, Google Research&\#x27;s Sleep framework, updated model weights from self-generated practice examples during an offline phase, though it relied on pre-allocated Mixture-of-Experts memory blocks rather than the no-gradient self-rewrite this paper claims \(tool-3-1\).

**「What to check before trusting the result」** The concrete improvement reported, according to one commenter&\#x27;s reading, was a reduction in the length of the model&\#x27;s reasoning traces to avoid hitting a token limit — a fix to an obvious defect rather than a demonstration of general capability gain. Readers weighing the method should check whether the described edits produce gains on models that lack such a flaw, since improvement attributable to a single known weakness would not support broader claims about models improving themselves.

**「Community discussion」** Commenters questioned both novelty and substance: one argued the sole self-modification was shortening reasoning traces to dodge a token limit, citing prior weight-space programming work in which a model failed to improve without an obvious flaw to fix, while another pointed to Google&\#x27;s &quot;sleep&quot; framework as an earlier demonstration of offline weight updates from self-generated examples. Others asked how the model knows which weights to adjust and whether filtering edits by tested performance amounts to training under another name, and one proposed training a model to repair deliberately damaged weights as a path toward recursive self-improvement.

<details><summary>References</summary>
<ul>
<li><a href="https://arxiv.org/abs/2611.21885">[2611.21885] Language Models Can Rewrite Their Own Weights</a></li>
<li><a href="https://research.google/blog/the-sleep-framework-a-new-way-for-llms-to-retain-knowledge-in-continual-learning/">The sleep framework : A new way for LLMs to retain knowledge in...</a></li>

</ul>
</details>

**Tags**: `#self-modifying language models`, `#weight-space editing`, `#training-free adaptation`, `#AI research`, `#community skepticism`

---

<a id="item-tech-news-9"></a>
### [Thinking Machines announces Inkling 2 Mini local MoE model](https://thinkingmachines.ai/news/inkling-2-mini/) ⭐️ 7.0/10

Thinking Machines announced Inkling 2 Mini, a local-oriented mixture-of-experts model that uses a looped-transformer architecture and was trained end-to-end in NVFP4. The release claims benchmark performance competitive with Qwen3.8-27B and is positioned for local inference and multi-agent workloads, but those benchmark and architecture claims are not independently verified in the supplied material. Commenters expect the MoE design to provide higher decode speed and to let multiple agents keep separate KV caches within VRAM, though those expectations remain untested here.

hackernews · jasondavies · Nov 20, 20:12 · [Discussion](https://news.ycombinator.com/item?id=50581260)

**「Background」** A mixture-of-experts model routes each token through only a subset of its parameters, so it can carry a large total parameter count while keeping per-token compute and decode cost comparatively low — the property commenters expect to make Inkling 2 Mini faster locally than a dense model of similar quality. A looped transformer, the architecture described here, reuses the same layer block across multiple passes rather than stacking distinct layers. Thinking Machines&\#x27; Inkling 2 line also includes an Inkling 2 Small variant, listed at 594B parameters with 17B active and an NVFP4 checkpoint that requires at least 500GB of aggregated VRAM, a scale at which single-machine local deployment is not practical.

**「What local users should check」** The concrete comparison point is Qwen3.8-27B, a dense 27B model documented to run on roughly 17GB of RAM/VRAM, so anyone on a 16–24GB GPU should verify Inkling 2 Mini&\#x27;s quantized weight and KV-cache footprint rather than assume the MoE design makes it a drop-in replacement. The expected benefit — higher decode throughput at comparable quality — is what commenters intend to test on consumer hardware such as an AMD 7900XTX, and the multi-agent case depends on each agent&\#x27;s KV cache fitting in VRAM, a figure the announcement leaves unverified.

**「Community discussion」** Commenters were enthusiastic but had not verified the claims: one argued it could be the first model to run multi-agent reasoning harnesses reliably on local hardware because separate agents can each keep KV caches in VRAM, while another planned to test it on an AMD 7900XTX against Qwen 3.8 27B and expected the MoE design to deliver higher decode speed. A third pointed to SenseNova&\#x27;s recently released looping model as another recent example of the approach.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/thinkingmachines/Inkling-2-Small">thinkingmachines/ Inkling - 2 -Small · Hugging Face</a></li>
<li><a href="https://kie.ai/blog/what-is-inkling-2-small">What Is Inkling 2 Small? Specs, Costs &amp; Benchmarks</a></li>
<li><a href="https://unsloth.ai/docs/models/qwen3.8">Qwen 3 . 8 - How to Run Locally | Unsloth Documentation</a></li>

</ul>
</details>

**Tags**: `#local LLMs`, `#model release`, `#mixture-of-experts`, `#looped transformer`, `#NVFP4`

---

<a id="item-tech-news-10"></a>
### [Terry Tao Post Reportedly Covers Navier-Stokes Singularity and GRH](https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/) ⭐️ 7.0/10

A Terry Tao blog post dated November 20, 2026 reportedly discusses an unforced Navier-Stokes singularity and a Generalized Riemann Hypothesis result. No post text, theorem statements, or proof details were supplied, so the mathematical claims and their verification status cannot be assessed from the available material.

hackernews · archon1410 · Nov 20, 17:21 · [Discussion](https://news.ycombinator.com/item?id=50578358)

**「Background」** The underlying problem is singularity formation in incompressible fluids: whether smooth solutions of the Euler or Navier–Stokes equations can break down in finite time. In an October 4, 2026 post, Tao noted that recent Euler and Navier–Stokes work carried out with large language models had renewed attention on that question; the November 20 post identifies the new unforced Euler/Navier–Stokes work as that of Levent Alpöge, Tristan Buckmaster, and Matei Coiculescu and connects it to a Generalized Riemann Hypothesis claim.

**「Verification impact」** Commenters report that two independent kernels accepted the GRH proof: the described workflow has Lean’s kernel check the proof object first, then exports it for nanoda to recheck through Comparator. For formal-math and AI-for-math teams, that makes independent kernel replay the practical acceptance test—especially for AI-assisted proofs—rather than relying on a single prover’s acceptance.

**「Community discussion」** Commenters focused on verification and method: one cited a Lean Zulip thread as indicating that two independent kernels accept the result, suggesting no kernel-bug exploitation, while another said the GRH proof appears to have been generated directly in Lean and the Navier-Stokes proof in natural language before formalization. A further commenter questioned how new mathematical abstractions—rather than proofs built on existing ones—are created, and another questioned why Tao&\#x27;s post did not discuss the result&\#x27;s significance.

<details><summary>References</summary>
<ul>
<li><a href="https://terrytao.wordpress.com/2026/11/20/unforced-euler-singularity-unforced-navier-stokes-singularity-and-the-generalized-riemann-hypothesis/">Unforced Navier-Stokes Singularity and the Generalized ...</a></li>
<li><a href="https://terrytao.wordpress.com/2026/10/04/on-classical-solutions-and-singularity-formation-in-incompressible-fluids/">On classical solutions and singularity formation in ...</a></li>
<li><a href="https://www.riemannzeta.fun/methodology">Verification methodology · Riemann zeta function</a></li>
<li><a href="https://github.com/CocoSgt/riemann-hypothesis-lean">GitHub - CocoSgt/riemann-hypothesis- lean : Mirror of Levent...</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#Lean theorem prover`, `#AI for mathematics`, `#Riemann Hypothesis`, `#Navier-Stokes`

---

<a id="item-tech-news-11"></a>
### [Mozilla Post Details Why iOS Still Lacks Non-WebKit Browser Engines](https://blog.mozilla.org/en/mozilla/internet-policy/apple-ios-browser-engine-rules/) ⭐️ 7.0/10

Mozilla has published a policy analysis explaining why iOS still has no non-WebKit browser engines, pointing to Apple&\#x27;s app rules and the practical barriers developers face. According to the accompanying Hacker News discussion, building and running a custom engine is effectively limited to Europe: developers elsewhere report needing a VPN or special network so iOS believes they are in the EU. The barriers also include Apple&\#x27;s notarization process, which commenters tie to the BrowserEngineKit and safe-programming guidelines needed for distribution and JIT support, plus a condition barring disclosure of non-public information about the project. The post is advocacy and analysis rather than a shipped capability or an announced Apple policy change.

hackernews · lapcat · Nov 20, 15:03 · [Discussion](https://news.ycombinator.com/item?id=50575644)

**「Apple&\#x27;s EU-only browser-engine opening」** Apple&\#x27;s route to non-WebKit engines on iOS runs through BrowserEngineKit, the framework introduced with iOS 17.4 that lets dedicated browsers and in-app browsers on devices in the EU request alternative engines under Apple&\#x27;s entitlement and notarization process. At the time, Mozilla said it was &quot;extremely disappointed&quot; with the rules, and both Mozilla and Google asked Apple to apply the EU browser-engine changes worldwide rather than only in Europe.

**「Impact」** For browser developers, the immediate consequence is that testing a non-WebKit engine on iOS requires being in the EU or spoofing location, and store distribution depends on meeting Apple&\#x27;s notarization and safe-programming requirements, including BrowserEngineKit for JIT access. Commenters cite existing Gecko- and Chromium-based iOS browsers, Reynard and Blinker-Fluid, as examples that exist but likely do not qualify for notarization because they do not follow those requirements, leaving them outside normal distribution. The non-disclosure condition also limits developers&\#x27; ability to publicly report progress on such projects.

**「Community Discussion」** Commenters reported that work on custom engines is practically confined to Europe, with st3fan calling the need for VPNs to build and run &quot;completely bonkers&quot; and arguing Apple could allow the capability worldwide while still profiting. dadoum noted that non-WebKit browsers such as Reynard \(Gecko-based, iOS 13+\) and Blinker-Fluid \(Chromium-based, iOS 12+\) already exist, but guessed they do not rely on BrowserEngineKit or Apple&\#x27;s safe-programming guidelines and therefore likely fail notarization.

<details><summary>References</summary>
<ul>
<li><a href="https://arstechnica.com/gadgets/2024/02/google-and-mozilla-dont-like-apples-new-ios-browser-rules/">Google and Mozilla don’t like Apple ’s new iOS browser rules</a></li>
<li><a href="https://www.theverge.com/2024/1/26/24052067/mozilla-apple-ios-browser-rules-firefox">Mozilla says Apple ’s new browser rules are ‘as painful as... | The Verge</a></li>
<li><a href="https://factually.co/fact-checks/technology/ios-17-browser-engine-rules-privacy-implications-6a77e3">How iOS 17 Changes Browser Engine Rules And What It Me...</a></li>

</ul>
</details>

**Tags**: `#Apple`, `#iOS`, `#browser engines`, `#WebKit`, `#platform regulation`

---

<a id="item-tech-news-12"></a>
### [Signal Publishes Privacy Update on AI App Chat Access](https://signal.org/blog/protecting-your-privacy/) ⭐️ 7.0/10

Signal published a privacy-protection update aimed at limiting AI apps&\#x27; access to Signal chats on mobile devices, according to the item summary. Commenters linked it to a concern Meredith Whittaker has discussed: AI apps with broad device access may reach Signal chats, including through contacts who use such apps. The supplied material gives no technical details, rollout timeline, or independent testing, so this is a vendor update rather than a demonstrated fix.

hackernews · dotcoma · Nov 20, 09:42 · [Discussion](https://news.ycombinator.com/item?id=50572348)

**「Background」** Mobile AI agents such as Gemini and Siri can read what is displayed inside other apps, which is the access path Signal&\#x27;s new protections target. The Verge reported that Signal is blocking those AI agents from reading users&\#x27; messages, while Meredith Whittaker acknowledged the screenshot-blocking remedy is &quot;incomplete&quot; because agents can still retrieve app data through the device file system.

**「Device-level isolation still matters」** Signal&\#x27;s protections do not close the contact-side exposure path: if a contact&\#x27;s phone is compromised by an over-permissioned app, the chat can still leak, so high-risk users need OS-level isolation—such as a hardened Android build with stricter permission controls—rather than relying on Signal alone.

**「Community Discussion」** One commenter said it was good to see Signal making progress and asked the company to publish its forensic findings, ideally as a collaborative document other developers could use. Others argued that relying on an app to prevent screenshots is insufficient and recommended OS-level control through GrapheneOS or Linux, while another asked why Signal requires a phone number or identifying payment method instead of supporting Monero.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/1038390/signal-blocking-ai-agent-screenshots-mobile-app">Signal is blocking Gemini and Siri AI from reading your... | The Verge</a></li>
<li><a href="https://www.cape.co/blog/grapheneos-supported-devices">GrapheneOS -Supported Devices: A Complete List [2026] | Cape - Cape</a></li>

</ul>
</details>

**Tags**: `#Signal`, `#privacy`, `#mobile security`, `#AI app permissions`, `#GrapheneOS`

---

<a id="item-tech-news-13"></a>
### [Ravi Vakil announces proposed Masullo proof of Generalized Riemann Hypothesis](https://simonwillison.net/2026/Nov/20/ravi-vakil/) ⭐️ 7.0/10

Ravi Vakil announced that Alessandro Masullo has a proposed proof of the Generalized Riemann Hypothesis, with the current draft being put out sooner than planned. Vakil said Brian Conrad has examined the work closely for months and provided extensive feedback that is being incorporated, and that the work so far looks good. Vakil also said the work is entirely human, with no AI. The claim is unverified and still under review, so it should be treated as a proposal rather than a confirmed proof.

rss · Simon Willison · Nov 20, 19:21

**「What the GRH is」** The generalized Riemann hypothesis \(GRH\) extends the Riemann hypothesis&\#x27;s claim about the zeros of the Riemann zeta function to Dirichlet L-series, conjecturing that neither the zeta function nor any Dirichlet L-series has a zero with real part greater than 1/2. The Riemann hypothesis itself concerns the location of the zeta function&\#x27;s nontrivial zeros, and GRH applies that same bound to a broader class of L-functions.

**「What a proof would and wouldn&\#x27;t change」** For number theorists, the immediate consequence is procedural rather than mathematical: because the draft is being released mid-review, any reliance on it should wait for the refereeing Vakil describes as still unfinished. The best-documented algorithmic payoff of GRH — a deterministic polynomial-time primality test via the Miller test — was already obtained unconditionally by the AKS test in 2002, so a proof would not by itself alter the foundations of practical primality testing or the cryptographic schemes built on it. No cases of GRH beyond the algebraic function field setting have been proven, which is what makes an unverified number-field claim noteworthy but not yet usable.

<details><summary>References</summary>
<ul>
<li><a href="https://mathworld.wolfram.com/GeneralizedRiemannHypothesis.html">Generalized Riemann Hypothesis -- from Wolfram MathWorld</a></li>
<li><a href="https://en.wikipedia.org/wiki/Generalized_Riemann_hypothesis">Generalized Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Riemann_hypothesis">Riemann hypothesis - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#mathematics`, `#number-theory`, `#riemann-hypothesis`, `#research-verification`, `#cryptography`

---

<a id="item-tech-news-14"></a>
### [UK tribunal orders public hearing in Apple encryption case](https://appleinsider.com/articles/26/11/19/uk-cant-hide-that-it-tried-ordering-apple-to-allow-access-to-user-data) ⭐️ 7.0/10

A UK tribunal has reportedly ruled in Apple&\#x27;s favor, preventing the Home Office from keeping secret its demand that Apple provide access to encrypted iPhone data; most of the case will be heard publicly. The Home Office confirmed it issued a Technical Capability Notice \(TCN\) and said the measure was intended to bring criminals to justice. The tribunal found the government&\#x27;s national-security justification &quot;not realistic,&quot; according to the report.

telegram · zaihuapd · Nov 20, 04:13

**「Background」** A technical capability notice \(TCN\) is a secret UK order that can require a communications provider to take specified technical steps; the Home Office TCN at issue sought access to encrypted iPhone data. The Investigatory Powers Tribunal, which hears challenges to UK surveillance decisions, had already rejected the Home Office’s attempt to conceal the case’s existence in an April 2025 ruling, according to Winbuzzer.

**「What the ruling changes for UK users」** With the secrecy order rejected, the Home Office&\#x27;s technical capability notice becomes a matter of public record, giving UK users, security researchers and outside lawyers their first official confirmation that the government demanded access to encrypted iPhone data and a basis to contest its scope. Apple told TechCrunch it welcomes publication of the notice and reiterated that it has never built a backdoor or master key and never will, which means any move to satisfy the demand would surface as a visible change to its products rather than an undisclosed one.

<details><summary>References</summary>
<ul>
<li><a href="https://winbuzzer.com/2025/04/07/uk-court-rejects-secrecy-in-apples-icloud-encryption-dispute-with-the-uk-home-office-xcxwbn/">UK Court Rejects Secrecy in Apple ’s iCloud Encryption Dispute with...</a></li>
<li><a href="https://techcrunch.com/2026/11/19/u-k-government-forced-to-disclose-secret-apple-backdoor-order/">UK government forced to disclose secret Apple ... | TechCrunch</a></li>

</ul>
</details>

**Tags**: `#encryption`, `#privacy`, `#Apple`, `#UK surveillance`, `#legal/policy`

---

<a id="item-tech-news-15"></a>
### [U.S. House panel discloses 879,868 approved AI-chip exports to China](https://foreignaffairs.house.gov/news/press-releases/chairman-brian-mast-exercises-legislative-authority-to-publicly-release-ai-chip-license-information-for-china) ⭐️ 7.0/10

A U.S. House Foreign Affairs Committee disclosure shows that from December 2025 through May 2026 the U.S. government approved licenses for 879,868 Nvidia and AMD AI chips to China, including H200 and MI325X models, out of 3.444 million requested. Approved buyers include Tencent and ByteDance at 150,000 chips each; Alibaba, Kuaishou and Didi at 75,000 each; and miHoYo, Baidu and JD, according to the released documents. The committee highlighted that Alibaba, Tencent, Baidu and BYD appear on a U.S. list of companies linked to China&\#x27;s military, and that 21 cited approvals had not shipped as of May 11, so the approved volume does not represent delivered hardware.

telegram · zaihuapd · Nov 20, 04:25

**「Background」** Under U.S. export-control rules, advanced AI chips such as Nvidia’s H200 and AMD’s MI325X require government licenses before shipment to Chinese customers. The House Foreign Affairs Committee’s release covers approvals by the Trump administration between December 2025 and May 2026, according to Wccftech, and it distinguishes licensed volumes from actual exports.

**「Approvals Without Delivery」** For the named Chinese buyers — Tencent, ByteDance, Alibaba, Baidu and others — the licences do not translate into available compute: the committee found 21 approved licences still unshipped as of May 11, and Reuters reported that Beijing was withholding approval for large-scale H200 imports, so procurement plans depend on Chinese regulatory clearance as much as on U.S. licensing.

<details><summary>References</summary>
<ul>
<li><a href="https://wccftech.com/trump-administration-approved-nearly-900000-nvidia-amd-ai-chips-for-china/">Over 30% Of Approved U.S. AI Chips , Including NVIDIA ’s H 200 , Went...</a></li>
<li><a href="https://www.usnews.com/news/top-news/articles/2026-11-11/exclusive-pla-linked-chinese-university-bought-nvidia-h200-chips-despite-us-blacklist-records-show">Exclusive-Military-Linked Chinese University Bought Nvidia ...</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#export controls`, `#Nvidia`, `#AMD`, `#US-China tech policy`

---

<a id="item-tech-news-16"></a>
### [US chip curbs prompt India AI compute buildout](https://www.bloomberg.com/news/articles/2026-11-20/nvidia-scandal-fallout-india-ai-yotta-ambani-adani-am-intelligence-e2e-networks) ⭐️ 7.0/10

Bloomberg reports that US restrictions on advanced chip exports to Malaysia, Thailand, and Singapore are prompting India&\#x27;s AI sector to try to absorb spillover demand. Yotta says it plans to add about 100,000 GPUs over the next year, roughly a 10% increase over India&\#x27;s existing compute capacity. India currently has 153 data centers, ranking 14th globally, while Reliance has pledged up to $110 billion and Adani $100 billion for AI infrastructure. Those are announced commitments rather than completed capacity, and the sector has long been held back by compute infrastructure shortages and limited capital.

telegram · zaihuapd · Nov 20, 07:31

**「Background」** The shift comes amid a Trump administration proposal in mid-November 2026 to tighten overseas access to advanced AI chips, which rattled Southeast Asia because Chinese companies had been using the region&\#x27;s data centers to work around U.S. limits on Nvidia&\#x27;s most powerful chips. Malaysia then sought clarification from Washington on licensing requirements and on providing data-center services to third parties, underscoring the regional uncertainty that India&\#x27;s AI sector is trying to exploit.

**「Impact」** For Indian AI developers and startups, the nearer-term supply change is Yotta&\#x27;s plan to add about 100,000 GPUs over the next year—roughly a 10% increase in India&\#x27;s current compute—while the much larger Reliance and Adani pledges are broad infrastructure commitments rather than currently available capacity. Capacity planning should therefore treat Yotta&\#x27;s expansion as the near-term supply signal, not the corporate pledges.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/17/business/southeast-asia-china-ai-chips.html">Trump’s New A.I. Chip Rules Rattle Southeast Asia - The New York...</a></li>
<li><a href="https://www.freemalaysiatoday.com/category/nation/2026/11/18/malaysia-seeks-us-clarification-on-new-ai-chip-restrictions">Malaysia seeks US clarification on new AI chip restrictions | FMT</a></li>
<li><a href="https://www.linkedin.com/pulse/make-india-made-ai-next-chapter-indias-tech-ambition-ai4india-org-c4nuc">Make in India , Made for AI : The Next Chapter in India ’s Tech Ambition</a></li>
<li><a href="https://theoutpost.ai/news-story/adani-group-commits-100-billion-to-build-renewable-powered-ai-data-centers-across-india-by-2035-23846/">India AI Infrastructure Push Targets $200B by 2028</a></li>

</ul>
</details>

**Tags**: `#semiconductor export controls`, `#AI infrastructure`, `#India`, `#GPUs`, `#data centers`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Serving Inkling 2 Mini&\#x27;s Looped Layers on vLLM](https://vllm.ai/blog/2026-11-20-inkling2-mini) ⭐️ 7.0/10

rss · vLLM Blog · Nov 20, 00:00

**「Background」** Inkling 2 Mini is a 26B-total, 3.5B-active multimodal MoE whose middle 12 layers run three times per token with shared weights, making inference a repeated-state problem rather than a conventional single-pass transformer.

**「Solution」** Thinking Machines splits its 24 layers into a prelude \(0–5\), a three-pass loop core \(6–17\), and a coda \(18–23\); each core pass starts from the prelude output and reads 48 gated messages per token—four per core layer—from the previous pass via a learned attention-residual read and rank-64 controller. Because every pass keeps its own KV and conv-state cache, the model exposes 48 of each, and vLLM registers each extra pass as an ordinary attention layer so existing cache management and prefix caching apply unchanged. To avoid many tiny launches, vLLM reads all four messages of a layer in one attention-residual kernel, batches controller projections as GEMMs, uses Triton kernels to compute their RMS normalizations and fuse the FP32 gated merge into the sublayer RMSNorm, and generalizes Inkling 2 Small&\#x27;s fused sublayer kernels from hidden size 4,608 to 2,304. For the variable-loop research checkpoint, vLLM exposes pass-count and shared-KV options; on one GB200 at 4K context, the author reports batch-1 decode steps of 1.51, 2.67, and 3.85 ms for one, two, and three passes, with KV capacity falling from 352K to 233K to 175K tokens, while sharing the cache leaves step time roughly unchanged and frees less memory than dropping a pass.

**「Takeaway」** The article&\#x27;s larger claim is that looped models can fit existing serving infrastructure when each pass is treated as another cache-bearing layer and message handling is fused into established kernels, though the evidence remains a day-0, single-GPU vendor benchmark.

**Tags**: `#looped models`, `#vLLM`, `#KV cache`, `#kernel fusion`, `#LLM inference`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Fed Officials Speak More as Warsh Avoids Rate Guidance](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

Federal Reserve officials are publicly debating whether to raise rates faster while Chair Kevin Warsh avoids signaling future policy, CNBC reported Nov. 20. A Bank of America analysis found more Fed commentary in the prior two weeks than in any comparable period since early 2025, as Governor Christopher Waller raised the possibility of a half-percentage-point hike in December.

rss · CNBC Finance · Nov 20, 21:10

**「Background」** Warsh has argued that forward guidance—public signals about future policy—handcuffs policymakers; October meeting minutes showed some officials who favored a hike would have accepted a hold if markets clearly understood further tightening was likely.

**「Impact」** Bank of America economist Aditya Bhave said the public back-and-forth is producing undue rate volatility in already turbulent times, affecting investors who price Fed-sensitive assets.

**Tags**: `#Federal Reserve`, `#Monetary policy`, `#Forward guidance`, `#FOMC`, `#Interest rates`

---