# Delegation Policy

## Direct Terra work

Prefer direct work for a typo, one small known change, a simple command, or a
task touching at most one or two already-understood files with no iterative
diagnosis. Direct shell use alone is not a reason to delegate.

## Luna work

Delegate when a package is bounded and gains from broad search, reading many
files, repetitive edits, repeated build/test/lint runs, large diagnostic output,
or independent verification. A Luna package must have a clear scope and done
condition.

## Never delegate the decision

Terra decides module boundaries, public APIs, schemas, concurrency/error/
permission models, dependency choice, significant refactors, compatibility,
and acceptance. For an unknown bug, Terra proposes up to three diagnostic
hypotheses, Luna collects evidence, and Terra identifies the root cause before
issuing any implementation package.

## Escalate immediately

Luna returns `escalation_required` before changing an unapproved file, adding a
dependency, altering a public API or architecture, encountering ambiguous
requirements or an unknown test failure, causing a likely breaking change, or
finding a security issue.

Never ask Luna to autonomously "fix the project", "choose the architecture",
or "keep debugging until it works".

## Destructive and Git operations

Terra retains decisions on reset/clean, force push, branch deletion,
release/tag changes, destructive migrations, bulk deletion, CI/CD or
production configuration, secrets, and user data. Normal code edits and
read-only Git inspection can be delegated within an explicit scope. No commit,
push, rebase, reset, amend, or tag happens without explicit user authorization.
