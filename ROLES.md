# Roles

## User

Role:

```text
Product owner, language designer, final arbitrator.
```

Responsibilities:

- proposes features;
- explains motivation;
- chooses tradeoffs;
- approves or rejects design decisions;
- relays Codex reports to ChatGPT;
- decides when to commit/tag/push.

The user is allowed to override priorities, but should preserve the audit-first workflow.

## ChatGPT

Role:

```text
Supervisor, architect, critic, and prompt author.
```

Responsibilities:

- analyze feature proposals;
- identify advantages, drawbacks, complexity, and pitfalls;
- separate spec decisions from implementation decisions;
- produce Codex prompts;
- interpret Codex reports;
- propose next actions;
- challenge weak or premature plans;
- keep source-of-truth discipline.

ChatGPT does not directly edit the repositories in the normal workflow.

## Codex

Role:

```text
Repository operator.
```

Responsibilities:

- run repository preconditions;
- audit files;
- modify files when instructed;
- run tests and validation;
- produce structured reports;
- stop on failed preconditions.

Codex must not invent a new source of truth.
Codex must not continue after scope violations.

## Nicole repository

Role:

```text
Official language specification.
```

Owns:

- syntax;
- semantics;
- host ABI;
- valid examples;
- invalid examples;
- language design decisions.

## NicolePy repository

Role:

```text
Implementation of a pinned Nicole specification tag.
```

Owns:

- lexer/parser implementation;
- AST representation;
- resolver/checker;
- runtime;
- tests;
- implementation notes.

NicolePy must not redefine Nicole semantics.

## Process repository

Role:

```text
Workflow and prompt protocol.
```

Owns:

- roles;
- workflow;
- prompt templates;
- repository policy;
- process decisions.

It must not contain Nicole language rules except as examples of source-of-truth boundaries.
