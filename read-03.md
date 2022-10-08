# FileIO & Exceptions

This topic matters as it relates to learning proper file manipulation and exceptions in python.

---

## Read & Write Files in Python

### What Is a File?

A file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable.

> Main parts

* **Header:** Metadata about the contents of the file.
* **Data:** Contents of the file as written by the creator or editor
* **End of file (EOF):** Special character that indicates the end of the file

**File Paths**

File path is a string that represents the location of a file.

>Main parts

* **Folder Path:** The file folder location on the file system where subsequent folders are separated by a forward slash / (Unix) or backslash \ (Windows)
* **File Name:** The actual name of the file
* **Extension:** The end of the file path pre-pended with a period (.) used to indicate the file type

### Opening and Closing a File in Python

* **Open a file**

We do this by invoking the `open()` built-in function. `open()` has a single required argument that is the path to the file. `open()` has a single return. (e.g.)

```python
file = open('dog_breeds.txt')
```
* **Close a file**

One way to close a file is by using a `try-finally` block (e.g.)

```python
reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()
```

Another way to close a file is by using a `with statement` (e.g.)

```python
with open('dog_breeds.txt') as reader:
    # Further file processing goes here
```

>Common mode options:

* `r`	Open for reading (default)
* `w`	Open for writing, truncating (overwriting) the file first
* `rb` or `wb`	Open in binary mode (read/write using byte data)


### Reading and Writing Opened Files

* Read

We use the following methods:

* `.read(size=-1)`	This reads from the file based on the number of size bytes. If no argument is passed or None or -1 is passed, then the entire file is read.
* `.readline(size=-1)`	This reads at most size number of characters from the line. This continues to the end of the line and then wraps back around. If no argument is passed or None or -1 is passed, then the entire line (or rest of the line) is read.
* `.readlines()` This reads the remaining lines from the file object and returns them as a list.

* Write

We use the following methods:

* `.write(string)`	This writes the string to the file.
* `.writelines(seq)` This writes the sequence to the file. No line endings are appended to each sequence item. It’s up to you to add the appropriate line ending(s).

[*source*](https://realpython.com/read-write-files-python/)

---

### Things I want to know more about

* I would like to know more about other options for modes to work with files.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
