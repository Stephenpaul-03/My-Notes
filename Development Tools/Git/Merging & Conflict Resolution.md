## Definition
**Merging** in Git is the process of combining the **changes from one branch into another** to produce a unified project history. It’s how multiple lines of development come back together.

## Merge Types
| Type              | Description                                                                                               |
| :---------------- | :-------------------------------------------------------------------------------------------------------- |
| **Fast-forward**  | Moves the branch pointer forward since no divergence occurred — no new merge commit is created.           |
| **3-way merge**   | Uses the common ancestor, `HEAD`, and the merging branch to combine changes. Creates a merge commit.      |
| **Octopus merge** | Combines more than two branches at once (useful for release integration), but not suitable for conflicts. |

## Commands
```shell
git checkout main
git merge feature-branch
````

## Merge Conflicts

A **merge conflict** happens when Git can’t automatically combine changes between branches — typically because both branches modified the same part of a file or one modified a file that the other deleted.

## Conflict Example

```diff
<<<<<<< HEAD
Current branch changes
=======
Incoming branch changes
>>>>>>> feature-branch
```

## Conflict Resolution Workflow

1. **Run the merge**

```shell
git merge feature-branch
```
    
    If conflicts exist, Git pauses and flags the conflicting files.
    
2. **Identify conflicts**
    
```shell
git status
```
    
    Shows which files need resolution.
    
3. **Resolve conflicts manually**  
    Edit the files, remove conflict markers, and finalize the correct version.
    
4. **Mark conflicts as resolved**
    
```shell
git add <conflicted-file>
```
    
5. **Complete the merge**
    
```shell
git commit
```
    
    Creates a merge commit (for 3-way merges).
    

## Tools

| Tool                      | Description                        |
| :------------------------ | :--------------------------------- |
| **Built-in text editors** | Manually handle conflict markers.  |
| **Git mergetool**         | Launches a visual diff/merge tool. |
| **VS Code / IntelliJ**    | Offer inline merge conflict views. |

Example:

```shell
git mergetool
```

## Best Practices

| Practice                          | Purpose                                            |
| :-------------------------------- | :------------------------------------------------- |
| **Small, frequent merges**        | Reduces the likelihood and size of conflicts.      |
| **Rebase before merging**         | Keeps commit history cleaner and easier to follow. |
| **Review changes manually**       | Avoid accidental overwrites or lost code.          |
| **Document conflict-prone areas** | Helps the team stay aware of recurring issues.     |
