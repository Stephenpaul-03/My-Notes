## Definition
**Tracking** in Git defines the link between a **local branch** and a **remote branch**. When a local branch is **tracking** a remote one, Git knows where to **pull**, **push**, and **compare** changes automatically - no need to keep typing remote names every time.

## Tracking Branch
A **tracking branch** is simply a local branch connected to a remote counterpart.  
This connection allows Git to:
- Automatically fetch updates from the correct remote.
- Push local commits to the right branch.
- Show how far your branch is ahead or behind using `git status`.

## Working

When you create a local branch from a remote one:
```shell
git checkout -b feature/login origin/feature/login
````

Git automatically sets up `feature/login` to track `origin/feature/login`.

You can also set it up manually:

```shell
git branch --track feature/login origin/feature/login
```

This relationship is stored in the config:

```plain
[branch "feature/login"]
    remote = origin
    merge = refs/heads/feature/login
```


## Key Operations

| Command      | Behavior when tracking is set                      |
| :----------- | :------------------------------------------------- |
| `git pull`   | Merges or rebases changes from the upstream branch |
| `git push`   | Pushes commits to the tracked remote branch        |
| `git status` | Shows ahead/behind status vs. the remote branch    |
| `git merge`  | Can merge with the upstream branch using `@{u}`    |

## Common Tracking Concepts

### Inspecting Tracking Info

```shell
git branch -vv
```

Displays:

- Local branches
- Their upstream branches
- Latest commit info

Example output:

```plain
* main         3f5c123 [origin/main] fix: correct typo in README
  feature/api  8a9b456 [origin/feature/api] feat: add endpoint routing
```


### Changing or Setting a Tracking Branch

To link an existing branch to a remote:

```shell
git branch --set-upstream-to=origin/dev dev
```

To remove tracking:

```shell
git branch --unset-upstream
```
