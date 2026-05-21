# TEMPLATE — Recovery Check

Model recommendation:
- Minimal: GPT-5.4
- Recommended: GPT-5.3-Codex
- Reasoning: low-medium

Role:

RECOVERY CHECK FIRST.

Do not modify files until repository state is classified.

Repository:

```text
<PATH_TO_REPO>
```

Expected baseline:

```text
<EXPECTED_HEAD_OR_TAG>
```

Run:

```bash
cd <PATH_TO_REPO>

git status --short
git rev-parse HEAD
git tag --points-at HEAD
git diff --stat
git diff --name-status
```

Classify:

## Case A — clean baseline

If expected HEAD/tag and empty status:

```text
Ready to rerun original prompt from scratch.
```

## Case B — partial expected changes

If only expected files are modified:

```text
Partial expected changes detected.
Safe to continue after inspecting diff.
```

## Case C — unsafe changes

If source/test files are modified unexpectedly, or HEAD/tag differs:

```text
Unsafe state detected.
Recommend restore or manual inspection before retry.
```

Output:

```markdown
## Repository state

## Diff classification

## Detected case

## Recommendation
```
