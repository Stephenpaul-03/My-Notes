## Common Rules
- Short, imperative, and lowercase.
- Avoid vague descriptions like "update code" or "changes made".
- Keep types consistent across team/projects.

## Format
```
<type>[optional scope][!]: <short description>  
[optional body]  
[optional footer(s)]
```

## Types of Commits
| Type       | Purpose                                           |
| :--------- | :------------------------------------------------ |
| `feat`     | Introduces a new feature (**MINOR** version bump) |
| `fix`      | Fixes a bug (**PATCH** version bump)              |
| `docs`     | Documentation only changes                        |
| `style`    | Formatting, missing semi-colons, etc.             |
| `refactor` | Code changes without affecting behavior           |
| `perf`     | Performance improvements                          |
| `test`     | Adding or updating tests                          |
| `chore`    | Maintenance tasks (e.g., build configs, tooling)  |
| `ci`       | Changes to CI/CD pipelines                        |
| `build`    | Changes that affect the build system              |

## Scopes
**Scope** is an optional identifier placed in parentheses after the commit `type` to clarify the area of the codebase the change affects.
- Format: `<type>(<scope>): <description>`
- Example: `feat(auth): implement login with JWT`

## Breaking Changes
**Breaking changes** are modifications that:
- Break backward compatibility
- Require users to modify their usage of the code (API, behavior, config, etc.)
- Usually justify a **MAJOR** version bump

**Method 1:** Add `!` after type/scope  
```plain
feat(api)!: require auth token for every request
````

**Method 2:** Add `BREAKING CHANGE:` in footer

```plain
feat: drop support for legacy API

BREAKING CHANGE: endpoints /v1/* are no longer available
```