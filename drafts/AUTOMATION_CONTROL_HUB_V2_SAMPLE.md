# DRAFT｜全系统自动化与智能中枢总树｜原格式复刻・13大核心・现役＋规划全量对账

> **仅打样。不得替代或修改 Drive 原自动化中枢、三业务线 Canonical、02_AUTOMATION_REGISTRY、任何现役 workflow。**
>
> 这版只做一件事：把“已经存在的自动化能力”与“三条业务线最近已经规划、但尚未施工完的重要自动化”挂回同一棵树，便于 Founder 一眼对账。
>
> 状态只写架构成熟度，不写死瞬时 `active/published/execution`；运行真相仍必须去当前 runtime / provider 现场读。

```text
====================================================================================================
             全系统自动化与智能中枢总树（Founder 原格式复刻 · 13大核心）
          【现役能力 + 已规划重要自动化一起对账｜不造第二系统｜不改旧树】
====================================================================================================
│
├── 💳 01. 交易、收款与订单事实中枢 ─────────────────────▶ 【原生真相源已确定｜不另造系统】
│   ├── 🎯 目的：所有“有没有付钱、付了多少、订单到哪一步”只认原生交易事实，给后面的财务、履约、数据回读提供唯一真相。
│   ├── 🧩 三线挂载：AuraSync（Shopify 下单/付款/弃购/退款）；XUJIE（Shopify Draft Order / PayPal / T/T / B2B付款状态）；Sierra（服务定金/尾款/收款事实）。
│   ├── 🔔 值得自动化的事件：付款成功、付款失败、弃购、高价值订单、退款、取消、异常订单；触发后只把必要事件送去 02/08/10/11/12。
│   ├── 🛠 现状：Shopify / 支付原厂已经承担交易真相源；02 Registry 只做定位，不缓存旧运行状态。
│   ├── 🔴 缺口：三条业务线的“订单事件 → 财务/履约/客户跟进/经营简报”还没有全部统一成稳定事件路由。
│   └── 🚀 怎么做：优先原厂 Webhook / API + 现有 n8n 编排；不建第二套 OMS，不复制订单数据库，不把旧 execution 当当前状态。
│
├── 📑 02. 财务、利润、报税与外贸单证自动化 ─────────────▶ 【部分已有｜自动串联待补】
│   ├── 🎯 目的：每笔真钱都能自动回答“实收多少、成本多少、净赚多少、该生成什么单证、季度报税要留什么凭证”。
│   ├── 💰 对账：Shopify / PayPal / Stripe / T/T / 国内账户流水 → 支付手续费 / 运费 / 退款 / 破损等真实成本 → 单单净利润。
│   ├── 📄 XUJIE：报价单、形式发票 PI、商业发票、装箱单、B2B付款与出货资料自动带入订单事实。
│   ├── 📄 AuraSync：团队订单收据/发票、国际运输与付款凭证；Sierra：服务收入、成本、客户发票/收款记录。
│   ├── 🧾 报税：按季度自动归集“收入流水 + 平台手续费 + 物流 + 可核成本 + 退款”到结构化表，供个体户做账使用。
│   ├── 🛠 现状：平台原生记账/交易数据有基础；B2B 单证和季度汇总仍有人工环节。
│   ├── 🔴 缺口：跨账户对账、利润口径、订单→PI/装箱单→付款→发货之间尚未完全自动串联。
│   └── 🚀 怎么做：标准模板 + 原厂数据 + n8n/Google Docs/Sheets 薄接入；不为了“财务自动化”先上重型 ERP/财务大系统。
│
├── 🔍 03. 市场情报、用户原声与商业信号雷达 ─────────────▶ 【核心能力｜多源覆盖继续补齐】
│   ├── 🎯 目的：机器持续找到“已经出现需求/变化/痛点的人”，而不是先写文案再到处撞人。
│   ├── 🚀 Sierra：重点抓 Shopify 招聘、改版/迁移、Liquid Bug、速度/CLS/移动端转化、App 差评、技术栈变化、公开求助与平台发标。
│   │   └── Sierra 六台获客机器归位：熟人/连接者→04；信号主动雷达→本节点；Upwork/Storetasker等市场意图→本节点；Agency白标→04；需求衍生内容→06/07；第三方信任→13。
│   ├── 🪨 AuraSync：桌搭/键盘/EDC 零售店扩品、Creator合作、正在开团的 Group Buy、Remote/Design Team、竞品 Review 差评、搜索需求与价格/页面变化。
│   ├── 🍵 XUJIE：海外茶商/茶器店/画廊/茶空间/礼赠采购、国内茶空间、展赛/文化机构/媒体节点、采购与合作信号。
│   ├── 📡 共用能力：竞品价格变化、页面变化、评论/VOC、关键词/搜索需求、公开社区求助、招聘/采购/合作窗口；统一证据封套、去重、限流、轮换。
│   ├── 🛠 现状：现有 Signal/Revenue Radar 与多源方案已有；过去曾发生单源偏科、429/OOM、数据断水等问题，因此禁止全源高并发硬扫。
│   ├── 🔴 缺口：不同人群的数据源轮换、稳定抓取、why-now 证据、同一目标跨源去重仍需持续真实运行验证。
│   └── 🚀 怎么做：原厂/成熟抓取器优先，Round-Robin 轮巡 + 小并发 + 失败隔离；输出只给 04，不直接替用户群发。
│
├── ✉️ 04. 全人群全渠道自适应外联与自动跟进中枢 ─────────▶ 【链路已有｜全渠道闭环待补】
│   ├── 🎯 目的：对象在哪里活跃，就在哪里联系；自动完成“线索合格 → 最合适渠道 → 个性化消息 → 回复 → 跟进 → 报价/付款入口”。
│   ├── 👥 Sierra：DTC店主/Shopify负责人（Email/LinkedIn/官网）；Upwork/Storetasker（原平台）；Agency白标伙伴（Email/LinkedIn/暖介绍）；Warm Network（转介绍/直接联系）。
│   ├── 👥 AuraSync：桌搭零售商（官网/IG/采购邮箱）；Creator（IG/YouTube/TikTok商务入口）；Group Buy 团长（Geekhack/Reddit/Discord）；团队客户（LinkedIn/官网）。
│   ├── 👥 XUJIE：茶商/茶器店/画廊（WhatsApp/采购邮箱/IG）；国内茶空间（微信/小红书/电话）；礼赠/机构（官网/企业联系人）。
│   ├── ✍️ 消息原则：利益前置、摩擦尽量低、只说有证据的事实；自动读取对应 Service/Product Truth，禁止代码日志腔、泛模板和强行冷邮件。
│   ├── 🔁 自动跟进：30天去重、已有草稿去重、已联系去重；Reply 后进入高意向识别 → Scope/Proposal/Quote → Payment Gate；未回复才进入有边界的 follow-up。
│   ├── 🛠 现状：Gmail 草稿/Telegram 卡片/部分渠道规则已有；三线高转化回复规范已建立。
│   ├── 🔴 缺口：各渠道真实 webhook/回读/账号授权并不齐全，不能把“有话术规范”写成“全平台自动回复已上线”。
│   └── 🚀 怎么做：一条共享 Router + 各平台薄适配；缺授权就标一次外部阻断，不安装第二套 Outreach/CRM/Agent 系统。
│
├── 🛠 05. Sierra 技术搜证、证明、成交与交付自动化 ────────▶ 【Sierra 专用｜阶段化自动化待完善】
│   ├── 🎯 目的：不用免费打工，用越来越强的客观证据推动“回复 → First Yes → 定金 → 交付 → 案例/转介绍”。
│   ├── ① 冷外联前：只抓真实技术事实（技术栈、移动端硬伤、速度/CLS、明显 UX/CRO 摩擦）＋极窄截图；不先做完整改版。
│   ├── ② 对方回复后：针对已确认痛点自动准备 Before/After 极窄证明、Scope Memo、报价/Proposal。
│   ├── ③ 深意向/付定金前：Staging Theme、短录屏、实施范围/验收标准，推动付款。
│   ├── ④ 交付后：Acceptance → Case/Proof → Review → Referral / Partner → 回灌 03/04/06/13，形成下一轮更强信任。
│   ├── 🧰 现役刀具只负责事实：Playwright / httpx / 技术识别等；不得让审计工具自己编营销结论。
│   ├── 🛠 现状：人工搜证/截图/交付规范成熟，部分依赖已就绪；自动截图、自动标准化证据与 Case writeback 仍需实跑。
│   ├── 🔴 缺口：从 Signal → Evidence → Message → Reply → Scope → Payment → Delivery → Proof 的全链还没有每一段都自动且可读回。
│   └── 🚀 怎么做：只在真实 Sierra 机会触发时调用本节点；不复制给 AuraSync / XUJIE，不建立“通用技术审计平台”。
│
├── 📣 06. 自营内容生产与社媒增长发射台（完整 13 阶段） ───▶ 【重点施工｜13阶段结构已锁定】
│   ├── 🎯 核心宗旨：不从零自嗨写内容；先找平台真实赢家，再拆赢钱机制，再换成三条业务线自己的真实产品/服务，最后用真钱数据回读。
│   ├── 00. 锁死真钱目标 ─────────▶ 进站 / 加购 / Checkout / Purchase；播放量不能替代真钱。
│   ├── 01. 找真钱 Winner ─────────▶ 小红书现有 MCP / TikHub / Instaloader / yt-dlp 等按平台找各自赢家。
│   ├── 02. 剥离伪爆款 ───────────▶ WF-05 / 账号基线 / 异常表现过滤，避免只看绝对点赞量。
│   ├── 03. 商业＋视觉双层拆解 ───▶ Pattern + Qwen3-VL；只有缺可复用字幕时才用 faster-whisper。
│   ├── 04. 锁死赢钱核心 ─────────▶ Hook / Proof / Offer / 节奏里哪些不能改。
│   ├── 05. 品牌转译 ─────────────▶ Gemini 只负责品牌/平台适配；必须经过 Product Truth Guard。
│   ├── 06. H3 镜头级蓝图 ────────▶ MiniMax H3 官方提示词 Skill；真实产品几何/工艺边界不能乱改。
│   ├── 07. 真实视频生成 ──────────▶ AutoDL + MiniMax H3；失败才按真实原因处理，不随手换一堆模型。
│   ├── 08. 成品封装质检 ──────────▶ 比例/字幕/音画/版式/产品真相；不合格 HOLD。
│   ├── 09. 全渠道排程发射 ────────▶ 海外 Postiz；国内只走已经授权的现役通道；没有 Aura 国内账号就不串用 Sierra/XUJIE 账号。
│   ├── 10. 真钱漏斗回读 ─────────▶ 每条内容唯一 run_id + UTM → PostHog → Shopify。
│   ├── 11. 归因诊断 ─────────────▶ 判断 Hook / Proof / Offer / Format 谁真正赢。
│   └── 12. 赢家复利放大 ──────────▶ 保留 LOCKED CORE → 变体家族 → 再分发；普通失败自动重试/隔离，Founder 日常操作目标=0。
│
├── 🌐 07. SEO、搜索需求与 Google 免费流量自动化 ─────────▶ 【规划明确｜已有基础，真钱闭环待收口】
│   ├── 🎯 目的：抓住“已经在 Google 主动搜索问题/产品”的成熟需求，让搜索词直接连到页面、加购和付款。
│   ├── 00 技术基础：Search Console、sitemap、抓取/404/索引健康；新页面发布后只做必要的 URL Inspection / Request Indexing。
│   ├── 01 搜索需求：真实 Query / Impression / Click + Google Trends；不凭空批量造关键词。
│   ├── 02 搜索意图：购买 / 痛点 / 比较 / 学习 → 决定用商品页、场景解决页、对比页还是文化/技术指南承接。
│   ├── 03 关键词→页面：Title / Meta / Alt / 内链 / PDP / Solution / Comparison；优先真钱页面，不先全站大改。
│   ├── 04 收录回读：提交 ≠ 已收录；必须等 Google 真实回读后才改状态。
│   ├── 05 免费商品流：Shopify ↔ Google Merchant Center / Free Product Listings；原生通道优先。
│   ├── 06–07 收益闭环：Search Console → UTM/页面 → PostHog → Shopify ATC/Checkout/Purchase，哪个词带真钱就继续扩。
│   ├── 三线挂载：AuraSync（产品/场景/材质搜索）；XUJIE（紫砂/工艺/茶器/文化搜索）；Sierra（真实 Shopify 痛点衍生技术内容与服务搜索）。
│   ├── 🛠 现状：AuraSync 已有 GSC / sitemap / URL Inspection / Merchant Center 基础记录；自然搜索→购买仍需真实样本回读。
│   └── 🚀 怎么做：先原生 Google + Shopify；长期排名监测、程序化 SEO、付费广告自动化都属于到量后再启用，不提前装系统。
│
├── 💬 08. 私信、客服、售后、复购与客户生命周期中枢 ───────▶ 【基础可用｜高量自动化规划中】
│   ├── 🎯 目的：把“点赞闲聊”和“询价/索样/合作/技术需求”分开；真正客户从第一次咨询一直跟到成交、售后、复购。
│   ├── 🔎 私信过滤：点赞/无意义互动静默；询价、索样、合作、报价、技术问题进入高意向通道。
│   ├── ✍️ 自动草拟：根据三线不同 Truth 生成低摩擦回复；Sierra 回 Scope/可行性，Aura 回产品/合作，XUJIE 回茶器/B2B/定制。
│   ├── 🛒 电商生命周期：弃购提醒 → Follow-up → Nurture → Win-back；不得无限骚扰，必须有频次/退出边界。
│   ├── ↩️ 售后学习：退款/退货原因、破损/物流问题、Review/差评、客户满意度 → 回灌产品/包装/页面/内容。
│   ├── 🛠 现状：Gmail / Shopify Inbox / 部分自动回复规范已有；当前咨询量小，人工处理仍然可能比上重系统快。
│   ├── 🔴 缺口：多渠道真实消息接入、统一会话上下文、售后原因结构化、老客复购触发尚未全面跑通。
│   └── 🚀 怎么做：低量阶段原生 Inbox/Gmail + 现有 Router；只有咨询明显放大后才启 Chatwoot，禁止提前建空 CRM。
│
├── 🧱 09. Product Truth、商品资料、店铺健康与数字销售资产中枢 ─▶ 【原生主档已定｜Truth 贯穿待加强】
│   ├── 🎯 目的：任何外联、内容、SEO、客服、报价都只读取一份当前真资料，禁止“各写各的版本”。
│   ├── AuraSync：Shopify Products + Aura Product Master + Fired-QC/库存/交期/材质/图片事实；未过 Fired-QC 的实物承诺自动 HOLD。
│   ├── XUJIE：现行产品/器型/泥料/容量/价格、B2B Price Sheet、图录、一器入席录、C2PA/存证；已删除产品不得因旧文件复活。
│   ├── Sierra：服务矩阵、能力边界、Pricing / First Yes、Proposal / Proof、案例与交付事实；不把未做过的案例包装成已交付。
│   ├── 店铺运营：Listing/Variant/价格/包装尺寸/翻译/库存展示/Google Merchant 同步/重要配置漂移，只在发生真实变化时触发检查。
│   ├── 销售资产：Sell Sheet / B2B报价 / Creator Pack / Proposal / Catalog / Evidence 一次生成，多节点复用。
│   ├── 🛠 现状：三线都有自己的现有 Truth/Canonical/资料资产；旧文件多，历史污染是主要风险之一。
│   ├── 🔴 缺口：Truth 变化后的自动传播、旧资产失效、不同渠道重新生成时的 Guard 还需要更严格闭环。
│   └── 🚀 怎么做：原生 Shopify / 当前 Drive Authority 为真相源；不装第二 PIM，不让 Gemini/Agent 自创规格、库存、交期、功效或价格。
│
├── 📦 10. 采购、工坊、QC、库存、仓储、发货与物流自动化 ─────▶ 【原生/人工可用｜事件自动化待补】
│   ├── 🎯 目的：从“要不要补货/生产”到“客人有没有签收”都能被真实状态驱动，但小规模阶段不被 ERP 绑架。
│   ├── AuraSync：工坊/模具/生产批次 → 出窑/烧成 QC → 可售库存 → 打包 → 国际发货；Fired-QC 未过不得自动承诺现货/寄样。
│   ├── XUJIE：宜兴工坊/现货/定制排期、陶刻/包装、B2B 批量备货、装箱与国际物流；高客单订单必须保留人工质量判断。
│   ├── 库存：On-hand / Available / Safety Stock / 低库存 / 滞销；优先 Shopify 原生数量事实。
│   ├── 物流：Pack / Ship / Tracking 回传 / 签收 / 退件 / 物流异常；异常才上浮，不把每个正常轨迹推给 Founder。
│   ├── 🛠 现状：Shopify 原生库存 + 国内工坊/线下协同 + 国际专线已有现实基础；复杂采购/仓库软件不是当前必要条件。
│   ├── 🔴 缺口：生产/QC/库存/订单/Tracking 之间的事件接线、低库存/延误/退件异常提醒还未成为统一闭环。
│   └── 🚀 怎么做：先事件提醒和状态回写；只有供应商/仓库/订单量明显扩大后才考虑 ERPNext/Odoo/WMS，当前保持备用。
│
├── 📊 11. 经营数据、归因、真相回读与异常简报中枢 ─────────▶ 【读回已有｜跨渠道归因待补】
│   ├── 🎯 目的：所有“这个动作有没有用”最终看真钱和真实行为，不看 Agent 自己汇报“运行成功”。
│   ├── 电商真钱：Shopify GMV / Orders / AOV / Purchase / Refund；PostHog 看 UTM / Page / Session / ATC / Checkout。
│   ├── 内容归因：每条内容 run_id / UTM → 访问 → 加购 → 结账 → 购买；Winner 自动回灌 06。
│   ├── SEO归因：Query / Click → Landing Page → ATC / Purchase；赢家词回灌 07。
│   ├── 外联归因：Signal source → Contact → Reply → First Yes / Sample / Quote → Payment；三线分别记录真钱果实而不是只记“发了多少”。
│   ├── 经营异常：转化骤降、退款异常、库存异常、连续运行失败、授权失效、来源断水，只在超过阈值/影响真钱时进入 12。
│   ├── 简报：Daily/Periodic 只汇总变化、结果、真正阻断和下一动作；常规成功静默。
│   ├── 🛠 现状：Shopify Analytics / PostHog 与部分 readback 已有；跨 Content/SEO/Outreach 的统一来源→真钱归因仍不完整。
│   └── 🚀 怎么做：先复用原生 Analytics/PostHog/平台回读；不建“漂亮但没新增真相”的第二 BI 大屏。
│
├── 📱 12. Founder 手机总控、异常治理、公司记忆与未来自主运营控制 ─▶ 【现有基础＋重要规划未上线】
│   ├── 🎯 目的：Founder 不做人工路由器；正常事情机器自己跑，只有高价值机会、不可逆动作、真实致命故障才上浮。
│   ├── 📱 当前控制面：00_CURRENT_EXECUTION → 01_SYSTEM_STATE → 对应 Canonical/Product Truth → 04 Blockers → 02 Registry 定向定位 → live runtime readback；Telegram 只承接高价值卡片/必要审批。
│   ├── 🔕 降噪：普通 retry、429、GPU排队、长日志、routine success 不刷屏；可自动恢复的就恢复并写回。
│   ├── 🧠 公司记忆：03 Decisions 保留长期约束但禁止整本读；05 Changelog 记历史；Evidence/Company Memory 只做可追溯证据，不冒充 Current。
│   ├── 🛡 可靠性治理【规划/部分已有】：Trace / Observability / Incident / Eval / hard invariant；发现真实故障才按 upstream debugging 修最小根因。
│   ├── 🧭 项目优先级控制【规划中】：一次只保留真正 Current WIP；记录当前瓶颈、被挤掉的工作、Hold/Monitor/Kill，防止“每件事都重要”。
│   ├── 🪪 权限边界【规划中】：每个 workflow/agent 写清可自动做什么、不能做什么、Founder 不在线时安全默认、什么情况必须升级。
│   ├── ⏱ 节奏与触发【规划中】：实时 / 静默持续 / 每日简报 / 周期复盘 / 仅触发时运行；没触发就不占 Founder 注意力。
│   ├── 📋 决策卡【规划中】：为什么现在、为什么需要 Founder、当前真相、2–3个可选项、推荐、没回复时安全默认、证据链接。
│   ├── 🔒 承诺与关闭【规划中】：One Decision → One Commitment → Acceptance → Writeback → Close；明确 Reopen Trigger，防止已关闭事项被历史文件反复复活。
│   ├── 📴 Founder 离线演练【规划中】：先 4–6h → 24h → 72h 分级验证；Routine继续、异常正确上浮、WIP无孤儿、回来能快速恢复全局。
│   ├── 🛠 现状：00/01/02/04 已压成短 Current 路由；基础 Telegram / n8n / approval/readback 能力存在；上面“项目重配/动态权限/完整关闭/72h离线”不得假称已上线。
│   └── 🚀 怎么做：只复用成熟上游 Skill/原厂能力 + 现有 control plane；明确禁止恢复 automation-closure-operator，禁止第二 Automation Registry / 第二 Company OS。
│
└── 🏆 13. 权威背书、PR、展赛、政策与知识图谱自动监听中枢 ─────▶ 【规划明确｜常驻监听待完善】
    ├── 🎯 目的：把“第三方替我们建立的信任”持续沉淀成可销售资产，并自动抓住有截止日期/状态变化的机会。
    ├── XUJIE：国际展赛截稿/申报状态、文化出海/非遗/文旅扶持政策、海外媒体/PR 收录、Wikipedia/Wikidata/官方档案、展览/画廊/文化机构节点。
    ├── AuraSync：真实 Creator 内容、Retail Shelf/Stockist、设计/桌搭媒体、外部评价与合作案例；只沉淀真实发生的证明。
    ├── Sierra：Upwork/Storetasker/平台评价、Case/Review、Agency伙伴、第三方技术信誉/认证；回灌陌生客户信任。
    ├── 🔔 自动监听：Deadline 30/15/7天、页面变化、审核状态、媒体收录、政策更新、奖项结果、知识图谱状态；只有状态变化才通知。
    ├── 🔁 输出回灌：03 提高机会评分 → 04 提高外联信任 → 06 内容引用 → 09 销售资产/图录/Proposal。
    ├── 🛠 现状：XUJIE 已有真实媒体/展赛/知识图谱相关资料与规划；三线部分背书存在，但常驻监听与统一回灌没有完全自动化。
    ├── 🔴 缺口：名单/截止日/审核状态/媒体收录的稳定监测、去重、状态变化识别与资产写回。
    └── 🚀 怎么做：优先官方 RSS/API/网页变化监听 + n8n；不为 PR/展赛再建独立 Agent 公司，只把证据送回已有中枢。

====================================================================================================
【本轮从旧自动化中枢外面找回、重新挂回来的重要“孤儿自动化”】
====================================================================================================
1. SEO / Search Console / Google Merchant Center / 搜索→真钱归因 ───────▶ 已挂 07
2. 客服 / 售后 / 弃购 / Nurture / Win-back / Review / Return Reason ──▶ 已挂 08
3. Product Truth / PIM / 店铺健康 / Merchant 同步 / 销售资产 ────────▶ 已挂 09
4. 采购 / 工坊 / Fired-QC / 库存 / 打包 / Tracking / 物流异常 ───────▶ 已挂 10
5. 三线 Content/SEO/Outreach → Money 的统一归因与经营简报 ──────────▶ 已挂 11
6. Reliability / Priority / Delegation / Cadence / Decision / Closure / Founder Absence ─▶ 已归类挂 12，不另开六个大枝
7. 展赛 / 政策 / PR / Wikipedia/Wikidata / 第三方信任的状态监听 ─────▶ 已挂 13
8. Sierra 六台获客机器中不属于“信号雷达”的 Warm Network / Partner / Inbound / Authority ─▶ 分别挂 04 / 06-07 / 13，避免重复长枝

【版本纪律】
- 本文件只是 Founder 样板，不是 Current Authority；旧自动化中枢原文件一字不改。
- 三业务线 Canonical Whole Map 仍是商业/架构 Authority；本树只做自动化能力归类与遗漏检查。
- “规划中”只表示已经在业务/经营树里明确需要，不代表已 Build / LIVE / E2E PASS。
- 运行状态只从 live runtime/provider readback 读取，不把树上的历史状态当实时状态。
- 新增工具前必须先问：现有 Shopify / Google / Postiz / n8n / Gmail / Telegram / PostHog / 原厂 API 能不能直接承担；能就不造轮子。
- 单次脚本、临时测试、一次性迁移、Acceptance Harness 不占一级大枝，只挂所属节点。
====================================================================================================
```

