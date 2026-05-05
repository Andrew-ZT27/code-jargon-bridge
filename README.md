Code Jargon Bridge
Code Jargon Bridge helps non-programmers safely participate in vibe coding with Codex.

It is not just a jargon translator. Its job is to make technical work understandable enough that the user can keep control of the product:

what is happening
why it matters
whether users are affected
how risky the action is
what happens next
whether the user needs to decide anything
Who This Is For
designers building products with AI
founders, PMs, and operators who can guide product direction but do not read code comfortably
Chinese-speaking users who are blocked by English engineering terms
anyone who wants Codex to explain technical work without turning every answer into a programming lesson
What Changed From A Glossary
The old version focused on this pattern:

stack trace（报错调用路径）
The new version focuses on this pattern:

我先检查测试失败。

大白话：现在不是产品功能已经坏了，而是验证环节发现一处代码行为和预期不一致。
对用户的影响：如果不修，某些情况下页面可能看起来能跑，但实际操作会出错。
下一步：我会先定位是哪条测试失败，再判断是代码错了，还是测试已经过时。你现在不需要操作。
Technical terms are still explained, but only when they help the user understand the action or decision.

What It Does
When coding work gets technical, Codex should explain:

Plain Chinese summary
Why the action is needed
Product or user impact
Risk level
Next step
Necessary jargon
Example:

我会改登录表单的校验逻辑。
大白话：现在用户输错内容时，系统没有给出清楚反馈。
对用户的影响：改完后用户会更容易知道哪里填错了。
风险：中风险，因为会改实际代码。我会改完后跑测试。
Built-In Scenarios
The skill includes reference patterns for:

starting work
editing code
debugging
tests, lint, and build
dependency installation
Git
deployment
architecture decisions
code review
asking the user for decisions
Repository Structure
code-jargon-bridge/
├── SKILL.md
├── references/
│   ├── scenarios.md
│   └── glossary.md
└── agents/
    └── openai.yaml
Use With Codex
Install this folder as a Codex skill, then invoke it with:

Use $code-jargon-bridge while coding with me. Explain actions, risks, user impact, next steps, and necessary jargon in plain Chinese.
Design Principle
The user should not need to understand code to understand the development process.

Codex should carry the technical complexity, while the user keeps control over product goals, UX decisions, risk, and publishing.
