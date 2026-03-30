# Contributing to SchedJoules

## How we work

Read the [Way of Working](https://github.com/schedjoules/schedjoules-app/blob/main/docs/WAY_OF_WORKING_GITHUB.md) first. It describes our experiment pipeline, issue structure, and verification process.

Issues are created by the pipeline with numbered specs and clear acceptance criteria. Owners pick up assigned issues, build the implementation, and open PRs. The verification agent checks each PR against the spec automatically.

## Development setup

We develop AI-first: Claude Code writes the Swift code, humans steer and review. Xcode is still required for compiling, signing, and running on simulator/device.

Here is how the full setup works:

1. **Claude Code** is the primary development tool. It writes Swift code, runs `xcodebuild` commands, and iterates on compiler errors. The human provides direction, reviews output, and makes judgment calls.

2. **`CLAUDE.md` in each repo** gives Claude full context about the codebase: build commands, architecture (API layer, managers, view controllers), third-party SDKs, and learned rules about how things work. This is what makes Claude effective on our codebase specifically.

3. **Specialized agents** (`.claude/agents/`) handle focused tasks: iOS development, UX research, analytics, feedback analysis, ASO, growth strategy. Each agent has its own prompt with domain knowledge.

4. **claude-code-action on GitHub Actions** automatically reviews every PR. It checks for spec alignment, scope drift, and whether PostHog tracking is present. It also responds to `@claude` mentions in issues and PRs.

5. **Verification agent** runs when a PR merges and verifies that the implementation matches the experiment spec. This is the final automated quality gate.

6. **Issue templates** (experiment, implementation, bug) at org level enforce structured input so the pipeline can parse and process issues consistently.

7. **CODEOWNERS and branch protection** on each repo require review from the right person plus a passing Claude review before any PR can merge.

8. **PR template** with linked issue, deviation flag, and checklist. Deliberately minimal to reduce human input.

9. **CI-specific `CLAUDE.md`** (`.github/CLAUDE.md`) gives the review agent its own instructions: review priorities, tone, and constraints (no auto-merge, no direct pushes).

10. **Signing and distribution** are managed through the Apple Developer portal. Certificates and provisioning profiles are stored centrally, not on any individual machine. Any Mac with Xcode and the developer account can build and release.

## Quick reference

1. Pick up your assigned issue
2. Read the spec carefully
3. Build on a feature branch
4. Open a PR with `Refs #N` linking to the issue. Use `Closes #N` only in the PR description when the issue is fully resolved.
5. If the implementation matches the spec: done
6. If the implementation deviates: check the deviation flag and explain in one line

## Branch naming

- `feature/short-description` for new work
- `fix/short-description` for bug fixes

## PR rules

- One concern per PR
- Always link the issue with `Closes #N`
- No direct pushes to main
