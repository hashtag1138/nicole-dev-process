# TEMPLATE — Nicole Spec Release

Model recommendation:
- Minimal: GPT-5.4
- Recommended: GPT-5.3-Codex
- Reasoning: low-medium

Role:

Finalize spec changes only.

Do not modify files.
Do not add cleanup work.

---

# Repository

```text
<PATH_TO_NICOLE_SPEC_REPO>
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
cd <PATH_TO_NICOLE_SPEC_REPO>

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

# Stage exact files

```bash
git add \
<FILES>
```

---

# Commit

```bash
git commit -m "<COMMIT_MESSAGE>"
```

---

# Tag

```bash
git tag -a <TAG_NAME> -m "<TAG_MESSAGE>"
```

---

# Push

```bash
git push origin main
git push origin <TAG_NAME>
```

---

# Output format

```markdown
## Modified files

## Validation results

## Commit

## Tags created

## Push results

## Final repository state

## Recommendation
```
