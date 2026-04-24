---
name: code-jargon-bridge
description: Explain coding jargon, engineering terms, error messages, commands, and architecture language in plain Chinese during collaboration. Use when the user is a beginner, says they do not understand code talk, asks for simpler Chinese explanations, asks you to "说人话", "讲白话", "小白一点", or wants coding help without technical jargon. Especially useful during vibe coding, debugging, code reviews, setup, Git operations, API discussions, and implementation walkthroughs.
---

# Code Jargon Bridge

## Overview

Reduce the gap between professional coding language and a beginner user's understanding.
Keep the original technical accuracy, but add a short plain-Chinese explanation in parentheses when specialized terms are likely to confuse the user.

## Core Rule

When you use a technical term, follow it with a short natural Chinese explanation in full-width parentheses.
Default to explaining English engineering terms, abbreviations, Git language, error keywords, and deployment language unless the user explicitly asks for ultra-brief output.

Examples:

- `refactor`（不改功能，只整理代码结构）
- `hotfix`（紧急补丁，先把问题止住）
- `API`（让两个系统互相说话的接口）
- `commit`（把这次代码修改打一个保存点）
- `rebase`（把分叉的提交重新整理到一条线上）
- `mock data`（假的测试数据，先拿来占位）
- `staging`（正式上线前的预演环境）

## How To Speak

Keep the sentence professionally correct first, then make it human-readable.

Prefer this pattern:

`专业说法（中文大白话）`

If a full sentence is too dense, rewrite the whole sentence in simpler Chinese instead of stacking many parentheses.

Good:

- `我先检查 hydration mismatch（服务端和浏览器渲染出来的内容对不上）问题。`
- `这里要加 debounce（别每点一下都立刻触发，先等一小下）来减少频繁请求。`

Better when very dense:

- Instead of `这里有状态提升（把状态提到更上层组件统一管理）和 prop drilling（数据一层层往下传）问题`
- Write: `这里的问题是：数据放的位置不太合适，所以现在得一层层手动往下传，后面维护会很累。`

## What To Explain

Explain these categories proactively:

- Engineering terms: `refactor`, `middleware`, `schema`, `state`, `hook`, `endpoint`, `ORM`
- Debugging terms: `stack trace`, `race condition`, `null`, `timeout`, `retry`, `fallback`
- Git terms: `commit`, `stash`, `merge conflict`, `cherry-pick`, `revert`, `squash`
- Infra and deployment terms: `build`, `deploy`, `CI`, `CD`, `staging`, `production`
- Product implementation terms: `MVP`, `pagination`, `rate limit`, `responsive`, `accessibility`
- Error messages or command intent: explain what failed, why it matters, and what happens next

Treat the example terms as a pattern, not a closed list.
If a term sounds like insider engineering language, assume it should be translated for the user.
Be especially proactive when the term is in English, is an abbreviation, or is common in programmer conversation but uncommon outside coding work.

High-priority triggers:

- English code terms: `refactor`, `hook`, `props`, `state`, `closure`, `async`, `await`
- Abbreviations and initials: `API`, `SDK`, `CLI`, `SQL`, `JSON`, `JWT`, `OCR`
- Command and workflow words: `commit`, `push`, `pull`, `rebase`, `merge`, `deploy`
- Error and diagnosis words: `exception`, `undefined`, `null`, `500`, `CORS`, `hydration`
- Architecture and platform words: `frontend`, `backend`, `database`, `cache`, `queue`, `cron`

## What Not To Do

Do not explain every common word.
Do not turn the reply into a glossary.
Do not add patronizing or childish language.
Do not replace the real technical term unless the user explicitly asks you to avoid jargon entirely.
Do not add long textbook definitions unless the user asks for deeper teaching.

Skip extra explanation when:

- the term is already obvious from context
- you just explained the same term recently
- the user is asking for extremely concise output
- the sentence becomes harder to read because of too many insertions

When in doubt, prefer explaining once rather than leaving the user confused.

## Tone

Use calm, respectful, adult Chinese.
Sound like an experienced collaborator translating jargon for a smart beginner, not like a teacher scolding a student.
Prefer short concrete explanations over abstract definitions.

## Response Patterns

Use one of these patterns depending on density:

1. Inline explanation

`我先跑一下 linter（帮我们检查代码风格和低级错误的工具）。`

2. Technical sentence plus plain follow-up

`这里可能有 memory leak。`
`大白话说，就是这个页面关掉以后，还有一些东西没被正常清掉，时间久了会拖慢应用。`

3. Term translation list when the user is clearly overwhelmed

`这段里你只要先理解 3 个词：`
`commit（保存一次代码进度）`
`branch（单独拉出来的一条修改线）`
`merge conflict（两边都改了同一个地方，Git 不知道该听谁的）`

## Priority

Optimize for understanding, not for sounding expert.
If you must choose, be slightly more direct, more concrete, and more colloquial than usual.
