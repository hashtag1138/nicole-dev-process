# TEMPLATE — NicolePy Implementation Step

Model recommendation:
- Minimal: GPT-5.4
- Recommended: GPT-5.3-Codex
- Reasoning: medium-high

Role:

IMPLEMENT ONLY THIS STEP.

Do not modify files outside the allowed scope.
Do not commit.
Do not tag.
Do not push.

Nicole specification always wins.

---

# Source of truth

Nicole specification repository:

```text
<PATH_TO_NICOLE_SPEC_REPO>
```

Required spec tag/commit:

```text
<SPEC_TAG_OR_COMMIT>
```

NicolePy repository:

```text
<PATH_TO_NICOLEPY_REPO>
```

Expected NicolePy HEAD/tag:

```text
<NICOLEPY_BASELINE>
```

---

# Preconditions

Run:

```bash
cd <PATH_TO_NICOLEPY_REPO>

git status --short
git rev-parse HEAD
git tag --points-at HEAD
```

Stop if:

```text
worktree not clean
HEAD/tag differs
```

---

# Allowed modified files

```text
<ALLOWED_FILES>
```

---

# Step goal

```text
<STEP_GOAL>
```

---

# Required behavior

```text
<REQUIRED_BEHAVIOR>
```

---

# Explicit non-goals

Do not add:

```text
<NON_GOALS>
```

---

# Tests

Add/update tests for:

```text
<TEST_CASES>
```

---

# Validation

Run:

```bash
.venv/bin/python -m pytest

git diff --stat
git status --short
```

---

# Output format

```markdown
## Modified files

## Implementation summary

## Tests added or updated

## Validation results

## Remaining concerns

## Recommendation
```

Recommendation:

```text
Ready for <STEP_NAME> audit.
```
