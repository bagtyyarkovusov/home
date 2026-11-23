# Design and prototyping

## Plan the flow

1. Read the owning project's issue and accepted decisions. Name each workflow's actor, trigger, entry screen or state, intended outcome, and failure or recovery paths that affect acceptance. Set the entry frame as the prototype's starting point and record its viewer link. [Requirements and diagrams](requirements-and-diagrams.md)
2. Sketch and walk the rough flow before styling it. Give each actor a separate screen for each distinct step or state. Pair frames in a review when seeing both sides clarifies a handoff or shared state. Resolve behavior in the rough flow and update the issue's acceptance checks before refining it.
3. Use the design tool's **project → file → page → frame** hierarchy. Give each workflow one active home and link it from the issue. A small product can keep workflows on pages in one file. A larger product can use separate files for flows or surfaces, with a shared library. Name frames `<actor> / <step> / <state> / <viewport>`. Continue in the linked file and mark superseded copies as archived.

## Build from the library

Use one shared library for the product. Bind layers to named color and typography styles or tokens, and use component instances for recurring controls. Hardcoded values drift when the library changes. Inspect the binding and fix recurring styling and alignment in the library.

Build alignment, spacing, and interaction states into buttons, fields, and other reusable controls. Use the component's layout alignment to set label position. Check that rendered text sits visually centered in a centered control on both axes. For icon-and-label controls, center the group and inspect icon alignment with the text. Check the longest supported label and any applicable focus, disabled, or busy states in representative instances.

Choose a **Base** reference viewport and record width × height in logical units, such as CSS px or pt. Name the **Compact** or other viewports exercised in review and record their dimensions in the same units. Use responsive layout on the base frames and check representative screens at compact width, with long localized copy, and with larger text. Add a named frame variant only where a viewport or text setting changes layout or interaction in a way the reviewer needs to see. Record its trigger, such as a breakpoint that moves actions into a menu.

## Coordinate local Penpot editing

The lead assigns one editing owner and one editor tab per local MCP token. The owner connects from that tab and runs an authenticated, read-only check of the active file and page against the brief before editing. Reviewers use the viewer. If the token is busy, the lead identifies the holder and coordinates release. Disconnect only a confirmed idle bridge and repeat the file and page check after reconnecting.

At handoff, verify the save and viewer link, disconnect MCP, close the job's editor tab if you opened it for the task, and report release. The lead verifies the bridge is free before assigning the token again. Keep machine-specific and private connection instructions in Home's `.local/design-workflow.md` and credentials in private client configuration. Keep the design link, assets, and acceptance evidence with the owning project.

## Prepare vector assets

Keep the editable Inkscape SVG source with the project. Use a simple page and `viewBox`, with bounds and padding that fit the artwork, including strokes. Record the intended logical icon sizes and check rendering at those sizes on the target backgrounds. Hand off the editable source, the required exports, and their intended sizes and uses together.

For a repeatable bounds and render check, set `svg` to the source path, `png` to a disposable output path, and `size` to the intended export width in pixels. Use an existing Inkscape executable on `PATH`.

```sh
inkscape --query-all "$svg" &&
  inkscape --export-area-page --export-width="$size" --export-filename="$png" "$svg"
```

Compare the reported object bounds in SVG pixels (96 dpi) with the page bounds. Account for the source `viewBox` origin and scale if they differ from the page. Inspect the PNG for clipping, padding, and legibility. Export width sets the raster width and preserves the page aspect ratio.

## Workflow brief

Copy into the owning issue or spec. Repeat the workflow and frame entries as needed.

```text
Issue / active design file / page
Workflow / actor / trigger / entry frame and viewer link
Outcome / failure or recovery behavior / acceptance check
Frame / step and state / next frame / paired actor frame if useful
Base viewport / width × height and logical units
Compact viewport / width × height and logical units
Localized copy / larger-text setting / variant and trigger if needed
Shared library / asset sources and exports / evidence links
```

## Review checklist

- [ ] Open each workflow's start link with reviewer access. Walk the main path and the acceptance-relevant failure paths in the viewer. Confirm each transition and outcome.
- [ ] Inspect style bindings and component instances in the editor. In the viewer, check rendered control alignment and applicable interaction states.
- [ ] Check the base and representative compact, localized, and larger-text cases for clipping, overlap, and reachable actions. Open any variants from the brief.
- [ ] Check SVG source and exports at intended sizes. Record viewer links and observed acceptance outcomes in the project issue or spec.
- [ ] For local Penpot MCP work, confirm the owner released the connection and the viewer still opens the saved design.

## Scored visual review

Before calling a delegated UI change finished, give a separate reviewer fresh context and have them score the rendered screens or prototype. The implementer verifies the artifact and supplies viewer links and reproducible scenarios. Cite the exact board or captured screen, viewport, locale and state checked. Include the most relevant normal and recovery states and a compact or larger-text check when the change can affect layout.

1. **Review.** Brief the reviewer with the accepted design requirements, current artifact, representative scenarios and required test conditions. Keep the implementer's self-assessment and any prior findings or scores out of the brief and its references.
2. **Revise.** Give the assigned implementer the findings with the affected state, expected behavior and evidence. Use a fix delegate for a scoped revision and handle small corrections directly. Verify the saved revision and hand back its current viewer links.
3. **Review again.** Start a new reviewer with fresh context. Give them the same requirements and comparable conditions against the revised artifact. Keep the fix list, earlier verdict and earlier score out of the handoff. Compare the reviews after the new verdict is in.

Score each criterion from 0 to 2. Use **0** for a blocking problem, **1** for a visible issue to correct and **2** when the inspected examples pass. Report the five scores and their total out of 10. If the earlier version is available under the same conditions, score it as well and show the change. Mark any unverified criterion pending and report a partial score against the points inspected.

| Criterion | What to inspect |
| --- | --- |
| Hierarchy and copy | The most important information and action stand out, and the labels fit. |
| Alignment and spacing | Rendered labels, icons, control bounds and spacing align across states. |
| Visual consistency | The screens use the intended shared components, type, colors and icon treatments. |
| Accessibility and layout | Contrast, visible focus, compact layouts, localized text and larger text behave as applicable. |
| State and motion | Feedback, transitions and recovery make the current state and next action clear. |

List concrete findings with the affected screen and condition. Fix confirmed issues, rerun the affected checks, and record the revised score and remaining gaps before handoff.
