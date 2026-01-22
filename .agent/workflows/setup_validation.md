---
description: Workflow to validate the installation of Global Skills and Rules.
---

# Workflow: Setup Validation

This workflow validates that the "Antigravity Pro" environment is correctly configured.

## Steps

1.  **Verify Rules**:
    Check if the global rules are readable.
    `cat /home/kris/.gemini/GEMINI.md`

2.  **Verify Skills Structure**:
    Ensure the skills directory exists and is populated.
    `ls -R /home/kris/.agent/skills`

3.  **Test Skill Awareness**:
    Read the description of the `code_quality` skill to confirm access.
    `grep "description" /home/kris/.agent/skills/code_quality/SKILL.md`

4.  **Self-Check**:
    If all commands succeed, the setup is **COMPLETE**.
    Print: "✅ Antigravity Pro Setup: Verified & Active."
