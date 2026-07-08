# Agent OS Toolchain Case

这个案例来自一组小型 Agent 工具的连续维护：`butler-skill`、`codex-butler-relay`、`dream-skill`、`maintenance-capsule-skill` 和 `minimal-skill` 本体。

目标不是把每个仓库都写厚，而是让一组轻工具形成可长期演化的个人 Agent OS。

## Project Identity

- 服务对象：长期使用 AI Agent 做个人项目维护的人。
- 当前状态：工具分散存在，部分能用但缺少证据、版本记录和交接边界。
- 目标状态：每个小工具都有清楚身份、稳定接口、最小证据和可替换实现空间。
- 价值变化：从“能用的小脚本/Skill”变成“可维护、可解释、可恢复的工具链”。

## Minimal Topology

```text
User Goal
  -> Core Skill Contract
  -> Execution / Relay / Memory / Maintenance Tool
  -> Evidence
  -> Versioned Evolution
```

## Core Invariants

| 不变量 | 保护对象 |
|---|---|
| 每个工具只承担一个清楚责任 | 防止小工具膨胀成大平台 |
| 上游目标和边界不可丢 | 防止执行成功但方向错误 |
| 证据优先于模型自述 | 防止“声称完成”替代真实验收 |
| 默认实现可替换 | 防止绑定某个模型、目录或流程 |
| 版本和变更可追溯 | 支持跨窗口、跨模型、隔月恢复 |

## Narrow Waist Examples

| 工具 | 窄腰 |
|---|---|
| `butler-skill` | 目标 -> 自主执行/可选外包 -> 验证后终态 |
| `codex-butler-relay` | Goal -> detached worker -> terminal signal -> Codex acceptance |
| `dream-skill` | Memory inventory -> candidate changes -> reversible changeset -> evidence report |
| `maintenance-capsule-skill` | 项目核心 -> 当前状态 -> 恢复入口 -> 刷新规则 |
| `minimal-skill` | Identity -> Boundary -> Contract -> Evidence -> Evolution |

## Flexible Defaults

以下是有用默认，不是身份核心：

- `docs/`、`examples/`、`evals/` 目录名；
- `VERSION` 和 `CHANGELOG.md` 的具体格式；
- JSON eval 的字段命名；
- 10分钟、14天、6阶段等具体节奏；
- Claude、Codex、GitHub Actions 或某个临时工 provider。

只要核心身份和窄腰契约还成立，这些实现都可以换。

## What Changed

这组项目的升级策略是：

1. 对成熟但轻的 Skill，补版本、变更记录、例子和 evals。
2. 对有真实执行逻辑的 Relay，补状态契约和恢复规则。
3. 对容易变硬的 Dream，明确核心红线和柔性默认方案。
4. 对个人主页和网站，补项目展示与自动同步，减少手工维护。

## Deletion Test

| 候选元素 | 删除后果 | 分类 |
|---|---|---|
| `GOAL_DONE/NEED_DECISION/NEW_WINDOW` | Relay 无法识别终态 | Core contract |
| `docs/relay-contract.md` 文件名 | 可改名，只要入口和内容仍可发现 | Flexible default |
| `evals/evals.json` | 失去回归证据，维护风险升高 | Essential support |
| 特定模型供应商 | 可替换，只要结果可验证 | Implementation |
| 强制每个 Skill 都 10 个 eval | 容易变成形式主义 | Burden / over-hardening |

## Lesson

小工具的升级重点不是“多加东西”，而是让维护者知道：

- 哪些不能删；
- 哪些只是当前做法；
- 什么证据说明它真的工作；
- 下一次改动怎样不破坏身份。

