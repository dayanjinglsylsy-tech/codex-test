# DRAFT SAMPLE｜AUTOMATION CONTROL HUB V2

> **仅打样，不替代 Drive 原自动化中枢，不修改任何现役 workflow / Canonical / Registry。**
>
> 目的：把“已经存在的自动化”与“已经在经营总树里明确规划、未来值得自动化的重要能力”放在同一张可读总图里。
>
> 本文件不是 Skill、不是第二套 Automation Registry、不是新工作流系统。它只是 Founder 看全局的**自动化能力地图**。

## 先定 4 条规则

1. **一级只按经营能力归类，不按工具名堆树枝。** Postiz、n8n、Shopify、Gmail、PostHog 都是节点 owner / provider，不单独长成公司架构。
2. **已存在 + 已规划的重要自动化都可以进入，但必须标状态。** 推荐只用：`EXISTING OWNER` / `PLANNED` / `RESERVE` / `FROZEN NATIVE`。真实 active / published / execution 状态仍去 live runtime fresh-read。
3. **不够重要的不进一级。** 单次脚本、临时测试、Acceptance Harness、一次性迁移工具只挂到对应枝下，不占一级。
4. **禁止造轮子。** 有 Shopify / Google / Postiz / sau / n8n / PostHog / Gmail / Telegram 等现成 owner 时直接挂载；只有真实缺口才允许 minimum adapter。

---

# 全系统自动化与智能中枢｜V2 样板｜13 个经营域

