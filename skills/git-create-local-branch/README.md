# Git Create Local Branch

Create a local branch from a source branch while checking remote refs and preserving any working changes. The complete assistant workflow is in [SKILL.md](SKILL.md).

## Invocation

Ask an AI assistant to create a branch, or use one of these trigger phrases:

- "Create a new Branch"
- "run/git-local-branch"
- "run/create-local-branch"
- "run/local-branch"
- "run/create-branch"

Provide the source branch and the desired target branch name. Use a lowercase, focused name with a prefix such as `feature/`, `fix/`, `hotfix/`, `docs/`, or `chore/`.

## Workflow

The assistant checks the working tree and stashes existing changes when necessary, fetches `origin`, verifies that the source branch exists remotely and the target is not already on `origin`, then creates the local branch and verifies the result. If changes were stashed, it reapplies them after creating the branch.

To reuse this skill in another repository, copy `SKILL.md` into that repository's supported project-skills directory. The receiving AI assistant must support that directory format.
