---
description: Standards for git automation, commit messages, and branching.
---

# Skill: Git Automation

This skill defines the standards for all git operations performed by the agent.

## 1. Commit Messages (Conventional Commits)
Always use the [Conventional Commits](https://www.conventionalcommits.org/) format:
`type(scope): description`

**Types**:
- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Changes that do not affect the meaning of the code (white-space, formatting, etc)
- `refactor`: A code change that neither fixes a bug nor adds a feature
- `perf`: A code change that improves performance
- `test`: Adding missing tests or correcting existing tests
- `chore`: Changes to the build process or auxiliary tools and libraries

**Example**:
`feat(auth): add google oauth login support`
`fix(ui): resolve button alignment issue on mobile`

## 2. Branching Strategy
- **Feature Branches**: `feat/description-of-feature`
- **Bug Fixes**: `fix/description-of-bug`
- **Hot Fixes**: `hotfix/critical-issue`

## 3. Workflow
1.  **Check Status**: Always run `git status` first.
2.  **Pull Updates**: `git pull` to avoid conflicts (if applicable).
3.  **Stage Changes**: `git add <files>` (be specific, avoid `git add .` unless necessary).
4.  **Commit**: `git commit -m "..."`.
