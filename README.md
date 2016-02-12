## TEdit - Let you edit the stdout

![python-3.x](https://img.shields.io/badge/python-3.x-green.svg) ![Unix/Windows](https://img.shields.io/badge/platform-unix%2Fwindows-blue.svg)
> *My first useful Python program (possible)*  

It's a simple Python program which can let you call your favorite editor, edit a temp file, print it out, and delete it automatically.


### Wait, edit the stdout? Why?

Well, sometimes if you want...for example I want edit a code block on [Stack Overflow](https://stackoverflow.com/), and I want use **my editor** (vim). So I need:

1. Open vim edit a file.
2. Copy the code into my editor.
3. Edit edit and edit, then save.
4. Use `cat` command print the file out.
5. Delete the file.

Yeah, too complex. I really don't need create a file and delete it. Can I just use my vim edit the stdout?


### Is it magic? How is that possible?

Nope, it's simple. Just use:

1. Create a temp file use [`tempfile.NamedTemporaryFile()`](https://docs.python.org/3/library/tempfile.html#tempfile.NamedTemporaryFile).
2. Run the editor, edit that file.
3. Read the file and print the content of it out.
4. That file'll be deleted automatically.


### That's cool, how can I use it?

First at all, this is a Python 3 project. You need install Python 3 and use it run the script.

> Don't ask me how to install Python if you don't know, [ask it here](https://www.google.com/).

Then, run the file like:

    python3 tedit

You can change the suffix by add a shell argument if your editor can check the suffix and change the code highlight like my vim:

    python3 tedit py

This will create a file which's filename like this:

    /tmp/tmps27sm02r.py

Instead of just this:

    /tmp/tmps27sm02r

---------------------------------

You can also open the file with a program rather than print the file out now.

To use this feature, you have to set two shell arguments. For example:

    python3 tedit html google-chrome-stable

After you saved the file, tedit will open the file with Google Chrome, and delete it when done.
