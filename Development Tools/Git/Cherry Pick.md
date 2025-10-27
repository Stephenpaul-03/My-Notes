## Definition
`git cherry-pick` is a Git command used to **apply a specific commit (or series of commits) from one branch onto another**, without merging the full branch. It is a precision tool for **selective integration** of changes.
## Use Case
You're working on `main`, and a bug fix exists on `feature-x` that’s needed in production immediately. You don’t want all of `feature-x`, just one commit. Use `cherry-pick` to port that commit.
## Basic Syntax
```shell
git cherry-pick <commit-hash>
git cherry-pick <hash1> <hash2>
git cherry-pick <start-commit>^..<end-commit>
````

Applies the changes introduced by the given commit to your current branch as a **new commit** (with a new hash).

| Flag                 | Purpose                                                   |
| :------------------- | :-------------------------------------------------------- |
| `-n` / `--no-commit` | Apply changes but don’t commit them (stages them instead) |
| `-x`                 | Append "cherry picked from commit" to the commit message  |
| `--continue`         | Continue cherry-pick after resolving conflicts            |
| `--abort`            | Cancel cherry-pick and revert to pre-state                |
## Workflow Example

```shell
# Assume you're on main branch
git checkout main
# Cherry-pick a commit from another branch
git cherry-pick a1b2c3d
```

Result:
- Git applies the patch from `a1b2c3d` to `main`.
- A new commit is created in `main` with the same changes but a different commit hash.
## Caveats

| Risk                     | Detail                                                                                                    |
| :----------------------- | :-------------------------------------------------------------------------------------------------------- |
| **Commit duplication**   | Cherry-pick creates a new commit; rebasing or merging may later cause duplication if not handled properly |
| **Non-linear history**   | Overusing cherry-pick can create tangled commit trees                                                     |
| **Conflicts are common** | Especially if cherry-picking across long-diverged branches                                                |
### Best Practices

| Practice                                           | Benefit                                      |
| :------------------------------------------------- | :------------------------------------------- |
| Use `-x` for traceability                          | Helps others know where the commit came from |
| Avoid cherry-picking large, context-heavy commits  | They're likely to break in isolation         |
| Prefer cherry-picking into release/hotfix branches | Strategic and controlled use                 |
