---
layout: default
title: "Horizon Summary: 2026-11-21 (EN)"
date: 2026-11-21
lang: en
---

> From 28 items, 8 important content pieces were selected

---

**Technology News**
1. [Lean post claims Riemann Hypothesis formal proof, sparking checker-trust debate](#item-tech-news-1) ⭐️ 8.0/10
2. [Zhejiang University reports first QRAM run on a superconducting chip](#item-tech-news-2) ⭐️ 8.0/10
3. [GPGME vulnerability affects versions before 2.3.0; RCE severity disputed](#item-tech-news-3) ⭐️ 7.0/10
4. [Microsoft previews RDMA over USB4 for multi-PC local AI](#item-tech-news-4) ⭐️ 7.0/10
5. [OpenRouter Warns MiniMax Prompts May Have Been Read by Third Parties](#item-tech-news-5) ⭐️ 7.0/10

**Technology Blog**
1. [Why caching LLM outputs is low-leverage](#item-tech-blog-1) ⭐️ 7.0/10

**Financial News**
1. [TSMC Reportedly Halts 16nm-and-Below Orders From Chinese Firms](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed officials speak more as Warsh avoids guidance](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Lean post claims Riemann Hypothesis formal proof, sparking checker-trust debate](https://leanprover-community.github.io/blog/posts/riemann-hypothesis/) ⭐️ 8.0/10

A Lean community blog post dated Nov. 20, 2026 claims that Levent Alpöge released a Lean formalization of the Riemann Hypothesis running to about 17 million lines. The post says that on Nov. 21 the Lean FRO and Mathlib Initiative jointly certified the statement and proof as correct, that the statement matches Mathlib&\#x27;s RiemannHypothesis, and that the code compiles cleanly and passes multiple independent checkers. Those claims are not independently verified in the supplied material; they rest on the project&\#x27;s announcement and community checks.

hackernews · g-b-r · Nov 21, 14:36 · [Discussion](https://news.ycombinator.com/item?id=50589618)

**「Background」** Lean is a proof assistant that mechanically checks a formal proof against a small trusted kernel; Mathlib is the shared library that supplies definitions and theorem statements for such work. Because the check is only as meaningful as the statement being checked, the community’s comparison with Mathlib’s \`RiemannHypothesis\` and the use of independent checkers are central to interpreting the claim.

**「Impact」** If the claim holds, Lean users and mathematicians would gain a machine-checkable artifact for a major open problem, but its usefulness depends on auditing the exact formal statement and the trusted kernel/checker chain; the 17-million-line codebase makes broad human review impractical.

**「Community discussion」** Commenters treated the main residual risk as a bug or mismatch in the checking chain: one argued that compromising the result would now require a bug affecting multiple kernels and their consistency proofs, while another pointed to a fake Collatz refutation that previously passed an independent checker. Several also stressed that a human expert was in the loop and credited Alpöge with getting strong results from Claude, rather than treating the formalization as fully autonomous.

**Tags**: `#Lean`, `#formal verification`, `#Riemann Hypothesis`, `#AI for math`, `#proof assistants`

---

<a id="item-tech-news-2"></a>
### [Zhejiang University reports first QRAM run on a superconducting chip](https://finance.sina.com.cn/stock/2026-11-21/doc-iniznhsk3530826.shtml) ⭐️ 8.0/10

Zhejiang University researchers report the first real-hardware demonstration of quantum random access memory \(QRAM\), run on their self-fabricated superconducting chip &quot;Tianmu-2&quot; and published in Nature Physics. The chip ran prototypes that retrieved 4-bit and 8-bit data with accuracies of 80.9% and 60.4%, respectively, while using more than 30% less circuit depth than an unoptimized scheme. The team also reports the first validation of local noise resilience for this architecture and says its next step is scaling QRAM research.

telegram · zaihuapd · Nov 21, 08:31

**「Why QRAM matters」** QRAM is a quantum memory that lets a quantum algorithm fetch classical data in superposition, so many memory locations can be read out in a single query rather than one at a time. That capability is the assumed input model for speedups in algorithms such as Grover search and quantum linear-algebra routines, and the absence of a working device has been described as a data-access bottleneck for practical quantum computing.

**「Impact」** For quantum-computing developers, the reported 60.4% accuracy for 8-bit retrieval shows that this QRAM demonstration is a research prototype rather than a reliable memory component; integrating it into algorithms would require further error reduction or architectural changes. The reported circuit-depth reduction also makes compilation and circuit optimization a concrete lever for future QRAM experiments.

<details><summary>References</summary>
<ul>
<li><a href="https://thequbitreport.com/hardware/2026/06/06/zhejiang-university-achieves-breakthrough-with-worlds-first-superconducting-qram-prototype/">Zhejiang University Achieves Breakthrough with World’s First ...</a></li>

</ul>
</details>

**Tags**: `#quantum computing`, `#QRAM`, `#superconducting qubits`, `#hardware research`

---

<a id="item-tech-news-3"></a>
### [GPGME vulnerability affects versions before 2.3.0; RCE severity disputed](https://lists.gnupg.org/pipermail/gnupg-announce/2026q4/000517.html) ⭐️ 7.0/10

A security disclosure for GPGME states that all versions before 2.3.0 are affected, including when the library is used as a shared library, DLL, or statically linked. The bug was discovered by Johan Carlsson; GitLab notified the maintainers on 2026-11-12, and the issue was published on 2026-11-20 instead of the planned 2026-11-25 coordinated date because of the Ruby2Shell bug. The item is titled &quot;RCE in Gnupg,&quot; but commenters describe the defect as a double free rather than a confirmed remote-code-execution chain, so the RCE severity remains disputed.

hackernews · gdgghhhhh · Nov 21, 08:32 · [Discussion](https://news.ycombinator.com/item?id=50587208)

**「Background」** GPGME is the library that applications such as mail clients, XMPP clients, Samba and Gpg4win use to call GnuPG functions. The vulnerability, CVE-2026-129975, is a double free triggered when GPGME parses an OpenPGP key containing a crafted, very long user ID; GnuPG&\#x27;s advisory says updated Gpg4win, GnuPG Desktop and GnuPG VS-Desktop builds include the fix, while coverage places affected GPGME versions before 2.3.0, with one analysis listing 2.3.1 and 1.24.4 as fixed releases.

**「Who needs to rebuild」** Any application linking GPGME before 2.3.0 — mail and XMPP clients, Samba, Flatpak, Gpg4win and GnuPG Desktop — must move to GPGME 2.3.1, which closes CVE-2026-129975. Because affected software may link GPGME statically or ship it as a bundled DLL, replacing a system-wide shared library is not sufficient in every case; those builds need to be relinked against the fixed version.

**「Community Discussion」** Commenters added patch-history and scope caveats: one pointed to a Red Hat fix from about five years earlier that upstream missed, while another listed Gpg4win, GnuPG Desktop, most mail clients, many XMPP clients, Samba, and Flatpak as downstream users and asked whether package managers such as apt are unaffected. A separate commenter argued that developers should not write C/C++ without Rust-level tooling to prevent such bugs.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.ostorlab.co/gpgme-double-free-cve-2026-129975.html">GPGME Double Free: Data Theft, Possible RCE (CVE-2026-129975)</a></li>
<li><a href="https://lists.gnu.org/archive/html/info-gnu/2026-11/msg00006.html">GnuPG Security Advisory for GPGME (T8557,CVE-2026-129975)</a></li>
<li><a href="https://threatcluster.io/cluster/gnupg-warns-of-gpgme-double-free-flaw-cve-2026-129975-affect-9de35a20">GnuPG Warns of GPGME Double-Free Flaw (CVE-2026-129975 ...</a></li>
<li><a href="https://www.fosslinux.com/164437/gpgme-critical-bug-email-clients-flatpak.htm">GPGME Critical Bug: Update Email Clients and Flatpak Now</a></li>
<li><a href="https://lists.gnu.org/archive/html/info-gnu/2026-11/msg00006.html">GnuPG Security Advisory for GPGME (T8557,CVE-2026-129975)</a></li>

</ul>
</details>

**Tags**: `#security-vulnerability`, `#GPGME`, `#open-source`, `#cryptography`, `#coordinated-disclosure`

---

<a id="item-tech-news-4"></a>
### [Microsoft previews RDMA over USB4 for multi-PC local AI](https://videocardz.com/newz/microsoft-brings-rdma-over-usb4-to-windows-allowing-multiple-pcs-to-run-one-local-ai-model) ⭐️ 7.0/10

Microsoft has released a Windows developer preview of RDMA over USB4 that lets multiple PCs share memory and GPU resources to run a single local AI model over ordinary USB4 connections, without a dedicated network card or switch. In a demonstration, three AMD Ryzen AI Max+ 395 systems ran Qwen3-235B-A22B at 4-bit quantization at about 18.5 tokens per second. Microsoft says the preview will be distributed through Windows Insider.

telegram · zaihuapd · Nov 21, 06:13

**「Background」** RDMA, or remote direct memory access, lets one machine read and write another machine&\#x27;s memory with minimal CPU involvement; it is commonly used in data-center fabrics such as InfiniBand and RoCE. Local LLM inference is constrained by memory capacity and bandwidth, so pooling unified memory and GPU resources across separate PCs can let a model too large for one system run as a single job. Microsoft&\#x27;s preview applies that cluster approach to ordinary USB4 cables, connecting Windows 11 machines without dedicated network adapters or switches.

**「Impact」** For developers, the preview provides a way to run a model that exceeds one PC&\#x27;s memory by pooling several USB4-connected machines. Its scope remains limited: it is an early developer preview delivered through Windows Insider, and the published demonstration used specific Ryzen AI Max+ 395 hardware.

<details><summary>References</summary>
<ul>
<li><a href="https://www.goha.ru/microsoft-dobavila-v-windows-11-tehnologiyu-rdma-po-usb4-dlya-obedineniya-neskolkih-pk-v-edinyj-lokalnyj-ii-klaster-lWoPRN">Microsoft добавила в Windows 11 технологию RDMA по USB 4 для...</a></li>

</ul>
</details>

**Tags**: `#RDMA over USB4`, `#local AI inference`, `#distributed inference`, `#Windows`, `#USB4`

---

<a id="item-tech-news-5"></a>
### [OpenRouter Warns MiniMax Prompts May Have Been Read by Third Parties](https://news.ycombinator.com/item?id=50585962) ⭐️ 7.0/10

An OpenRouter email notice, reported on Hacker News, warned that prompts sent to MiniMax models may have been read by third parties. Security researchers sent prompts containing test URLs to MiniMax models between July and October 2026, and third parties accessed those URLs 40 to 130 hours later, according to the notice. OpenRouter attributed the issue to MiniMax and forwarding providers AtlasCloud, Novita and StreamLake, removed zero-data-retention labels from the affected endpoints, and advised users with sensitive credentials to change API keys and passwords. OpenRouter&\#x27;s website had not published a notice about the issue as of the report.

telegram · zaihuapd · Nov 21, 06:53

**「Background」** OpenRouter is a marketplace that routes each API request to a model and provider based on live availability and pricing, so users often do not choose the underlying inference host directly. MiniMax models on OpenRouter are served through third-party providers, including AtlasCloud, Novita and StreamLake, meaning prompt handling can depend on those intermediaries as well as MiniMax. The “zero data retention” label at issue refers to endpoints advertised as not retaining prompt data.

**「Impact」** Users who sent sensitive credentials in prompts to these MiniMax endpoints should rotate the affected API keys and passwords, and should not rely on the removed zero-data-retention designation for those routes.

<details><summary>References</summary>
<ul>
<li><a href="https://openrouter.ai/">OpenRouter</a></li>

</ul>
</details>

**Tags**: `#AI security`, `#data privacy`, `#OpenRouter`, `#MiniMax`, `#API`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Why caching LLM outputs is low-leverage](https://seangoedecke.com/why-output-caching-doesnt-work/) ⭐️ 7.0/10

rss · Sean Goedecke · Nov 21, 00:00

**「Background」** LLM inference economics already relies on caching model inputs in the KV cache so the entire conversation history need not be recomputed for every message. Sean Goedecke asks whether outputs should be cached similarly, since coding and research agents often repeat code snippets, evidence documents, and sample outputs in their visible replies.

**「Solution」** The author argues that this repetition is only a small part of what models generate. From his own agent histories, he estimates that visible output is about 6% of output tokens, while reasoning tokens account for roughly 50% and tool calls about 44%. Optimizing output caching therefore runs into Amdahl&\#x27;s law: even saving two-thirds of visible output, an admittedly optimistic estimate, would cut only about 4% of total output tokens. A caching scheme would require fine-tuning or prompting a model to emit references such as file ranges or conversation segments instead of repeating them, with the harness expanding those references transparently for the user. But that still targets only the visible slice; the larger opportunity is reducing invisible reasoning and tool-call tokens, which the author says depends largely on model intelligence and harness quality. Smarter models can need fewer reasoning and tool tokens, so a model that costs 5x more per token can be cheaper overall if it reaches the answer with 6x fewer tokens. The 6/50/44 split is anecdotal, and the author flags only moderate confidence about frontier chains of thought and uncertainty about repetition inside tool calls.

**「Takeaway」** Goedecke concludes that output caching is low-leverage because it addresses a small visible fraction of token output. The more promising route to lower LLM costs is reducing hidden reasoning and tool-call work, often by using more capable models despite their higher per-token prices.

**Tags**: `#LLM inference economics`, `#output caching`, `#token cost`, `#Amdahl&\#x27;s law`, `#AI agents`

---

## Financial News

<a id="item-finance-news-1"></a>
### [TSMC Reportedly Halts 16nm-and-Below Orders From Chinese Firms](https://appleinsider.com/articles/26/11/20/apple-supplier-tsmc-cuts-off-china-chip-orders-amid-tighter-export-controls) ⭐️ 8.0/10

TSMC has reportedly stopped accepting orders from Chinese companies for chips at 16nm and below, after tighter U.S. export rules began requiring prior U.S. licenses or exemptions instead of letting TSMC assess eligibility itself.

telegram · zaihuapd · Nov 21, 02:01

**「Background」** Because TSMC’s plants use U.S. chipmaking technology, Chinese customers need U.S. approval to make advanced chips there; under the tightened rules they must apply for a licence in advance rather than leaving the exemption check to TSMC.

**「Who is affected」** Chinese chip designers are left with only older 28nm and 40nm production and, according to the report, cannot use the high-bandwidth memory needed for AI data centers; TrendForce, citing the Financial Times, says the reported suspension may also extend to shipments for consumer electronics.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/16/us/politics/trump-china-ai-chip-loophole.html">Trump Administration Moves to Close A.I. Chip Loophole Ahead of...</a></li>
<li><a href="https://www.trendforce.com/news/2026/11/20/news-tsmc-samsung-reportedly-pause-china-consumer-chip-shipments-under-new-u-s-rules-16nm-orders-affected/">[News] TSMC, Samsung Reportedly Pause China Consumer Chip ...</a></li>

</ul>
</details>

**Tags**: `#semiconductors`, `#export controls`, `#TSMC`, `#China tech`, `#AI hardware`

---

<a id="item-finance-news-2"></a>
### [Fed officials speak more as Warsh avoids guidance](https://www.cnbc.com/2026/11/20/warsh-fed-forward-guidance-rate-hikes.html) ⭐️ 7.0/10

Federal Reserve officials are publicly airing competing views on raising rates as Chair Kevin Warsh avoids signaling future policy, and traders assign a 100% probability to at least a quarter-point hike in December, according to CME Group’s FedWatch.

rss · CNBC Finance · Nov 20, 21:10

**「Background」** Six months into the job, Warsh argues that guidance about future policy locks policymakers in before decisions; October minutes showed some officials who wanted a hike would have accepted a hold if markets clearly expected further tightening.

**「Impact」** Bank of America economist Aditya Bhave said the public back-and-forth is producing undue rate volatility, a complication for borrowers and investors trying to price Fed policy.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#FOMC communication`, `#forward guidance`

---