# Core, Waist, Flexibility

Minimal-skill 的作用不是把项目压成最少文件，也不是把所有经验写成规则。它要帮助维护者区分三层东西：

```text
Core -> Narrow Waist -> Flexible Defaults
```

## Core

Core 是项目身份。删掉它，项目就不再服务同一对象、产生同一价值变化，或无法判断成功失败。

Core 通常包括：

- 服务对象和目标状态变化；
- 不可违反的边界；
- 必须成立的稳定契约；
- 能证明目标发生的证据；
- 支持长期演化的验证与回退关系。

Core 应该少而硬。不要把目录、框架、模型、偏好、示例或一次成功经验直接升级为 Core。

## Narrow Waist

Narrow Waist 是多变输入和多变实现之间的稳定接口。它回答：

- 输入是什么；
- 必要状态转换或不变量是什么；
- 输出是什么；
- 错误和不确定如何表达；
- 什么证据可验收；
- 下游消费者是谁。

窄腰不是“流程越短越好”，而是“跨实现仍必须成立的接口越清楚越好”。

## Flexible Defaults

Flexible Defaults 是当前推荐做法。它们有价值，但默认可替换：

| 类型 | 例子 | 何时升级 |
|---|---|---|
| 工具 | SQLite、GitHub Actions、Claude、Codex | 只有当替换会破坏稳定契约或证据链 |
| 目录 | `docs/`、`evals/`、`examples/` | 只有当目录本身是消费者契约 |
| 流程 | 6阶段、10分钟检查、14天归档 | 只有当流程保护高成本风险且被验证 |
| 示例 | 具体案例、模板、报告格式 | 通常不升级，只作为学习材料 |
| 偏好 | 命名、语气、视觉风格 | 除非承载品牌或兼容性，否则保持柔性 |

## Decision Test

判断一个元素属于哪一层：

1. 删除后项目身份是否改变？是 -> Core。
2. 替换实现后是否仍要保持这个接口？是 -> Narrow Waist。
3. 多数场景有用但可被更好方案替代？是 -> Flexible Default。
4. 只是一次尝试或未验证想法？是 -> Experiment。
5. 不保护目标、边界、证据或恢复能力？可能是 Burden。

## Upgrade Discipline

默认策略升级为硬约束前，必须说明保护对象和证据：

```text
Rule -> protected goal/boundary/evidence -> failure evidence -> lighter alternative checked -> review condition
```

如果说不清保护对象，它就不该变硬。Minimal-skill 应该帮助项目保持骨架，而不是穿上越来越厚的铠甲。

