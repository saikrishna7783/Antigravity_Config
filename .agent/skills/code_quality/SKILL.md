---
description: A skill to review code for quality, security, and performance.
---

# Skill: Code Quality Review

When asked to "review code" or "check quality", follow this procedure:

## 1. Static Analysis
- **Linter Check**: Look for obvious syntax errors, unused variables, or undefined imports.
- **Formatting**: Ensure consistent indentation and style (matches existing codebase).

## 2. Architectural Review
- **Complexity**: Identify functions that are too long or complex (Cyclomatic Complexity).
- **Coupling**: Flag tight coupling between unrelated components.
- **DRY (Don't Repeat Yourself)**: Point out duplicated logic that should be refactored into helpers.
- **Professionalism**: Ensure no emojis in comments/code. Comments should be technical and formal.

## 3. Best Practices
- **Naming**: Are variable/function names descriptive? (e.g., `getUserById` vs `func1`)
- **Error Handling**: Are errors caught and handled gracefully? No empty `catch` blocks.
- **Security**: Check for hardcoded secrets, injection vulnerabilities, or unsafe inputs.

## 4. Semantic Alignment (The "Jules" Check)
- **Intent Matching**: Does the code actually solve the user's problem?
- **Scope Creep**: Did you add code that wasn't asked for? (Remove it).
- **Complexity**: Is this the simplest way to solve the problem? (Economy of Code).

## Output Format
Provide the review in the following markdown format:
```markdown
### 🔍 Code Quality & Alignment Review

**Summary**: [Brief verdict: Pass, Needs Improvement, or Critical Issues]

**Issues**:
- [Severity: Low/Med/High] Description of issue @ [File:LineNumber]

**Suggestions**:
- Refactoring ideas or improvements.
```
