# Working from Home

Home is the personal wiki and T3 starting point for planning, research, and work across projects.

## Start a session

1. For project work, find the project in the [project index](projects/README.md) or in `.local/README.md` when present. Resolve the owning repository and read its `AGENTS.md` and governing issue before proposing or changing project work.
2. For open scope or delivery decisions, read the [shared workflow](docs/workflow.md). For an MVP or a flow with unclear behavior at a boundary, use the [scenario and diagram guide](docs/requirements-and-diagrams.md) to turn open questions into acceptance checks.
3. For implementation, use the target T3 project and an owned worktree. Carry over the issue, accepted decisions, and required proof. Follow the target project's review, merge, and environment rules.
4. For UI design, redesign, or copy review, read the [design workflow](docs/workflow.md#ui-design).

## Delegate work

Prefer delegates for work with a clear brief and a result the lead agent can verify. Use these defaults when creating delegates, subject to the task and target project's instructions.

| Role | Model | Reasoning effort |
| --- | --- | --- |
| Implementer | `gpt-6.2-sol` | `medium` |
| Reviewer | `gpt-6.2-sol` | `high` |

## Update the wiki

- Put cross-project decisions and lessons in Home. Use the [write-back rules](docs/workflow.md#where-findings-go) to route project facts and reusable skill changes to their owners.
- When adding a project, add one page and link it from the matching index. Use `.local/` for private projects, thread links, and machine-specific references.
- When a shared term changes how we work, update the [wiki glossary](GLOSSARY.md). Capture the rationale for a lasting workflow decision in [docs/adr](docs/adr).
