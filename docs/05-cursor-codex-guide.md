# 05 · Cursor / Codex 编程订阅指南

> 适用范围:Cursor IDE 全部档位 + OpenAI Codex(2025 重启版)+ Claude Code(简要,详细见 02-claude)。
> 数据时间:2026-05。Cursor 定价 2025 调过两次,本篇是最新版。

## 编程 AI 订阅生态

主流玩家在 2026-05 的局面:

| 工具          | 形式            | 月费基础档     | 主要特点                               |
| ------------- | --------------- | -------------- | -------------------------------------- |
| Cursor        | 独立 IDE(VS Code fork) | $20           | 全场景 IDE + AI 集成,内置多家模型      |
| GitHub Copilot| VS Code 插件    | $10            | 微软 / OpenAI 体系,深度 GitHub 集成     |
| Claude Code   | 命令行 + IDE 插件 | 含在 Claude Pro / Max | 命令行 Agent,Claude Sonnet / Opus 驱动 |
| OpenAI Codex  | 命令行 + 网页   | 含在 ChatGPT Plus / Pro | OpenAI 自家 Agent,GPT-5 Pro 驱动        |
| Continue / Cline / Aider | 开源插件 | 自带 API key   | 完全可控,适合自建工作流                |
| Windsurf      | 独立 IDE        | $10            | Cursor 主要竞品,主打"Cascade Flow"     |

本篇重点写 Cursor 和 Codex 这两个收专门订阅费的产品。

## Cursor 档位

| 档位          | 月费(美元) | 主要差异                                                    |
| ------------- | ----------- | ----------------------------------------------------------- |
| Hobby(免费) | $0          | 2 周 Pro 试用、限量 Tab 补全、~50 次月度 Slow 请求           |
| Pro           | $20(月付) / $16(年付) | 无限 Tab + Pro Agent 无限 Slow 请求 + 500 次 Fast 高级请求 |
| Pro+          | $40(月付)  | Pro 全部 + 1500 Fast 请求 + 优先速度                         |
| Ultra         | $200(月付) | 几乎不限 Fast,最优先模型访问,Agent 无上限                    |
| Business      | $40/人(月付)| Pro 全部 + 团队 admin + SSO + 隐私保证(数据不训练)         |
| Enterprise    | 谈           | SSO / SCIM / 审计 / 定制额度                                  |

**Fast vs Slow 请求**:Cursor 用"信用点"系统。Fast 请求是直连模型立即响应,Slow 是排队执行,峰期可能等几十秒。Pro 给 500 Fast/月,用完后可以继续用 Slow 不限。

**Pro 实际能撑多久**:
- 重度日常编程(每天 4-6 小时):500 Fast 大概 2 周用完,后半月用 Slow 偶尔挫折
- 中度(每天 1-2 小时):一个月撑得过 Fast 配额
- 偶尔用(每周几次):Fast 一直用不完

## Cursor Pro vs Pro+ vs Ultra

二选一:

- **Pro $20**:大部分人够用。重度用户后半月在 Slow 上排队几秒可以接受
- **Pro+ $40**:每天写 6+ 小时代码、不接受 Slow 排队、用 Claude Opus 或 GPT-5 Pro 频繁
- **Ultra $200**:专业 Agent 开发者,一天跑大量长任务(Composer Agent / 多步执行)

实测建议:**先订 Pro,撞上限再升级**。绝大多数人 Pro 够用。

## Cursor vs GitHub Copilot

Copilot 现在 $10/月,半价。但功能差距正在拉开:

| 维度                 | Cursor Pro $20                   | Copilot Pro $10                        |
| -------------------- | -------------------------------- | -------------------------------------- |
| 模型选择             | Claude Sonnet/Opus、GPT-5、Gemini 2.5 Pro 等多家可选 | 主用 GPT-5 / Claude Sonnet,可切换不多 |
| Agent 能力           | Composer 可多步执行 / 大改       | Workspace agent,中等                  |
| Tab 补全速度         | 极快(自家模型)                  | 快                                     |
| 编辑器体验           | 全 IDE,VS Code 100% 兼容          | VS Code 插件,体验弱一档                |
| 大改代码 / 跨文件    | 强                               | 较弱                                    |
| GitHub 深度集成      | 基础                             | 强(PR 评审、Issue 关联)               |
| 价格                 | $20                              | $10                                     |

