### Definition
`git bisect` is a powerful debugging tool that automates the process of **finding the commit that introduced a bug** using **binary search** over the project's history.  
Instead of manually checking every commit, it narrows down the faulty commit in **log₂(n)** steps.

---
### Need
When you know:
- A commit in the past **was working** (`good`)
- The current state of the code **is broken** (`bad`)

---
### Basic Workflow
```shell
git bisect start
git bisect bad            # Mark current commit as bad
git bisect good <commit>  # Mark a known good commit

# For each midpoint commit:
git bisect good           # If the midpoint works
# OR
git bisect bad            # If the midpoint is broken

# Repeat until found
git bisect reset          # Return to your original HEAD
````

---
### Commands

| Command            | Description                              |
| :----------------- | :--------------------------------------- |
| `git bisect log`   | Show the log of all good/bad markings    |
| `git bisect reset` | Abort bisect and return to original HEAD |
| `git bisect skip`  | Skip a commit (e.g., it doesn’t compile) |

---
## Internal Working

`git bisect` performs a **binary search over the commit history DAG** to pinpoint the first "bad" commit that introduced a bug, using developer (or script) feedback at each step.

---
### Conceptual Model

The process assumes:

- One **known good** commit (bug-free)
- One **known bad** commit (bug present)
- A bug was introduced somewhere **between** the two

It then searches that range to find the **first commit** that transitioned from good → bad.

### Step-by-Step Internal Breakdown

#### 1. Start State

```shell
git bisect start
git bisect bad HEAD
git bisect good <commit>
```

- Git stores these two points.
- It generates a **topological commit range** from `good..bad`.

#### 2. Build Candidate Set

- Git traverses the DAG (Directed Acyclic Graph) of commits from the `good` commit to the `bad` commit.
- It creates a **search space** of candidate commits that could contain the bug.

#### 3. Select Midpoint

- Git picks the **"best" candidate** to test next — the commit that **divides the remaining search space most evenly**.
- In simple terms: Git does a **binary search**, reducing steps to `O(log₂ n)`.

#### 4. Checkout and Test

Git checks out the midpoint commit, and you (or your script) test that version:

```shell
git bisect good   # If the bug is not present
git bisect bad    # If the bug is still there
git bisect skip   # If the commit is broken or untestable
```

#### 5. Iterate

- Git uses your feedback to update the range:
    - If `good`, search proceeds **after** that commit.
    - If `bad`, search continues **before** that commit.
- This continues until **only one commit** is left — the **first bad commit**.

#### 6. End and Cleanup

Once identified, Git shows the offending commit:

```plain
<commit-hash> is the first bad commit
```

Then restore your working directory:

```shell
git bisect reset
```

---

Combine `git bisect run <script>` to automate the process with test scripts; it can find the bug-causing commit without manual input.