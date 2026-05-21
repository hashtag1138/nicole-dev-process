# Decision Log

This file records process-level decisions and selected cross-cutting language-process decisions.

It is not the Nicole language specification.
Language decisions must still be reflected in the Nicole spec repository.

## 2026-05 — Source of truth separation

Decision:

```text
Nicole repository is the source of truth for the language.
NicolePy must not duplicate normative language rules.
```

Reason:

Duplicated local docs in NicolePy created drift and repeated cleanup work.

Impact:

NicolePy should keep only implementation-facing docs and a `SPEC_TARGET.md` file.

## 2026-05 — Standard development cycle

Decision:

```text
Feature work starts with discussion, then spec audit, then spec patch, then implementation audit, then implementation phases.
```

Reason:

This avoids implementing features before semantics are stable.

Impact:

Codex prompts must always include baseline checks and source-of-truth references.

## 2026-05 — DirtyQuote construction reconsideration for v0.15+

Decision:

```text
Reconsider v0.14 rule that pure frames cannot construct DirtyQuote.
```

Preferred future direction:

```text
Pure code may construct DirtyQuote values but may not execute them or pass them to operations that execute them.
```

Reason:

Constructing an effectful computation value is itself pure; execution is the effect boundary.

Impact:

Requires spec and checker changes in a future Nicole version.

## 2026-05 — v0.15 collection-core scope

Decision:

```text
Add collection builtins without introducing Tuple/Pair.
```

Approved additions in spec:

```text
list.is-empty
list.first
list.last
list.append
list.reverse
map.is-empty
map.keys
map.values
```

Excluded:

```text
list.zip
map.to-list
map.entries
Tuple
Pair
```

Reason:

Expose fundamental collection operations without adding a new product type.

## 2026-05 — Release lifecycle distinction

Decision:

```text
Three release layers exist:

1. Git release
   commit + tag

2. Published release
   branch/tag pushed

3. GitHub release
   release entry attached to tag
```

Reason:

Git tags and GitHub releases are distinct concepts and should not be conflated.

Impact:

Release prompts should state which release layer is being executed.
