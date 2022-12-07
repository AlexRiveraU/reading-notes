# Automation

This topic matters as it relates to learning about automation.

---

## Python Regular Expressions Tutorial

Regular Expressions (regex) are a sequence of characters used to check whether a pattern exists in a given text (string) or not.

In Python, regular expressions are supported by the `re` module. (e.g.)

```python
import re

pattern = r"Cookie"
sequence = "Cookie"
if re.match(pattern, sequence):
    print("Match!")
else: print("Not a match!")
```

#### Grouping in Regular Expressions

The group feature of regular expression allows you to pick up parts of the matching text. Parts of a regular expression pattern bounded by parenthesis () are called groups. The parenthesis does not change what the expression matches, but rather forms groups within the matched sequence. You have been using the group() function all along in this tutorial's examples. The plain match.group() without any argument is still the whole matched text as usual. (e.g.)

```python
statement = 'Please contact us at: support@datacamp.com'
match = re.search(r'([\w\.-]+)@([\w\.-]+)', statement)
if statement:
  print("Email address:", match.group()) # The whole matched text
  print("Username:", match.group(1)) # The username (group 1)
  print("Host:", match.group(2)) # The host (group 2)
```

#### Summary Table

Character(s)	What it does
* `.`	A period. Matches any single character except the newline character.
* `^`	A caret. Matches a pattern at the start of the string.
* `\A`	Uppercase A. Matches only at the start of the string.
* `$`   Dollar sign. Matches the end of the string.
* `\Z`	Uppercase Z. Matches only at the end of the string.
* `[ ]`	Matches the set of characters you specify within it.
* `\`	If the character following the backslash is a recognized escape character, then the special meaning of the term is taken. Else the backslash () is treated like any other character and passed through. It can be used in front of all the metacharacters to remove their special meaning.
* `\w`	Lowercase w. Matches any single letter, digit, or underscore.
* `\W`	Uppercase W. Matches any character not part of \w (lowercase w).
* `\s`	Lowercase s. Matches a single whitespace character like: space, newline, tab, return.
* `\S`	Uppercase S. Matches any character not part of \s (lowercase s).
* `\d`	Lowercase d. Matches decimal digit 0-9.
* `\D`	Uppercase D. Matches any character that is not a decimal digit.
* `\t`	Lowercase t. Matches tab.
* `\n`	Lowercase n. Matches newline.
* `\r`	Lowercase r. Matches return.
* `\b`	Lowercase b. Matches only the beginning or end of the word.
* `+`   Checks if the preceding character appears one or more times.
* `*`   Checks if the preceding character appears zero or more times.
* `?`   Checks if the preceding character appears exactly zero or one time. Specifies a non-greedy version of +, *
* `{ }`	Checks for an explicit number of times.
* `( )`	Creates a group when performing matches.
* `< >`	Creates a named group when performing matches.

[*source*](https://www.datacamp.com/tutorial/python-regular-expression-tutorial)

---

## Shutil

The shutil module includes high-level file operations such as copying and archiving.

* `copyfile()` copies the contents of the source to the destination and raises IOError if it does not have permission to write to the destination file.
* `copytree()` accepts two callable arguments to control its behavior. The ignore argument is called with the name of each directory or subdirectory being copied along with a list of the contents of the directory. It should return a list of items that should be copied. The copy_function argument is called to actually copy the file.
* `The which()` function scans a search path looking for a named file. The typical use case is to find an executable program on the shell’s search path defined in the environment variable PATH.
* `make_archive()` creates a new archive file.

[*source*](https://pymotw.com/3/shutil/)

---

### Things I want to know more about

* I would like to know more about how to implement regex and the shutil module in python. 

---

[-back](https://alexriverau.github.io/reading-notes/code401)
