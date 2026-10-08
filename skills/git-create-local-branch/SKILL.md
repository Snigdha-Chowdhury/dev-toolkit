---
name: git-create-local-branch
description: Create a new local Git branch from a source branch, preserve current changes, validate remote branches, and follow branch naming and lifecycle best practices. Use this skill when the user says "Create a new Branch", "run/git-local-branch", "run/create-local-branch", "run/local-branch", or "run/create-branch".
---

# Git Create Local Branch

Create a new local Git branch using the source and target branch names provided by the user.

Check the current working branch for existing changes using `git status`. If changes exist, run `git stash`. If no changes exist, continue. Fetch the latest remote changes using `git fetch origin` or `git pull origin <source-branch>`. Verify that the source branch exists on `origin`. Verify that the target branch does not already exist on `origin`. Check out the new local branch using `git checkout -b <target-branch>`. Ensure that the new local branch tracks the correct remote branch if applicable.

Always check `origin` to confirm whether a branch exists remotely.

Use a structured, lowercase format separated by forward slashes (`/`) or hyphens (`-`).

- `feature/` or `feat/`: New feature development, for example `feature/login-page`.
- `bugfix/` or `fix/`: Standard bug fixes, for example `bugfix/issue-404-broken-link`.
- `hotfix/`: Urgent production fixes, for example `hotfix/security-patch`.
- `docs/` or `chore/`: Documentation updates or routine tasks, such as dependency updates.

Do not let feature branches linger. The longer a branch remains disconnected from the core branch, such as `main` or `develop`, the harder it becomes to merge because of branch drift.

- Aim to merge branches within a few days, rather than weeks.
- Break down large projects into smaller, independent tasks.
- Keep individual branches concise and focused.

## Workflow

1. Ask the user for the source branch and target branch.
2. Run `git status` to check the current working branch for existing changes.
3. If changes exist, run `git stash` and confirm that the stash was created. If no changes exist, continue without stashing.
4. Run `git fetch origin` or `git pull origin <source-branch>` to get the latest changes from the source branch.
5. Verify that the source branch exists on `origin`.
6. Verify that the target branch does not already exist on `origin`.
7. Create the new local branch using `git checkout -b <target-branch>`.
8. Ensure the new branch tracks the appropriate remote branch if applicable.
9. Verify the active branch and working tree.
10. If a stash was created, apply it with `git stash apply` after creating the branch.

## Best practices

- Use lowercase branch names and structured prefixes.
- Verify remote branch existence before creating a local branch.
- Do not overwrite an existing local or remote branch.
- Do not use `git checkout -B` or any forced reset.
- Keep feature branches short-lived and merge them promptly.
- Rebase or merge the latest core branch before creating a pull request.
- Fetch and prune `origin` frequently to detect drift.
- Delete merged branches when they are no longer needed.

Trigger when the user says:

- "Create a new Branch"
- "run/git-local-branch"
- "run/create-local-branch"
- "run/local-branch"
- "run/create-branch"
