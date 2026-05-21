# TEMPLATE — NicolePy Implementation Step Audit

Model recommendation:
- Minimal: GPT-5.4
- Recommended: GPT-5.3-Codex
- Reasoning: medium-high

Role:

AUDIT ONLY.

Do not modify files.
Do not commit.
Do not tag.
Do not push.

Goal:

Audit the completed implementation step `<STEP_NAME>`.

---

# Repository

```text
<PATH_TO_NICOLEPY_REPO>
```

Expected HEAD:

```text
<EXPECTED_HEAD>
```

Expected modified files:

```text
<EXPECTED_FILES>
```

---

# Preconditions

Run:

```bash
cd <PATH_TO_NICOLEPY_REPO>

git status --short
git rev-parse HEAD
git diff --stat
```

Stop if:

```text
HEAD differs
unexpected modified files exist
```

---

# Audit checklist

```text
<CHECKLIST>
```

---

# Required output format

```markdown
## Summary

## Scope findings

## Behavior findings

## Test findings

## Regression findings

## Risks

## Recommendation
```

Recommendation must be one of:

```text
<STEP_NAME> passes audit.
<STEP_NAME> requires correction.
```
