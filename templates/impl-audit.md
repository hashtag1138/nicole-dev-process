# TEMPLATE — NicolePy Implementation Audit

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

Audit NicolePy against a pinned Nicole specification tag for `<FEATURE>`.
Produce a precise gap matrix before implementation.

Nicole specification always wins.

---

# Repositories

Nicole specification repository:

```text
<PATH_TO_NICOLE_SPEC_REPO>
```

Expected spec tag/commit:

```text
<SPEC_TAG_OR_COMMIT>
```

NicolePy repository:

```text
<PATH_TO_NICOLEPY_REPO>
```

Expected NicolePy baseline:

```text
<NICOLEPY_TAG_OR_COMMIT>
```

---

# Preconditions

Run in spec repo:

```bash
cd <PATH_TO_NICOLE_SPEC_REPO>

git status --short
git rev-parse HEAD
git tag --points-at HEAD
```

Run in NicolePy repo:

```bash
cd <PATH_TO_NICOLEPY_REPO>

git status --short
git rev-parse HEAD
git tag --points-at HEAD
```

Stop if either repository differs from expected state.

---

# NicolePy files to inspect

```text
src/nicole/standard_symbols.py
src/nicole/checker.py
src/nicole/runtime.py
src/nicole/host_abi.py
src/nicole/parser.py
src/nicole/ast_nodes.py
src/nicole/pipeline.py
tests/*
README.md
docs/*
```

---

# Gap matrix

For each feature item report:

```text
Spec requirement
Standard symbol / parser support
Checker support
Runtime support
Tests
Status: implemented | partial | missing | contradicted
```

---

# Required output format

```markdown
## Summary

## Spec baseline verification

## NicolePy baseline verification

## Gap matrix

## Existing behavior/regression findings

## ABI findings

## Effect-system findings

## Test gaps

## Implementation impact estimate

## Risks

## Recommendation
```

Recommendation must be one of:

```text
Ready to implement NicolePy <FEATURE>.
More design/audit work required before implementation.
```
