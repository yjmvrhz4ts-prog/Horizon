---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 36 items, 12 important content pieces were selected

---

**Technology News**
1. [Nvidia Reinstates Jensen Huang as CEO After Abrupt Removal](#item-tech-news-1) ⭐️ 9.0/10
2. [Claimed formal proof separates VP from VNP over every field](#item-tech-news-2) ⭐️ 9.0/10
3. [Ladybird browser reaches alpha with macOS and Linux builds](#item-tech-news-3) ⭐️ 8.0/10
4. [Z.ai releases GLM-5.4 with first loop-transformer architecture](#item-tech-news-4) ⭐️ 8.0/10
5. [Google Reportedly Built a Simulated Web to Test Chrome&\#x27;s AI Agent](#item-tech-news-5) ⭐️ 7.0/10
6. [Windows Server 2028 drops WoW64 by default](#item-tech-news-6) ⭐️ 7.0/10
7. [Codex2api releases suspected backdoored after author account compromise](#item-tech-news-7) ⭐️ 7.0/10
8. [Meta AI chief says superintelligence is near and control is at risk](#item-tech-news-8) ⭐️ 7.0/10

**Financial News**
1. [AI selloff clouds planned listings by DeepSeek, Moonshot and StepFun](#item-finance-news-1) ⭐️ 8.0/10
2. [Fed&\#x27;s Williams Says More Work Needed on Inflation, Signals Gradual Rate Rises](#item-finance-news-2) ⭐️ 7.0/10
3. [Ant Group leads $100 million pre-A round in Simplexity Robotics at $1.6 billion valuation](#item-finance-news-3) ⭐️ 7.0/10
4. [Shanghai to Adjust Metro Fares for First Time in 21 Years](#item-finance-news-4) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Nvidia Reinstates Jensen Huang as CEO After Abrupt Removal](https://www.cnbc.com/2026/11/23/nvidia-jensen-huang-ceo.html) ⭐️ 9.0/10

Nvidia has reinstated Jensen Huang as CEO, reversing an abrupt removal. A company statement quoted in the discussion said the board received input from senior levels of the U.S. government and was confident that Huang&\#x27;s reinstatement &quot;poses no national security risk.&quot; The supplied material does not establish why Huang was removed, who served as interim CEO, or what specific government review occurred.

hackernews · jaz · Nov 23, 14:00 · [Discussion](https://news.ycombinator.com/item?id=50611576)

**「Background」** Nvidia’s Nov. 23, 2026 announcement said the board voted unanimously to reinstate Huang as president, CEO and board member effective immediately. The move reverses his earlier removal from the CEO role; the supplied material does not detail the grounds for that removal or its exact timing.

**「Impact」** For Nvidia&\#x27;s customers and partners, the CEO is unchanged in the immediate term, but the board has publicly tied his reinstatement to U.S. government review—an unusual dependency for decisions involving export-controlled AI chips.

**「Community Discussion」** Commenters split over the government&\#x27;s role: some called the intervention hypocritical given U.S. pressure on ASML and Japanese chip companies to restrict China sales, while others argued that no evidence of wrongdoing has surfaced and that Delaware&\#x27;s Caremark standard makes board liability unlikely. Several also criticized the board for reversing its position within two weeks without clearly explaining the evidence behind the original removal.

<details><summary>References</summary>
<ul>
<li><a href="https://nvidianews.nvidia.com/news/nvidia-board-reinstates-jensen-huang-as-president-ceo-and-board-director">NVIDIA Board Reinstates Jensen Huang as President, CEO and ...</a></li>
<li><a href="https://investor.nvidia.com/news/press-release-details/2026/NVIDIA-Board-Reinstates-Jensen-Huang-as-President-CEO-and-Board-Director/default.aspx">NVIDIA Corporation - NVIDIA Board Reinstates Jensen Huang as ...</a></li>

</ul>
</details>

**Tags**: `#Nvidia`, `#AI hardware`, `#semiconductor policy`, `#corporate governance`, `#US-China tech restrictions`

---

<a id="item-tech-news-2"></a>
### [Claimed formal proof separates VP from VNP over every field](https://github.com/anthropics/formal-math/tree/main/vp-vnp) ⭐️ 9.0/10

A paper hosted in Anthropic&\#x27;s formal-math repository claims a formal proof that VP ≠ VNP over every field, a separation in algebraic complexity theory. The repository and community re-checks have drawn attention, but the work has not been peer reviewed, and the paper itself says it has not analyzed how the result relates to relativization or algebrization. The claim is therefore a formally checked artifact under scrutiny, not an established theorem.

hackernews · mikeryan52 · Nov 23, 22:09 · [Discussion](https://news.ycombinator.com/item?id=50620102)

**「What VP and VNP are」** VP vs VNP is the algebraic analogue of P vs NP, formulated by Leslie Valiant in 1979: VP contains polynomials computable by polynomial-size arithmetic circuits, while VNP contains polynomials whose coefficients are efficiently computable, with the determinant and permanent as the canonical contrasting examples. Whether the two classes differ has stayed open, so the claim concerns a longstanding open problem rather than a settled result.

**「Impact」** If the proof survives scrutiny, it would establish that the algebraic complexity classes VP and VNP differ over every field, resolving a major open question; complexity researchers should treat the missing relativization and algebrization analysis as a central technical issue to test before relying on the result.

**「Community discussion」** Commenters split between treating the result as a serious checkable claim and reacting to the pace of AI-assisted mathematics; one said they reran the checks and found the theorems imply a restatement of the claims, while another quoted the paper&\#x27;s admission that it has not analyzed relativization or algebrization. Others speculated that Anthropic is pursuing P versus NP and that math graduate students face a rapidly changing problem landscape.

<details><summary>References</summary>
<ul>
<li><a href="https://www.kipuhub.com/en/article/algebraic-complexity-vp-vnp/">Algebraic Complexity: VP vs VNP – The Determinant vs the ...</a></li>
<li><a href="https://www.machucavalley.tech/blog/vp-vnp-algebraic-complexity-explained/">The Holy Grail of Algebraic Complexity: Is VP ≠ VNP?</a></li>

</ul>
</details>

**Tags**: `#VP vs VNP`, `#algebraic complexity`, `#formal verification`, `#AI for mathematics`, `#computational complexity`

---

<a id="item-tech-news-3"></a>
### [Ladybird browser reaches alpha with macOS and Linux builds](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird released its first alpha, with installable builds for macOS and Linux that no longer require users to compile the browser themselves. The project implements most of its own browser stack—HTML parsing, CSS, layout, JavaScript, and WebAssembly—while relying on HarfBuzz, Skia, ffmpeg, and SQLite for text shaping, 2D graphics, video, and storage. The alpha is explicitly unfinished: some sites will fail and crashes are expected, and a tester found Datasette Lite broken because navigator.serviceWorker.startMessages is unimplemented. Ladybird&\#x27;s October newsletter reported 2,184,722 passing web-platform-tests subtests, ahead of Safari&\#x27;s 2,172,990 but behind Firefox and Chrome.

hackernews · janvdberg · Nov 23, 16:13 · [Discussion](https://news.ycombinator.com/item?id=50614249)

**「Background」** Ladybird draws code from its predecessor project SerenityOS and is unusual in implementing most of a browser engine from scratch rather than relying on an existing engine for those core pieces. The alpha is the first release distributed as a binary, so macOS and Linux users can try it without compiling.

**「Impact」** For macOS and Linux users willing to test it, the alpha makes Ladybird installable without a build toolchain, and the browser includes in-app broken-site reporting and optional crash-report submission. Web developers should treat service-worker-dependent apps as a known gap: Datasette Lite fails on the missing navigator.serviceWorker.startMessages API.

**「Community discussion」** Commenters reported that many ordinary and difficult sites rendered correctly—including ProxMox and NoVNC, with one saying NoVNC felt snappier than in Firefox—while one noted jerky scrolling. One commenter warned that the JavaScript engine lacks a JIT and will struggle with JS-heavy sites such as ChatGPT, and another expressed nostalgia for Ladybird&\#x27;s earlier self-built libraries after its move to SQLite and Skia.

**Tags**: `#browsers`, `#ladybird`, `#open-source`, `#web-engines`, `#software-engineering`

---

<a id="item-tech-news-4"></a>
### [Z.ai releases GLM-5.4 with first loop-transformer architecture](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai has made GLM-5.4 available, describing it as the lab&\#x27;s first loop transformer: a group of weight-shared layers runs for multiple iterations, refining hidden states from the previous pass to create a deeper network without increasing parameter count. The coding-focused model is currently reachable through Z.ai&\#x27;s API via its Coding Plan subscription, not the regular API plan, and open weights have not been released.

hackernews · foohis · Nov 23, 10:06 · [Discussion](https://news.ycombinator.com/item?id=50609685)

**「Background」** A standard Transformer runs each layer once per forward pass. A looped transformer instead runs a group of weight-shared layers for multiple iterations, refining hidden states to add effective depth without increasing the parameter count. GLM-5.4 follows Thinking Machines Lab&\#x27;s Inkling 2 Mini, announced November 20, which runs its middle layers three times per token; Zhipu&\#x27;s earlier GLM-5.1, 5.2, and 5.3 releases provide the comparison baseline cited in the source.

**「Developer impact」** Developers testing GLM-5.4 need a Coding Plan subscription, but its API key works with Z.ai&\#x27;s shared OpenAI-compatible Responses API at https://api.z.ai/api/v1. Tooling compatibility is still catching up: the existing llm-zai plugin does not yet support the model, prompting a separate llm-glm plugin.

**「Community discussion」** Commenters welcomed Zhipu&\#x27;s technical disclosure and explained looped transformers as a way to reduce memory-bandwidth pressure by computing a layer multiple times instead of moving each layer through the chip once. One developer complained that Chinese models&\#x27; long &quot;marathon thinking&quot; sessions make even conceptually simple tasks much slower, though the comment did not tie that behavior to the looped architecture.

**Tags**: `#loop transformers`, `#LLM architecture`, `#coding models`, `#inference efficiency`, `#Zhipu AI`

---

<a id="item-tech-news-5"></a>
### [Google Reportedly Built a Simulated Web to Test Chrome&\#x27;s AI Agent](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

Google reportedly built a simulated internet, called Mirror Dimension, to test Chrome&\#x27;s AI agent performing tasks such as opening sites, searching, logging in, adding items to a cart, and completing jobs. The environment is said to contain thousands of simulated websites, with each engineer testing in a separate isolated setup and more than 1,000 test cases run daily. The reported focus is defending against prompt-injection and other attacks from malicious webpages; the account comes from a secondary report and provides no primary technical details or availability information.

telegram · zaihuapd · Nov 23, 01:30

**「Background」** Indirect prompt injection hides malicious instructions in webpage text, images, or HTML so that a browsing AI agent may treat them as commands; testing such an agent on the live web could expose real accounts and data. Google&\#x27;s security blog describes Mirror Dimension as a synthetic version of the web, with thousands of simulated sites, that lets Chrome engineers evaluate its &quot;auto browse&quot; agent in realistic environments without real-world security risk.

**「Impact」** For browser-agent developers, the reported setup points to a concrete testing requirement: run task flows against synthetic sites in isolation so injection attempts can be exercised without exposing real accounts or production pages.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/security/mirror-dimension-for-agents/">Mirror Dimension for Agents: Evaluating Browser-Use Agents ...</a></li>
<li><a href="https://indianexpress.com/article/technology/artificial-intelligence/google-mirror-dimension-explained-fake-internet-ai-agents-10975011/">What is Google’s ‘Mirror Dimension’, the fake internet built ...</a></li>

</ul>
</details>

**Tags**: `#AI agents`, `#browser security`, `#prompt injection`, `#Chrome`, `#testing`

---

<a id="item-tech-news-6"></a>
### [Windows Server 2028 drops WoW64 by default](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

Microsoft said at Ignite 2026 that Windows Server 2028 will ship without the WoW64 compatibility subsystem by default, so 32-bit applications will not run out of the box. The server release is planned for fall 2027 alongside Windows 11 27H2. Administrators can add WoW64 back as a Feature on Demand, typically via PowerShell or DISM on Server Core; Microsoft cites reducing attack surface and blocking 32-bit malware. Windows 11 still includes WoW64, and Microsoft has not announced a removal plan for it.

telegram · zaihuapd · Nov 23, 03:03

**「Background」** WoW64 is the Windows compatibility subsystem that allows 32-bit applications to execute on 64-bit installations. Because it sits between the app and the operating system, its presence or absence determines whether legacy 32-bit software can launch at all.

**「Impact」** Organizations upgrading to Windows Server 2028 will need to inventory 32-bit applications and add WoW64 back as an optional feature—generally via PowerShell or DISM on Server Core—before or during deployment, or those apps will not launch on a default installation. That makes the feature-on-demand step a required item in imaging and upgrade checklists for any environment still running legacy 32-bit management tools or line-of-business software.

<details><summary>References</summary>
<ul>
<li><a href="https://www.neowin.net/news/windows-server-2028-dropping-support-for-32-bit-apps-wow64-will-be-available-as-fod/">Windows Server 2028 dropping support for 32-bit apps (WoW64 ...</a></li>
<li><a href="https://windowsreport.com/microsoft-is-dropping-32-bit-app-support-by-default-in-windows-server-2028/">Microsoft Is Dropping 32-Bit App Support by Default in ...</a></li>

</ul>
</details>

**Tags**: `#Windows Server`, `#WoW64`, `#32-bit compatibility`, `#Microsoft`, `#enterprise IT`

---

<a id="item-tech-news-7"></a>
### [Codex2api releases suspected backdoored after author account compromise](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

The Codex2api project&\#x27;s author account was reportedly compromised, and an attacker pushed tags outside the main branch so that Release builds shipped a backdoor; the incident write-up identifies v3.1.10–v3.1.12 as the affected range. In v3.1.11, authentication was removed, allowing unauthenticated remote command execution, while a workflow exfiltrated 16 GitHub Actions secrets from the repository, affecting at least 21 repositories under the same account. The report comes from a Telegram post and an incident retrospective, not independent verification. Users who installed or updated to those versions are advised to stop using them, roll back to v3.1.9, and rotate GitHub tokens, SSH keys, database credentials and other related secrets, including DeepSeek keys.

telegram · zaihuapd · Nov 23, 11:21

**「Background」** GitHub release artifacts are typically built by CI when a tag is pushed, so a compromised maintainer account can publish a release without merging code to the main branch or passing the review that branch normally receives. GitHub Actions secrets are credentials made available to those workflows, which is why the reported exfiltration of 16 secrets across at least 21 repositories turns a malicious release into a broader credential-rotation problem.

**「Impact」** Anyone who ran v3.1.10–v3.1.12 should treat the host and connected credentials as potentially compromised: the authentication bypass permits command execution without a password, and the workflow&\#x27;s secret exfiltration means rolling back does not undo possible credential theft. Rotating GitHub tokens, SSH keys, database credentials and DeepSeek keys is required, not optional, for affected installations.

**Tags**: `#supply-chain-attack`, `#GitHub-Actions`, `#security-incident`, `#secrets-exfiltration`, `#remote-code-execution`

---

<a id="item-tech-news-8"></a>
### [Meta AI chief says superintelligence is near and control is at risk](https://thenextweb.com/news/metas-ai-chief-says-superintelligence-is-arriving-and-control-is-at-risk) ⭐️ 7.0/10

Alexandr Wang, Meta&\#x27;s chief AI officer and head of Meta Superintelligence Labs, argued in a post on X that superintelligence is no longer a &quot;someday&quot; issue and that humans may struggle to control systems capable of unlimited self-improvement or 1,000 times greater intelligence than people. He cited a Riemann hypothesis proof by mathematician Levent Alpöge, produced with Anthropic&\#x27;s Claude and machine-verified on Saturday by the Lean and Mathlib community. Wang said the gap between AI and leading humans now comes down to concrete knowledge, engineering integration, and experimentation. The proof has no human-readable exposition yet, and Wang&\#x27;s post calls for urgent safety, alignment, and safeguard research rather than reporting a demonstrated control method.

telegram · zaihuapd · Nov 23, 12:49

**「What a Lean-verified proof means」** The Riemann hypothesis is one of mathematics&\#x27; best-known unsolved problems. Lean is a proof assistant, and Mathlib is its community mathematics library; a proof checked there has its logical steps mechanically verified, which is different from a human-readable exposition that mathematicians can evaluate. The claimed proof cited by Wang is described as having no such human-readable version yet.

**「Verification outpaces human review」** The immediate pressure falls on mathematicians and the venues that publish them: the Alpöge result is attested by Lean/Mathlib machine checking and independent verification rather than a human-readable exposition, so reviewers and journals would need to treat a formal proof artifact as primary evidence while a readable account is still pending. Wang&\#x27;s call for safety and alignment investment is a stated position, not a demonstrated capability or committed program.

<details><summary>References</summary>
<ul>
<li><a href="https://www.telegraph.co.uk/business/2026/11/23/humans-risk-losing-control-to-superintelligent-ai-warns-met/">‘Hard to imagine’ humans staying in control of AI, warns Meta</a></li>
<li><a href="https://kingy.ai/blog/levent-alpoge-claude-riemann-hypothesis-proof/">Riemann hypothesis proof verified in Lean</a></li>
<li><a href="https://www.theguardian.com/technology/2026/nov/21/anthropic-riemann-hypothesis-solved-claude-ai">Two groups verify mathematician’s claim that Claude ... | The Guardian</a></li>

</ul>
</details>

**Tags**: `#AI safety`, `#superintelligence`, `#Lean theorem proving`, `#Riemann hypothesis`, `#Meta AI`

---

## Financial News

<a id="item-finance-news-1"></a>
### [AI selloff clouds planned listings by DeepSeek, Moonshot and StepFun](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

A global AI stock selloff after Anthropic’s $119.5 billion IPO is weighing on Chinese tech shares, which have lost $1.7 trillion in market value since end-June, and clouding share-sale plans at DeepSeek, Moonshot and StepFun, Bloomberg reported.

telegram · zaihuapd · Nov 23, 09:31

**「Background」** Anthropic’s record initial public offering \(IPO\)—the largest U.S. listing—failed to revive the AI trade, and global stocks sold off afterward.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/19/anthropic-ipo-ai-stocks-selloff.html">Anthropic IPO fails to lift AI stocks - CNBC</a></li>

</ul>
</details>

**Tags**: `#AI selloff`, `#China tech stocks`, `#IPOs`, `#Anthropic`, `#market volatility`

---

<a id="item-finance-news-2"></a>
### [Fed&\#x27;s Williams Says More Work Needed on Inflation, Signals Gradual Rate Rises](https://www.cnbc.com/2026/11/23/john-williams-fed-inflation-rate-hikes.html) ⭐️ 7.0/10

New York Fed President John Williams said more work is needed to bring inflation back to the Fed&\#x27;s 2% target, indicating further rate increases can unfold &quot;over time&quot; ahead of a Dec. 8-9 policy meeting where markets fully price a quarter-point rise from the current 3.75%-4% range.

rss · CNBC Finance · Nov 23, 21:02

**「Background」** The Fed has kept its benchmark rate in a 3.75%-4% range while inflation runs well above its goal, and officials have split over how fast to raise rates, with Williams favoring a measured approach; he said he expects inflation to move closer to 2% in 2027 and reach the target the following year.

**「Impact」** If the quarter-point increase markets expect is delivered, households and businesses with loans priced off the Fed&\#x27;s benchmark, such as variable-rate credit card balances, would face higher borrowing costs.

**Tags**: `#Federal Reserve`, `#monetary policy`, `#interest rates`, `#inflation`, `#U.S. economy`

---

<a id="item-finance-news-3"></a>
### [Ant Group leads $100 million pre-A round in Simplexity Robotics at $1.6 billion valuation](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

Ant Group led a $100 million pre-A funding round in Chinese embodied-AI startup Simplexity Robotics, giving the company a post-money valuation of $1.6 billion, according to Bloomberg. Existing backers Alibaba, Tencent, HongShan \(Sequoia China\) and BlueRun Ventures also invested, and chairman and co-founder Wang Kai confirmed the deal to Bloomberg.

telegram · zaihuapd · Nov 23, 02:02

**「Background」** Simplexity Robotics was founded in Hangzhou in July 2025 by a team drawn from Li Auto, and in March it said it had completed five funding rounds within six months totaling 2 billion yuan, at a post-money valuation already above $1 billion \(tool-1-3\). A pre-A round is an early-stage private financing that comes before a company&\#x27;s first Series A.

**「Market impact」** The proceeds are intended to help Simplexity contest market share with more established Chinese humanoid-robot makers Unitree and UBTech, adding competitive pressure on those incumbents.

<details><summary>References</summary>
<ul>
<li><a href="https://equalocean.com/news/2026030921780">Five Rounds, RMB 2B: Simplexity Robotics Emerges... | EqualOcean</a></li>

</ul>
</details>

**Tags**: `#具身智能`, `#人形机器人`, `#风险融资`, `#蚂蚁集团`, `#中国科技`

---

<a id="item-finance-news-4"></a>
### [Shanghai to Adjust Metro Fares for First Time in 21 Years](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

Shanghai will adjust its metro fares for the first time in 21 years starting Dec 1, Xinhua reported, with a 3-yuan starting fare for 0–4 km and 1-yuan increments after each additional 4, 4, 4, 7, 7, 10 and 10 km, then every 15 km beyond 50 km. The same package, aimed at reducing the effect on frequent riders, includes 35-, 45-, 60- and 90-ride tickets priced at 190, 210, 270 and 390 yuan, on sale Nov 26, plus a 10% discount after 90 yuan of monthly spending on the same payment channel.

telegram · zaihuapd · Nov 23, 10:45

**「Background」** Shanghai’s last systemic metro fare adjustment was in 2005, when the starting fare rose from 2 yuan to 3 yuan; the new plan takes effect on December 1, 21 years later.

**「Impact」** Shanghai commuters who ride frequently are directly affected, because fares will now vary by distance traveled while the new multi-ride tickets and 90-yuan monthly spending threshold are designed to soften the cost for heavy users.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bilibili.com/video/BV1hy3W6SEZb/?spm_id_from=333.788.recommend_more_video.6">上 海 地 铁 要 调 价 了！ 9月7日召开听证会，这是自 2005 ... | 哔哩哔哩</a></li>

</ul>
</details>

**Tags**: `#Shanghai metro`, `#public transit fares`, `#fare adjustment`, `#commuter discounts`, `#China transport policy`

---