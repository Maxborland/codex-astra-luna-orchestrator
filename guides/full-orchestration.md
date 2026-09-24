# Pro Profile: Astra + Luna Orchestration

Choose this preset when you want Astra to plan, orchestrate, and review while
Luna handles the execution roles. Select Pro in `setup.sh` or `setup.ps1`.
Setup copies `profiles/pro/codex/` to `.codex/` and
`profiles/pro/agents/` to `.agents/` in the target repository without
rewriting configuration. For manual installation, copy those same folders
and the repository's `AGENTS.md` to the target.

The role files provide distinct capabilities; they are not a fixed pipeline.
Use the smallest routing that can finish the task. A worker completes a bounded
change and focused checks; add exploration, research, or independent testing
only when the task needs them. Require a read-only independent review for
high-risk work.

```text
Astra root
├── worker (bounded implementation + focused checks)
├── explorer / researcher (when facts or code paths are unclear)
├── tester (when independent verification adds value)
└── reviewer (required for high-risk work)
```

Put the root settings in the project-scoped `.codex/config.toml`, or merge
them into `~/.codex/config.toml` for a personal/global setup:

```toml
model = "gpt-6-astra"
model_reasoning_effort = "medium"

[agents]
enabled = true
max_concurrent_threads_per_session = 4
default_subagent_model = "gpt-6-luna"
default_subagent_reasoning_effort = "max"
```

For the named roles, use these model settings in the corresponding files under
`.codex/agents/`:

```toml
# explorer.toml, worker.toml, tester.toml, researcher.toml
model = "gpt-6-luna"
model_reasoning_effort = "max"
```

```toml
# reviewer.toml
model = "gpt-6-astra"
model_reasoning_effort = "low"
```

The role files override the inherited `[agents]` defaults. Keep those explicit
overrides when you want the topology above to remain stable. Remove them when
you want all named roles to follow the defaults in `config.toml`.

For the Luna-root configuration, use the [Plus profile](plus-plan.md).
