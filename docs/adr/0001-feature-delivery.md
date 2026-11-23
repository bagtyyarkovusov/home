# Use independent PRs as the default feature delivery path

Accepted 2026-11-23.

Use Pocock's shaping flow to settle the problem, vocabulary, and design before writing a spec and independently verifiable tickets. In T3, use the Carberk approach of landing ready slices through review and CI on `main`. This gives each ready slice a route to delivery and lets its dependent tickets start from a verified base.

Keep an explicit `/implement-spec` pilot for a feature whose interactions need combined review. It assembles a feature on an integration branch and can make joint validation easier. The combined diff may take more work to review and land. Choose a pilot with a clear need for that tradeoff and agree on the landing plan.

Pin the shared skill set and confirm that the integration pilot fits T3 worktree handling and the target project's delivery rules before using it there. The [shared workflow](../workflow.md) is the current operating guide.

[AI Hero feature walkthrough](https://www.aihero.dev/watch-me-ship-a-21-000-line-feature-with-mattpocock-skills~ez95n) · [Pocock's shipping options](https://www.aihero.dev/skills-changelog-v13-implement-spec-pr-retro-and-glossary-md)
