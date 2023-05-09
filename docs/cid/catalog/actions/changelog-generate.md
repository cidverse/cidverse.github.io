# changelog-generate

Generates a changelog based on the commit history.

The default regex expression supports parsing semantic commit messages.
The following types are supported: `build`, `ci`, `docs`, `feat`, `fix`, `perf`, `refactor`, `style`, `test`, `chore`.


## Rules

One or multiple of the following rules must be satisfied for the action to be executed.

- `NCI_COMMIT_REF_TYPE == "tag"`

## Configuration


No configuration is required.
