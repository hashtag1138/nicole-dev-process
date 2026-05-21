# TEMPLATE — NicolePy Implementation Release

Model recommendation:
- Minimal: GPT-5.4
- Recommended: GPT-5.3-Codex
- Reasoning: low-medium

Role:

Finalize implementation changes only.

Do not modify files.
Do not add cleanup work.

---

# Workspace

```text
WORKSPACE_ROOT=<WORKSPACE_ROOT>

SPEC_REPO=${WORKSPACE_ROOT}/nicole_language_docs_seed

IMPLEMENTATION_REPO=${WORKSPACE_ROOT}/nicole_python_implementation

PROCESS_REPO=${WORKSPACE_ROOT}/nicole-dev-process
```

---

# Repository

```text
${IMPLEMENTATION_REPO}
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

# Validation

Run:

```bash
.venv/bin/python -m pytest

git diff --stat
git status --short
```

Stop if tests fail or unexpected files are modified.

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
