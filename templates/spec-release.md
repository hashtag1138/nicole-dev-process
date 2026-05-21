# TEMPLATE — Nicole Spec Release

Model recommendation:
- Minimal: GPT-5.4
- Recommended: GPT-5.3-Codex
- Reasoning: low-medium

Role:

Finalize spec changes only.

Do not modify files.
Do not add cleanup work.

Process baseline:

- `README.md` read
- `WORKFLOW.md` read
- `PROMPT_PROTOCOL.md` read

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
${SPEC_REPO}
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
cd ${SPEC_REPO}

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
