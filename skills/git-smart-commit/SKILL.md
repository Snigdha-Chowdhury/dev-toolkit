---
name: git-smart-commit
description: Create a conventional Git commit from the current working changes, confirm staging when needed, and run the commit without a Co-Authored-By trailer. Use this skill when the user says "Write a commit message", "generate a commit", "commit my changes", "run/git-smart-commit", or "run/git-commit".
---

# Git Smart Commit

Create a conventional Git commit from the current repository changes. Follow this workflow exactly.

## 1. Check the current branch

Run:

```bash
git branch
```

Confirm that the active branch is correct. Do not commit until the user confirms the branch. If the branch is wrong, stop and ask which branch to use.

## 2. Check for changes

Run:

```bash
git status
git diff
git diff --cached
```

If there are no staged or unstaged changes, stop immediately and tell the user: "No staged or unstaged changes were found. Make some changes before generating a commit."

## 3. Stage changes only after explicit confirmation

If changes are unstaged, ask the user whether to stage everything or only specific files.

- If the user chooses all files, run:

  ```bash
  git add .
  ```

- If the user chooses specific files, ask for the file names and run:

  ```bash
  git add <filename>
  ```

  Repeat for each selected file.

- If the user says to skip staging, stop and ask them to stage the intended files.

Never stage files automatically without explicit user confirmation.

## 4. Generate the commit message

Review the staged diff and write a conventional commit message in this format:

```text
type(scope): short subject

- bullet of what changed
- bullet of why changed
```

Rules:

- Use only `feat`, `fix`, `refactor`, `docs`, `test`, or `chore`.
- Keep the subject under 60 characters.
- Omit the scope when it does not improve clarity.
- Keep the bullets brief and factual.
- Do not include a `Co-Authored-By` trailer or any other trailer.
- Do not include unrelated content.

If the diff is ambiguous, ask a concise clarification question instead of guessing.

## 5. Commit the changes

Run:

```bash
git commit -m "<generated message>"
```

If Git reports that no changes are staged, stop and ask the user to stage the intended files.

If the commit succeeds, report the branch name, commit hash, and final commit message.

Do not run `git commit --amend` or rewrite existing commits.
