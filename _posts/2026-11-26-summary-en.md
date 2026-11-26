---
layout: default
title: "Horizon Summary: 2026-11-26 (EN)"
date: 2026-11-26
lang: en
---

> From 43 items, 9 important content pieces were selected

---

**Technology News**
1. [FCC Approves SpaceX&\#x27;s 1 Million-Satellite Starmind Data Center Constellation](#item-tech-news-1) ⭐️ 8.0/10
2. [Minipg packages PostgreSQL as a single CLI-friendly executable](#item-tech-news-2) ⭐️ 7.0/10
3. [Google&\#x27;s Workspace MCP Servers Reportedly Omit Gmail Sending](#item-tech-news-3) ⭐️ 7.0/10
4. [Huawei to Present HBM Paper Claiming Double Data-Pin Density](#item-tech-news-4) ⭐️ 7.0/10
5. [Neuralink gets FDA clearance for pivotal ALS brain-implant trial](#item-tech-news-5) ⭐️ 7.0/10
6. [ASML CEO warns full China export cutoff would spur domestic tools](#item-tech-news-6) ⭐️ 7.0/10

**Financial News**
1. [Chip exports overtake oil and gas in global trade, Deutsche Bank says](#item-finance-news-1) ⭐️ 8.0/10
2. [Nvidia Halts AI Server Shipments to Four Southeast Asian Countries](#item-finance-news-2) ⭐️ 8.0/10
3. [荷兰大臣称不接受美国限制 ASML 对华销售的法案](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [FCC Approves SpaceX&\#x27;s 1 Million-Satellite Starmind Data Center Constellation](https://www.geekwire.com/2026/fcc-clears-spacex-million-satellites-starmind-data-center/) ⭐️ 8.0/10

The FCC has approved SpaceX to deploy up to 1 million satellites for Starmind, an in-orbit data-processing network, at altitudes of 500 to 1,002 km. The agency said it is the first US authorization for a space data-center constellation. The approval requires communications backup, periodic progress reports, and a detailed orbital-debris mitigation plan; the first satellite must be operational by 2033 and the full constellation by 2040. The FCC rejected objections from Amazon, Viasat, and the American Astronomical Society.

telegram · zaihuapd · Nov 26, 04:45

**「Background」** Starmind is SpaceX&\#x27;s proposed in-orbit data-processing network, meaning the satellites would handle computing tasks in space rather than only relay communications. The FCC&\#x27;s release describes the action as the first U.S. authorization for a constellation of data centers in space, a regulatory category distinct from a conventional satellite communications license.

**「Impact」** SpaceX gains the regulatory basis to build Starmind, but the 2033 first-satellite deadline, 2040 full-constellation deadline, and debris-mitigation conditions mean the approval does not establish that the full network will be deployed on schedule.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.fcc.gov/public/attachments/DOC-427572A1.pdf">FCC Authorizes 1 Million Satellites for Data Centers in Space</a></li>

</ul>
</details>

**Tags**: `#FCC approval`, `#SpaceX`, `#space data centers`, `#satellite constellations`, `#orbital debris`

---

<a id="item-tech-news-2"></a>
### [Minipg packages PostgreSQL as a single CLI-friendly executable](https://progrium.github.io/minipg/) ⭐️ 7.0/10

Minipg packages PostgreSQL as a single, CLI-friendly executable aimed at self-hosted and lightweight deployments that want a SQLite-like command-line database rather than an embedded library. A commenter describes it as running the Alpine PostgreSQL Docker image without Docker, using the h9 embedded hypervisor. In the discussion, the creator says Minipg is about the CLI-friendly database model and that PGlite, while appealing, only runs in single-connection mode, which did not fit the motivating problem. Commenters compare it with PGlite and embedded-postgres, noting those options already cover many embedded, in-process, and test use cases.

hackernews · rguiscard · Nov 26, 03:00 · [Discussion](https://news.ycombinator.com/item?id=50650892)

**「How minipg works」** Minipg embeds Docker Hub&\#x27;s \`postgres:18-alpine\` image and runs it with h9, a Zig library; h9&\#x27;s Linux personality runs Alpine&\#x27;s own Postgres binaries directly on the host hypervisor, with a Plan 9 kernel answering system calls and without a Linux kernel, VM image, or Docker \(\`tool-1-1\`\). The author positions it for local, single-user programs where SQLite would fit but Postgres is needed, rather than cloud, replica, or many-connection deployments \(\`tool-1-3\`\).

**「What it means for adopters」** For developers weighing a single-binary Postgres, the constraint to check first is connection concurrency: the author notes that PGlite, built on PostgreSQL&\#x27;s single-user mode, runs in single-connection mode, so an application that issues another query while inside a transaction cannot simply swap in PGlite and must look at a fork-per-connection approach like Minipg instead. Because Minipg runs PostgreSQL via the young h9 embedded hypervisor rather than Docker, teams adopting it are also taking on a less-established runtime dependency than either PGlite or the download-a-native-binary embedded-postgres packages.

**「Community discussion」** Commenters questioned the niche: one argued that PGlite and embedded-postgres already cover most “SQLite-style PostgreSQL” needs without a hypervisor layer, while another saw value for small self-hosted apps but said a real server is not ideal there and that Podman with official images suffices for unit tests. The creator responded that Minipg targets the CLI-friendly database use case rather than the embedded-library model, and that PGlite’s single-connection limitation was relevant to the original problem.

<details><summary>References</summary>
<ul>
<li><a href="https://progrium.github.io/minipg/">minipg: PostgreSQL as a single executable - progrium.github.io</a></li>
<li><a href="https://progrium.xyz/articles/2026/single-binary-postgres">How I Got Postgres into a Single Binary · progrium</a></li>
<li><a href="https://github.com/electric-sql/pglite">GitHub - electric-sql/pglite: Embeddable Postgres with real ...</a></li>

</ul>
</details>

**Tags**: `#PostgreSQL`, `#embedded databases`, `#single-binary deployment`, `#database tooling`, `#open source`

---

<a id="item-tech-news-3"></a>
### [Google&\#x27;s Workspace MCP Servers Reportedly Omit Gmail Sending](https://techstackups.com/articles/google-workspace-ai-agents-mcp/) ⭐️ 7.0/10

Google is reportedly exposing Google Workspace capabilities to AI agents through MCP servers, but the Gmail integration apparently cannot send email. The reported setup would let developers connect agents to Workspace services via MCP, with outbound email standing out as a missing Gmail capability. The limitation is central to the report and to concerns about how agents complete email workflows.

hackernews · ritzaco · Nov 26, 09:44 · [Discussion](https://news.ycombinator.com/item?id=50653477)

**「Background」** MCP is a standard interface that lets AI agents invoke external tools and data sources, so a Gmail MCP server defines which mailbox operations an agent can perform instead of requiring a custom integration for each client. Google&\#x27;s developer documentation lists search, thread retrieval, and label listing for its Gmail MCP server, while a third-party overview reports that a public developer preview adds drafting and some read/write actions.

**「Impact」** Developers building agents that need to send email cannot complete that step through the Gmail MCP integration and would need a separate API or another workaround.

**「Community discussion」** Commenters questioned whether withholding Gmail sending is a safety measure or a competitive decision; one argued that MCP&\#x27;s elicitation primitive already allows a server to pause for human confirmation, making a partner-only send tool look like business lock-in, while another suggested it protects Gemini&\#x27;s native Workspace integration. Others predicted agents would fall back to browser automation, which they described as messy and wasteful.

<details><summary>References</summary>
<ul>
<li><a href="https://developers.google.com/workspace/gmail/api/guides/configure-mcp-server">Configure the Gmail MCP server | Google for Developers</a></li>
<li><a href="https://www.getmailbird.com/ai-email-agents-what-they-can-actually-do-today/">AI Email Agents : What They Can Actually Do Today | Mailbird</a></li>

</ul>
</details>

**Tags**: `#Google Workspace`, `#MCP`, `#AI agents`, `#Gmail`, `#platform strategy`

---

<a id="item-tech-news-4"></a>
### [Huawei to Present HBM Paper Claiming Double Data-Pin Density](https://www.bloomberg.com/news/articles/2026-11-26/huawei-teases-next-gen-ai-memory-chip-to-take-on-samsung-hynix) ⭐️ 7.0/10

Huawei plans to present a research paper in February at a conference in San Francisco describing a next-generation high-bandwidth memory chip, according to Bloomberg. The paper&\#x27;s title states that the part&\#x27;s data-pin density is twice that of mass-production HBM from Samsung and SK Hynix, which in theory would substantially increase memory bandwidth. Huawei is also pushing to manufacture HBM inside China, where the component is restricted by US sanctions. No product, sampling timeline, yields, capacity figures, or independent measurements were disclosed; the claim currently rests on a paper title and a future presentation.

telegram · zaihuapd · Nov 26, 05:30

**「Background」** HBM stacks DRAM dies and connects them through a wide, high-density interface, so data-pin density is a key indicator of the bandwidth a memory package can potentially deliver. Huawei is pursuing domestic Chinese production of HBM, a component subject to US sanctions, and the reported disclosure is a research paper scheduled for a February conference rather than a commercial product launch.

**「Impact」** Because only a paper title and a scheduled February presentation have been disclosed, hardware planners have no yield, capacity, or sampling data with which to judge whether Huawei&\#x27;s HBM could substitute for Samsung or SK Hynix parts. Huawei&\#x27;s stated effort to produce HBM domestically also faces US sanctions that restrict access to the relevant equipment and components.

**Tags**: `#HBM`, `#Huawei`, `#semiconductor memory`, `#AI hardware`, `#US sanctions`

---

<a id="item-tech-news-5"></a>
### [Neuralink gets FDA clearance for pivotal ALS brain-implant trial](https://www.bloomberg.com/news/articles/2026-11-25/neuralink-gets-clearance-for-brain-implant-trial-in-als-patients?srnd=phx-technology) ⭐️ 7.0/10

Neuralink said the FDA has cleared its LINK pivotal U.S. clinical trial of an implanted brain-computer interface in ALS patients. The trial is intended to translate brain signals directly into computer-control commands, and Neuralink describes it as the first U.S. pivotal trial of its kind; its data are meant to support a future medical-device marketing approval. Neuralink said earlier studies had implanted its device in more than 30 paralyzed patients worldwide. The announcement did not disclose enrollment targets, trial sites, timing, or results.

telegram · zaihuapd · Nov 26, 07:15

**「Background」** A pivotal trial is the late-stage study regulators use to determine whether a medical device&\#x27;s benefits outweigh its risks, and its data typically form the core of a marketing application. Neuralink had previously implanted its device in more than 30 paralyzed patients through early research, but those studies were aimed at safety and feasibility rather than approval.

**Tags**: `#Neuralink`, `#brain-computer interface`, `#FDA approval`, `#ALS`, `#clinical trials`

---

<a id="item-tech-news-6"></a>
### [ASML CEO warns full China export cutoff would spur domestic tools](https://www.semafor.com/article/11/25/2026/asml-makes-the-case-for-selling-chips-to-china) ⭐️ 7.0/10

ASML CEO Christophe Fouquet said on Semafor&\#x27;s Future Proof program that export controls should protect the most advanced technology but should not exclude China entirely, warning that a full cutoff would push China to double or triple investment in its own lithography tools. He said ASML equipment sold to China is more than a decade behind the most advanced processes, and that preserving that gap has kept China dependent on Western equipment; he noted ASML has held close to 100% of China&\#x27;s lithography market over the past 30 years. The remarks come as the U.S. pushes the MATCH Act, which would extend controls from EUV to immersion DUV and maintenance services. Both the Dutch government and ASML oppose that expansion; Fouquet&\#x27;s position is a public argument, not a change in export policy.

telegram · zaihuapd · Nov 26, 12:19

**「Earlier export-control baseline」** Existing U.S. and Dutch export controls already keep ASML&\#x27;s most advanced EUV lithography systems out of China, and the proposed MATCH Act would widen the restrictions to cover immersion DUV machines and maintenance services as well. According to Fu Kai&\#x27;s remarks, ASML has held close to a 100% share of the Chinese lithography market for roughly 30 years, so an expansion of controls would reach a customer base built on long-standing dependence on Western tools rather than only future leading-edge purchases.

**「Impact」** If the MATCH Act&\#x27;s proposed expansion were enacted, Chinese chipmakers would face restrictions covering immersion DUV tools and maintenance services, not just EUV, extending the policy&\#x27;s reach to servicing installed equipment as well as new purchases. ASML&\#x27;s argument is that such a step would weaken the dependence created by selling tools that lag the leading edge by more than a decade.

**Tags**: `#export-controls`, `#semiconductors`, `#ASML`, `#China`, `#lithography`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Chip exports overtake oil and gas in global trade, Deutsche Bank says](https://www.cnbc.com/2026/11/26/semiconductor-chips-are-the-new-oil-heres-why.html) ⭐️ 8.0/10

Semiconductor exports overtook oil and gas in global trade value for the first time in the January–March 2026 quarter, reaching about $1.61 trillion versus $1.53 trillion on a four-quarter rolling basis, according to a Deutsche Bank analysis of International Trade Centre data.

rss · CNBC Finance · Nov 26, 17:52

**「Background」** The &quot;petrodollar&quot; label describes how oil-exporting countries historically recycled trade surpluses into U.S. Treasuries and other bonds, helping finance U.S. deficits. Deutsche Bank&\#x27;s Jim Reid argues that because Asia&\#x27;s semiconductor-surplus economies are more closely tied to U.S. tech companies, some chip-export earnings could flow back into U.S. technology stocks, startups and data centers.

**「Impact」** Deutsche Bank&\#x27;s Jim Reid suggests that, unlike oil exporters who recycled surpluses into U.S. Treasuries, Asia&\#x27;s chip-surplus economies are more closely tied to U.S. tech companies, so some chip earnings could flow into U.S. technology stocks, startups and data centers — a shift he says could bring &quot;structurally higher yields&quot; on corporate and government debt.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Petrodollar_recycling">Petrodollar recycling - Wikipedia</a></li>

</ul>
</details>

**Tags**: `#semiconductors`, `#global trade`, `#AI investment`, `#market volatility`, `#macro-financial flows`

---

<a id="item-finance-news-2"></a>
### [Nvidia Halts AI Server Shipments to Four Southeast Asian Countries](https://www.ft.com/content/7838a715-07d4-4605-aa60-21f5af2b2370) ⭐️ 8.0/10

Nvidia has told major manufacturing partners to suspend AI-server shipments to Malaysia, Singapore, Thailand and Indonesia, with assemblers including Dell and Supermicro notifying buyers in those countries that orders cannot leave their factories, the Financial Times reported, citing three people familiar with the matter. The reported freeze, which the companies have not publicly confirmed, is linked to a new round of U.S. export controls announced last week that require regional cloud providers to obtain export licenses within 90 days and verify customers do not include restricted Chinese entities.

telegram · zaihuapd · Nov 26, 07:38

**「Background」** Malaysia, Singapore, Thailand and Indonesia have served as intermediate shipping points for Chinese AI companies seeking Nvidia’s most advanced chips, which cannot be exported directly to mainland China. The reported suspension follows a US interim rule requiring licenses for AI-chip and server exports to data centers worldwide that may provide computing power to Chinese or other restricted entities \[tool-1-1\].

**「Who is affected」** The freeze hits regional cloud providers and data-center projects that reporting links to Chinese demand: under the new US rule they must obtain export licences within 90 days and verify customers, while Dell and Supermicro hold orders already assembled for buyers in the four countries.

<details><summary>References</summary>
<ul>
<li><a href="https://techcrunch.com/2026/11/16/us-tightens-ai-chip-export-controls-to-deter-chinese-companies-from-accessing-compute-remotely/">US tightens AI chip export controls to deter Chinese ... | TechCrunch</a></li>
<li><a href="https://www.ft.com/content/7838a715-07d4-4605-aa60-21f5af2b2370?syn-25a6b1a6=1">Nvidia halts chip shipments to south-east Asia</a></li>
<li><a href="https://www.zerohedge.com/ai/nvidia-halts-ai-chip-shipments-four-southwest-asian-countries">&quot;Causing Sheer Chaos&quot;: Nvidia Halts AI Chip Shipments ... | ZeroHedge</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#US export controls`, `#AI servers`, `#Southeast Asia`, `#semiconductor supply chain`

---

<a id="item-finance-news-3"></a>
### [荷兰大臣称不接受美国限制 ASML 对华销售的法案](https://www.bloomberg.com/news/articles/2026-11-26/netherlands-plans-to-fight-rollout-of-proposed-us-curbs-on-asml) ⭐️ 7.0/10

荷兰外贸与发展合作大臣 Sjoerdsma 于 11 月 26 日在议会表示，荷兰不会接受美国通过 MATCH Act 进一步限制 ASML 对华销售，并反对该法案的域外管辖效力。该法案由美国两党共同提出，要求荷兰、日本等盟友对华实施更严格的出口管制，否则美方将单方面限制其半导体设备；中国约占 ASML 今年销售额的 20%，外界预计国会将在 12 月中旬表决。

telegram · zaihuapd · Nov 26, 14:56

**「Background」** The Dutch government had already objected in May 2026 to the proposed US law that could further restrict ASML&\#x27;s China exports, and Trade Minister Sjoerd Sjoerdsma renewed that criticism in parliament on Nov. 26, saying the Netherlands &quot;will not be told what to do.&quot;

**「What it means」** If the bill becomes law, ASML&\#x27;s Chinese chipmaker customers and the wider semiconductor-equipment supply chain would be affected: allied governments would get 150 days to match stricter controls, and China accounted for about 20% of ASML&\#x27;s sales this year.

<details><summary>References</summary>
<ul>
<li><a href="https://www.reuters.com/world/asia-pacific/dutch-government-objects-proposed-us-law-restricting-asmls-china-exports-2026-05-14/">Dutch government objects to proposed US law restricting ASML ...</a></li>
<li><a href="https://nltimes.nl/2026/11/26/netherlands-draws-line-us-plan-restrict-asml-exports-china">Netherlands draws line over U.S. plan to restrict ASML ...</a></li>
<li><a href="https://www.thedefensenews.com/US-Pushes-Bill-to-Compel-Netherlands-to-Halt-Remaining-ASML-Machine-Sales-and-Service-to-China/">US Pushes Bill to Compel Netherlands to Halt Remaining ASML ...</a></li>

</ul>
</details>

**Tags**: `#semiconductor export controls`, `#ASML`, `#Netherlands-EU trade policy`, `#US-China tech restrictions`, `#MATCH Act`

---