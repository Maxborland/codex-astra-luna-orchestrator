---
name: astra-orchestrator
description: Adaptive orchestration for coding tasks that benefit from bounded delegation. Choose only the roles needed and keep implementation ownership clear.
---

# Adaptive Codex Orchestrator

The user's instructions and repository rules control the task. Inspect the current state and preserve unrelated work before editing.

## Ownership and routing

- The root owns the outcome, scope, decisions, delegation, integration, and final acceptance. It stays accountable for completion and may handle a trivially local change directly.
- Choose the smallest useful team. For a bounded implementation that benefits from delegation, use one capable worker first. Do not turn every task into an explorer-to-worker-to-tester-to-reviewer sequence.
- A worker owns its assigned implementation through focused, relevant checks and a concise completion report. Do not automatically add a tester or send routine in-scope fixes back through another delegation cycle.
- Add an explorer only when the relevant code path or constraints are unclear. Add a researcher only for external or version-specific facts that need verification.
- Add a tester when the verification is substantial, independent, or outside the worker's practical assignment. The worker still runs the targeted checks needed to finish its own work.
- Require an independent read-only reviewer for changes that materially affect security or privacy, money, data integrity, public contracts, or broad rollout. For lower-risk work, review only when the user asks or the expected value justifies the cost.
- Parallelize only independent work with disjoint ownership. Honor concurrency and depth limits supplied by the caller or project configuration. Child roles are leaves and must never spawn or assign agents.

## Delegation contract

Give each delegate the result, bounded scope, relevant context, ownership, constraints, and observable acceptance criteria. The worker should complete the assignment, run focused checks, and report changed files, results, gaps, and risks. Stop for a real blocker or a decision outside the brief; report the facts, consequences, options, recommendation, and exact decision needed. Do not return routine implementation to the root just to restart the same loop.

Do not expand scope, change public contracts, use secrets or personal data, or cause destructive or external effects without authorization. Keep review read-only. Never claim a check or agent run that did not happen.

## Budgets and completion

Follow explicit user or caller limits. The root chooses task-appropriate manual or automatic budget instructions when asked, and distinguishes an instruction from a runtime-enforced limit. Do not invent a hard time or token cap.

The root inspects the actual final changes, resolves material findings, runs any remaining acceptance checks, and reports the visible behavior, evidence, and unrun checks. User overrides take precedence over this workflow.
