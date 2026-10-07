# dev-toolkit

A small collection of reusable development workflows and project-scoped skills for AI coding assistants.

## Git Smart Commit

The Git Smart Commit skill helps an AI assistant create a conventional Git commit safely. It is located at [skills/git-smart-commit/SKILL.md](skills/git-smart-commit/SKILL.md).

### How an AI agent can use it

An AI assistant should read the skill file, identify its workflow and trigger phrases, and follow the instructions in the repository context. The assistant may be invoked through a supported project-skill interface, a slash command, or a user request containing one of these phrases:

- "Write a commit message"
- "Generate a commit"
- "Commit my changes"
- "run/git-smart-commit"
- "run/git-commit"

The skill requires a Git repository, a current branch, and either staged or unstaged changes. It must:

1. Run git branch and confirm that the working branch is correct.
2. Run git status, git diff, and git diff --cached.
3. Stop and ask the user to make changes when no changes are available.
4. Ask before staging unstaged files, using git add . for all files or git add <filename> for selected files.
5. Generate a conventional commit message using feat, fix, refactor, docs, test, or chore.
6. Run git commit -m with the generated message.
7. Never add a Co-Authored-By trailer.

### Example commit message

```text
type(scope): add user profile validation

- validate the submitted profile fields
- prevent invalid data from being saved
```

### Reusing the skill

To use the skill in another repository, copy [skills/git-smart-commit/SKILL.md](skills/git-smart-commit/SKILL.md) into that repository's supported project-skills directory. The receiving AI assistant must support the directory format used by its tooling.

## Tracer Bullet Strategy

Use tracer bullets to create small, testable slices of functionality that provide early feedback. Each bullet should represent a minimal, independently verifiable outcome rather than a large, speculative implementation.

When working on a feature:

1. Identify the smallest valuable outcome.
2. Build the narrowest possible implementation.
3. Validate the result with an appropriate check.
4. Use the feedback to decide the next bullet.
5. Keep each iteration focused and easy to review.

This approach helps reveal assumptions quickly, reduce delivery risk, and make progress visible before committing to a broader implementation.