```text
全系统自动化与智能中枢
│
├── 01｜💰 收钱、订单与交易真相
│   ├── AuraSync：Shopify Order / Payment / Abandoned Cart
│   ├── XUJIE：Shopify Draft Order / PayPal / T/T / B2B付款事实
│   ├── Sierra：服务定金 / 尾款 / 收款事实
│   ├── 自动触发：Paid / Failed / Abandoned / Refund / High-value order
│   └── 原则：Shopify / 支付原厂是真相源，不建第二 OMS
│
├── 02｜📑 财务、利润、报税与外贸单证
│   ├── 多账户流水归集与对账
│   ├── 单单净利润：实收 - 支付费 - 运费 - 退款/破损等真实成本
│   ├── XUJIE：Quote / PI / Commercial Invoice / Packing List
│   ├── AuraSync：团队订单发票 / 收据
│   ├── Sierra：服务收入 / 成本 / 发票
│   ├── 季度报税凭证结构化汇总
│   └── 状态：PLANNED / PARTIAL；优先标准模板 + 原生数据，不上重型财务系统
│
├── 03｜🔍 市场、VOC、商业信号与机会雷达
│   ├── Sierra：Shopify招聘 / 求助 / 改版 / 技术痛点 / DTC变化信号
│   ├── AuraSync：竞品差评 / Desk Setup / Creator / Group Buy / Remote Team需求
│   ├── XUJIE：茶商 / 画廊 / 茶空间 / 礼赠 / 采购需求
│   ├── 竞品价格 / 页面变化 / Review / Search demand变化
│   ├── 多源轮换 + 限流 + 证据封套 + 去重
│   └── 输出：只把真实 why-now 信号交给 04，不直接乱发消息
│
├── 04｜✉️ 全渠道自适应外联与自动跟进
│   ├── Qualification：ICP / Score / Why-now / Evidence
│   ├── Channel Router：Email / LinkedIn / Upwork / IG / WhatsApp / Discord / Reddit 等
│   ├── 个性化消息：利益前置 + Zero Friction + Product/Service Truth
│   ├── Gmail Draft / Telegram direct card / 对应平台入口
│   ├── 30天去重 / 已联系去重 / 已有草稿去重
│   ├── Reply 后自动进入 follow-up / proposal / quote / payment gate
│   └── 禁止：为了“全渠道”造第二套 Outreach Engine
│
├── 05｜🛠 Sierra 技术搜证、证明与交付自动化
│   ├── 阶段1：真实站点问题 / 技术栈 / 移动端摩擦搜证
│   ├── 阶段2：有回复后再做 Before / After 极窄证明
│   ├── 阶段3：深意向后 Staging / 录屏 / 实施证明
│   ├── Playwright / httpx / 技术识别只做客观 Evidence
│   ├── Proposal / Proof / Delivery / Case writeback
│   └── 仅 Sierra 使用，不复制到 AuraSync / XUJIE
│
├── 06｜📣 Owned Content Engine｜自营内容与社媒增长
│   ├── 00 锁真钱目标：ATC / Checkout / Purchase
│   ├── 01 FIND：各平台 Winner discovery
│   ├── 02 ATTENTION_OUTLIER：剥离伪爆款
│   ├── 03 MULTIMODAL DNA：商业结构 + Qwen3-VL / transcript
│   ├── 04 LOCKED CORE：锁死 Hook / Proof / Rhythm
│   ├── 05 Gemini Brand Adaptation + Product Truth Guard
│   ├── 06 H3 镜头级蓝图
│   ├── 07 AutoDL + MiniMax H3 真实视频生成
│   ├── 08 Layout / Video QC
│   ├── 09 Postiz 海外 / sau 国内排程发布
│   ├── 10 UTM + PostHog + Shopify 真钱回读
│   ├── 11 归因诊断：Hook / Proof / Offer 谁赢
│   └── 12 Winner 复利：变体家族 + 再分发
│
├── 07｜🌐 SEO、搜索需求与 Google 免费流量
│   ├── Technical Foundation：GSC / sitemap / 404 / crawl health
│   ├── Keyword Research：真实 Query / Trends / 搜索需求
│   ├── Search Intent：购买 / 痛点 / 比较 / 学习
│   ├── Keyword → Page Mapping：PDP / Solution / Comparison / Guide
│   ├── Indexing / URL submission / 收录回读
│   ├── Google Merchant Center / Free Product Listings
│   ├── Search Console → PostHog → Shopify Revenue attribution
│   └── RESERVE：数据量足够后再上长期排名监测 / Programmatic SEO / Paid Ads自动化
│
├── 08｜💬 私信、客服、售后与客户生命周期
│   ├── DM Filter：点赞闲聊静默，高意向询价/索样/合作上浮
│   ├── 多语言售前咨询自动草拟
│   ├── Gmail / Shopify Inbox / WhatsApp 等会话入口
│   ├── Abandoned Cart / Follow-up / Nurture / Win-back
│   ├── Refund / Return reason 归因
│   ├── Review / 差评 / CSAT / 老客维护
│   └── RESERVE：咨询量明显上升后再启 Chatwoot，不提前造空 CRM
│
├── 09｜🧱 Product Truth、PIM、店铺运营与数字资产
│   ├── Shopify Products = 商品事实主档
│   ├── Product Truth Guard：规格 / 材质 / 库存 / 交期 / 声明边界
│   ├── Listing / Variant / Translation / Price / Packaging data
│   ├── B2B Price Sheet / Sell Sheet / Creator Pack / Proposal / Catalog
│   ├── C2PA / 一器一码 / Evidence / Company Memory可复用资产
│   ├── Store Health / Merchant sync / 重要配置漂移提醒
│   └── 原则：资产只做一份真相，被 04 / 06 / 07 / 08 重复调用
│
├── 10｜📦 采购、QC、库存、仓储、发货与物流
│   ├── 供应商 / 工坊档案、采购价、MOQ、Lead Time
│   ├── PO / 排产 / 到货 / 出窑 QC / 补货判断
│   ├── On-hand / Available / Safety Stock / 低库存预警
│   ├── Pack / Ship / Tracking 回传
│   ├── 签收 / 退件 / 物流异常提醒
│   ├── AuraSync：最终烧成 QC 未证实时禁止自动承诺 ready-to-ship
│   └── RESERVE：只有供应商/仓库规模明显扩大后才考虑 ERP/WMS
│
├── 11｜📊 Analytics、归因、Reality Readback 与经营简报
│   ├── Shopify：GMV / Orders / AOV / Purchase truth
│   ├── PostHog：UTM / Page / Session Replay / ATC / Checkout
│   ├── 渠道归因：Content / SEO / Outreach → Visit → Money
│   ├── 异常诊断：转化骤降 / Refund spike / 库存异常 / 链路断裂
│   ├── Daily / Periodic brief：只报影响真钱与经营决策的变化
│   └── 禁止：另建漂亮但没有新增真钱真相的数据大屏
│
├── 12｜📱 Founder Console、Exception、Governance 与公司记忆
│   ├── Telegram = 唯一高价值人工上浮口之一
│   ├── 高价值机会 / 不可逆动作 / 致命 Runtime Failure 才打扰 Founder
│   ├── routine success silent；普通 retry / 429 / queue 不刷屏
│   ├── Decision / Approval / Safe default / Readback
│   ├── 00 / 01 / 02 / 03 / 04 / 05 / 06 状态与证据写回
│   ├── Company Memory / Evidence Registry / Change log
│   ├── Closure / Reopen / Historical contamination 防护
│   └── 明确禁止恢复 automation-closure-operator 或建立第二 Automation Registry
│
└── 13｜🏆 Authority、PR、展赛、政策与知识图谱监听
    ├── XUJIE：国际展赛 / 截稿 / 申报材料状态
    ├── 文化出海 / 非遗 / 商务扶持政策变化
    ├── 海外 PR / 媒体发布与收录状态
    ├── Wikipedia / Wikidata / 官方档案推进状态
    ├── AuraSync：真实 Creator / Retail / Media 背书沉淀
    ├── Sierra：Case / Review / 平台信誉沉淀
    └── 输出回灌：04 外联 / 06 内容 / 09 销售资产
```

