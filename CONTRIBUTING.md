# Contributing to SchedJoules

## How we work

Read the [Way of Working](https://github.com/schedjoules/schedjoules-app/blob/main/docs/WAY_OF_WORKING_GITHUB.md) first. It describes our experiment pipeline, issue structure, and verification process.

Issues are created by the pipeline with numbered specs and clear acceptance criteria. Owners pick up assigned issues, build the implementation, and open PRs. The verification agent checks each PR against the spec automatically.

## Quick reference

1. Pick up your assigned issue
2. Read the spec carefully
3. Build on a feature branch
4. Open a PR with `Closes #N` linking to the issue
5. If the implementation matches the spec: done
6. If the implementation deviates: check the deviation flag and explain in one line

## Branch naming

- `feature/short-description` for new work
- `fix/short-description` for bug fixes

## PR rules

- One concern per PR
- Always link the issue with `Closes #N`
- No direct pushes to main