**Copilot 适合**:
- GitHub 重度用户(企业集成无敌)
- 预算紧 + 需求是补全为主
- 微软 / Azure 生态

**Cursor 适合**:
- 想要最好的 Agent 编程体验
- 习惯切换不同模型
- 不在乎 GitHub 集成

## OpenAI Codex(2025 版)

不是 2021 那个旧 Codex。现在的 Codex 是 OpenAI 在 2025-05 重新发的命令行 Agent + 网页版,逻辑跟 Claude Code 几乎一致。

档位:

- **Codex CLI 免费版**:有 GPT-5 mini 限量、跑得了简单任务
- **含在 ChatGPT Plus**($20):用 GPT-5 / o-系列,有用量(每天数百次小任务,大任务限量)
- **含在 ChatGPT Pro**($200):用 GPT-5 Pro,几乎不限
- **企业版**:跟 OpenAI Enterprise 打包

**Codex 跟 Claude Code 的区别**:

| 维度          | Claude Code                      | OpenAI Codex (2025)                    |
| ------------- | -------------------------------- | -------------------------------------- |
| 主力模型      | Sonnet / Opus                    | GPT-5 / o3-pro                          |
| 命令行体验    | 成熟,生态大                      | 较新,2025-05 起逐步赶上                |
| 多文件编辑    | 强                               | 强                                      |
| MCP 协议支持  | 自带 + 大量 marketplace          | 跟进中                                  |
| Agent 长任务  | 优秀(Anthropic 把 Agent 当核心) | 优秀(OpenAI 推 Agent SDK)              |
| 跟订阅绑定    | 含在 Claude Pro / Max            | 含在 ChatGPT Plus / Pro                 |

**怎么选**:

- 已经订了 ChatGPT Plus / Pro -> 直接用 Codex,不要再订 Claude
- 已经订了 Claude Pro / Max -> 用 Claude Code,不要换
- 全新选 -> 看你写什么。前端 / 全栈 -> Claude Code 略胜;后端 / 数据 / 复杂推理 -> Codex 略胜;两者差距越来越小

## 编程订阅怎么组合

### 场景 A:个人独立开发

预算 $20:**Cursor Pro 单个**。不订 ChatGPT / Claude(Cursor 内置模型已经够用)。

预算 $40:**Cursor Pro $20 + Claude Pro $20**。Cursor 写代码,Claude.ai 处理长文档 / 写文章 / 偶尔聊。

预算 $60:**Cursor Pro $20 + Claude Max $100 折半使用** —— 不,直接 Cursor Pro $20 + ChatGPT Plus $20 + Claude Pro $20 更划算。

### 场景 B:重度 Agent 开发者

预算 $100-150:**Cursor Pro $20 + Claude Max $100**。Cursor 做日常补全,Claude Max 提供 Claude Code 大额度跑长 Agent。

预算 $200+:**Cursor Pro+ $40 + Claude Max $200** 或 **Cursor Ultra $200 + Claude Pro $20**。前者偏 Agent / 命令行,后者偏 IDE 内一站式。

### 场景 C:企业 / 团队

5-50 人:**Cursor Business $40/人 + Claude Team $30/人**。两个都给团队订,SSO / 数据隔离 / admin 都到位。

100+ 人:都谈 Enterprise,有量价折扣。

## 国内订阅路径

跟 ChatGPT / Claude 一样的逻辑(因为底层都是 Stripe 收单)。Cursor 实测国内卡通过率类似 OpenAI(40-60%)。代充选项最稳。

特殊点:**Cursor 账号封号率比 OpenAI / Anthropic 都低**。共享账号、IP 漂移基本不会触发封号,所以代充市场价格也更便宜。

## 价格历史

| 时间    | 事件                                              |
| ------- | ------------------------------------------------- |
| 2023-03 | Cursor 上线,免费                                  |
| 2024-01 | Cursor Pro $20 上线                                |
| 2024-12 | Cursor Pro+ $40 / Business $40 推出                |
| 2025-05 | OpenAI Codex 重启                                  |
| 2025-08 | Cursor Ultra $200 推出                             |
| 2026-02 | Cursor 集成 GPT-5 Pro / Claude Opus 4.5            |

---

**国内订 Cursor Pro / Business 卡在付款?** [payforgpt.com](https://payforgpt.com) 支持 Cursor 全档位代充,中文客服、支付宝/USDT 付款,Pro 月费 99 RMB 起。