---

## 为什么这版比旧 12 类多出来/重新归类

### 明确补回来的未来自动化

- **SEO / Search / Google Shopping**：旧自动化树只在 09 内容和 10 Analytics 间接出现，但最近经营母树已明确是一条独立真钱增长链。
- **客服 / 售后 / 生命周期 / 复购**：旧树只有 DM Filter，不够；未来 Abandoned Cart、Nurture、Win-back、Review/Return reason 都属于同一客户生命周期域。
- **采购 / QC / 库存 / 发货 / Tracking**：旧树几乎没进入自动化中枢，但经营母树明确存在；不应现在安装 ERP，却应该在总图中保留未来自动化位置。
- **Product Truth / PIM / Store Ops**：不能只叫“Digital Assets”。它实际上是内容、SEO、客服、外联都要读取的事实母源。
- **订单/OMS**：不另装系统，但 Shopify 原生订单事件本身就是非常重要的自动化触发层。

### 为了不让树越来越肥，合并掉的一级

- 原“技术审计与客观搜证刀具” → 并入 **05 Sierra 技术搜证、证明与交付**。
- 原“Digital Assets & Vault” → 扩成 **09 Product Truth / PIM / Store Ops / Assets**。
- 原“Founder Console”与未来治理/Company Memory → 归入 **12 Founder Control / Governance**。

---

## 建议状态标记法

不要在总树里写死 `LIVE=1` 或旧 Execution 状态，只标架构成熟度：

- `FROZEN NATIVE`：原厂能力足够，保持冻结，例如 Shopify订单/Product/基础库存。
- `EXISTING OWNER`：已经有 owner / workflow / provider，但实时运行状态必须 fresh-read。
- `PLANNED`：业务树已明确需要，尚未完成真实 E2E。
- `RESERVE`：达到量级/条件后再启用，例如 Chatwoot、ERP/WMS、Programmatic SEO。

运行时真相继续只认：

`00_CURRENT_EXECUTION → 01_SYSTEM_STATE → 02_AUTOMATION_REGISTRY → live runtime/provider readback`

---

## Source pointers used for this sample

- Drive｜`DRAFT 02｜自动化中枢耦合树｜12大核心 × 三业务线挂载｜待Founder确认`
- Drive｜`三业务线全景总图与真实施工进度清单（Founder大白话可打印对账版）`
- Drive｜`2026-08-29｜自营跨境电商经营能力母树与三层唤醒总图｜Upstream-First`
- Drive｜`02_AUTOMATION_REGISTRY｜自动化总表入口`
- Drive｜`09_AUTONOMOUS_OPERATING_CONTROL｜...｜DESIGNED`

**Disposition：SAMPLE ONLY / NOT AUTHORITY / DO NOT AUTO-MERGE INTO DRIVE**
