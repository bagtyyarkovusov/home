# Shared workflow

| Work | Path |
| --- | --- |
| Small, clear change | Work from one issue. Implement, prove the result, and open a PR. |
| Feature with open decisions | Use `/grill-with-docs`, prototype if it resolves an open question, then use `/to-spec` and `/to-tickets` as the scope warrants. Use `/ship-tickets` for an approved ticket graph in T3. |
| Feature that needs combined review | Consider the `/implement-spec` pilot. Agree on the integration and review plan before starting. |

For a new MVP, read the existing product decisions and use the [scenario and diagram guide](requirements-and-diagrams.md) to clarify the system boundary, first useful outcome, and acceptance checks. For an existing planning map, resume from the open decision or verification issue.

Review each slice against its acceptance criteria and observed proof. Around 1,000 handwritten changed lines is a prompt to discuss scope. Split when outcomes can be reviewed and landed independently. Give more human attention to changes that are difficult to reverse or have broad effects. Apply the project's review, CI, merge authorization, and runtime proof rules.

Use the target project's pinned skills when working there. For wiki shaping in Home, consult the local skill checkout listed in `.local/README.md` if the harness does not expose `/grill-with-docs`. Record agreed vocabulary in the owning glossary.

## Delivery roles

- **Lead.** Settle scope with the user, identify the owning project, and give the implementer a brief with accepted requirements and proof. Coordinate dependencies, review handoffs and landing. Confirm the result against the brief and the project's delivery rules.
- **Implementer.** Own implementation, verification and review revisions in the target project. After review, the lead assigns the findings and evidence to the existing implementer or a delegate for the scoped revision. The implementer returns the revised artifact and verification.
- **Reviewer.** Independently evaluate the current artifact against the assigned decision. Use the [scored visual review workflow](design-and-prototyping.md#scored-visual-review) when a scored checkpoint was agreed, and the owning project's review rules for other work.

Use the [delegate model defaults](../AGENTS.md#delegate-work). Apply explicit user instructions and required execution rules to the assignment for the current task.

## UI design

For design and prototyping, use the [design and prototyping guide](design-and-prototyping.md) to plan actor workflows, organize the design file, and check the prototype before handoff.

Match [review depth](design-and-prototyping.md#choose-the-review-depth) to the impact of the change. Verify routine edits directly. Agree on independent review for consequential UI decisions and use the rubric when a numeric score serves the agreed checkpoint.

Use Anthropic's `frontend-design` for visual design and redesign alongside the relevant project design skills. From Home, read `.agents/skills/frontend-design/SKILL.md` when the harness does not expose it. On another machine, use the pinned `skills/frontend-design/` from Agent-kit to set up that Home-local copy. For project work, use the project's installed UI set.

When reviewing or changing user-facing copy, apply the **UI copy check** in the installed `product-design` skill or in Agent-kit's `skills/product-design/SKILL.md`. See `.local/design-workflow.md` for Penpot and Inkscape preferences when available.

## Where findings go

- Project terminology or durable product decisions go to the project's glossary or ADRs. Use the issue and PR for delivery scope and proof.
- Reusable skill or template improvements go to the kit that distributes them.
- Personal preferences, cross-project lessons, and project pointers go in Home. Link to the original issue, PR, or thread when it helps explain the lesson.

Read the [delivery decision](adr/0001-feature-delivery.md) for the choice of default and the integration pilot.
