# Git Smart Commit

Review the current changes and create a conventional Git commit after confirming the branch and staging choices. The complete assistant workflow is in [SKILL.md](SKILL.md).

## Invocation

Ask an AI assistant to write a commit message or commit the changes, or use one of these trigger phrases:

- "Write a commit message"
- "Generate a commit"
- "Commit my changes"
- "run/git-smart-commit"
- "run/git-commit"

## Workflow

The assistant confirms the active branch, reviews the working tree and diffs, and stops if no changes are available. It asks before staging any unstaged files, then generates a conventional commit message using `feat`, `fix`, `refactor`, `docs`, `test`, or `chore`, and commits the staged changes. It must not add a `Co-Authored-By` trailer.

To reuse this skill in another repository, copy `SKILL.md` into that repository's supported project-skills directory. The receiving AI assistant must support that directory format.

## Example commit message

```text
type(scope): add user profile validation

- validate the submitted profile fields
- prevent invalid data from being saved
```
