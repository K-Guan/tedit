## TEdit - Temporary file Editor

![python-3.x](https://img.shields.io/badge/python-3.x-green.svg) ![Unix/Windows](https://img.shields.io/badge/platform-unix%2Fwindows-blue.svg)

TEdit is a Python program, you can use it to edit a temporary file, print it out or run (open) the file by the selected program, etc.


### Basic usage

First at all, this is a Python 3 project. You must install Python 3 before run the program.

Then, just run it like:

    python3 tedit

It'll creates a temporary file and opens it use the default editor of the system, and print the content of that temporary file after you saved it.

> **Note:** If you didn't save the file, it'll do nothing.

### Arguments

TEdit also accepts some arguments:

```
  -f FILE, --file FILE  
                        Edit the file as a temporary file
  -s SUFFIX, --suffix SUFFIX
                        Set the temporary file's suffix
  -p PROGRAM, --program PROGRAM
                        Program you want to 'run stdout'
  -e EDITOR, --editor EDITOR
                        Use anoter editor instead of the system default
```

- `-f/--file`: TEdit will uses `FILE`'s content as the temporary file's default content.

  Use it when you're going to edit a file, but you don't want *change* it.

- `-s/--suffix`: Set suffix of the temporary file.

  Use it when your editor has the *auto style highlight by the file's suffix* feature.  
  `SUFFIX` (you don't need put a dot `.` before the `SUFFIX` yourself) will be the suffix of the temporary file.

- `-p/--program`: Use the selected program to run (open) the file instead of print it out.

  For example, you're editing a HTML source code, and you don't want save it, but want open it with Google Chrome instead, you can simply run tedit like:

  ```
  python3 tedit -s html -p google-chrome-stable
  ```

  Arguments of the program are also allowed, for example, open Google Chrome in incognito mode:

  ```
  python3 tedit -s html -p 'google-chrome-stable --incognito'  # don't forget the quotes!
  ```

- `-e/--editor`: Set an editor to edit the temporary file.

  If you didn't set this, the editor will be the default editor of the system.

  Arguments of the editor are also allowed. For example:

  ```
  python3 tedit -e 'vim -u /path/to/vimrc'
  ```
