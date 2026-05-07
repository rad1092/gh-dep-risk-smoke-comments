# gh-dep-risk smoke comments

Owned fixture PRs for `gh-dep-risk` comment-upsert smoke tests.

This repository exists so remote comment mode can be tested without a
cross-repository PAT. The `comment-smoke` workflow checks out
`rad1092/gh-dependency-risk`, builds the requested ref, and comments on a PR in
this repository with this repository's `GITHUB_TOKEN`.

## Fixture PR

- [#1 Add express to npm app](https://github.com/rad1092/gh-dep-risk-smoke-comments/pull/1): npm `package-lock.json`

## Remote Comment Smoke

```bash
gh workflow run comment-smoke.yml --repo rad1092/gh-dep-risk-smoke-comments -f pr=1 -f source_ref=main -f no_registry=true
gh run watch --repo rad1092/gh-dep-risk-smoke-comments
```

The workflow permissions are intentionally repository-scoped:

- `contents: read`
- `pull-requests: write`
- `issues: write`

Read-only analysis fixtures live in
[`rad1092/gh-dep-risk-smoke-matrix`](https://github.com/rad1092/gh-dep-risk-smoke-matrix).

Main project documentation:
[`docs/smoke-test.md`](https://github.com/rad1092/gh-dependency-risk/blob/main/docs/smoke-test.md).
