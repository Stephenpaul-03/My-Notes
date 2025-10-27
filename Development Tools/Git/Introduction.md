## Definition
**Git** is a **distributed version control system (DVCS)** used to track and manage changes in source code. It helps developers **collaborate**, **experiment safely**, and **recover past versions** of their projects — all without stepping on each other’s toes.

---

## Uses
- Tracks every change made to the codebase.  
- Enables multiple developers to work simultaneously.  
- Supports branching for experimentation and feature development.  
- Allows rollback to any previous state.  
- Fast, lightweight, and completely open source.

---

## Core Terminologies
| Term                     | Meaning                                       | Analogy                                            |
| :----------------------- | :-------------------------------------------- | :------------------------------------------------- |
| **Repository (repo)**    | Stores the project’s full version history.    | A **project folder** with a built-in time machine. |
| **Working Directory**    | Current snapshot of files on your disk.       | Your **workspace desk**.                           |
| **Staging Area (Index)** | Where files wait before being committed.      | A **draft tray** for review.                       |
| **Commit**               | A saved checkpoint of your project.           | **Taking a photo** of your code at that moment.    |
| **Branch**               | A separate line of development.               | A **parallel universe** for trying ideas safely.   |
| **HEAD**                 | Pointer to your current commit.               | A **bookmark** showing where you’re at.            |
| **Remote**               | The repo hosted elsewhere (e.g., GitHub).     | A **shared drive** everyone syncs to.              |
| **Clone**                | A local copy of a remote repo.                | **Photocopying** the project for yourself.         |
| **Fork**                 | A personal remote copy of someone’s repo.     | A **spin-off movie** based on the original.        |
| **Pull**                 | Fetch and merge remote changes.               | **Import teammates’ updates** into your copy.      |
| **Push**                 | Send local commits to the remote repo.        | **Upload your work** to the shared version.        |
| **Fetch**                | Retrieve remote changes without merging.      | **Checking your mail**, not replying yet.          |
| **Merge**                | Combine work from multiple branches.          | **Merging two documents** into one.                |
| **Conflict**             | When Git can’t auto-merge.                    | **Two people edited the same line** differently.   |
| **Reset**                | Move HEAD and optionally discard changes.     | **Rewind time** and possibly delete the draft.     |
| **Rebase**               | Reapply commits onto a new base.              | **Rewriting history** so it looks linear.          |
| **Stash**                | Temporarily save uncommitted work.            | **Putting papers in a drawer** for later.          |
| **Tag**                  | Label a specific commit (often for releases). | A **sticky note** marking version 1.0.             |
| **Cherry-pick**          | Apply a specific commit from another branch.  | **Copy-paste** a change between timelines.         |
| **Bisect**               | Finds the commit that introduced a bug.       | **Binary search** for the problem’s origin.        |

---

## Workflow Basics

1. **Initialize a repo**
   ```shell
   git init
```
2. **Add files to staging**
```shell
git add <file>
```
3. **Commit changes**
```shell
git commit -m "commit message"
```
4. **Check status**
```shell
git status
```
5. **View history**
```shell
git log
```
6. **Create a branch**
```shell
git branch feature-x
```
7. **Switch branches**
```shell
git checkout feature-x
```
8. **Merge branches**
```shell
git checkout main
git merge feature-x
```
9. **Push to remote**
```shell
git push origin main
```
10. **Pull updates**
```shell
git pull origin main
```
