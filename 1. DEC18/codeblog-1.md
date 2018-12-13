## CodeBlog - 1

### 0x02 C Programming

* Run the program using `./<program-name>`

* Run `env` on console to see list of environment variables

It displays a list containing all environment variables including `PATH` that contains the path location of programs like `ls`

* Filter outpot of env using grep to find `PATH` 

```bash
env | grep 'PATH'
```

or simple use echo to print the content of `PATH` variable

```bash
echo $PATH
```

* Find location of program using `whereis`

* Add stuff to path

```bash
export PATH <location> #note that you must append to original
```

### Access `printf` man page 

```bash
man 3 printf
```

* using `gcc` to compile with warnings

```bash
gcc matrix.c -o matrix -Wall
```

* display exit code of previously ran program using 
```bash

```

**Trick:** select text on terminal and then click middle mouse to paste directly

### Vim

* press `i` to enter *INSERT* mode
* press `Esc` to enter *COMMAND* mode
    * `:w - save`
    * `:q - quit`
    * `:wq - save and quit`
    * `syntax on - turn on syntax highlighting`
    * `set number - turn on line numbering`
    * `o - enter *INSERT* mode along with entering a newline '\n'`
    * `shift + g - goto end of document`

### Exercise

`.bashrc` - contains commands that are run every terminal start

* open `.bashrc` using vim
* goto end of file
* insert the following lines

```bash
export PATH=$PATH:$HOME
./matrix $USER
```

* open a terminal window and see the `effect`

*Alternatively, we can do it without altering PATH*

```bash
$HOME/matrix $USER
```

