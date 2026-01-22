---
description: A "Quality Gate" to verify valid alignment between Plan, Code, and Intent.
---

# Workflow: Verify Alignment (The "Feedback Loop")

This workflow acts as a strict "CodeRabbit" reviewer for your own work.

## When to Run
- **Trigger**: IMMEDIATELY after writing code or refactoring (Task Status: `Verification`).
- **Skip**: When answering questions, explaining concepts, or planning.


## Steps

1.  **Fetch The Plan**:
    Read the active `implementation_plan.md` to remind yourself of the *Promised Scope*.
    (If no plan exists, use the User's last prompt as the source of truth).

2.  **Analyze Changes (Git-Agnostic)**:
    -   **Git Available**: Run `git diff HEAD` (or staged changes) to see the *Actual Code*.
    -   **No Git**: Identify files modified in the last 1 hour using `find . -type f -mmin -60 -not -path '*/.*'`.
    -   **Context**: Review the specific files you just edited.

3.  **Integrity Check (The "Paranoia" Scan)**:
    -   **Truncation**: "Did the file size drop drastically? Does the file end abruptly?"
    -   **Context Loss**: "Did I delete a function that was actually needed? Did I ignore the root directory context?"
    -   **Memory**: "Does this contradict what I said 5 minutes ago?"

4.  **The "Architect's Gaze" (Audit)**:
    Compare **Plan** vs **Actual Code** using strict criteria:
    -   **Economy of Code**: "Did you use 20 lines where 5 would do? Rewrite it."
    -   **Critical Thinking**: "Did you just copy-paste, or did you solve the *root cause*?"
    -   **Hallucination Check**: "Did you verify that variable exists?"
    -   **Feasibility Check**: "Is this actually possible? Did you promise the moon? Be honest."
    -   **Prudence**: "Is this action calculated and necessary?"

5.  **Verdict**:
    Generate a report:
    -   ✅ **aligned**: Code matches intent perfectly.
    -   ⚠️ **warning**: Minor issues (style, comments).
    -   ❌ **misaligned**: Scope creep, hallucinations, truncation, or complexity violations. STOP and fix.
