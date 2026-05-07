# gh-dep-risk smoke comments

This repository holds owned fixture PRs for `gh-dep-risk` comment-upsert smoke
tests.

The `comment-smoke` workflow checks out `rad1092/gh-dependency-risk`, builds
the requested ref, and comments on a PR in this repository with this
repository's `GITHUB_TOKEN`. No cross-repository write token is required.
