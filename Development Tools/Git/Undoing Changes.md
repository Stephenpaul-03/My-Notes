### Definition
Undoing changes in Git depends on *what stage* your changes are in—working directory, staging area, committed, or pushed—and *what you’re trying to do*: rollback, reset, discard, or amend. Git gives you different tools for each of these situations.

---

## Change States
| State                    | Description                           |
| :----------------------- | :------------------------------------ |
| **Working Directory**    | Local, uncommitted file edits         |
| **Staging Area (Index)** | Files marked for the next commit      |
| **Repository (Commits)** | Snapshots saved in commit history     |
| **Remote**               | Commits pushed to a shared repository |

---

## Undoing Uncommitted Changes

### 1. Undo changes in working directory
Revert changes in modified but unstaged files:
```shell
git restore <file>
````

Effect: Discards file edits since the last commit.

---

### 2. Undo changes in staging area

Unstage a file but keep its content:

```shell
git restore --staged <file>
```

Effect: Removes from staging but keeps the local modifications.

---

### 3. Discard all unstaged changes

```shell
git restore .
```

Effect: Resets all modified files to match the last commit.

---

## Undoing Commits (Local Only)

### 4. Amend the last commit

Fix the last commit (message, added files, etc.):

```shell
git commit --amend
```

Effect: Rewrites the previous commit.

---

### 5. Reset to a previous commit

Different reset modes for different levels of destruction:

- **Soft reset**: Keeps staged changes
    
```shell
git reset --soft <commit>
```
    
- **Mixed reset** _(default)_: Keeps changes in working directory
    
```shell
git reset <commit>
```
    
- **Hard reset**: Discards everything after that commit
    
```shell
git reset --hard <commit>
```
    

Tip: Use `git log` or `git reflog` to find the commit hash.

---

## Undoing Pushed Commits

### 6. Revert a commit

Safely undo a pushed commit by creating a new “undo” commit:

```shell
git revert <commit>
```

Effect: Keeps history clean and auditable. Use this for shared branches.

---

### 7. Force push after local reset _(use with caution)_

```shell
git reset --hard <commit>
git push --force
```

Effect: Overwrites remote history. Only do this if you’re working on a private branch or have team approval.

---

## Advanced: Recover Lost Commits

### 8. Recover commits using `reflog`

```shell
git reflog
git checkout <reflog-hash>
```

Effect: Restores lost commits or branches that were reset or deleted.  
Reflog tracks every movement of `HEAD`, even those not visible in `git log`.
