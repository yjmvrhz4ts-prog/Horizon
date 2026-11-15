---
layout: default
title: "Horizon Summary: 2026-11-15 (EN)"
date: 2026-11-15
lang: en
---

> From 33 items, 6 important content pieces were selected

---

**Technology News**
1. [SpaceX catches Starship after Flight 15; booster splashes down](#item-tech-news-1) ⭐️ 8.0/10
2. [Investigation finds Lovable-built apps exposed passport data, 200K messages](#item-tech-news-2) ⭐️ 8.0/10
3. [BiRefNet-lite rewritten for phone NPUs: 23.7 ms at 1024px, int8](#item-tech-news-3) ⭐️ 8.0/10
4. [Meituan open-sources LongCat-2.5, claims Huawei-only training](#item-tech-news-4) ⭐️ 8.0/10
5. [Papr reports 96.0% on LongMemEval-S, with tuned-retrieval caveat](#item-tech-news-5) ⭐️ 7.0/10
6. [FAA ground stop tied to router fault after copper-to-fiber upgrade](#item-tech-news-6) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [SpaceX catches Starship after Flight 15; booster splashes down](https://www.spacex.com/launches/starship-flight-15) ⭐️ 8.0/10

SpaceX says Starship Flight 15 ended with the vehicle caught by the launch tower&\#x27;s mechanical arms after returning from orbit, a first for the program. The flight lasted about 22.5 hours and roughly 14 orbits, and it deployed 26 next-generation Starlink V3 satellites. The Super Heavy booster did not return to the tower as planned and splashed down in the Gulf of Mexico, so SpaceX did not achieve a two-stage catch on this attempt.

hackernews · ls612 · Nov 14, 21:22 · [Discussion](https://news.ycombinator.com/item?id=50500963)

**「Background」** Starship is SpaceX’s two-stage reusable launch system, consisting of the Super Heavy booster and the Starship upper stage. SpaceX’s recovery concept uses the launch tower’s mechanical arms to catch a returning vehicle instead of landing it on legs. Flight 15 applied that tower-catch approach to the ship after its orbital mission.

**「Impact」** SpaceX&\#x27;s Starlink and commercial launch customers still lack a demonstrated two-stage recovery on a single Starship mission: Flight 15 recovered the ship, but the Super Heavy booster splashed down in the Gulf of Mexico. Until SpaceX catches and reflies both stages, the cost-per-payload gains cited for full reusability remain unproven in operation, even though the mission deployed 26 Starlink V3 satellites.

**「Community discussion」** Commenters treated heat-shield durability as the decisive question and outlined the next test: catching both stages, then re-flying and recatching the same ships to lower payload costs. Others questioned the eventual mass fraction to orbit and argued that a fully reusable vehicle would beat Falcon 9&\#x27;s partially reusable design, while one commenter suggested extra booster propellant might have made a booster catch possible.

**Tags**: `#SpaceX Starship`, `#reusable rockets`, `#spaceflight`, `#hardware engineering`, `#Hacker News`

---

<a id="item-tech-news-2"></a>
### [Investigation finds Lovable-built apps exposed passport data, 200K messages](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

A security investigation reported that apps built with Lovable exposed sensitive user data, including passport details and more than 200,000 private messages, because of insufficient Row-Level Security and insecure defaults. Lovable&\#x27;s head of security said insufficient Row-Level Security was the root cause and that the company automatically scans every app before publish, offers a free deeper SAST scan, and provides manual or automatic fixes.

hackernews · armcat · Nov 14, 17:43 · [Discussion](https://news.ycombinator.com/item?id=50499017)

**「Why Row-Level Security matters here」** Lovable is an AI app builder whose generated apps can use Supabase, a hosted Postgres development platform. In that architecture, Postgres Row-Level Security is the database-side rule set that determines which rows a logged-in user can read or modify; if it is missing or misconfigured, the client can query more data than intended. In the HN thread, one commenter argued Supabase shares responsibility, saying a years-old onboarding tradeoff produced weak defaults and that a reported October 30 fix may not cover existing projects—a community claim, not independently verified here.

**「Impact」** The reported exposure means users of these Lovable-built apps could have passport and message data reachable through browser-visible requests, and builders need to verify Row-Level Security policies instead of relying on defaults.

**「Community Discussion」** Commenters disagreed over where responsibility lies: one argued that Supabase&\#x27;s long-standing permissive defaults are a major cause and that reports suggest existing projects may still use the old defaults, while another said data breaches predate AI but these apps are easier to probe and far more numerous. Lovable&\#x27;s security lead responded that pre-publish scanning and optional fixes are designed to catch the reported Row-Level Security failures.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/supabase/supabase">GitHub - supabase / supabase : The Postgres development platform. ...</a></li>

</ul>
</details>

**Tags**: `#application security`, `#AI coding tools`, `#data exposure`, `#Supabase`, `#Row-Level Security`

---

<a id="item-tech-news-3"></a>
### [BiRefNet-lite rewritten for phone NPUs: 23.7 ms at 1024px, int8](https://www.reddit.com/r/MachineLearning/comments/1xwuvaz/birefnetlite_at_1024px_fully_on_a_phone_npu_237/) ⭐️ 8.0/10

An independent researcher rewrote and int8-quantized BiRefNet-lite so that all 2,060 layers run as a single NPU partition, reporting 23.7 ms per 1024×1024 mask on a Galaxy S26 \(Snapdragon 8 Elite Gen 5\), 31.1 ms on an S25, and 182 ms on a mid-range Snapdragon 7 Gen 1. Stock BiRefNet-lite runs out of memory at 1024px on the same phones and falls back to CPU at 512px, taking 677 ms with a 2.1 GB peak. The rewrite replaces 20 deformable convolutions with plain convolutions, feeds a 1024px mask from a 640px backbone, and swaps the 5D/6D Swin tensors and cyclic-roll shifted windows for 4D window partitioning and roll-free masked shifting, with quantization-aware distillation performed through the exported NPU graph. The author reports the int8 student matching its fp32 teacher in S-measure on held-out ECSSD and DUT-OMRON \(0.939 vs 0.938 and 0.830 vs 0.826\) but losing 0.017 S-measure on fine structures in DIS-VD; weights, 42 AOT-compiled Snapdragon chip files, and MIT-licensed code are released, with no MediaTek or Tensor support and no power measurements yet. All latency and accuracy figures are author-reported in the linked writeup and paper.

reddit · r/MachineLearning · /u/subhashg547 · Nov 15, 12:58

**「Background」** BiRefNet-lite is an open-weight image segmentation model whose decoder uses deformable convolutions and whose Swin transformer stages rely on 5D/6D tensors and cyclic window rolls. Those operations, together with 1024px activations, are poorly matched to phone NPUs, which need compiler-friendly graphs and fit within limited on-chip memory; unsupported pieces force CPU fallback or out-of-memory failures.

**「Deployment trade-off」** Developers targeting Snapdragon phones get a fully on-NPU 1024px matting model, compiled AOT for 42 chips, but the same app cannot use it on MediaTek or Tensor devices, which the author lists as unsupported. The 23.7 ms figure is tied to the Snapdragon 8 Elite Gen 5 version of the Galaxy S26; regional S26 units shipping Exynos silicon fall outside both the benchmark and the precompiled binaries. Applications that depend on thin structures such as wires and fences should also account for the reported 0.017 S-measure drop versus the fp32 teacher on DIS-VD.

<details><summary>References</summary>
<ul>
<li><a href="https://www.promptquorum.com/fr/local-llms/galaxy-s26-local-ai-on-device-2026">Galaxy S 26 IA Locale: Galaxy AI et NPU Fonctionnement</a></li>

</ul>
</details>

**Tags**: `#on-device ML`, `#int8 quantization`, `#NPU deployment`, `#image segmentation`, `#model optimization`

---

<a id="item-tech-news-4"></a>
### [Meituan open-sources LongCat-2.5, claims Huawei-only training](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

Meituan&\#x27;s LongCat team released weights for LongCat-2.5, a 1.6-trillion-parameter agent model, one week after launch under an MIT license that allows commercial use. The model accepts text, image, and video input, activates about 48 billion parameters per token, and is aimed at long, multi-step tasks such as coding. Meituan reports an 88.4 score on Terminal Bench v2.1, just below Claude Opus 5&\#x27;s 89.1, and says the model was trained entirely on Huawei Ascend chips without Nvidia GPUs; both are vendor claims not independently verified in the supplied material.

telegram · zaihuapd · Nov 15, 11:08

**「Background」** LongCat-2.5 is a sparse-activation model: about 48 billion of its parameters are active per token, so that figure describes the compute path used for each token rather than the model&\#x27;s full size. Meituan&\#x27;s LongCat team announced the model first and published the downloadable weights about a week later under an MIT license, which permits commercial use.

**「Developer impact」** Because the weights are MIT-licensed for commercial use, developers can self-host, fine-tune, and ship LongCat-2.5 in products without a Meituan commercial agreement; however, its headline 88.4 Terminal Bench v2.1 score is vendor-reported and unverified by third parties, so teams should test it on their own coding-agent tasks before adoption.

<details><summary>References</summary>
<ul>
<li><a href="https://tpsreport.news/models/longcat-2-5">LongCat - 2 . 5 specs, benchmarks and changelog | TPS</a></li>

</ul>
</details>

**Tags**: `#open-source LLMs`, `#agentic coding`, `#Huawei Ascend`, `#model training`, `#benchmarks`

---

<a id="item-tech-news-5"></a>
### [Papr reports 96.0% on LongMemEval-S, with tuned-retrieval caveat](https://www.reddit.com/r/MachineLearning/comments/1xwnloh/longmemevals_960_with_the_official_judge_and_what/) ⭐️ 7.0/10

Papr reports 96.0% on all 500 LongMemEval-S questions using a Papr-Embed 0.6B retriever, a Gemini Flash 2.5 reranker, and a single-turn answer model under the official answer prompt and the unmodified gpt-4o-2024-08-06 judge; per-question answers and judge labels are public, so the official metrics script reproduces the score. Its ablations put evidence-session recall at 97.9% \(all evidence sessions in the top 5 for 460 of 470 answerable questions\) and show top-20 retrieval over top-5 is a trade: 11 questions gained, 8 lost, net +3, with temporal reasoning rising from 123 to 130 of 133 and abstention flat at 27/30. Papr cautions that the run is self-reported, run-to-run variance is about ±3 questions—making 96.0% versus Chronos&\#x27;s 95.6% a tie—and top-20 was chosen after reviewing top-5 misses, so the 96.0% result is tuned on this set; gpt-5-mini reached 94.4% on the same retrieval.

reddit · r/MachineLearning · /u/remoteinspace · Nov 15, 05:40

**「Background」** LongMemEval-S is a 500-question benchmark for long-term memory in LLM assistants, scored with an official answer prompt and judge. Reported comparisons are not fully apples-to-apples: the post cites Chronos at 95.6%, Hindsight at 94.6% with a different judge and 43.6k tokens per question, and gbrain at 90.6%.

**「Impact」** For teams using LongMemEval-S as a procurement or regression benchmark, the practical takeaway is to rerun the public per-question artifacts with the official judge and fix retrieval depth before comparing systems; the reported ±3-question variance means small headline gaps are not decision-grade.

**Tags**: `#llm-memory`, `#retrieval-augmented-generation`, `#benchmarks`, `#evaluation`, `#long-context`

---

<a id="item-tech-news-6"></a>
### [FAA ground stop tied to router fault after copper-to-fiber upgrade](https://www.theverge.com/transportation/1033898/faa-ground-stop-sean-duffy-faa-copper-wire) ⭐️ 7.0/10

U.S. Transportation Secretary Sean Duffy said on Nov. 14 that the FAA&\#x27;s national ground stop was triggered by routine maintenance at a remote facility that replaced aging copper wiring with fiber; the newly installed router then malfunctioned, grounding thousands of flights. The router sent more than 1,000 connection requests every 4 to 5 seconds to other routers, disrupting radar signals and aircraft communications, according to Duffy. He said the root cause is not yet confirmed and could be a hardware failure, a configuration error, or a mistake by contractor L3Harris. Duffy also called on Congress to provide additional funding for air-traffic-control modernization.

telegram · zaihuapd · Nov 15, 02:10

**「Background」** The FAA issued a nationwide ground stop at 20:54 UTC on November 13, 2026, because of a communications outage. The maintenance work was part of an ongoing upgrade of an older L3Harris-managed communications system from copper wire to fiber-optic cable, which is the context for why a newly installed router&\#x27;s overload could affect air traffic communications.

**「Impact」** The ground stop delayed or canceled more than 11,000 U.S. flights, and the air travel schedule was not expected to recover until Sunday. Because Transportation Secretary Sean Duffy said the cause could be hardware, configuration, or contractor L3Harris error, the FAA cannot yet rule out the same failure mode at other remote facilities undergoing similar copper-to-fiber upgrades.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_FAA_nationwide_ground_stop">2026 FAA nationwide ground stop - Wikipedia</a></li>
<li><a href="https://www.cnbc.com/2026/11/14/faa-ground-stop-flights-resume-delays.html">Ground stop followed contractor upgrade to L 3 Harris telecom system...</a></li>
<li><a href="https://www.theguardian.com/world/2026/nov/13/faa-nationwide-ground-stop-flights">Flights slowly resume after US aviation agency lifts nationwide ...</a></li>
<li><a href="https://weather.com/2026/11/13/travel/faa-nationwide-ground-stop-equipment-outage-flights">US air travel schedule should recover from ground stop by Sunday...</a></li>

</ul>
</details>

**Tags**: `#FAA`, `#网络故障`, `#路由配置`, `#空管基础设施`, `#系统可靠性`

---