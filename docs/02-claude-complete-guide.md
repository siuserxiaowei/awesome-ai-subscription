# 02 · Claude 完整订阅指南

[English](./en/02-claude-complete-guide.md) | 中文

---

> 适用范围:Anthropic 旗下 Claude.ai 网页版 + iOS / Android + Console / API。
> 数据时间:2026-05。Claude Pro / Max 档位结构在 2025-04 大改过一次,本篇基于改后结构。

## 档位概览

Anthropic 的订阅有两条线 —— Claude.ai 消费者订阅 和 Console / API 计费。两边逻辑完全不同:

**消费者订阅(Claude.ai)**

| 档位             | 月费       | 主要面向            | 关键差异                                   |
| ---------------- | ---------- | ------------------- | ------------------------------------------ |
| Free             | $0         | 试用                | Sonnet 4.x 限量、无 Opus、无 Projects       |
| Pro              | $20        | 个人付费            | Sonnet + Opus + Projects + 5x Free 用量     |
| Max ($100)       | $100       | 重度个人 / 开发     | 5x Pro 用量、优先访问、Claude Code 高额度  |
| Max ($200)       | $200       | 整天泡 Claude       | 20x Pro 用量、Opus 几乎不限、最高优先级    |
| Team             | $30/人(年付)| 5+ 人小团队        | Pro 全功能 + 共享 Projects + admin          |
| Enterprise       | 谈          | 企业                | SSO、SCIM、SLA、定制额度                    |

**API / Console**

按 token 计费(input / output 分价),没有月订阅概念。Console 提供组织管理、key 轮换、用量看板,但不是订阅产品。

## 档位对比

### Free vs Pro

| 维度         | Free                  | Pro ($20)                            |
| ------------ | --------------------- | ------------------------------------ |
| 主力模型     | Claude Sonnet 4.5    | Sonnet 4.5 + Opus 4.5(限量)         |
| 5 小时窗口配额 | ~10-25 条短消息       | ~45-100 条 + Opus 抽样               |
| Projects     | 不可用                | 可用,单 Project 最多 200k token 上下文 |
| 文件上传     | 5 个 / 对话           | 30 个 / 对话                          |
| Artifacts    | 限量                  | 完整                                  |
| Computer Use(实验) | 不可用            | 可用                                  |
| Claude Code  | 不可用                | 可用,有用量上限                       |

Pro 的核心是 **Projects** 和 **Opus 访问**。Projects 让你把一组文档(代码库、合同、研究材料)加成 Claude 的"长期记忆",同一项目里多个对话都共享上下文。这是 Claude 比 ChatGPT 在长文档场景下最大的优势。

### Max $100 vs Max $200 怎么选

这两档分界点经常被问。一句话:**用 Claude Code(命令行 / IDE 编程代理)的人才会撞 $100 的额度**。

| 维度                      | Max $100                | Max $200              |
| ------------------------- | ----------------------- | --------------------- |
| 5 小时窗口配额            | 5x Pro                  | 20x Pro               |
| Opus 用量                 | 优先,但仍有限制         | 几乎不限              |
| Claude Code 编码额度      | 高,日活程序员可能撞顶   | 几乎不限              |
| 优先级队列                | 高                      | 最高(峰期不排队)     |
| 适合人群                  | 重度写作 + 偶尔 Code    | 整天用 Claude Code 的程序员 / Agent 开发者 |

实测数据:
- 一个把 Claude.ai 当主写作工具的用户,$100 一个月用不完
- 一个把 Claude Code 当主 IDE 的程序员,$100 大约能撑 8-15 天就撞上限,要 $200 才能整月不间断
- 两档都给 Opus 优先,但 $200 在 Opus 高峰期(亚洲晚上)排队短得多

**判断标准**:如果你过去 30 天 Claude Code 命令运行超过 200 次,直接 $200;低于 100 次,$100 够用;0 次,Pro 就够。

### Team / Enterprise

- **Team** 最低 5 人,$30/月或 $25/月年付。比起 Pro 多了:共享 Projects、统一计费、admin、数据隔离强保证。
- **Enterprise** 联系销售,起步通常 50-100 人,带 SSO、SCIM、审计日志、专属 SLA、地区数据驻留。

## Console / API 计费

不是订阅,是按用量预付费。

**当前定价(2026-05)**:

| 模型             | Input ($/M tokens) | Output ($/M tokens) | 上下文窗口 |
| ---------------- | ------------------ | ------------------- | ---------- |
| Claude Haiku 4.5 | $1                 | $5                  | 200k       |
| Claude Sonnet 4.5| $3                 | $15                 | 200k(Pro 用户 1M beta) |
| Claude Opus 4.5  | $15                | $75                 | 200k       |

