---
name: terra-luna-development
description: "Use when planning, implementing, debugging, or reviewing software changes that may benefit from dividing high-judgment work from bounded repository exploration, implementation, or verification."
---

# Terra–Luna Development

Keep global judgment with Terra; delegate only a bounded, independently
verifiable work package to Luna. The parent remains accountable for decisions,
integration, and acceptance.

## Route the work

Before editing, establish the goal, non-goals, affected interfaces or formats,
compatibility requirements, and any destructive or security-sensitive effects.

- Work directly when it is a tiny, local change or a simple read/test command;
  subagent overhead must be justified.
- Use Luna for bounded exploration, mechanical edits with an existing design,
  deterministic verification, log collection, or a fix with a confirmed root
  cause.
- Keep architecture, API and data-model choices, unknown-cause debugging,
  dependency selection, security decisions, and final review with Terra. Luna
  may gather evidence for these tasks.

When multiple independent investigations would help, parallelize read-only
Luna tasks. Never parallelize overlapping writes.

## Delegate safely

Use the current Codex multi-agent capability only when it can explicitly route
the worker to the configured Luna model. If model selection is unavailable,
keep the role split but do not claim a model binding that the runtime cannot
enforce. Give workers the minimum relevant context, not the full conversation.

For every Luna task, use the complete contract in
[references/task-contract.md](references/task-contract.md). Luna must stop and
escalate rather than infer an architectural decision or widen its scope.

Read [references/delegation-policy.md](references/delegation-policy.md) when
routing is ambiguous, debugging has an unknown cause, or an operation could be
destructive.

## Review and accept

After Luna returns, Terra inspects `git diff` (and `git status --short` or
`git diff --stat` when useful), checks the stated acceptance criteria and test
evidence, and looks for scope creep or accidental API changes. Passing commands
are evidence, not acceptance. Replan or issue a narrower correction package if
the result is incomplete.

Do not commit, push, rebase, reset, amend, tag, delete branches, or perform a
destructive data/configuration operation unless the user explicitly authorizes
it.

When a commit is explicitly authorized, write its subject in this form:

```text
<type>[optional scope]: <short description>
```

Use a concise imperative description. Include a scope only when it clarifies
the affected area; do not fabricate one. Examples: `feat(auth): add magic-link
callback`, `fix: handle empty export path`.
