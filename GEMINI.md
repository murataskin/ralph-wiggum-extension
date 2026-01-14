# Ralph Wiggum Extension for Gemini CLI

> "Me fail English? That's unpossible!"

This extension implements the **Ralph Wiggum** technique for iterative development.

## The Ralph Philosophy

1.  **Memory is File-Based**: Ralph forgets everything in the chat window. His memory is strictly:
    *   `RALPH_TASK.md` (The Anchor / Goal)
    *   `.ralph/progress.md` (The Memory / Log)
    *   `.ralph/guardrails.md` (The Signs / Laws)
    *   The Codebase (The Reality)

2.  **Context Pollution is Toxic**: The "chat context" accumulates errors and confusion. Ralph clears his head by relying ONLY on the files.

3.  **Guardrails are Learned**: When Ralph touches a hot stove, he puts up a sign. `.ralph/guardrails.md` contains these signs. **Read them before acting.**

## Commands

### `/ralph:init`
Initialize the Ralph state structure in the current directory.
- Creates `.ralph/`
- Creates templates for Task, Progress, and Guardrails.

### `/ralph:loop`
Start (or continue) working on the task defined in `RALPH_TASK.md`.
- Reads state files.
- Executes the next step.
- Updates progress.

### `/ralph:status`
Display the current state of the loop (Task, Progress, Signs).

### `/ralph:learn`
Add a new "Sign" to `.ralph/guardrails.md`. Use this when a mistake is made to prevent it from happening again.

### `/ralph:log`
Manually append an entry to `.ralph/progress.md`.

## Workflow

1.  **Init**: Run `/ralph:init` in your project root.
2.  **Define**: Edit `RALPH_TASK.md` to describe what you want to build.
3.  **Loop**: Run `/ralph:loop`. Ralph will work on the first item.
4.  **Iterate**: As Ralph completes items, he updates `progress.md`. If he fails, he updates `guardrails.md`.
5.  **Done**: When all items in `RALPH_TASK.md` are checked `[x]`.

## The State Files

-   **`RALPH_TASK.md`**: The immutable (mostly) definition of "Done".
-   **`.ralph/guardrails.md`**: A list of "Signs". E.g., *"Sign: Read Before Write | Trigger: Modifying a file | Instruction: Read file content first."*
-   **`.ralph/progress.md`**: A checklist of what has been done in previous iterations.

---
*Powered by "I'm helping!" energy.*