# Example — Starting a New ChatGPT Conversation

User message:

```text
On reprend le travail sur Nicole.
Commence par lire le repo nicole-dev-process, puis attends mes instructions.

WORKSPACE_ROOT=/data/data/com.termux/files/home/Sources/nicole

PROCESS_REPO=${WORKSPACE_ROOT}/nicole-dev-process

SPEC_REPO=${WORKSPACE_ROOT}/nicole_language_docs_seed

IMPLEMENTATION_REPO=${WORKSPACE_ROOT}/nicole_python_implementation
```

Expected ChatGPT behavior:

- understand roles;
- ask for the current task or feature;
- generate Codex prompts using the process templates;
- preserve source-of-truth boundaries.
