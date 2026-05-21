# Workflow

This document defines the standard workflow for Nicole and NicolePy work.

The workflow is intentionally conservative. It favors explicit baselines, audits, small phases, and reproducible prompts.

## 0. Process bootstrap

Before starting a major phase:

- verify process repository location
- read:
  - `README.md`
  - `WORKFLOW.md`
  - `PROMPT_PROTOCOL.md`
- identify source-of-truth repository
- identify target repository
- identify expected baseline commit/tag

This step applies only to:

- new conversations
- resumed interrupted work
- beginning of a new feature
- beginning of a specification phase
- beginning of an implementation phase

## Actors

- User: proposes features, makes tradeoffs, approves decisions.
- ChatGPT: supervises, analyzes, challenges, drafts Codex prompts.
- Codex: audits repositories, edits files, runs validation, reports results.
- Repositories: source of truth and implementation artifacts.

## Global invariants

Every task must respect these invariants:

```text
1. Source of truth must be explicit.
2. Repository baseline must be checked before work.
3. Audit precedes patching.
4. Patch scope must be explicit.
5. Post-patch audit precedes commit.
6. Commit/tag/push happen only after validation.
7. Spec and implementation work are not mixed.
8. No tool silently continues after failed preconditions.
```

## Feature lifecycle

```text
Process bootstrap
  ↓
Idea
  ↓
Discussion and tradeoff analysis
  ↓
Spec audit
  ↓
Decision review
  ↓
Spec patch
  ↓
Spec audit
  ↓
Spec commit/tag/push
  ↓
Implementation audit against pinned spec
  ↓
Implementation plan
  ↓
Implementation phase 1
  ↓
Phase audit
  ↓
Plan/roadmap update
  ↓
Repeat phases as needed
  ↓
Final implementation audit
  ↓
Implementation commit/tag/push
```

## Discussion phase

Before any repository work, discuss:

- purpose;
- user-facing value;
- semantic consequences;
- implementation complexity;
- pitfalls;
- alternatives;
- out-of-scope items;
- minimum coherent surface.

The discussion should end with a small set of explicit decisions.

## Spec phase

Spec work happens in the Nicole repository.

Standard sequence:

```text
1. Spec audit
2. Decision review
3. Spec patch
4. Spec audit
5. Commit/tag/push
```

Spec patching must modify only specification documents.
It must not modify NicolePy.

## Implementation phase

Implementation work happens in NicolePy.

Standard sequence:

```text
1. Implementation audit against pinned spec tag
2. Gap matrix
3. Implementation plan
4. Step implementation
5. Step audit
6. Roadmap update
7. Repeat
8. Final audit
9. Commit/tag/push
```

## Recovery workflow

If Codex stops mid-task or model capacity fails, do not assume repository state.

Run:

```bash
git status --short
git rev-parse HEAD
git tag --points-at HEAD
git diff --stat
```

Classify:

```text
Clean baseline:
  rerun original prompt.

Partial expected changes:
  audit diff and continue only if safe.

Unexpected source/test changes:
  stop and restore or inspect manually.
```

Tool failure recovery additions:

- do not infer successful completion;
- classify partial-change state;
- run recovery checks;
- prefer repository-relative paths;
- record unavailable tools.

## WORKSPACE_CLEANUP

Purpose:

```text
Remove temporary artifacts created during development tooling.
```

Checks:

- `git status --short`
- `git diff --name-only`
- external artifact existence
- repository integrity after cleanup

Requirements:

- cleanup must not modify tracked files;
- cleanup artifacts must remain outside repository contents.

## RELEASE_FIXUP

Purpose:

```text
Correct release metadata state.
```

Examples:

- release notes added after tag creation;
- tag attached to wrong commit;
- release metadata incomplete.

## Commit/tag policy

Commits should be small and phase-specific.

Examples:

```text
docs: add v0.15 collection core spec
feat: add phase 5 dirty quote effects
fix: enforce v0.14 ABI type whitelist
chore: clean up v0.14 repository hygiene
```

Tags should mark stable boundaries:

```text
v0.15.0-collection-core-spec
v0.15.0-collection-core-implementation
v0.14.1-cleanup
```
