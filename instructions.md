# INSTRUCTIONS.md — Autonomous Codex Behavior Manual

# Project: Physical AI Textbook Engine

# Purpose: Define EXACT behavior Codex must follow.

Codex MUST follow every rule in this file.

──────────────────────────────────────────────────────────────

# 1. GENERAL BEHAVIOR RULES

Codex MUST:

- Execute tasks strictly in order.
- **LOG EVERYTHING**: Generate history and commit files for EVERY interaction.

──────────────────────────────────────────────────────────────

# 2. TASK EXECUTION RULES

Codex ONLY executes tasks when the user says:
`Proceed with Task <number>`

After completing a task, Codex MUST:

1. Mark the task as done `[x]` in tasks.md
2. Generate a history file
3. Generate a GitHub commit file
4. STOP and wait.

──────────────────────────────────────────────────────────────

# 3. HISTORY FILE RULES (LOG EVERYTHING)

**Rule:** Every prompt/message from the user triggers a history file.

- **Task-based**: `history/prompts/<category>/task-<number>-<name>.md`
- **Misc/General**: `history/prompts/misc/<timestamp>-<topic>.md`

──────────────────────────────────────────────────────────────

# 4. GITHUB COMMIT FILE RULES (LOG EVERYTHING)

**Rule:** Every prompt/message from the user triggers a commit file.

- **Task-based**: `github-commit/task-<number>-<name>.commit.md`
- **Misc/General**: `github-commit/misc-<timestamp>-<topic>.commit.md`

**CRITICAL: AUTOMATIC GIT PUSH**
After generating the commit file, Codex MUST automatically:
1. Ensure Git is initialized and remote is set to: `https://github.com/NomanKhaliq1/Physical-AI-Textbook-Engine`
2. Run the actual git commands:
   ```bash
   git add .
   git commit -m "<Commit Title>"
   git push origin main
   ```

──────────────────────────────────────────────────────────────

# 5. USER INTERACTION RULES

Codex MUST read `instructions.md` after EVERY task.

──────────────────────────────────────────────────────────────

# END OF INSTRUCTIONS.md
