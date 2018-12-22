## CodeBlog - 2

### 0x03 Python Programming

`C` code is compiled by a compiler in order to be converted to machine code. The `Python interpreter` is written in C and it interprets Python code line by line to convert it into machine code.  

The file type for compiled `C file` is:
```bash
file compiled.out

compiled.out : ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 2.6.32, BuildID[sha1]=307f29afdda0943cece323d05294b6cccb2cdec7, not stripped
```

Similarly, we find for `python executable`:

```bash
file /usr/bin/python3.5

/usr/bin/python3.5: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 2.6.32, BuildID[sha1]=dd6fd4f087561148594326363d9e5c8ca3025c4e, stripped
```

* `vim` : open two files side-by-side:

```vim
vim -O matrix.py matrix.c
```

* switch between windows: Press `Ctrl + W`
* execute command in terminal without minimizing `vim`:

```bash
# In command window, type:
:<command here>

# e.g.
: python main.py
```
* execute command in terminal by minimizing `vim`:

```bash
# In command window, type:
:!<command here>

# e.g.
:!python main.py

Press ENTER to return back to vim
```

* Enter INSERT mode by creating a newline below the cursor
```
Enter o in command mode
```

* Enter INSERT mode by creating a newline above the cursor
```
Enter shift + o in command mode
```

* Executing python scripts requires us to write command in the following form:

```bash
python <file.py> <arguments, if any>
```

In order to execute the file without the preceding `"python"`, we need to add the line `#!/usr/bin/python3` to the beginning of the script, this line is known as `shebang`. Read more about it [here](https://en.wikipedia.org/wiki/Shebang_(Unix)). 

Now, try running it as:

```bash
./<file.py> <args>

# We get the error:

bash: ./matrix.py: Permission denied
```

This is because we don't have the required permissions to execute the script.

* You can view the file permissions as:
```bash
ls -al matrix*

# Search for the executable `x` in the ruleset
ls -al matrix* | grep x
```

* Add permission to execute for the file as:

```bash
chmod +x matrix.py
```

* Now, you can execute the python script with no errors:
```bash
./<file.py> <args>
```