降价 / 优化策略:
- **Prompt Caching**:重复 prompt 部分缓存,缓存 hit 部分 input 价格降到 1/10。长系统提示和长文档场景能省 50-90%
- **Batch API**:异步批处理,价格 5 折,24 小时内返回
- **Message Batches + Caching 组合**:写作 / 摘要等离线场景能把成本压到原价 1/4

**什么时候选 API 而不是订阅?**

- 程序员 / 开发者要把 Claude 集成进自己的 App
- 团队要共享一个 key 给多个用户用(订阅是绑账号的)
- 单月用量极不稳定(月用 1 小时 vs 月用 100 小时,API 按需付费更省)
- 要用 200k 以上的长上下文(Sonnet 4.5 的 1M beta 仅 API 开放)

**什么时候订阅更好?**

- 个人日常用,不写代码集成
- 用量稳定每天 1-3 小时
- 想用 Projects、Artifacts、Computer Use 这些只在 Claude.ai 提供的功能
- 不想自己管 API key、不想看 token 计费表

经验数据:每天 30-90 分钟轻度对话用户,Pro $20 比 API 便宜 3-10 倍。每天 30 分钟内或周用 1-2 次的人,API 反而便宜。

## 国内订阅路径

### 路径 A:海外信用卡直付

跟 ChatGPT 一样的逻辑。Claude 用 Stripe 收单,Stripe 风控比 OpenAI 略宽松,实测国内段卡通过率 50-70%(高于 OpenAI 的 40-60%)。

注意:
- 注册 Claude 账号需要外国手机号验证(Anthropic 不支持 +86)
- 部分国家(包括中国大陆)在 Anthropic 的 supported regions 之外,即使付款成功了,IP 落在中国大陆 Claude.ai 也会拒绝服务

### 路径 B:Apple App Store 内购

跟 ChatGPT 同理,iOS 付费要 $25(苹果抽 30%)。优点不需要海外信用卡,缺点贵 25%。

### 路径 C:代充

国内付订阅最稳的方式。代充店帮你登录 / 升级,价格通常比官网贵 10-30 RMB(月)。

挑代充的检查清单见 [06-付款方式](./06-payment-methods.md#代充服务)。

### 中国大陆地区限制

Anthropic 官方明确不支持中国大陆 IP 访问 Claude.ai。即使账号订阅成功:
- 中国大陆 IP 直连会被 403
- 必须挂稳定的海外节点(美国、日本、新加坡都行)
- 节点 IP 不能频繁切换(短时间多国 IP 会触发账号风控)

## Claude vs ChatGPT —— 选哪个

简化版决策:

- **写长文(论文、报告、合同分析)** → Claude Pro 完胜,200k 上下文 + Projects 是 ChatGPT Plus 拿不出的牌
- **聊天 / 日常 / 写代码片段** → 各有所长,看个人偏好。Claude 风格更"聪明克制",ChatGPT 更"百科全书"
- **图像 / 视频生成** → ChatGPT(DALL·E + Sora),Claude 不做生图
- **语音对话** → ChatGPT(高级语音很成熟),Claude 没语音
- **重度编程 Agent / 命令行** → Claude(Claude Code 是行业标杆,Cursor 也用 Claude)
- **企业 / 法律 / 长合规文档** → Claude(对长文本理解更稳)

很多重度用户两边都订:Plus + Claude Pro 一共 $40/月,覆盖几乎所有场景。

## 退款 / 取消

- 取消:Settings -> Account -> Manage Plan -> Cancel
- 退款:Anthropic 提供 14 天内全额退款,前提是没有"重度使用"。客服 support@anthropic.com 邮件申请,2-5 天回复
- Apple 内购:reportaproblem.apple.com,跟苹果谈

## 价格历史

| 时间    | 事件                                              |
| ------- | ------------------------------------------------- |
| 2023-09 | Claude Pro 上线 $20                               |
| 2024-09 | Claude.ai 推出 Projects                           |
| 2025-04 | Max $100 / $200 双档发布                          |
| 2025-08 | Claude 4 系列发布,Pro / Max 价格不变              |
| 2025-12 | Computer Use 公测,Claude Code 进 Pro 档           |
| 2026-02 | Sonnet 4.5 发布,1M token 上下文(beta)            |

---

**在国内订不到 Claude Pro / Max?** [payforgpt.com](https://payforgpt.com) 处理过几千单 Claude 订阅,中文客服 + 卡密发货 + USDT/支付宝付款,新号也能代订。
