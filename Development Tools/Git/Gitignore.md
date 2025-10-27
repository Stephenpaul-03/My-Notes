## Definition
`.gitignore` is a **special configuration file** in a Git repository that tells Git which **files or directories to ignore** — meaning not to track, not to commit, and not to push.  
It ensures that **unnecessary, sensitive, or machine-specific files** don’t pollute version control.

[https://gitignore.io](https://gitignore.io/) - Generate `.gitignore` files
## Purpose
- Exclude local or system-generated files (e.g., `.DS_Store`, `thumbs.db`)
- Prevent committing secrets (e.g., `.env`, `config.json`)
- Avoid versioning build artifacts (e.g., `dist/`, `target/`)
- Ignore IDE/editor files (e.g., `.vscode/`, `.idea/`)
- Keep the repository clean, portable, and consistent

## Key Concepts

### 1. File Location
- Typically placed in the **root** of the repository  
- Can also be placed in **subdirectories** for more granular control  
- Git processes `.gitignore` **hierarchically** - rules in deeper directories override parent rules

### 2. Wildcard Patterns
Git matches patterns using globs, not regex.

| Pattern          | Meaning                                    |
| :--------------- | :----------------------------------------- |
| `*.log`          | Ignore all `.log` files                    |
| `build/`         | Ignore everything in the `build` directory |
| `*.class`        | Ignore compiled Java class files           |
| `**/temp/`       | Ignore all `temp` directories at any level |
| `!important.txt` | Negation — explicitly include this file    |

### 3. Negation (`!`)
Use `!` to un-ignore a file or directory that would otherwise be ignored.
```plain
*.log
!important.log
````

### 4. Comments

Lines starting with `#` are comments.

```plain
# Ignore logs
*.log
```

### 5. Order Matters

- Git processes `.gitignore` from **top to bottom**
- If a file matches multiple patterns, the **last match wins**
## Limitations

- It only prevents **untracked files** from being added
- It does **not remove** already committed files
- If a file is already in Git, `.gitignore` has no effect until it’s removed:

```shell
git rm --cached <file>
```

## Common Entries

**Node.js**

```plain
node_modules/
.env
dist/
```

**Python**

```plain
__pycache__/
*.pyc
.env
```

**Java**

```plain
*.class
target/
```

**General**

```plain
*.log
.DS_Store
.idea/
.vscode/
```