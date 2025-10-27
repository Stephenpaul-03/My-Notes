## Definition
**Git hooks** are scripts that Git runs automatically when certain events occur in a repository.  
They act like **event listeners** — letting you trigger custom behavior at specific points in your Git workflow
There are two main types:
- **Client-side hooks**: Run locally on your machine (e.g., during commits, merges, or rebases)
- **Server-side hooks**: Run on the Git server (e.g., during pushes)
## Working
1. Navigate to your repo’s `.git/hooks/` folder  
2. You’ll see sample files like `pre-commit.sample` — rename and customize them  
3. Hooks are just **executable scripts** (shell, Python, Node, etc.)

```shell
#!/bin/sh
# Example pre-commit hook
echo "Running pre-commit checks..."
npm run lint || exit 1
chmod +x .git/hooks/pre-commit
````
## Client-Side Hooks

| Hook File     | Trigger Point                       | Common Use                                                 |
| :------------ | :---------------------------------- | :--------------------------------------------------------- |
| `pre-commit`  | Before a commit is finalized        | Linting, formatting code, checking for secrets             |
| `commit-msg`  | After the commit message is written | Enforce commit message format (e.g., Conventional Commits) |
| `pre-push`    | Before a push happens               | Run tests, block broken code                               |
| `pre-rebase`  | Before a rebase starts              | Prevent rebasing protected branches                        |
| `post-commit` | After a commit is done              | Notifications, logging, etc.                               |
| `post-merge`  | After a merge                       | Auto-install dependencies, clean up                        |

## Server-Side Hooks

| Hook File      | Trigger Point                      | Common Use                                         |
| :------------- | :--------------------------------- | :------------------------------------------------- |
| `pre-receive`  | Before refs update on server       | Validate pushed code, reject unauthorized branches |
| `update`       | Similar to pre-receive, per branch | Apply branch-specific checks                       |
| `post-receive` | After a push completes             | Deploy code, trigger CI/CD jobs, notify team       |

## Best Practices

- Don’t hardcode hooks in `.git/hooks/` — Git doesn’t track them. Use a hook manager instead.
- Keep hooks **fast** — slow ones frustrate developers.
- If a hook fails, **explain clearly** what went wrong and how to fix it.

## Tools

| Tool           | Description                                                     |
| :------------- | :-------------------------------------------------------------- |
| **Husky**      | Popular for JS/TS projects; integrates hooks via `package.json` |
| **Lefthook**   | Fast, language-agnostic alternative                             |
| **Pre-commit** | Python tool for managing hooks via `.pre-commit-config.yaml`    |
## Use Cases

- Auto-format code with Prettier or Black
- Reject `TODO` or `console.log` statements before pushing
- Enforce signed commits
- Run security or lint checks pre-push
- Block pushes to protected branches like `main`