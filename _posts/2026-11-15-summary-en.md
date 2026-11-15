---
layout: default
title: "Horizon Summary: 2026-11-15 (EN)"
date: 2026-11-15
lang: en
---

> From 33 items, 7 important content pieces were selected

---

**Technology News**
1. [Lovable apps exposed passport details and 200K messages via RLS gaps](#item-tech-news-1) ⭐️ 8.0/10
2. [BiRefNet-lite rewritten for phone NPUs: 23.7 ms 1024px masks, int8, open weights](#item-tech-news-2) ⭐️ 8.0/10
3. [SpaceX reports first Starship tower catch after orbital return](#item-tech-news-3) ⭐️ 8.0/10
4. [Meituan releases LongCat-2.5 weights, claims all-Huawei Ascend training](#item-tech-news-4) ⭐️ 8.0/10
5. [PyPI project pages now show provenance and security signals](#item-tech-news-5) ⭐️ 7.0/10
6. [Tesla Cybercab terms require $299 monthly autonomy subscription](#item-tech-news-6) ⭐️ 7.0/10
7. [FAA says nationwide ground stop linked to router in copper-to-fiber upgrade](#item-tech-news-7) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Lovable apps exposed passport details and 200K messages via RLS gaps](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

Security researchers reported that apps built with Lovable exposed passport details and more than 200,000 private messages because of insufficient Row-Level Security. Lovable&\#x27;s head of security, commenting as igorandri, said the root cause was insufficient RLS and that Lovable scans every app before publishing, offers a deeper SAST scan, and provides fix, auto-fix, and publishing-block options; those are vendor claims not independently verified in the supplied material.

hackernews · armcat · Nov 14, 17:43 · [Discussion](https://news.ycombinator.com/item?id=50499017)

**「Why RLS matters for Lovable apps」** Supabase, the backend Lovable commonly generates against, relies on Postgres Row-Level Security policies to decide which rows each user may read or write; tables shipped without RLS enabled, or with permissive policies, are readable by anyone holding the public API key. This failure mode was already tracked as CVE-2025-48757 \(CVSS 9.3\), which covered Lovable-generated Supabase applications leaking data through missing or broken RLS. Subsequent write-ups noted that Lovable&\#x27;s built-in scan checked whether policies existed rather than whether they actually restricted access, leaving per-table audits and auth.uid\(\) checks as the practical verification step.

**「Impact」** For developers using Lovable, the immediate task is to verify that Row-Level Security is enabled and tested on every client-reachable table; one commenter noted that the reported exposures could be found by inspecting browser network calls rather than through sophisticated exploitation.

**「Community discussion」** Commenters split over responsibility: one argued that Supabase&\#x27;s long-standing permissive defaults are the deeper issue and said a supposed October 30 fix may not apply to existing projects, while Lovable&\#x27;s security lead said insufficient RLS is exactly what its pre-publish and SAST scans are designed to catch. Another commenter described these AI-generated apps as easy, numerous targets whose users often cannot judge the risk.

<details><summary>References</summary>
<ul>
<li><a href="https://elysiancrest.com/insights/custom-software/cve-2025-48757-lovable-rls-audit">CVE-2025-48757 &amp; Lovable RLS: What to Verify Before Launch</a></li>
<li><a href="https://www.brinztech.com/breach-alerts/brinztech-alert-critical-row-level-security-rls-vulnerability-cve-2025-48757-exposed-lovable-supabase-applications/">Critical Row Level Security (RLS) Vulnerability (CVE-2025 ...</a></li>
<li><a href="https://ptkd.com/journal/lovable-dev-supabase-rls-bypass-vulnerability">Lovable.dev Supabase RLS bypass: how it happens, how to fix it</a></li>

</ul>
</details>

**Tags**: `#security`, `#AI-generated-code`, `#Supabase`, `#row-level-security`, `#app-builder`

---

<a id="item-tech-news-2"></a>
### [BiRefNet-lite rewritten for phone NPUs: 23.7 ms 1024px masks, int8, open weights](https://www.reddit.com/r/MachineLearning/comments/1xwuvaz/birefnetlite_at_1024px_fully_on_a_phone_npu_237/) ⭐️ 8.0/10

An independent researcher released an int8 rewrite of BiRefNet-lite that keeps all 2,060 layers on a phone NPU and returns a 1024×1024 matte in 23.7 ms on a Galaxy S26 \(Snapdragon 8 Elite Gen 5\), 31.1 ms on an S25, and 182 ms on a mid-range Snapdragon 7 Gen 1. The original model does not compile to phone NPUs, so the rewrite swaps 20 deformable convolutions for plain convs, removes 5D/6D tensors and cyclic window rolls through exact graph rewrites, pairs a 640px backbone with a slim full-resolution tail, and distils through the exported NPU graph with all 8-bit weights. Weights plus AOT-compiled binaries for 42 Snapdragon chips are on Hugging Face with MIT-licensed code and a Zenodo paper, but the latency and accuracy figures are self-reported on Reddit and not independently validated. On held-out ECSSD and DUT-OMRON the int8 model tracks its fp32 teacher in S-measure \(0.939 vs 0.938 and 0.830 vs 0.826\), while losing 0.017 S-measure on DIS-VD fine structures such as wires and fences, and six public models beat it on DUT-OMRON.

reddit · r/MachineLearning · /u/subhashg547 · Nov 15, 12:58

**「Background」** BiRefNet is an open-source bilateral-reference model for dichotomous image segmentation, and its lite variant has 44.4M parameters, according to its Hugging Face model card. The project had already released a BiRefNet-lite-2K version for 2560×1440 inputs in September 2024, so the starting point for this phone-NPU port was an existing high-resolution segmentation model rather than a purpose-built mobile network.

**「Impact」** Android developers can test the precompiled Qualcomm binaries directly, but the release covers Snapdragon only — there is no MediaTek or Tensor support — and power draw is unmeasured, so the battery cost of a per-tap cutout remains unknown. The author also flags a distillation failure that his loss curve hid: a sigmoid gate on the deepest decoder branch saturated to about 1e-11 and went dead while the rest of the decoder compensated, and he restored it from the teacher with a feature loss rather than retraining from scratch.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/ZhengPeng7/BiRefNet_lite">ZhengPeng7/ BiRefNet _ lite · Hugging Face</a></li>
<li><a href="https://github.com/ZhengPeng7/BiRefNet">GitHub - ZhengPeng7/ BiRefNet : [CAAI AIR&#x27;24] Bilateral Reference for...</a></li>

</ul>
</details>

**Tags**: `#on-device AI`, `#mobile NPU`, `#model quantization`, `#image segmentation`, `#model optimization`

---

<a id="item-tech-news-3"></a>
### [SpaceX reports first Starship tower catch after orbital return](https://www.spacex.com/launches/starship-flight-15) ⭐️ 8.0/10

SpaceX announced that Starship completed its 15th test flight and, after about 22.5 hours in space and roughly 14 orbits, returned to its Texas launch site and was caught directly by the launch tower&\#x27;s mechanical arms for the first time. The mission also deployed 26 next-generation Starlink V3 satellites. However, the Super Heavy booster did not return to the tower as planned and splashed down in the Gulf of Mexico, so SpaceX has not yet recovered both stages at the launch site on the same flight.

telegram · zaihuapd · Nov 14, 23:49

**「Background」** Starship is a two-stage launch vehicle consisting of the Super Heavy booster and the Starship upper stage; recovering both is central to SpaceX&\#x27;s reusable heavy-lift design. The reported mission was the program&\#x27;s 15th test flight, so it followed an extended flight-test campaign rather than being an initial demonstration. The upper stage&\#x27;s return from orbital velocity is a distinct recovery problem from the booster&\#x27;s return to the launch site.

**「Starlink capacity gain scales with payload load」** For Starlink users and partners, the practical payoff depends on how fully each Starship is loaded: SpaceX has said a Starship launch can deploy roughly 20× the capacity of a Falcon 9 launch carrying V2 satellites, but this flight deployed 26 V3 satellites, while SpaceX&\#x27;s own materials project up to about 60 V3 satellites per Starship flight. The roughly 20× capacity figure should therefore be read as a vendor projection contingent on near-full payloads and sustained cadence, not something demonstrated on this mission.

<details><summary>References</summary>
<ul>
<li><a href="https://cheatsheets.davidveksler.com/starlink-satellite-anatomy.html">Starlink V3 Satellite Specs: Size, Mass &amp; V1-V3 Anatomy</a></li>
<li><a href="https://starlink.com/updates/starlink-version-3-satellites">Starlink Version 3 Satellites</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#Starship`, `#spaceflight`, `#reusable spacecraft`, `#Starlink`

---

<a id="item-tech-news-4"></a>
### [Meituan releases LongCat-2.5 weights, claims all-Huawei Ascend training](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

Meituan&\#x27;s LongCat team released open weights for LongCat-2.5 a week after the model&\#x27;s launch, a 1.6-trillion-parameter agent model aimed at long, multi-step tasks such as coding; the weights use the MIT license and permit commercial use. The company claims the model was trained entirely on Huawei Ascend accelerators without Nvidia GPUs, activates about 48 billion parameters per token, and accepts text, image, and video inputs. Meituan reports 88.4 on Terminal Bench v2.1 versus 89.1 for Claude Opus 5, but the benchmark and all-Huawei training claims have not been independently verified in the supplied material.

telegram · zaihuapd · Nov 15, 11:08

**「Background」** LongCat-2.5 is a mixture-of-experts model: it has 1.6 trillion total parameters, but only about 48 billion are activated per token, so each token uses a fraction of the full network. Meituan&\#x27;s LongCat team published the weights roughly a week after the model&\#x27;s formal launch, moving LongCat-2.5 from an announced model to downloadable open weights.

**「Hardware independence with caveats」** Organizations weighing Huawei Ascend as an Nvidia alternative have another option: an MIT-licensed 1.6T-parameter model claimed to be trained entirely on Ascend, following Zhipu&\#x27;s GLM-5. Because the Ascend-only training claim and the 88.4 Terminal Bench v2.1 score are vendor-reported, teams should reproduce both on their own workloads before basing procurement or deployment decisions on them.

<details><summary>References</summary>
<ul>
<li><a href="https://huggingface.co/meituan-longcat/LongCat-2.5">meituan - longcat / LongCat - 2 . 5 · Hugging Face</a></li>
<li><a href="https://readalchemist.com/articles/glm-5-breaks-the-nvidia-monopoly-on-frontier-training">GLM-5 Breaks the NVIDIA Monopoly on Frontier Training</a></li>

</ul>
</details>

**Tags**: `#open-weight models`, `#AI agents`, `#Huawei Ascend`, `#LLM training`, `#benchmarks`

---

<a id="item-tech-news-5"></a>
### [PyPI project pages now show provenance and security signals](https://blog.pypi.org/posts/2026-11-06-ui-updates-complete/) ⭐️ 7.0/10

PyPI’s redesigned project pages are now live, adding provenance and security signals to the pages Python developers use to inspect packages. The Files tab shows whether a project has provenance—datasette is shown with it, while dlt is shown without—making release-integrity information visible on PyPI itself. Coverage varies by project rather than applying uniformly across the registry.

hackernews · rbanffy · Nov 14, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50497892)

**「Background」** PyPI&\#x27;s Trusted Publishing lets a project trust a specific CI service configuration as an OIDC publisher, so releases can be uploaded without long-lived API tokens. PEP 740 attestations build on those OIDC workflows: the same publishing job can automatically obtain a Sigstore certificate that binds the upload to a machine identity such as a GitHub repository and workflow, creating verifiable provenance.

**「Impact」** Python developers can now compare provenance status per project directly from the Files tab, as shown by datasette and dlt, making release verification a visible step on PyPI rather than an entirely external check.

**「Community discussion」** Commenters debated the trust model: time4tea argued that centering trust on “big cloud” providers promotes lock-in and is “a bit anti-pythonic,” while zoobab asked whether the security scanning itself is open source. samhclark said they want Sigstore-style keyless short-lived signatures to spread to more CI/CD providers, and mhils asked PyPI’s trusted publishing to support reusable workflows.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.trailofbits.com/2024/11/14/attestations-a-new-generation-of-signatures-on-pypi/">Attestations: A new generation of signatures on PyPI - The Trail of Bits...</a></li>
<li><a href="https://docs.pypi.org/trusted-publishers/">Getting Started - PyPI User Documentation</a></li>
<li><a href="https://yossarian.net/res/pub/soss-fusion-2024.pdf">[SOSS Fusion 2024] PEP 740 and PyPI : Bootstrapping Provenance ...</a></li>

</ul>
</details>

**Tags**: `#PyPI`, `#software supply chain security`, `#provenance`, `#open source`, `#package management`

---

<a id="item-tech-news-6"></a>
### [Tesla Cybercab terms require $299 monthly autonomy subscription](https://www.tesla.com/configurator/api/v4/terms?category=autonomy_subs&amp;amp;locale=en_US&amp;amp;model=cc&amp;amp;saleType=Sale) ⭐️ 7.0/10

Reports citing Tesla&\#x27;s Cybercab configurator terms say the vehicle costs $29,990 and requires a $299-per-month autonomous-driving subscription to operate. The terms state that Tesla can change the subscription price with one month&\#x27;s notice, and that nonpayment or violations can lead to suspension or cancellation; three accumulated warnings disable autonomous driving for one week. Cybercab operation is limited to designated areas, and unauthorized use on ride-hailing, delivery, or rental platforms is prohibited. Electrek notes that Cybercab and the Model Y used for Robotaxi share AI4 hardware and autonomous-driving software, while FSD for ordinary owners still requires human supervision.

telegram · zaihuapd · Nov 15, 01:10

**「Background: from a $30,000 robotaxi promise to a personal-use purchase」** Tesla CEO Elon Musk unveiled the Cybercab in 2024 as a roughly $30,000 driverless Tesla, and The Verge reports Tesla has now begun inviting selected customers to buy one for personal use. Gizmodo notes the ownership terms confine operation to Tesla-enabled Robotaxi geofences, which so far exist only in Texas.

**「Impact」** For buyers, operation is conditional on an ongoing $299 monthly payment on top of the $29,990 purchase price, and nonpayment can lead to suspension or cancellation. The terms also bar unauthorized use on ride-hailing, delivery, or rental platforms, limiting owners&\#x27; ability to use the vehicle for commercial revenue.

<details><summary>References</summary>
<ul>
<li><a href="https://gizmodo.com/the-terms-of-cybercab-ownership-dont-add-up-musk-admits-2000840094">Musk Admits $ 299 Monthly Cybercab Fee Is Too High</a></li>
<li><a href="https://www.theverge.com/transportation/1033844/tesla-personal-cybercab-orders-299-subscription-fine-print">Tesla is inviting some people to buy a Cybercab ‘for personal use ...</a></li>

</ul>
</details>

**Tags**: `#Tesla`, `#Cybercab`, `#autonomous driving`, `#subscription pricing`, `#robotaxi`

---

<a id="item-tech-news-7"></a>
### [FAA says nationwide ground stop linked to router in copper-to-fiber upgrade](https://www.theverge.com/transportation/1033898/faa-ground-stop-sean-duffy-faa-copper-wire) ⭐️ 7.0/10

US Transportation Secretary Sean Duffy said on November 14 that Friday&\#x27;s FAA nationwide ground stop stemmed from routine maintenance at a remote facility replacing aging copper wire with fiber; a newly installed router then failed, grounding thousands of flights. Duffy said the root cause remains unclear and could be a hardware fault, a configuration error or a mistake by contractor L3Harris. According to Duffy, the router sent more than 1,000 connection requests every 4 to 5 seconds to other routers, disrupting radar signals and aircraft communications. He called on Congress to provide additional funding for air-traffic-control modernization.

telegram · zaihuapd · Nov 15, 02:10

**「Background」** A nationwide ground stop is an FAA order that halts departures across the National Airspace System, typically invoked when controllers cannot assure safe separation of traffic. The facility involved in this incident was simultaneously performing routine maintenance to replace legacy copper cabling with fiber as part of ongoing upkeep of air traffic control infrastructure.

**Tags**: `#FAA`, `#network outage`, `#critical infrastructure`, `#router failure`, `#aviation`

---