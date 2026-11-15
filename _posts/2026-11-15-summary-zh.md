---
layout: default
title: "Horizon Summary: 2026-11-15 (ZH)"
date: 2026-11-15
lang: zh
---

> 从 33 条内容中筛选出 6 条重要资讯。

---

**科技新闻**
1. [SpaceX 星舰第 15 次试飞实现轨道返回后机械臂捕获](#item-tech-news-1) ⭐️ 8.0/10
2. [Lovable 应用 RLS 不足泄露护照信息与 20 万私信](#item-tech-news-2) ⭐️ 8.0/10
3. [BiRefNet-lite 以 int8 在手机 NPU 跑 1024px 抠图](#item-tech-news-3) ⭐️ 8.0/10
4. [美团开源 LongCat-2.5：MIT 许可、称全程用升腾训练](#item-tech-news-4) ⭐️ 8.0/10
5. [Papr 自报 LongMemEval-S 96.0%，并公开检索消融结果](#item-tech-news-5) ⭐️ 7.0/10
6. [FAA 全国停飞：铜线换光纤后路由器故障，根因未确认](#item-tech-news-6) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [SpaceX 星舰第 15 次试飞实现轨道返回后机械臂捕获](https://www.spacex.com/launches/starship-flight-15) ⭐️ 8.0/10

SpaceX 宣布，星舰第 15 次试飞中，飞船在约 22.5 小时、绕地球约 14 圈的飞行后返回得克萨斯州发射基地，并首次由发射塔机械臂直接捕获，完成轨道返回后的回收。任务还部署了 26 颗新一代星链 V3 卫星。不过，超重型助推器未按计划返回发射塔，而是在墨西哥湾溅落，因此这次尚未实现两级同时回收；上述结果来自 SpaceX 的公布，而非独立测量。

hackernews · ls612 · 11月14日 21:22 · [社区讨论](https://news.ycombinator.com/item?id=50500963)

**「背景」** 星舰是两级系统：超重型助推器负责第一级推进，星舰飞船则进入轨道并执行载荷任务。所谓完全重复使用，需要这两级都能受控返回、被回收并再次使用，而不只是回收其中一级。

**「对复用的实际影响」** 对卫星客户来说，捕获成功本身还不等于可用运力：同一艘飞船尚未复飞，再入后隔热罩的状况将决定检修成本与周转时间，而能否快速复用正是星舰报价低于现役火箭的前提。此次超重型助推器未能按计划返回发射塔、最终溅落在墨西哥湾，说明两级同时回收这一成本关键环节仍未验证；此前第 14 次试飞同样部署了 26 颗下一代星链卫星，但任务并非完全成功，因此星舰的商业载荷节奏仍取决于复用验证而非单次捕获。

**「社区讨论」** 评论普遍称赞工程团队，但最实质的讨论集中在可复用性：ChuckMcM 认为助推器若多携带几吨推进剂和氧化剂或许也能被捕获，并称最终入轨质量分数仍不清楚；small\_model 则把热防护罩能否承受再入视为关键，认为下一步是两级同时回收并复飞同一飞船。上述判断均为社区推测，并非任务公布的数据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.fool.com/investing/2026/10/31/spacex-says-starship-flies-commercial-payloads-thi/">SpaceX Says Starship Flies Commercial Payloads ... | The Motley Fool</a></li>

</ul>
</details>

**标签**: `#SpaceX Starship`, `#reusable rockets`, `#spaceflight`, `#hardware engineering`, `#Hacker News`

---

<a id="item-tech-news-2"></a>
### [Lovable 应用 RLS 不足泄露护照信息与 20 万私信](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

一项安全调查发现，部分用 Lovable 构建的应用因行级安全（RLS）配置不足和默认设置不安全，暴露了敏感用户数据，包括护照信息和超过 20 万条私信。Lovable 安全负责人回应称，这些应用的根因是 RLS 不足，并称平台会在发布前自动扫描每个应用，还提供更深入的 SAST 扫描、修复建议和自动修复。调查作者与部分评论者则把部分责任指向 Supabase 的默认配置，并称有报告显示旧项目可能仍沿用原有默认值。

hackernews · armcat · 11月14日 17:43 · [社区讨论](https://news.ycombinator.com/item?id=50499017)

**「背景」** 这批应用的风险点集中在 Supabase/Postgres 的行级安全（RLS）上：它决定不同登录用户能读写哪些数据行，缺失或策略过宽时，客户端就可能直接读到他人的记录。Lovable 安全负责人称根因正是 RLS 不足；评论中还有人把部分责任指向 Supabase 早年便于上手的默认设置，并称相关默认值问题虽在 10 月 30 日宣布修复，存量项目是否仍受影响仍有争议。

**「影响」** 对使用 Lovable 生成应用并依赖 Supabase 默认配置的开发者来说，具体行动是上线前核查 RLS 策略、匿名访问权限和前端可调用的 API 范围；调查显示，配置不足会让其他用户直接读到护照信息或私信等本应受限的数据。

**「社区讨论」** 评论区的核心分歧是责任归属：一位评论者认为 Supabase 多年前为降低上手门槛而采用的默认配置也应负责，并称有报告显示旧项目仍沿用这些默认值；Lovable 安全负责人则强调平台已提供发布前扫描、SAST 和自动修复，将根因归于应用层 RLS 不足。另有评论者认为，这类 AI 生成应用数量多、攻击门槛低，普通用户难以判断风险。

**标签**: `#application security`, `#AI coding tools`, `#data exposure`, `#Supabase`, `#Row-Level Security`

---

<a id="item-tech-news-3"></a>
### [BiRefNet-lite 以 int8 在手机 NPU 跑 1024px 抠图](https://www.reddit.com/r/MachineLearning/comments/1xwuvaz/birefnetlite_at_1024px_fully_on_a_phone_npu_237/) ⭐️ 8.0/10

独立研究者将 BiRefNet-lite 重写并做 int8 量化，使其在 1024×1024 分辨率下完全运行在高通手机 NPU 上，并开放了权重、42 个已编译芯片文件和 MIT 许可代码。作者报告在 Galaxy S26（骁龙 8 Elite Gen 5）上生成 1024×1024 掩码耗时 23.7 ms，S25 为 31.1 ms，7 Gen 1 为 182 ms，2,060 层全部在 NPU 上运行；原始模型在 1024px 会内存溢出，512px 时回退 CPU，耗时 677 ms、峰值 2.1 GB。为适配 NPU，作者采用 4D 窗口划分、无循环 roll 的移位窗口和通道拆分卷积等精确图重写，并以普通卷积替代可变形卷积、用 640px 骨干生成 1024px 掩码，再通过导出的 NPU 图做全 8 位 QAT 蒸馏。作者称在未参与训练的 ECSSD 和 DUT-OMRON 上，int8 学生模型与 fp32 教师的 S-measure 基本持平，但在细结构数据集 DIS-VD 上低 0.017，且暂不支持 MediaTek/Tensor、尚未测量功耗。

reddit · r/MachineLearning · /u/subhashg547 · 11月15日 12:58

**「背景」** BiRefNet-lite 是面向高分辨率图像分割的轻量模型，但原始结构在解码器中含有 20 个可变形卷积，Swin 模块使用 5D/6D 张量并依赖循环 roll 实现移位窗口，因此难以编译到手机 NPU；1024px 的激活值也超出片上内存。作者因此保留相同输出语义重写计算图，并针对 NPU 做 int8 量化与知识蒸馏。

**「影响」** 对想在 Android 相册里做本地抠图的开发者来说，这条路径目前只覆盖骁龙设备：作者已为 42 款骁龙芯片预编译成单个 NPU 子图，但明确不支持 MediaTek 和 Tensor；而据 tool-2-3，Galaxy S26 在不同地区分别搭载 Exynos 2600 与骁龙 8 Elite Gen 5，Exynos 版本的用户无法走这条 NPU 路径。作者尚未测量功耗，若要把它做成常驻的相册功能，实际续航与发热需要自行实测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.promptquorum.com/fr/local-llms/galaxy-s26-local-ai-on-device-2026">Galaxy S 26 IA Locale: Galaxy AI et NPU Fonctionnement</a></li>

</ul>
</details>

**标签**: `#on-device ML`, `#int8 quantization`, `#NPU deployment`, `#image segmentation`, `#model optimization`

---

<a id="item-tech-news-4"></a>
### [美团开源 LongCat-2.5：MIT 许可、称全程用升腾训练](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

美团 LongCat 团队在模型发布一周后公开了 LongCat-2.5 的权重，采用 MIT 许可证、可商用，面向需要自主完成多步骤任务的智能体，尤其是编程场景。官方称该模型总参数为 1.6 万亿，每个 token 激活约 480 亿参数，支持文本、图像和视频输入，并称训练全程使用华为升腾加速卡、未使用英伟达 GPU。官方还称其在 Terminal Bench v2.1 上得分 88.4，略低于 Claude Opus 5 的 89.1；这些均为厂商说法，现有材料未提供更详细的技术细节或独立复现结果。

telegram · zaihuapd · 11月15日 11:08

**「背景」** LongCat-2.5 并非首次亮相：据源报道，LongCat 团队在一周前已正式发布该模型，此次是随后公布权重。此前公开的是模型发布信息，现在新增的是 MIT 许可下的可商用权重；而“全程使用华为升腾、未用英伟达 GPU 训练”仍是美团方面的说法。

**「试用与选型」** 想在智能体编程任务中评估 LongCat-2.5 的开发者可在 OpenCode 中获得两周免费使用窗口，但 88.4 的 Terminal Bench v2.1 成绩尚未经第三方验证，生产选型应安排自己的任务集复测。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=xYo_lFvVKpY">LongCat 2 . 5 Is Now FREE on OpenCode?! - YouTube</a></li>
<li><a href="https://tpsreport.news/models/longcat-2-5">LongCat - 2 . 5 specs, benchmarks and changelog | TPS</a></li>

</ul>
</details>

**标签**: `#open-source LLMs`, `#agentic coding`, `#Huawei Ascend`, `#model training`, `#benchmarks`

---

<a id="item-tech-news-5"></a>
### [Papr 自报 LongMemEval-S 96.0%，并公开检索消融结果](https://www.reddit.com/r/MachineLearning/comments/1xwnloh/longmemevals_960_with_the_official_judge_and_what/) ⭐️ 7.0/10

Papr 报告其记忆检索系统在 LongMemEval-S 全部 500 道题上达到 96.0%，使用官方答案提示词和未修改的 gpt-4o-2024-08-06 评审模型，并公开逐题答案与评审标签，称官方指标脚本可复现这些数字。该公司还披露，470 道可答题中有 460 道（97.9%）的证据会话位于检索前 5；把检索从 top-5 扩到 top-20 后，11 题改善、8 题变差，净增 3 题，时间推理从 123/133 升至 130/133，拒答维持 27/30。Papr 说明这些结果来自其自报，top 20 是在查看 top-5 错误后选定的，因此 96.0% 可视为在该题集上调优过；运行波动约 ±3 题，96.0 与 95.6 应看作持平。

reddit · r/MachineLearning · /u/remoteinspace · 11月15日 05:40

**「背景」** 长时记忆类基准的典型流程是：先检索出历史会话，再交给一个“阅读器”模型作答，最后由 LLM 裁判按官方提示词打分；LongMemEval-S 共有 500 道问题，其中包含 133 道时序推理题和 30 道应拒答（abstention）题。由于各家公布的分数常使用不同的裁判和 token 预算（本文即指出 Chronos 的 95.6% 使用全上下文与多轮代理、Hindsight 的 94.6% 换用了不同的裁判），跨系统的横向比较并不牢靠，这正是本次强调使用官方答案提示词和未修改的 gpt-4o-2024-08-06 裁判、并公开逐题答案与裁判标签的原因。

**「影响」** 公开逐题产物让评估者可以复算结果，但跨系统比较仍受评审模型和 token 预算不同的限制；开发者若引用该成绩，应区分官方评审下的自报结果与独立复现。其消融显示 top-20 仅净增 3 题，不足以证明扩大检索普遍更优，而 gpt-5-mini 在相同检索下达到 94.4%，提示剩余错误更多来自阅读器而非召回。

**标签**: `#llm-memory`, `#retrieval-augmented-generation`, `#benchmarks`, `#evaluation`, `#long-context`

---

<a id="item-tech-news-6"></a>
### [FAA 全国停飞：铜线换光纤后路由器故障，根因未确认](https://www.theverge.com/transportation/1033898/faa-ground-stop-sean-duffy-faa-copper-wire) ⭐️ 7.0/10

美国交通部长 Sean Duffy 于 11 月 14 日表示，FAA 周五下令的全国停飞与一处偏远设施的例行维护有关：该设施将老旧铜线更换为光纤，随后新装路由器出现异常，导致数千架次航班停飞。他说，故障路由器以每 4 到 5 秒超过 1000 次连接请求冲击其他路由器，干扰雷达信号和飞机通信，但根因仍未确认，可能是硬件故障、配置错误或承包商 L3Harris 的失误。Duffy 同时呼吁国会追加空管现代化资金。

telegram · zaihuapd · 11月15日 02:10

**「背景」** 这起全国停飞发生在 2026 年 11 月 13 日 20:54 UTC，FAA 当时以通信中断为由发布停飞令。受影响的是 L3Harris 管理的一套老旧通信系统，当时正在进行铜线换光纤的改造；交通部长 Sean Duffy 次日表示，偏远设施升级后的一台路由器使系统过载，但根因仍在调查。

**「实际影响」** 对旅客和航空公司而言，停飞令约四小时后解除，但据 FlightAware 统计，超过 1.1 万架次美国航班被延误或取消，航班时刻表预计到周日才能恢复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/2026_FAA_nationwide_ground_stop">2026 FAA nationwide ground stop - Wikipedia</a></li>
<li><a href="https://www.cnbc.com/2026/11/14/faa-ground-stop-flights-resume-delays.html">Ground stop followed contractor upgrade to L 3 Harris telecom system...</a></li>
<li><a href="https://www.nytimes.com/live/2026/11/14/us/faa-nationwide-ground-stop-flights">Upgrade Work Blamed for Nationwide Flight Shutdown, Duffy Says</a></li>
<li><a href="https://www.theguardian.com/world/2026/nov/13/faa-nationwide-ground-stop-flights">Flights slowly resume after US aviation agency lifts nationwide ...</a></li>
<li><a href="https://weather.com/2026/11/13/travel/faa-nationwide-ground-stop-equipment-outage-flights">US air travel schedule should recover from ground stop by Sunday...</a></li>

</ul>
</details>

**标签**: `#FAA`, `#网络故障`, `#路由配置`, `#空管基础设施`, `#系统可靠性`

---