# GitHub Collaboration Infrastructure

**Date:** 2026-03-24

## What changed

Organization-level GitHub defaults added via the `schedjoules/.github` repo:

- **Issue templates**: Experiment, Implementation, and Bug report templates enforce consistent structure across all repos
- **PR template**: Links issue, deviation flag, and testing checklist on every pull request
- **CONTRIBUTING.md**: Single reference for how to pick up work, branch, and open PRs
- **Blank issues disabled**: All issues must use a template, with a link to the Way of Working doc

## Why

Ensure every team member works in the same structure. Minimize human input in the process. Make the experiment pipeline structure enforceable at the GitHub level instead of relying on convention.

## Before vs After

| Aspect | Before | After |
|--------|--------|-------|
| Issue structure | Manual, inconsistent formatting | Enforced via templates with required fields |
| PR format | Freeform description | Template with linked issue, deviation flag, checklist |
| Blank issues | Anyone could create unstructured issues | Disabled, must use a template |
| Contribution guide | Scattered across docs | Single CONTRIBUTING.md at org level |
| Experiment specs | Copy/paste from previous issues | Dedicated template with hypothesis, appetite, scope |
| Implementation specs | Manual formatting | Template matches verification agent expectations |

## What this means for each team member

**Wilfred**: When creating experiment issues, the template pre-structures the hypothesis, appetite, and scope fields. No more formatting from scratch. The pipeline output maps directly onto the implementation template.

**Rutger**: Implementation issues have clear "What to build" and "Done when" sections. Open a PR with `Closes #N` and the verification agent handles the rest. If something deviates from spec, check the flag and explain in one line.

**Irmak**: Same structure applies. Bug reports have a product dropdown, so issues are immediately categorized. The PR template checklist ensures device/simulator testing is confirmed before review.
