# The Command Line

This topic matters as it relates to learning some of the more common terminal commands.

---

## Summary

* **The Command Line**

The command line, also known as terminal, is a text based interface to our computer. We type commands and we get feedback in return as text.

* **Basic Navigation**

The command `pwd` stands for Print Working Directory. It tells us where our current working directory is. (e.g)

```
  pwd
  /home/user
```

The command `ls` lists the contents of a directory. (e.g)

```
  ls
  bin Documents public_html
```

The command `cd` changes directories.

* **More About Files**

Under Linux everything is a file, even directories. It is an extension-less system, it ignores the extension and looks inside the file to determine what type of file it is. It is also case sensitive.

The command `file` gets information about what type of file it is.

The command `ls -a` lists the contents of a directory, including hidden files.

* **Manual Pages**

Manual pages are a set of pages that explain every command available on our system including what they do, the specifics of how you run them and what command line arguments they accept.

The command `man <command to look up>`invokes the manual pages. (e.g)

```
  man ls
  Name
      ls - list directory contents
  
  Synopsis
      ls [option] ... [file] ...
  
  Description
      List information about the FILEs (the current directory by default). Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.
  
      Mandatory arguments to long options are mandatory for short options too.
```

To do a keyword search for all manual pages containing the given search term we use the `man -k <search term>` command.

* **File Manipulation**

  * To make / create a directory we use `mkdir`.
  * To remove  a directory we use `rmdir`.
  * To create a blank file we use `touch`.
  * To copy a file or directory we use `cp`.
  * To move a file or directory we use `mv`.
  * To delete a file we use `rm`.

[Cheat Sheet](https://ryanstutorials.net/linuxtutorial/cheatsheet.php)

---

### Things I want to know more about

* I would like to learn more about all of the other not so common terminal commands.

---

[-back](https://alexriverau.github.io/reading-notes/code401)
