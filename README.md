## TEdit - Let you edit the stdout

![python-3.x](https://img.shields.io/badge/python-3.x-green.svg) ![Unix/Windows](https://img.shields.io/badge/platform-unix%2Fwindows-blue.svg)
> *My first useful Python program (possible)*  

It's a Python program which lets you edit a temporary file, print it out or run (open) the file by selected program, and delete it automatically then.


### Edit the stdout? Why?

Well, sometimes if you want...for example I want edit a code block on [Stack Overflow](https://stackoverflow.com/), and I want use **my editor** (vim). So I need:

1. Open vim edit a file.
2. Copy the code into my editor.
3. Edit edit and edit, then save.
4. Use `cat` command (on Unix/Linux )print the file out; run or the file by a program
5. Delete the file.

Yeah, too complex. I really don't want create a file and delete it. Can I just edit the stdout?


### How does "tedit" edit the stdout? Pipes?

Nope, pipes isn't needed. This is TEdit (Temporary Edit), so just:

1. Create a temporary file use [`tempfile`](https://docs.python.org/3/library/tempfile.html).
2. Run the editor, edit that file.
3. Read the file and print the content of it out; run or the file by a program.
4. That file'll be deleted automatically.


### What's the useage of it?

First at all, this is a Python 3 project. You mush install Python 3 before run the program.

Then, run the file like:

    python3 tedit


It'll create a temporary file and open it with the default editor of the system, and print the content of that temporary after you saved it.

> **Note:** If you didn't save the file, it'll do nothing.


tedit also accepts some arguments, for example:

```
  -f FILE, --file FILE  Edit the file as a temporary file
  -s SUFFIX, --suffix SUFFIX
                        Set the temporary file's suffix
  -p PROGRAM, --program PROGRAM
                        Program you want to 'run stdout'
  -e EDITOR, --editor EDITOR
                        Use anoter editor instead of the system default
```

- `-f/--file`: tedit will use `FILE`'s content as the temporary file's content (before your edit).

- `-s/--suffix`: Set the temporary file's suffix.

  Use it when your editor has the *highlight auto-enable by check the file's suffix* feature.  
  `SUFFIX` (no need put `.`in `SUFFIX` yourself, but no matter if you would like to do) will be the suffix of the temporary file.

- `-p/--program`: Use a program run (open) the file instead of print the file out.

  For example, you're editing a HTML source code, and you don't need save it, but want open it with Google Chrome instead, you can simply use tedit like:

  ```
  python3 tedit -s html -p google-chrome-stable
  ```

  Arguments of the program is also allowed, for example, open Google Chrome in incognito mode:

  ```
  python3 tedit -s html -p 'google-chrome-stable --incognito'  # don't forgot the quotes!
  ```

- `-e/--editor`: Set a editor to edit the temporary file.

  If you didn't set this, the editor will be the default editor of the system.

  Arguments also allowed. For example:

  ```
  python3 tedit -e 'vim -u /path/to/vimrc'
  ```
