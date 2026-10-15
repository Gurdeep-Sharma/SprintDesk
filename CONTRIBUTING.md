# Contributing to SprintDesk

Thanks for contributing. SprintDesk is a learning and portfolio project focused on maintainable full-stack engineering.

## Before opening a pull request

1. Check existing code and documentation before introducing a new pattern.
2. Keep the change focused.
3. Add or update tests for changed behavior.
4. Update documentation when commands, environment variables, routes, data models, or architecture change.
5. Never commit credentials, tokens, production data, or private environment files.
6. Describe important trade-offs and limitations honestly.

## Suggested workflow

1. Create a branch for the change.
2. Implement the smallest coherent increment.
3. Run the repository's documented lint, type-check, and test commands.
4. Review the diff for secrets, generated files, unrelated edits, and misleading comments.
5. Open a pull request with a clear summary and test results.

Use the actual package manager and scripts defined in the repository. Do not assume commands that are not present in `package.json`.

## Code quality

- Prefer clear names and small, cohesive functions.
- Avoid `any` unless there is a documented reason.
- Validate external input at runtime.
- Keep authorization checks on the server.
- Handle expected errors explicitly.
- Avoid unnecessary abstractions and premature optimization.
- Add comments to explain non-obvious decisions, not to restate each line.

## Pull request template

### What changed?
Describe the user-visible or architectural change.

### Why?
Explain the problem being solved.

### How was it tested?
List commands and meaningful manual checks that were actually run.

### Risks and trade-offs
Describe relevant failure cases, limitations, migration concerns, or follow-up work.

### Documentation
List documentation updated, or explain why none was needed.
