# Scenario Patterns

Use these patterns when the situation needs more structure than a short inline explanation.

## Starting Work

Use when beginning a technical task.

```text
我会先做一轮只读检查。
大白话：先看项目现在长什么样，不急着改代码。
为什么：这样可以避免凭猜测下手。
你现在不需要操作。
```

## Editing Code

Use when changing source files.

```text
我会改 [file/module]。
大白话：这里是负责 [user-facing behavior] 的地方。
为什么：当前问题来自 [cause].
对用户的影响：改完后用户会 [visible outcome].
风险：中风险，因为会改实际代码。我会改完后跑验证。
```

## Debugging

Use when something fails or behaves unexpectedly.

```text
现在失败的是 [test/build/runtime/setup].
大白话：[plain description of what broke].
严重程度：[low/medium/high]。
对用户的影响：[none/local-only/user-visible/production risk].
下一步：我会先确认失败能不能稳定复现，再定位根因。
```

If the root cause is not known yet, say so directly:

```text
现在还不能下结论。这个错误只告诉我们哪里爆了，还没告诉我们为什么爆。
```

## Tests, Lint, And Build

Use when running or explaining verification.

```text
我会跑 [command]。
大白话：这是检查 [what it validates]。
如果通过：说明 [confidence gained].
如果失败：我会看失败信息，判断是产品逻辑问题、测试过时，还是环境问题。
```

Explain common verification terms like this:

- `test`: 检查功能行为是否符合预期
- `lint`: 检查代码风格和容易出错的写法
- `build`: 确认项目能被正式打包运行
- `typecheck`: 检查数据类型是否对得上

## Dependency Installation

Use when adding, updating, or troubleshooting packages.

```text
这里涉及依赖。
大白话：项目需要外部工具包，当前版本不对或缺失。
风险：中风险，因为依赖版本会影响项目能不能稳定运行。
下一步：我会先看项目用的包管理器和锁文件，再决定怎么处理。
```

Avoid asking the user to choose package versions unless it is a product or cost decision.

## Git

Use when explaining Git operations.

```text
这是 Git 操作。
大白话：Git 是代码的版本记录系统。
影响范围：[local only / remote repository / shared branch].
风险：[low/medium/high].
下一步：[specific action].
```

Risk guide:

- `status`, `diff`, `log`: low risk, read-only
- `commit`, `stash`: medium risk, local history changes
- `push`, `merge`, `rebase`: medium to high risk depending on branch
- `reset --hard`, `force push`: high risk

For remote-changing operations, make clear whether this uploads changes to GitHub.

## Deployment

Use when deploying, configuring hosting, or touching production-like systems.

```text
这里涉及部署。
大白话：这一步会把本地代码变成别人能访问的版本。
影响范围：[preview/staging/production].
风险：[low/medium/high].
我会先确认项目自己的部署命令，不用 Git push 代替部署。
```

Pause before production deploys, database migrations, secret changes, and irreversible hosting changes.

## Architecture Decisions

Use when deciding between technical approaches.

```text
这里有一个技术选择。
推荐方案：[option].
为什么：它更符合 [user goal].
对用户的影响：[speed/reliability/UX/maintenance].
代价：[trade-off].
我会按这个方案做，除非你想优先考虑 [alternative user-facing priority].
```

Do not present architecture as taste. Tie the decision to user impact and project risk.

## Code Review

Use when reviewing code or responding to review comments.

```text
我会先看有没有真实风险。
大白话：代码 review 的重点不是挑毛病，而是找会导致用户问题、维护风险或验证缺口的地方。
我会按严重程度列问题，并说明为什么值得修。
```

## Asking The User

Ask only when the user is the right decision-maker.

Good reasons to ask:

- product behavior changes
- visual or UX trade-offs
- data deletion or migration
- publishing, deployment, or GitHub upload
- cost, account, or external service choices

Bad reasons to ask:

- internal implementation details with no user-facing consequence
- package version choices the agent can infer
- error diagnosis steps the agent can run safely

When asking, recommend a default:

```text
我建议选 A，因为它对用户最稳。B 更快，但后面维护风险更高。
```
