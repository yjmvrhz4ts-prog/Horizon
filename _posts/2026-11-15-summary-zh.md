---
layout: default
title: "Horizon Summary: 2026-11-15 (ZH)"
date: 2026-11-15
lang: zh
---

> 从 33 条内容中筛选出 7 条重要资讯。

---

**科技新闻**
1. [Lovable 应用因 RLS 不足泄露护照信息与逾 20 万条私信](#item-tech-news-1) ⭐️ 8.0/10
2. [BiRefNet-lite 改写后手机 NPU 上 1024px 抠图 23.7ms](#item-tech-news-2) ⭐️ 8.0/10
3. [SpaceX 星舰第 15 次试飞完成轨道返回并被机械臂捕获](#item-tech-news-3) ⭐️ 8.0/10
4. [美团开源 1.6 万亿参数 LongCat-2.5，称全程使用华为升腾训练](#item-tech-news-4) ⭐️ 8.0/10
5. [PyPI 新版项目页上线，突出来源与安全信号](#item-tech-news-5) ⭐️ 7.0/10
6. [特斯拉 Cybercab 协议曝光：月租 299 美元方能行驶](#item-tech-news-6) ⭐️ 7.0/10
7. [FAA 全国停飞：换光纤升级引发路由器故障](#item-tech-news-7) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Lovable 应用因 RLS 不足泄露护照信息与逾 20 万条私信](https://www.crissyfield.de/research/lovable-en/) ⭐️ 8.0/10

Crissy Field 团队报告称，用 Lovable 构建的应用因行级安全（RLS）配置不足，暴露了护照信息和超过 20 万条私人消息。Lovable 安全负责人 Igor 在 Hacker News 评论中表示，根因正是 RLS 不足；他称平台会在发布前自动扫描每个应用，并向所有用户免费提供更深入的 SAST 扫描和“Fix”/自动修复选项。上述扫描与修复能力属于厂商说法，现有材料未披露受影响应用数量或数据主体范围。

hackernews · armcat · 11月14日 17:43 · [社区讨论](https://news.ycombinator.com/item?id=50499017)

**「背景」** 这类事件的技术前提是 Supabase 的行级安全（Row-Level Security，RLS）：当应用在浏览器端用匿名密钥直接访问 Postgres 表时，RLS 策略决定谁能读写哪些行，未启用或策略过宽的表实际上等同于对外公开。据安全厂商通报，此前已有 CVE-2025-48757（CVSS 9.3）专门记录 Lovable 生成、以 Supabase 为后端的应用中的 RLS 缺陷；另有分析指出 Lovable 内置扫描只检查策略是否存在，而不检查策略是否真正生效，需要逐表审计并改用 auth.uid\(\) 收紧策略。本次曝出的护照信息与逾 20 万条私信泄露，属于同一类配置缺陷。

**「影响」** 对使用 Lovable 和 Supabase 的开发者而言，直接后果是需要逐表核对 RLS 策略，尤其是沿用既有 Supabase 默认配置的项目；评论称这些旧项目可能仍受宽松默认值影响。发布前查看扫描结果并使用“Fix”或自动修复，不能替代开发者对实际数据访问路径的确认。

**「社区讨论」** 评论的争论集中在责任归属：SOLAR\_FIELDS 认为 Supabase 多年前为降低上手难度而采用宽松默认值，并提到有报告称 10 月 30 日的修复对既有项目未必生效；Oras 则认为泄密并非 AI 独有，只是 AI 生成应用数量多且更容易被非专业攻击者发现。liquid\_thyme 主张平台应采用默认拒绝的数据库、最小权限 API 和自动化认证测试，让不安全部署更难发生。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://elysiancrest.com/insights/custom-software/cve-2025-48757-lovable-rls-audit">CVE-2025-48757 &amp; Lovable RLS: What to Verify Before Launch</a></li>
<li><a href="https://www.brinztech.com/breach-alerts/brinztech-alert-critical-row-level-security-rls-vulnerability-cve-2025-48757-exposed-lovable-supabase-applications/">Critical Row Level Security (RLS) Vulnerability (CVE-2025 ...</a></li>
<li><a href="https://ptkd.com/journal/lovable-dev-supabase-rls-bypass-vulnerability">Lovable.dev Supabase RLS bypass: how it happens, how to fix it</a></li>

</ul>
</details>

**标签**: `#security`, `#AI-generated-code`, `#Supabase`, `#row-level-security`, `#app-builder`

---

<a id="item-tech-news-2"></a>
### [BiRefNet-lite 改写后手机 NPU 上 1024px 抠图 23.7ms](https://www.reddit.com/r/MachineLearning/comments/1xwuvaz/birefnetlite_at_1024px_fully_on_a_phone_npu_237/) ⭐️ 8.0/10

独立研究者称已将 BiRefNet-lite 改写为全 NPU 驻留的 int8 模型：在 Galaxy S26（Snapdragon 8 Elite Gen 5）上生成 1024×1024 掩码耗时 23.7 ms，S25 为 31.1 ms，7 Gen 1 为 182 ms，2,060 层全部运行在 NPU 上。原版在 1024px 下会内存不足，512px 时回退 CPU，耗时 677 ms、峰值内存 2.1 GB。改写包括精确图重写、用普通卷积替代可变形卷积、640px 骨干加两路输入生成 1024px 掩码，以及穿过导出 NPU 图的 8 位 QAT 蒸馏；权重、代码和 42 个骁龙芯片的预编译文件已以 MIT 许可公开。作者报告 int8 学生在 ECSSD 和 DUT-OMRON 上的 S-measure 与 fp32 教师相当，但这是自述结果，尚未独立验证；细结构数据集 DIS-VD 上低 0.017，DUT-OMRON 上有六个公开模型更好，且暂不支持 MediaTek 或 Tensor、功耗未测。

reddit · r/MachineLearning · /u/subhashg547 · 11月15日 12:58

**「背景」** BiRefNet-lite 是 ZhengPeng7 发布的 44.4M 参数开放权重图像分割模型，面向高分辨率二值图像分割与主体抠图。原版解码器包含 20 个可变形卷积，Swin 主干使用 5D/6D 张量和循环移位窗口，1024px 激活也超出手机片上内存，因此它无法直接编译并完整运行在手机 NPU 上。

**「影响」** 对需要 Android 端主体分割的开发者，作者公开的权重、代码和 42 个骁龙芯片预编译文件提供了可复现的集成路径，但适用性受限于骁龙平台：MediaTek 与 Tensor 不在支持范围，功耗尚未测量，细结构分割也存在精度损失。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/ZhengPeng7/BiRefNet_lite">ZhengPeng7/ BiRefNet _ lite · Hugging Face</a></li>
<li><a href="https://github.com/ZhengPeng7/BiRefNet">GitHub - ZhengPeng7/ BiRefNet : [CAAI AIR&#x27;24] Bilateral Reference for...</a></li>
<li><a href="https://www.promptlayer.com/models/birefnetlite/">BiRefNet _ lite | PromptLayer Models</a></li>

</ul>
</details>

**标签**: `#on-device AI`, `#mobile NPU`, `#model quantization`, `#image segmentation`, `#model optimization`

---

<a id="item-tech-news-3"></a>
### [SpaceX 星舰第 15 次试飞完成轨道返回并被机械臂捕获](https://www.spacex.com/launches/starship-flight-15) ⭐️ 8.0/10

SpaceX 宣布，星舰第 15 次试飞中，飞船在约 22.5 小时、绕地球约 14 圈后返回得克萨斯州发射基地，并首次由发射塔机械臂直接捕获，完成轨道返回后的回收。此次任务还部署了 26 颗新一代星链 V3 卫星。但超重型助推器未按计划返回发射塔，最终溅落墨西哥湾，因此火箭两级同时回收尚未实现。

telegram · zaihuapd · 11月14日 23:49

**「背景」** 星舰是 SpaceX 正在迭代测试的两级重型运载系统，飞船与超重型助推器都计划返回发射塔，由机械臂直接捕获，以支持重复使用。此次第 15 次试飞首次验证了飞船从轨道返回后的机械臂捕获，但助推器仍以溅落墨西哥湾告终，说明两级同时回收尚未完成。

**「对星链扩容与两级复用的影响」** 此次任务部署的 26 颗 V3 卫星是短期内最直接的影响：SpaceX 官方称，星舰单次发射为星座增加的容量约为猎鹰 9 号发射 V2 卫星批次的 20 倍，因此星舰能否按节奏执行发射，将直接决定 V3 星座扩容的速度。与此同时，超重型助推器本次仍在墨西哥湾溅落，两级同时回收尚未实现，星舰的完全复用能力仍需分别验证助推器返回与飞船塔架捕获这两条流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://starlink.com/updates/starlink-version-3-satellites">Starlink Version 3 Satellites</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#Starship`, `#spaceflight`, `#reusable spacecraft`, `#Starlink`

---

<a id="item-tech-news-4"></a>
### [美团开源 1.6 万亿参数 LongCat-2.5，称全程使用华为升腾训练](https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/) ⭐️ 8.0/10

美团 LongCat 团队在模型正式发布一周后公开了 LongCat-2.5 的权重，这是一个面向自主完成冗长多步骤任务（尤其是编程）的智能体模型，总参数约 1.6 万亿、每个 token 激活约 480 亿参数，支持文本、图像和视频输入，并以 MIT 许可证发布、允许商用。官方称训练全程使用华为升腾加速卡，未使用英伟达 GPU。在 Terminal Bench v2.1 上，官方报告的得分为 88.4，略低于 Claude Opus 5 的 89.1。上述训练硬件与基准成绩均为厂商说法，尚未见到独立验证。

telegram · zaihuapd · 11月15日 11:08

**「背景」** LongCat-2.5 采用混合专家（MoE）架构：总参数为 1.6 万亿，但每个 token 只激活约 480 亿参数，这种稀疏设计使超大模型在推理时不必调用全部参数。其 Hugging Face 模型卡将 LongCat-2.5 定位为面向长程智能体任务的原生多模态模型；公开报道提到的样例部署使用 194 张华为升腾加速卡。

**「影响」** 对开发者和企业来说，最直接的影响是 MIT 许可证允许商用部署与微调，无需按 token 支付厂商 API 费用；但 1.6T 总参数、每 token 激活约 480 亿的规模意味着自建推理仍需可观的算力集群，所以能否实际用上，取决于是否有足够的部署资源。若“全程使用华为升腾、未用英伟达 GPU”的说法成立，中国团队在出口管制下就多了一条不依赖英伟达的前沿训练路径；此前已有报道称 GLM-5 使用 10 万颗升腾 910B 完成训练，可作参照。不过美团这一训练硬件说法目前仅为厂商自述，尚未见独立复现或验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/meituan-longcat/LongCat-2.5">meituan - longcat / LongCat - 2 . 5 · Hugging Face</a></li>
<li><a href="https://the-decoder.com/meituan-releases-a-1-6-trillion-parameter-agent-model-that-never-touched-an-nvidia-gpu/">Meituan releases a 1.6-trillion-parameter agent model that ...</a></li>
<li><a href="https://readalchemist.com/articles/glm-5-breaks-the-nvidia-monopoly-on-frontier-training">GLM-5 Breaks the NVIDIA Monopoly on Frontier Training</a></li>

</ul>
</details>

**标签**: `#open-weight models`, `#AI agents`, `#Huawei Ascend`, `#LLM training`, `#benchmarks`

---

<a id="item-tech-news-5"></a>
### [PyPI 新版项目页上线，突出来源与安全信号](https://blog.pypi.org/posts/2026-11-06-ui-updates-complete/) ⭐️ 7.0/10

PyPI 重新设计的项目页面现已上线，项目文件列表会更清楚地显示来源证明（provenance）等安全信号，帮助开发者在下载安装前判断包的可信度。该消息来自 PyPI 官方博客，属于界面与信息展示层面的更新；现有材料没有说明 provenance 如何生成、验证，也未说明是否强制。社区分享的页面示例显示，有的项目（如 datasette）标注了 provenance，有的（如 dlt）没有。

hackernews · rbanffy · 11月14日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50497892)

**「背景」** PyPI 的 Trusted Publishing 允许项目将特定的 CI 配置设为受信任的 OIDC 发布者。PEP 740 与 Sigstore 的结合使现有的 Trusted Publishing 流程能够自动获取短期签名证书，并生成可公开验证的发布证明；新版项目页所展示的 provenance 信号正是建立在这一机制之上。

**「影响」** 对依赖 PyPI 的开发者来说，项目文件页现在可作为安装前检查 provenance 的快速入口；未显示该信号的项目不会在页面上获得同等提示，用户需另查发布流程。维护者若希望展示该信号，需要确保发布流程生成并提交 provenance，但材料未列出具体支持范围。

**「社区讨论」** 评论区总体欢迎更突出 provenance，但 time4tea 担心信任被集中到“大云”厂商并造成锁定，zoobab 则追问安全扫描本身是否开源。samhclark 希望 Sigstore 式无密钥短时签名更普及、并让更多 CI 服务支持安全 OIDC，mhils 则呼吁 Trusted Publishing 支持可复用工作流。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.trailofbits.com/2024/11/14/attestations-a-new-generation-of-signatures-on-pypi/">Attestations: A new generation of signatures on PyPI - The Trail of Bits...</a></li>
<li><a href="https://docs.pypi.org/trusted-publishers/">Getting Started - PyPI User Documentation</a></li>
<li><a href="https://yossarian.net/res/pub/soss-fusion-2024.pdf">[SOSS Fusion 2024] PEP 740 and PyPI : Bootstrapping Provenance ...</a></li>

</ul>
</details>

**标签**: `#PyPI`, `#software supply chain security`, `#provenance`, `#open source`, `#package management`

---

<a id="item-tech-news-6"></a>
### [特斯拉 Cybercab 协议曝光：月租 299 美元方能行驶](https://www.tesla.com/configurator/api/v4/terms?category=autonomy_subs&amp;amp;locale=en_US&amp;amp;model=cc&amp;amp;saleType=Sale) ⭐️ 7.0/10

一则汇总报道称，特斯拉公布的 Cybercab 自主驾驶订阅协议要求车主每月支付 299 美元订阅费，车辆售价为 29,990 美元；若不订阅，车辆将无法运行，特斯拉可提前一个月通知调价。条款还规定，欠费或违规使用可能导致订阅暂停或取消，累计三次警告则自动驾驶功能停用一周；车辆仅在指定区域运行，未经授权不得接入网约车、配送或租赁平台。Electrek 指出，Cybercab 与用于 Robotaxi 的 Model Y 搭载相同的 AI4 硬件并运行同一套自动驾驶软件，但面向普通车主的 FSD 仍需人类监督。上述内容来自聚合摘要对条款页面的概述，尚无特斯拉官方说明或独立核实。

telegram · zaihuapd · 11月15日 01:10

**「背景」** 特斯拉在 2024 年发布 Cybercab 时，将其定位为售价约 3 万美元、可无人驾驶的车型；如今公司开始邀请部分用户以个人用途购买，并附带强制性的每月 299 美元订阅。早期条款还显示，车辆只能在特斯拉启用的 Robotaxi 地理围栏及其他运营限制内使用，而现有围栏均位于得克萨斯州。

**「影响」** 对购车者而言，这笔订阅费把年度使用成本抬高约 3,588 美元，且条款禁止接入网约车、配送或租赁平台，意味着无法用营运收入抵消该支出；地理围栏和“三次警告停用一周”的机制则直接压缩了车辆可用范围与容错空间。若条款照此执行，买家在评估总拥有成本时需把订阅费与使用限制一并计入，而非只看 29,990 美元的标价。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://gizmodo.com/the-terms-of-cybercab-ownership-dont-add-up-musk-admits-2000840094">Musk Admits $ 299 Monthly Cybercab Fee Is Too High</a></li>
<li><a href="https://www.theverge.com/transportation/1033844/tesla-personal-cybercab-orders-299-subscription-fine-print">Tesla is inviting some people to buy a Cybercab ‘for personal use ...</a></li>

</ul>
</details>

**标签**: `#Tesla`, `#Cybercab`, `#autonomous driving`, `#subscription pricing`, `#robotaxi`

---

<a id="item-tech-news-7"></a>
### [FAA 全国停飞：换光纤升级引发路由器故障](https://www.theverge.com/transportation/1033898/faa-ground-stop-sean-duffy-faa-copper-wire) ⭐️ 7.0/10

美国交通部长 Sean Duffy 11 月 14 日表示，FAA 周五下令的全国停飞源于一处偏远设施将老旧铜线更换为光纤的例行维护，新装路由器随后出现问题，导致数千架次航班停飞。他说根因仍不明确，可能是硬件故障、配置错误或承包商 L3Harris 的失误；该路由器每 4 到 5 秒向其他路由器发出逾千次连接请求，干扰了雷达信号和飞机通信。Duffy 借此呼吁国会追加空管现代化资金。

telegram · zaihuapd · 11月15日 02:10

**「背景」** 全国停飞是 FAA 在空管系统无法保证安全运行时暂停航班起飞的应急处置。此次维护发生在偏远设施，任务是把老旧铜线更换为光纤；新路由器处在网络升级的关键连接位置，其异常会波及依赖该设施的雷达信号与飞机通信。

**标签**: `#FAA`, `#network outage`, `#critical infrastructure`, `#router failure`, `#aviation`

---