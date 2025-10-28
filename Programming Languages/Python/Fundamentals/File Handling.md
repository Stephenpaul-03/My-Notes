## **Introduction**

- File handling in Python refers to the process of creating, opening, reading, writing, appending, and closing files.
- Python provides a simple and powerful set of built-in functions to work with files in text or binary mode.

## **Opening Files**

- Use the built-in `open()` function to access a file.
- Syntax: `open(filename, mode)`
- Modes include:
    - `"r"`: Read (default; file must exist)
    - `"w"`: Write (creates file or truncates existing)
    - `"a"`: Append (adds to the end of file)
    - `"x"`: Create (creates file, error if exists)
    - `"b"`: Binary mode (for non-text files)
    - `"t"`: Text mode (default)
- Modes can be combined like `"rb"` (read binary).

## **Reading Files**

- Use `read()`, `readline()`, or `readlines()` on an opened file object.
- Example:
    
    ```python
    # Reads the entire file
    with open("file.txt", "r") as f:
        content = f.read()
        print(content)
        
    # Reading Line by Line
    with open("file.txt", "r") as f:
        for line in f:
            print(line.strip())
    ```
    

## **Writing to Files**

- Open in `"w"` or `"a"` mode.
- Use `write()` or `writelines()`.

Example:

```python
with open("file.txt", "w") as f:
    f.write("Hello, world!\n")

with open("file.txt", "a") as f:
    f.write("Appending new line.\n")
```

## **Closing Files**

- It's important to close files to free resources.
- Use `close()` method if not using `with` statement.
- The recommended way is `with` statement which automatically handles closing.

## **File Object Methods**

| Method | Description |
| --- | --- |
| `close()` | Closes the file |
| `flush()` | Flushes internal buffer to disk |
| `read(size)` | Reads specified number of bytes |
| `readline()` | Reads a single line |
| `readlines()` | Reads all lines as a list |
| `seek(offset, whence)` | Moves the file pointer |
| `tell()` | Returns current file pointer position |
| `truncate(size)` | Resizes the file |
| `writable()` | Returns True if file supports writing |
| `readable()` | Returns True if file supports reading |

## **Handling Exceptions**

- Use `try-except` to handle file errors like `FileNotFoundError`.

```python
try:
    with open("nofile.txt", "r") as f:
        content = f.read()
except FileNotFoundError:
    print("File not found.")
```

## **Example**

```python
*# Writing to a file*
with open("sample.txt", "w") as f:
 write("Hello, File Handling!\n")

*# Reading from a file*
with open("sample.txt", "r") as f:
    print(f.read())

*# Appending to a file*
with open("sample.txt", "a") as f:
    f.write("Appended text.\n")
```