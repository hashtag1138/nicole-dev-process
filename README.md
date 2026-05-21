# Nicole Dev Process

This repository documents the development process used for the Nicole language specification and the NicolePy implementation.

It is **not** the Nicole language specification.
It is **not** the NicolePy implementation documentation.
It is a process repository: roles, workflow, prompt protocol, repository policy, and reusable Codex prompt templates.

## Purpose

The process exists to make work reproducible across conversations and tools:

- feature discussion happens with the user and ChatGPT;
- Codex performs repository audits and edits;
- the official Nicole spec remains the source of truth;
- NicolePy implements a pinned Nicole spec tag;
- every meaningful change is audited before and after implementation;
- commits/tags are created only after validation.

## Read first

1. `README.md`
2. `WORKFLOW.md`
3. `PROMPT_PROTOCOL.md`

For a complete startup example see:

`examples/start-new-conversation.md`

## Optional documents

- `ROLES.md`
- `REPOSITORY_POLICY.md`
- `DECISION_LOG.md`
- `templates/*`

## Repositories

Current workspace layout:

```text
WORKSPACE_ROOT=/data/data/com.termux/files/home/Sources/nicole

SPEC_REPO=${WORKSPACE_ROOT}/nicole_language_docs_seed

IMPLEMENTATION_REPO=${WORKSPACE_ROOT}/nicole_python_implementation

PROCESS_REPO=${WORKSPACE_ROOT}/nicole-dev-process
```

Prefer these variables in prompts and examples rather than repeating repository paths inline.

## Core rule

Nicole source of truth:

```text
Nicole repository:
SYNTAXE.md
SEMANTIQUE.md
HOST_ABI.md
```

NicolePy must not redefine language semantics. It implements a pinned Nicole spec tag.

## Process evolution

Codex may also work on this repository.
When changing this process repository:

- audit first;
- keep changes small;
- avoid embedding Nicole language rules here;
- update templates when the workflow changes;
- tag stable process versions.
