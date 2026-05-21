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

## Repositories

Default local paths used by the current workflow:

```text
Nicole spec repository:
/data/data/com.termux/files/home/Sources/nicole_language_docs_seed

NicolePy implementation repository:
/data/data/com.termux/files/home/Sources/nicole_python_implementation

Process repository:
/data/data/com.termux/files/home/Sources/nicole-dev-process
```

Adjust paths in prompts when repositories move.

## Read order for a new ChatGPT conversation

When resuming work, tell ChatGPT:

```text
On reprend le travail sur Nicole.
Commence par lire le repo nicole-dev-process, puis attends mes instructions.
```

Recommended reading order:

1. `WORKFLOW.md`
2. `ROLES.md`
3. `REPOSITORY_POLICY.md`
4. `PROMPT_PROTOCOL.md`
5. `DECISION_LOG.md`
6. `templates/*` as needed

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
