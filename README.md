# Code Jargon Bridge

让 AI 在讲编程术语、Git 操作、报错、部署和工程黑话时，顺手补一句中文大白话解释，帮助非技术用户也能看懂并参与做网站、工具和 app。

Make AI explain coding jargon in plain Chinese so non-technical users can understand while building apps and websites.

## What It Does

`Code Jargon Bridge` is a beginner-friendly AI skill/prompt pattern for programming collaboration.

Its job is simple:

- Keep the original technical term
- Add a short plain-Chinese explanation right after it
- Help non-technical builders understand coding conversations without losing accuracy

Example:

- `refactor` -> `refactor（不改功能，只整理代码结构）`
- `API` -> `API（让两个系统互相说话的接口）`
- `commit` -> `commit（把这次代码修改打一个保存点）`
- `rebase` -> `rebase（把分叉的提交重新整理到一条线上）`

## Who This Is For

- UI/UX designers who are starting to build tools, websites, or apps with AI
- Founders, PMs, and operators who can vibe code but do not speak "developer language"
- Anyone who wants AI to sound more human and less full of engineering jargon

## How It Works

When AI uses technical terms, English engineering words, Git commands, error keywords, abbreviations, or deployment language, it should usually add a short Chinese explanation in full-width parentheses.

Examples:

- `deploy（把网站或应用正式放到服务器上）`
- `fallback（主方案不行时的备用方案）`
- `rate limit（限制请求频率，防止接口被刷爆）`
- `CORS（浏览器因为安全规则拦住了跨网站请求）`

The examples are not a fixed word list. They are a pattern.

If a term sounds like insider engineering language, the AI should assume it needs translation.

## Repository Structure

```text
code-jargon-bridge/
├── SKILL.md
└── agents/
    └── openai.yaml
```

- `SKILL.md`: The main skill instructions
- `agents/openai.yaml`: UI metadata for Codex skill discovery

## Use With Codex

If you use Codex skills, place this folder in your skills directory and invoke it as:

```text
Use $code-jargon-bridge to explain coding jargon in plain Chinese while collaborating with a beginner user.
```

You can also say things like:

```text
Use $code-jargon-bridge. I am not technical, so when you use engineering terms, add a short plain-Chinese explanation in parentheses.
```

## Use Without Codex

If you do not use Codex, you can still use the same behavior by pasting the core rule into your AI system prompt or first message.

Suggested prompt:

```text
When you help me with coding, keep the correct technical terms, but whenever you use engineering jargon, Git terms, error keywords, abbreviations, or deployment language, add a short plain-Chinese explanation in full-width parentheses. Treat examples like refactor, API, commit, rebase, deploy, fallback, CORS, and schema as patterns, not a closed list. If a sentence becomes too dense, rewrite the whole sentence in simpler Chinese instead of stacking too many parentheses. Use calm, respectful, adult Chinese.
```

## Design Principles

- Translate jargon without dumbing down the real meaning
- Explain proactively, not only when asked
- Treat examples as patterns, not a dictionary
- Avoid over-explaining obvious words
- Prefer one clear explanation over long glossary-style answers

## Example

Instead of:

```text
I’ll refactor the upload flow, add a retry mechanism, and deploy it to staging first.
```

Use:

```text
我会先 refactor（不改功能，只整理代码结构）上传流程，再加一个 retry mechanism（失败后自动重试的机制），最后先 deploy 到 staging（先发布到正式上线前的预演环境）。
```

## Before vs After

### 1. Git collaboration

Without the skill:

```text
你先 commit，然后从 main rebase 一下，处理完 conflict 再 push。
```

With the skill:

```text
你先 commit（先把这次修改保存成一个版本点），然后从 main rebase 一下（把你的修改重新整理到最新主线上），处理完 conflict（两边改了同一个地方，Git 不知道该听谁的冲突）再 push（把本地代码传到远程仓库）。
```

Why it helps:

The sentence stays technically correct, but non-technical users can immediately follow it.

### 2. Debugging an error

Without the skill:

```text
这个报错像是 null reference，先看 stack trace，再排查是不是异步请求时序有问题。
```

With the skill:

```text
这个报错像是 null reference（本来该有值，但实际拿到的是空的），先看 stack trace（报错是沿着哪条调用路径冒出来的），再排查是不是异步请求时序有问题（请求返回的先后顺序乱了）。
```

Why it helps:

The error stops sounding like pure engineering jargon, so the user can understand what is actually going wrong.

### 3. Product-building discussion

Without the skill:

```text
第一版先做 MVP，后面再补 auth、queue 和 rate limit。
```

With the skill:

```text
第一版先做 MVP（先做一个最小可用版本，能跑起来最重要），后面再补 auth（登录鉴权，确认用户身份）、queue（任务排队处理，避免同时太多请求把服务挤爆）和 rate limit（限制请求频率，防止接口被刷爆）。
```

Why it helps:

This is especially useful for UI designers, PMs, founders, and other non-technical builders who can drive products but do not speak fluent engineering jargon.

## Why This Exists

Many people can already build useful things with AI, but they still get blocked by unfamiliar engineering language.

This project helps AI collaborate in a way that feels clearer, more inclusive, and more beginner-friendly.
