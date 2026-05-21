# TEMPLATE — Nicole Spec Patch

Model recommendation:
- Minimal: GPT-5.4
- Recommended: GPT-5.3-Codex
- Reasoning: high

Role:

PATCH SPEC ONLY.

Do not modify implementation repositories.
Do not modify NicolePy.
Do not add implementation code.

Goal:

Patch Nicole specification for `<FEATURE>` using only the approved decisions below.

---

# Repository

```text
<PATH_TO_NICOLE_SPEC_REPO>
```

Expected baseline:

```text
<COMMIT_OR_TAG>
```

---

# Preconditions

Run:

```bash
cd <PATH_TO_NICOLE_SPEC_REPO>

git status --short
git rev-parse HEAD
git log -10 --oneline
```

Stop if:

```text
worktree not clean
HEAD differs from expected baseline
```

---

# Allowed files

Modify only:

```text
<ALLOWED_SPEC_FILES>
```

---

# Approved decisions

```text
<APPROVED_DECISIONS>
```

---

# Explicit non-goals

Do not introduce:

```text
<OUT_OF_SCOPE_ITEMS>
```

---

# Required changes

```text
<FILE_BY_FILE_CHANGES>
```

---

# Validation

Run:

```bash
git diff --stat
<RELEVANT_GREP_CHECKS>
```

Verify:

```text
<VALIDATION_EXPECTATIONS>
```

---

# Required output format

```markdown
## Modified files

## Specification changes

## Examples added or updated

## Contradictions removed

## Validation results

## Risks

## Recommendation
```

Recommendation:

```text
Ready for <FEATURE> spec audit.
```
