### Definition
`git rebase` is a **powerful Git command** that **reapplies commits on top of another base**, creating a **linear and cleaner project history**. It’s heavily used in **trunk-based** or **GitFlow** workflows to maintain a tidy commit log.

---

### Working
Rebasing essentially **moves a branch’s commits** to start from a new base commit. This means:
- Integrating changes from another branch.
- Cleaning up commit history before merging.
- Avoiding unnecessary merge commits that clutter logs.

---

### Basic Syntax
```shell
git rebase <base-branch>
````

Tells Git:  
“Take my current branch and replay its commits on top of `<base-branch>`.”

---

### Example Workflow

You’re working on a feature branch `feature/login` based on `main`:

```shell
# Switch to feature branch
git checkout feature/login
# Rebase onto latest main
git rebase main
```

This reapplies your `feature/login` commits as if they were created after the latest commit in `main`.

---

### Reasons

| Benefit                  | Impact                                                                |
| :----------------------- | :-------------------------------------------------------------------- |
| **Cleaner History**      | Linear and easy-to-follow commit log.                                 |
| **Conflict Management**  | Handle conflicts once during rebase instead of multiple merge points. |
| **Better Collaboration** | Prevents diverging commit histories between teammates.                |

---

### Risks

| Concern                      | Explanation                                                                     |
| :--------------------------- | :------------------------------------------------------------------------------ |
| **Rewriting Public History** | Never rebase commits already pushed to shared branches unless your team agrees. |
| **Complex Conflicts**        | May need to resolve conflicts for each commit during rebase.                    |
| **Loss of Context**          | Hides the true chronological order of how commits were originally made.         |

---

### Best Practices

- Rebase **locally** and **before merging** to main/trunk.
- Use **interactive rebase** to curate and clean your commits.
- Communicate with your team before rebasing shared branches.
- Prefer pulling with rebase to avoid merge bubbles:
```shell
git pull --rebase
```

---

## Interactive Rebase

Interactive rebase (`-i`) lets you **manually rewrite or reorder commits** to make your history cleaner and more meaningful before merging.

---

### Basic Command

```shell
git rebase -i HEAD~N
```

- `HEAD~N` = last N commits in your branch.
- Opens a text editor showing your recent commits.

---

### Interactive Rebase Editor Example

```plain
pick 123abc1 Fix login UI
pick 456def2 Add login test
pick 789ghi3 Fix typo in login message
```

| Command  | Purpose                                                            |
| :------- | :----------------------------------------------------------------- |
| `pick`   | Use the commit as-is.                                              |
| `reword` | Edit the commit message.                                           |
| `edit`   | Pause rebase to modify the commit content.                         |
| `squash` | Combine this commit with the previous one and edit message.        |
| `fixup`  | Combine this commit with the previous one but discard its message. |
| `drop`   | Remove the commit entirely.                                        |

---

### Execution Flow

1. Run:
```shell
git rebase -i HEAD~3
```
2. Adjust commit actions in the editor.
3. If you reword or squash, Git opens a message editor.
4. If you used `edit`, make changes:
```shell
git add .
git commit --amend
git rebase --continue
```
5. If conflicts appear:
```shell
git status
# Resolve conflicts
git add <resolved-files>
git rebase --continue
```

---

### Caution

- Avoid rebasing **publicly shared commits** unless force-push is allowed.
- Verify rewritten history with:
```shell
git log --oneline
```
- Don’t rebase during active PR reviews - commit hashes will change.
