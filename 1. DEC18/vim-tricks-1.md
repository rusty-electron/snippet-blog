## 20-12-2018

*[Source](https://stackoverflow.com/questions/2514445/turning-off-auto-indent-when-pasting-text-into-vim)*

I am working in `vim` lately and in the process, I have learnt some useful configurations.

*For all configurations, create a `.vimrc` file in home directory and create necessary changes.*

* No Indentation for `new line` while writing code: 

Add the following line to `.vimrc`

```vim
set smartindent
```

* Extra indentation per line for pasted code

Pasting code into vim causes extra indentation per line as in:
```
line
  line
    line
```

To prevent this, before pasting code switch to *command mode* and
* type `:set past`. Note that the text in the tooltip now says `-- INSERT (paste) --`. 
* paste your code
* type `:set nopaste` and return to normal mode.

If you find this cumbersome. You can map `<F3>` such that it can switch between paste and nopaste modes while editing the text. Add this to `.vimrc`

```vim
set pastetoggle=<F3>
```

