# dev-toolkit

A small collection of reusable development workflows and project-scoped skills for AI coding assistants.

## Skills

- [Git Create Local Branch](skills/git-create-local-branch/README.md): Create a local branch from a selected source branch while checking remote refs and preserving working changes.
- [Git Smart Commit](skills/git-smart-commit/README.md): Review changes and create a conventional commit after confirming the branch and staging choices.

## Tracer Bullet Strategy

Use tracer bullets to create small, testable slices of functionality that provide early feedback. Each bullet should represent a minimal, independently verifiable outcome rather than a large, speculative implementation.

When working on a feature:

1. Identify the smallest valuable outcome.
2. Build the narrowest possible implementation.
3. Validate the result with an appropriate check.
4. Use the feedback to decide the next bullet.
5. Keep each iteration focused and easy to review.

This approach helps reveal assumptions quickly, reduce delivery risk, and make progress visible before committing to a broader implementation.