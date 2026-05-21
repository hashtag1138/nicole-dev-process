# Prompt Protocol

This document defines the standard structure of Codex prompts used in the Nicole workflow.

## Universal prompt rules

Every Codex prompt should include:

```text
1. Title
2. Model recommendation
3. Role
4. Source of truth
5. Repository path
6. Expected baseline commit/tag
7. Preconditions
8. Scope
9. Explicit non-goals
10. Required actions
11. Validation commands
12. Output format
13. Final recommendation wording
```

## Stop conditions

Codex must stop when:

- worktree is not clean when clean is required;
- HEAD differs from expected baseline;
- required tag is absent;
- unexpected files are modified;
- tests fail after implementation;
- source of truth is missing;
- prompt scope is ambiguous.

## Prompt types

### SPEC_AUDIT

Purpose:

```text
Read Nicole spec and determine what must change.
```

No file modifications.

Must output:

- existing state;
- contradictions;
- missing decisions;
- recommended patch plan;
- whether patching can begin.

### SPEC_PATCH

Purpose:

```text
Modify Nicole spec documents only.
```

Must include:

- exact files allowed;
- approved decisions;
- forbidden scope creep;
- grep validation for contradictions;
- post-patch audit recommendation.

### SPEC_AUDIT_POST_PATCH

Purpose:

```text
Verify spec patch consistency before commit.
```

Must compare:

- syntax vs semantics;
- examples vs invalid examples;
- deferred/out-of-scope lists;
- source-of-truth files.

### SPEC_RELEASE

Purpose:

```text
Commit, tag, and push spec changes.
```

Must include exact `git add` file list.

### IMPLEMENTATION_AUDIT

Purpose:

```text
Compare NicolePy implementation against a pinned Nicole spec tag.
```

Must produce a gap matrix:

```text
feature | spec | symbols/checker | runtime | tests | status
```

### IMPLEMENTATION_PLAN

Purpose:

```text
Convert audit result into phased implementation plan.
```

No code changes.

### IMPLEMENTATION_STEP

Purpose:

```text
Implement one phase only.
```

Must include:

- allowed files;
- forbidden files;
- validation commands;
- expected tests.

### IMPLEMENTATION_AUDIT_STEP

Purpose:

```text
Audit a completed implementation step.
```

No modifications.

### IMPLEMENTATION_RELEASE

Purpose:

```text
Commit, tag, and push implementation changes.
```

Must include exact staged files and final clean state check.

### RECOVERY_CHECK

Purpose:

```text
Classify repository state after interrupted Codex execution.
```

No modifications unless explicitly requested.

### Workspace contamination check

Purpose:

```text
Detect external artifacts that may affect process validation.
```

Include:

```bash
ls -ld <external-path> || true
```

## Model recommendation block

Every prompt should include:

```text
Model recommendation:
- Minimal: <model>
- Recommended: <model>
- Reasoning: <low|medium|high>
```

## Output formats

Output formats should be exact and structured.
Avoid freeform reports when a decision is needed.

Common final recommendations:

```text
Ready to patch ...
Ready for ... audit.
Ready for ... commit.
Additional work required before ...
Implementation complete for ...
```

Residual gap reporting block:

```text
Known residual gaps:
Blocking:
Non-blocking:
Deferred:
```
