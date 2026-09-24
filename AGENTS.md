# Codex project instructions

For complex coding tasks, use the `astra-orchestrator` skill when its trigger conditions match.

The root agent owns architecture, decomposition, integration, and final verification.
Prefer specialized subagents for bounded exploration, implementation, testing, review, and technical research.

Do not delegate trivial work merely for parallelism.
Do not let multiple implementation agents edit the same files without explicit ownership boundaries.
User instructions always take precedence over this orchestration policy.


## Development work logs

For each development task, including root-only work, create a local journal under
`.agent-graph/development/<UTC-timestamp>-<task-slug>/` before implementation.
The root owns `index.md` and its own journal; each direct writer owns a separate
participant journal. Read-only participants send concise factual `WORK_LOG`
entries to the root for prompt recording with both author and recorder named.
Record start, meaningful progress and decisions, checks, blockers, and terminal
handoff with UTC time, author, status, action/result, evidence, and next step.
Update at milestones and about every 60 seconds during active work when possible.
Exclude hidden reasoning, credentials, personal data, and raw tool output. Report
logging failures and gaps; do not widen permissions to work around them.
