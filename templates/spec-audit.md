# TEMPLATE — Nicole Spec Audit

Model recommendation:
- Minimal: GPT-5.4
- Recommended: GPT-5.3-Codex
- Reasoning: high

Role:

AUDIT ONLY.

Do not modify files.
Do not commit.
Do not tag.
Do not push.

Goal:

Audit the Nicole specification repository for `<FEATURE>`.
Determine what already exists, what is missing, what contradicts the proposed feature, and whether more design decisions are required.

Nicole specification is the source of truth.

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

Expected baseline:

```text
<COMMIT_OR_TAG>
```

---

# Preconditions

Run:

```bash
cd ${SPEC_REPO}

git status --short
git rev-parse HEAD
git tag --points-at HEAD
git log -10 --oneline
```

Stop if:

```text
worktree not clean
HEAD/tag differs from expected baseline
```

---

# Files to inspect

Inspect at least:

```text
README.md
SYNTAXE.md
SEMANTIQUE.md
HOST_ABI.md
EXAMPLES.md
INVALID_EXAMPLES.md
```

Also grep for:

```text
<FEATURE_TERMS>
```

---

# Audit questions

1. What is already specified?
2. What is missing?
3. What contradicts the proposed feature?
4. What decisions are still required?
5. What files/sections must change?
6. What examples/invalid examples must change?
7. What is out of scope?

---

# Required output format

```markdown
## Summary

## Existing specification findings

## Missing specification items

## Contradictions

## Decisions required

## Files and sections to change

## Examples to add or update

## Out-of-scope items

## Risks

## Recommendation
```

Final recommendation must be one of:

```text
Ready to patch <FEATURE> spec.
More design decisions required before patching.
```
