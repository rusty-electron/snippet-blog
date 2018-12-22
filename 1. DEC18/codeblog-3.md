## CodeBlog - 3

### 0x05 Simple Reverse Engineering 

Linux has `gdb` (GNU Debugger) preinstalled which is a useful tool for reverse engineering binary code. The dissassembly code is in `assembly language` which can be analyzed using `gdb` as per requirement.

* run `gdb` on a file as:
```bash
gdb <binary file>

#It results in the gdb prompt
(gdb)  
```

* set syntax type to `Intel` from `AT&T`
```bash
set disassembly-flavor intel
```

* disassemble `main`
```bash
disassemble main
```

* create breakpoints
```bash
# breakpoint at main
break *main

# breakpoint at an address
break *0x0000000000400604
```

* continue execution after breakpoint

```bash
run

# with arguments
run <args>
```
* examine contents of registers
```
info registers
```

* execute next instruction
```bash
# execute instructions and follow function calls
si

# only execute instructions and not follow function calls
ni
```

* continue program execution till next breakpoint
```
continue
```

* change value of register
```
set $eax = 0
```

*Note:* You can repeat the current instruction by simply typing ENTER. No need to retype the command.

### Useful Links:

1. [HopperApp](http://www.hopperapp.com/)
2. [IDA](https://www.hex-rays.com/products/ida/)
3. [radare2](https://github.com/radare/radare2)


