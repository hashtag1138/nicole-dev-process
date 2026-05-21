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

# Preconditions

Run:

```bash
cd ${IMPLEMENTATION_REPO}

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
