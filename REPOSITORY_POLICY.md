# Repository Policy

## Nicole repository

The Nicole repository is the only language source of truth.

Normative files:

```text
SYNTAXE.md
SEMANTIQUE.md
HOST_ABI.md
```

Derived/non-normative files may include:

```text
README.md
EXAMPLES.md
INVALID_EXAMPLES.md
DESIGN_NOTES.md
```

Policy:

- language decisions belong here;
- builtins are specified here first;
- syntax and semantics are never invented in NicolePy;
- tags define stable target baselines.

## NicolePy repository

NicolePy implements a pinned Nicole spec tag.

NicolePy may document:

- implementation architecture;
- runtime representation;
- checker passes;
- resolver structures;
- implementation limitations;
- current target spec tag.

NicolePy must not document as source of truth:

- Nicole syntax;
- Nicole typing rules;
- Nicole effect rules;
- builtin signatures;
- host ABI semantics.

Recommended file:

```text
SPEC_TARGET.md
```

Purpose:

```text
State the current Nicole spec tag implemented by NicolePy.
```

## Process repository

This repository documents how work is done.

It must not become:

- a third specification;
- a duplicate Nicole manual;
- a duplicate NicolePy implementation guide.

It should remain short, operational, and template-driven.

## Source-of-truth hierarchy

When conflicts exist:

```text
Nicole spec tag
  > NicolePy implementation docs
  > process templates
  > conversation memory
```

For process questions:

```text
Process repository
  > conversation memory
```

## Cross-repository work

Never patch spec and implementation in one Codex prompt.

Correct flow:

```text
1. Patch Nicole spec.
2. Commit/tag Nicole spec.
3. Audit NicolePy against new spec tag.
4. Patch NicolePy.
5. Commit/tag NicolePy.
```
