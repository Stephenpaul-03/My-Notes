## Definition
`git blame` is a powerful Git command used to **track who last modified each line of a file**, when, and why. It helps **attribute ownership** to specific changes, making it a key tool for debugging, auditing, and understanding code history.
## Working
It annotates each line of a file with:
- The **commit hash** responsible for the latest change to that line
- The **author** of the change
- The **timestamp** of the commit
- The **line number**

## Example
```shell
git blame <file>
$ git blame main.py
````

```plain
a1b2c3d4 (Alice   2024-12-10 10:01:23 +0000  1) def calculate_tax(amount):
e5f6g7h8 (Bob     2024-12-11 09:15:44 +0000  2)     return amount * 0.15
```

With specific options:

```shell
git blame -L <start>,<end> <file>        # Blame only lines in a given range
git blame <file> -w                      # Ignore whitespace changes
git blame <file> -C                      # Track lines across file copies
git blame <file> -M                      # Detect moved lines within a file
```

## Common Options

| Option        | Description                               |
| :------------ | :---------------------------------------- |
| `-L <n>,<m>`  | Limit output to lines `<n>` through `<m>` |
| `-w`          | Ignore whitespace when comparing          |
| `-e`          | Show author email instead of name         |
| `-M`          | Detect moved lines within the same file   |
| `-C`          | Detect copied lines from other files      |
| `--show-name` | Display the file name in blame output     |
## Limitations

- It **does not show the full commit diff** (use `git show <commit>` for that).
- It may **fail to track history correctly** if files were copied or renamed without the right flags (`C`, `M`).
- It **blames the last person who touched a line**, not necessarily who wrote it originally.