## 本样板主要对照来源

- `00_CURRENT_EXECUTION｜当前执行包`：当前 Authority 与 Codex 读取纪律。
- `SIERRA｜CANONICAL WHOLE MAP｜夺果实商业树｜Founder 人话总图｜CURRENT`：Sierra WHO/HOW 与六台获客机器。
- `AURASYNC｜CANONICAL WHOLE MAP｜一个成交底座，多条借力钱路｜CURRENT`：AuraSync 一个成交底座、多条钱路。
- `XUJIE TOTAL-MAP CODEX RELEASE｜Upstream-First｜2026-08-27`：XUJIE 总图 Authority。
- `2026-08-29｜自营跨境电商经营能力母树与三层唤醒总图｜Upstream-First`：SEO、客服、订单、采购、库存、财务、数据等经营能力。
- `SIERRA & AURASYNC & XUJIE｜全渠道高转化自动回复中枢与“神之一手”提示词规范（2026-08-29）`：三线回复/渠道 Router。
- `09_AUTONOMOUS_OPERATING_CONTROL｜...｜DESIGNED`：未来 Reliability / Portfolio / Delegation / Cadence / Decision / Commitment / Closure / Founder Absence 规划。
- `02_AUTOMATION_REGISTRY｜自动化总表入口`：现有自动化 owner/identity 只作定位，动态状态必须 fresh-read。

**Disposition：DRAFT SAMPLE ONLY / NOT AUTHORITY / DO NOT AUTO-MERGE INTO DRIVE**