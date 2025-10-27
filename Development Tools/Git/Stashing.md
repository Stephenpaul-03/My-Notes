### Definition
`git stash` temporarily saves local modifications (both staged and unstaged) in a **stack-like structure**, giving you a clean working directory without losing your work. It’s clutch when you need to switch branches or pull changes without committing your current progress.

---

### Working
- Saves the current state of tracked files.
- Resets the working directory and index to match `HEAD`.
- Pushes the saved snapshot onto the stash stack.

---

### Scope of Stash
| Element | Stashed by Default | Option to Include |
|:----------|:------------------|:------------------|
| Staged (index) changes | Yes | – |
| Modified tracked files | Yes | – |
| Untracked files | No | `git stash -u` / `--include-untracked` |
| Ignored files | No | `git stash -a` / `--all` |

---

### Common Commands
| Command | Description |
|:-----------|:-------------|
| `git stash` | Stash tracked changes |
| `git stash -u` | Include untracked files |
| `git stash -a` | Include ignored files |
| `git stash list` | Show all stash entries |
| `git stash show` | Show summary of latest stash |
| `git stash show -p` | Show diff of stashed changes |
| `git stash apply` | Apply a stash without deleting it |
| `git stash pop` | Apply and remove the latest stash |
| `git stash drop stash@{n}` | Delete a specific stash |
| `git stash clear` | Delete all stashes |

---

### Typical Workflow Example
```shell
git stash push -m "WIP: refactor auth"
git switch new-feature
# Work on another branch
git switch main
git stash pop
````

---

### Stash Internals

Each stash is a **hidden Git commit** stored under `.git/refs/stash`.  
It contains:

- The `HEAD` commit (base)
- The index (staged state)
- The working directory (unstaged state)

Each stash entry looks like:

```plain
stash@{0}: WIP on main: <commit-id> <commit-message>
```

---

### Caveats

- Conflicts can occur during `stash pop` if files have changed since the stash was created.
- Untracked/ignored files aren’t included unless specified.
- Stashes are **global** to the repo, not tied to specific branches.

---

### Best Practices

|Practice|Rationale|
|:--|:--|
|Use descriptive messages (`-m`)|Helps identify stashes later|
|Prefer `apply` over `pop` for testing|Keeps your stash safe|
|Avoid long-term stash storage|Use commits for proper backups|
|Use `git stash branch`|Creates a new branch and applies stash instantly|
