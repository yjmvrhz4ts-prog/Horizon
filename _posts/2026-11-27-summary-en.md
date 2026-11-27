---
layout: default
title: "Horizon Summary: 2026-11-27 (EN)"
date: 2026-11-27
lang: en
---

> From 34 items, 10 important content pieces were selected

---

**Technology News**
1. [OpenSec discloses 9.8-severity pre-auth NFS root flaw in Linux nfsd](#item-tech-news-1) ⭐️ 8.0/10
2. [Essay argues mainstream languages need formally verifiable foundations](#item-tech-news-2) ⭐️ 7.0/10
3. [Skimming scripts using WebRTC reportedly found on popular shopping sites](#item-tech-news-3) ⭐️ 7.0/10
4. [SemiAnalysis: Trainium3 Trades Blows With Nvidia GB300 on Inference Cost](#item-tech-news-4) ⭐️ 7.0/10
5. [Nadella concedes slower new-grad hiring as firms spend AI budgets first](#item-tech-news-5) ⭐️ 7.0/10
6. [Minecraft Bedrock resource-pack flaw affects 26.52–26.63, fixed in 26.65](#item-tech-news-6) ⭐️ 7.0/10

**Technology Blog**
1. [AI Detection Disputes Are Really About Gatekeeping Power](#item-tech-blog-1) ⭐️ 5.0/10

**Financial News**
1. [China State Council pushes stronger market-stabilization role for state-backed funds](#item-finance-news-1) ⭐️ 8.0/10
2. [PBOC lowers large-denomination CD purchase thresholds](#item-finance-news-2) ⭐️ 7.0/10
3. [China&\#x27;s Market Regulator Summons 15 E-Bike Makers Over Quality and Compliance](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [OpenSec discloses 9.8-severity pre-auth NFS root flaw in Linux nfsd](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec has disclosed CVE-2026-99362, a pre-authentication heap overflow in the Linux kernel&\#x27;s nfsd server rated CVSS 9.8. According to the advisory, an unauthenticated attacker can send a single connection to tcp/2049 to write out of bounds in the kernel heap and gain a root shell; the flaw has existed since Linux 3.16 in 2014 and affects servers running NFSv4.1 or 4.2, including file servers, NAS devices, and clustered storage nodes. Fixes are available in Linux 6.12.117, 6.18.61, 7.3.2, and 7.4-rc1, requiring a kernel upgrade and reboot, while systems that cannot be upgraded immediately should restrict tcp/2049 access at the firewall. The CVE was made public on November 20, 2026, but the notice provides no further technical detail and cites no independent validation.

telegram · zaihuapd · Nov 27, 12:57

**「Background」** The flaw is an out-of-bounds write in nfsd&\#x27;s SEQUENCE-reply handling; the fix preflights those replies before accepting a slot \(tool-2-3\). Red Hat rates the issue critical because an unauthenticated remote or network-adjacent attacker can corrupt kernel heap memory, potentially achieving remote code execution or causing a kernel panic, while its default configurations do not run the in-kernel nfsd, limiting exposure there \(tool-2-1\).

**「Patch and exposure」** Operators of affected nfsd servers should upgrade to a fixed kernel release and reboot; for systems that cannot be patched immediately, restricting access to tcp/2049 is a stopgap against remote exploitation. Because the flaw is reachable before authentication, Internet-exposed NFS services carry the highest immediate risk.

<details><summary>References</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99362">CVE-2026-99362 - Red Hat Customer Portal</a></li>
<li><a href="https://www.ox.security/ox-radar/cve/CVE-2026-99362/">CVE-2026-99362: kernel: kernel: Out-of-bounds write in nfsd ...</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99362">CVE-2026-99362 - Red Hat Customer Portal</a></li>
<li><a href="https://watchtowr.com/intelligence/nfs2root-linux-nfs-cve-2026-99362-faq/">NFS2ROOT (CVE-2026-99362) FAQ: Linux NFS Exposure and Fix</a></li>

</ul>
</details>

**Tags**: `#Linux kernel`, `#NFS`, `#CVE`, `#security vulnerability`, `#remote exploit`

---

<a id="item-tech-news-2"></a>
### [Essay argues mainstream languages need formally verifiable foundations](https://blainehansen.me/post/mainstream-verifiable-language/) ⭐️ 7.0/10

An essay by Blaine Hansen argues that mainstream programming languages need formally verifiable foundations, making verification part of the language rather than an external add-on. The item is a design argument aimed at language designers and working developers; it does not announce a new language, compiler, or shipped verification tool.

hackernews · todsacerdoti · Nov 27, 05:22 · [Discussion](https://news.ycombinator.com/item?id=50663089)

**「Background」** Formal verification means proving that a program satisfies a mathematical specification rather than relying only on tests. Ada SPARK, discussed in the comments, is an existing Ada subset with contracts and proof tools; its Silver level is intended to establish the absence of runtime errors.

**「Impact」** For language designers, the discussion identifies two practical requirements: a verifiable language must let users check that specifications match intended behavior, and it must remain usable as specifications and code grow. Developers can examine Ada SPARK as an existing approach, but the thread offers no evidence that its workflow generalizes to a mainstream language.

**「Community discussion」** Commenters disagreed about whether formal verification addresses the practical problem: socketcluster argued that it validates code against a specification but cannot validate the specification against reality, and that conflicts grow with complexity, while markhermeling reported success translating C repositories to Ada SPARK and finding integer overflows. ianjbutler argued for incremental adoption by programming more directly with formal concepts such as automata and process algebras rather than waiting for a unified language.

**Tags**: `#formal verification`, `#programming languages`, `#software correctness`, `#Ada SPARK`, `#formal methods`

---

<a id="item-tech-news-3"></a>
### [Skimming scripts using WebRTC reportedly found on popular shopping sites](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

Credit card skimming scripts that abuse WebRTC were reportedly found on popular shopping sites, according to an InfoHawk report dated November 27, 2026 and discussed on Hacker News. The supplied item does not include the article body, so the affected sites, the scale of any data exposure, and the precise mechanism are not confirmed here. The finding is framed around third-party scripts embedded in e-commerce pages as the exposure path.

hackernews · scanr · Nov 27, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50668145)

**「How checkout skimmers work」** Card-skimming scripts are malicious JavaScript injected into checkout pages, often through third-party code such as marketing pixels or consent-management tools, to capture payment details as shoppers enter them. WebRTC is a browser API for real-time data channels, which can give attackers an exfiltration path that differs from ordinary HTTP requests. Reports say the skimmer in this campaign was planted on Lascana, Samsonite, American Tourister, Revolve, and FWRD in the week before Black Friday, delivered via a consent-banner setting and a marketing pixel, appeared to target mobile devices, and was activated by the server on checkout pages.

**「Exposure for checkout pages」** The exposure falls on merchants whose checkout pages load third-party scripts, because Magecart-style skimming works by inserting a few lines of JavaScript into a checkout page that capture payment data in real time and forward it to an attacker-controlled server, with payment gateways and chat widgets among the common injection routes. The concrete action for site owners is to inventory which external scripts execute on payment pages and which outbound destinations they are permitted to reach; the supplied item does not name the affected shops or say how many sites carried the scripts, so the scope of this specific campaign is unconfirmed.

**「Community discussion」** Commenters pushed back on treating WebRTC as the root cause: afavour argued the technique is simply less frequently monitored for abuse, could be implemented with ordinary HTTP requests, and that embedding third-party scripts is the underlying vulnerability, while kevsamuel said normal AJAX or a cross-domain POST would work and speculated that a missing WebRTC entry in a site&\#x27;s connect-src CSP might be involved. Other commenters used the report to argue for ad blocking \(jszymborski\) or against allowing sites to run arbitrary third-party code in the browser \(snickerer\).

<details><summary>References</summary>
<ul>
<li><a href="https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer">Credit card skimming scripts using WebRTC found on popular ...</a></li>
<li><a href="https://daily.dev/posts/credit-card-skimming-scripts-using-webrtc-found-on-popular-shopping-sites-mr8zgdbaf">Credit card skimming scripts using WebRTC found on...</a></li>
<li><a href="https://thehackernews.com/2019/03/magecart-ecommerce-hackers.html">New MageCart Attacks Target Bedding Retailers My Pillow and...</a></li>
<li><a href="https://www.reflectiz.com/blog/magecart-attack-disguised-gtm/">Magecart attack wears GTM disguise – Reflectiz</a></li>

</ul>
</details>

**Tags**: `#web security`, `#credit card skimming`, `#WebRTC`, `#third-party scripts`, `#e-commerce`

---

<a id="item-tech-news-4"></a>
### [SemiAnalysis: Trainium3 Trades Blows With Nvidia GB300 on Inference Cost](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis published a microarchitecture and inference benchmark analysis arguing AWS Trainium3 can match or beat Nvidia&\#x27;s GB300 on cost per generated token, and trails only Nvidia&\#x27;s Vera Rubin across the full throughput-versus-latency frontier. The report attributes part of the advantage to design rather than AWS&\#x27;s supply chain: Trainium is built around tiles as a first-class primitive, and its Descriptor Generation Engines \(DGE\) — the counterpart to Nvidia TMA and AMD MI455X TDM — reached peak HBM bandwidth utilization at small message sizes in SemiAnalysis&\#x27;s microbenchmarks, which the authors say is not achievable on Nvidia GPUs. The measurements come from the firm&\#x27;s own UBenchX suite \(cycle-level SRAM scratchpad latency and bandwidth from SBUF to PSUM, rack-scale bandwidth and latency, attention exponential tests, and per-shape latency including attention head\_dim effects\) and from AgentX, which replays real coding-agent sessions against a Trainium3 server; Trainium3 running with PDS plus vLLM led the perf-per-TCO curve. SemiAnalysis says AWS Annapurna Labs co-founder Nafea Bshara and Trainium chief architect Ron Diamant helped validate the experiments, so these are vendor-assisted benchmarks rather than independent third-party results, and the supplied excerpt is truncated before the full data and methodology are shown.

rss · Semianalysis · Nov 27, 15:54

**「Tiles versus GPU-evolved AI hardware」** Nvidia&\#x27;s datacenter GPUs descend from graphics processors, with each recent generation adding AI-specific hardware to address the previous bottleneck: Volta introduced Tensor Cores, Hopper added TMA for tile movement between HBM and SRAM, and Blackwell added Tensor Memory for accumulation. Trainium instead treats tiles as a first-class primitive rather than layering tensor compute and data-movement engines onto a sea of threads, an approach SemiAnalysis says previously made software a major challenge but no longer does.

**「What it means for serving teams」** Because SemiAnalysis reports Trainium3 running through vLLM and landing on the better side of the perf-per-TCO frontier against every accelerator except Vera Rubin, teams doing token-cost comparisons for agentic coding workloads now have a reason to put Trainium3 in the bake-off rather than assuming Nvidia pricing. The practical caveat is that these figures come from a vendor-assisted microbenchmark suite \(UBenchX\) and replayed agent sessions \(AgentX\) rather than independent production traces, so an operator should reproduce the throughput-latency frontier on its own model and concurrency mix before treating the cost gap as bankable.

**Tags**: `#AWS Trainium`, `#AI accelerators`, `#inference`, `#microarchitecture`, `#Nvidia`

---

<a id="item-tech-news-5"></a>
### [Nadella concedes slower new-grad hiring as firms spend AI budgets first](https://www.windowslatest.com/2026/11/27/lets-add-the-next-human-satya-nadella-admits-new-grad-hiring-slowed-as-companies-rebuild-around-ai-and-says-every-company-will-add-its-next-person-after-it-burns-through-its-ai-budget/) ⭐️ 7.0/10

Speaking on The Pragmatic Engineer podcast, Microsoft CEO Satya Nadella acknowledged that new-grad hiring has slowed, saying the company first moves existing employees into open roles and only afterward backfills with new hires; he added that AI-native companies will &quot;burn through their AI budget first, then hire the next human,&quot; and that every company will eventually follow that pattern. The remarks, reported by Windows Latest and relayed here through a secondary Telegram summary, come as Microsoft&\#x27;s workforce fell to 223,000 as of June 30, a reduction of roughly 5,000 over the year and the company&\#x27;s first annual decline since 2016. Coverage also cites a paper from MIT and Microsoft Research finding that firms adopting GitHub Copilot cut quarterly technical hiring by 29%, with entry-level positions most affected, though the study&\#x27;s methodology and scope were not detailed in the source.

telegram · zaihuapd · Nov 27, 03:03

**「Background」** Earlier this year at Davos, Nadella said he still believed in campus recruiting, a position his new remarks qualify. Microsoft’s headcount had already fallen to 223,000 by June 30, down 5,000 over the year and the first annual decline since 2016; the source also cites an MIT and Microsoft Research paper finding that companies adopting GitHub Copilot cut quarterly technical hiring by 29%, with entry-level roles hit hardest.

**「Tighter entry-level pipeline」** New-grad applicants face a smaller pool of openings: Microsoft ended fiscal 2026 with 223,000 full-time employees as of June 30, down 5,000 \(about 2%\) year over year and the first annual decline since 2016, according to its regulatory filing. The MIT–Microsoft Research paper cited in the report ties Copilot adoption to a 29% drop in quarterly technical hiring, with junior roles hardest hit, and roughly 4,800 cuts reported for July fall outside that June 30 headcount — so candidates should plan for the recruiting base to shrink further before it stabilizes.

<details><summary>References</summary>
<ul>
<li><a href="https://stockanalysis.com/stocks/msft/employees/">Microsoft (MSFT) Number of Employees 1990-2026 - Stock Analysis</a></li>
<li><a href="https://www.seattletimes.com/business/microsoft/microsofts-head-count-falls-for-first-time-in-a-decade/">Microsoft’s head count falls for first time in a decade</a></li>
<li><a href="https://hiringforecast.com/microsoft-employee-headcount-2026-10-k">Microsoft Employee Headcount 2026 (10-K vs 4,800 Cuts)</a></li>

</ul>
</details>

**Tags**: `#AI labor impact`, `#Microsoft`, `#tech hiring`, `#entry-level jobs`, `#GitHub Copilot`

---

<a id="item-tech-news-6"></a>
### [Minecraft Bedrock resource-pack flaw affects 26.52–26.63, fixed in 26.65](https://www.zaikei.co.jp/article/20261119/878386.html) ⭐️ 7.0/10

A resource-pack vulnerability in Minecraft Bedrock allowed packs containing a content.zipe file to alter files in the Ore UI interface framework and run hidden scripts. 8Crafter disclosed the issue on Reddit on November 15 and said it confirmed impact on versions 26.52 through 26.63, with earlier versions possibly affected; it covers PC, mobile and console, while Java Edition is not affected. When resource-pack auto-download is enabled, players joining a server or Realm could receive a malicious pack without manually installing it; listed exploits include deleting all saves and obtaining the player&\#x27;s IP, and on Windows under specific conditions silently opening an arbitrary URI or launching a batch file in the pack to download malware. Mojang fixed the issue in version 26.65, and AxmBro released a read-only Windows detection tool that finds content.zipe but cannot determine whether a pack is malicious.

telegram · zaihuapd · Nov 27, 18:04

**「Why resource packs can carry the payload」** Bedrock Edition lets servers and Realms push resource packs — packages normally used for textures, sounds and interface assets — to clients automatically when the player has auto-download enabled, so a pack can arrive without any manual install step. The affected packages abused that path to alter files in Ore UI, the game&\#x27;s interface framework; Java Edition uses a separate pack and interface stack, which the reporter says is not affected.

**「Impact」** Players and server operators using resource-pack auto-download should update clients to 26.65 or disable automatic downloads, since the available detector can only find content.zipe and cannot establish whether a pack is malicious.

**Tags**: `#Minecraft Bedrock`, `#security vulnerability`, `#resource packs`, `#malware`, `#gaming`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [AI Detection Disputes Are Really About Gatekeeping Power](https://seangoedecke.com/who-gets-to-decide-if-something-is-written-by-ai/) ⭐️ 5.0/10

rss · Sean Goedecke · Nov 27, 00:00

**「Background」** Every day brings disputes over whether writing, a tweet, or a prize-winning story was AI-generated, often centered on the detection tool Pangram. Sean Goedecke argues that arguments about reliability and ethics sit downstream of a deeper conflict over who gets to decide.

**「Solution」** His central claim is that this is a question of power: who may gatekeep literary prizes, grades, and public discourse. He sympathetically reconstructs the anti-Pangram view: if AI threatens public spaces by concentrating social power in tech, then making another tech company the arbiter is not reassuring; distrust also reflects a broader shift from messy community processes to legible, tool-based ones. Goedecke nonetheless supports Pangram because the only alternative is community self-policing, which he considers worse: people who avoid AI are poor at recognizing its tells, and skilled AI writing can produce drafts and other hallmarks of human work, while ordinary investigation and cryptographic attestation offer no reliable path. He therefore urges AI skeptics who want to protect human arenas to use the strongest detection tools, ideally open-source or government-built, rather than leave judgment to the community. He acknowledges a reader&\#x27;s concern about false positives from flawed or dishonest AI tools.

**「Takeaway」** The essay&\#x27;s broader point is that disputes over AI provenance cannot be settled by detection alone; they are contests over institutional authority, and refusing tooling cedes that authority to informal community judgment that the author believes will misclassify more often.

**Tags**: `#AI detection`, `#AI-generated content`, `#trust and governance`, `#community moderation`, `#Pangram`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China State Council pushes stronger market-stabilization role for state-backed funds](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 8.0/10

China’s State Council executive meeting on Nov. 27 called for stronger use of state-backed “national team” investors to stabilize the stock market and for further improving Central Huijin’s function as a quasi market-stabilization fund. It also urged listed companies to increase dividends and buybacks and said support policies for insurers, enterprise annuity funds and social security funds to invest in stocks should be improved.

telegram · zaihuapd · Nov 27, 05:35

**「背景」** “国家队”主要指中央汇金公司等国有持股机构，而“类‘平准基金’”指其以增持股票等方式向市场注入流动性、平抑波动的托市职能；此次国常会要求优化的正是这一职能。

**Tags**: `#国常会`, `#资本市场政策`, `#中央汇金`, `#平准基金`, `#中长期资金`

---

<a id="item-finance-news-2"></a>
### [PBOC lowers large-denomination CD purchase thresholds](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

China&\#x27;s central bank published new rules for large-denomination certificates of deposit on Nov. 27, lowering the minimum individual purchase threshold to 100,000 yuan from 200,000 yuan and the institutional threshold to 5 million yuan from 10 million yuan, effective March 21, 2027.

telegram · zaihuapd · Nov 27, 11:36

**「Background」** The new rules replace 2015 interim measures that had set the previous thresholds and take effect alongside a separate PBOC regulation requiring financial institutions to set deposit and loan rates independently and banning improper tactics such as high-interest deposit-taking.

**「Impact」** From March 2027, households with 100,000 to 200,000 yuan will meet the individual minimum and become eligible to buy these fixed-term bank deposits.

**Tags**: `#央行监管`, `#大额存单`, `#存款利率`, `#零售银行`, `#中国金融政策`

---

<a id="item-finance-news-3"></a>
### [China&\#x27;s Market Regulator Summons 15 E-Bike Makers Over Quality and Compliance](https://www.news.cn/20261127/0c8c665ce70c417b9263b39fa8a519f0/c.html?hl=zh-CN) ⭐️ 7.0/10

On November 27, China&\#x27;s State Administration for Market Regulation \(SAMR\) held a group supervisory meeting with 15 electric-bicycle makers, including Yadea, Tailg, Aima, Ninebot and Niu. The regulator said recent full-coverage spot checks of CCC certification found some firms lacked quality-assurance capacity, poorly controlled product consistency, and shipped substandard products in violation of mandatory national standards. It ordered the companies to step up rectification, strictly apply the &quot;one vehicle, one battery, one charger, one code&quot; rule, stop shifting responsibility to consumers or misleading them into riding unregistered vehicles, and immediately recall products confirmed defective.

telegram · zaihuapd · Nov 27, 12:06

**「Background」** The 15 companies are subject to CCC \(China Compulsory Certification\), a mandatory product-safety approval, and to mandatory national standards; regulators use surprise inspections to check whether factory output matches certified designs.

**「Impact」** Owners of the affected brands&\#x27; e-bikes could be required to return vehicles for recall if a defect is confirmed, while the companies face tighter scrutiny of their certification and factory quality controls.

**Tags**: `#电动自行车监管`, `#产品质量`, `#CCC认证`, `#企业约谈`, `#消费者权益`

---