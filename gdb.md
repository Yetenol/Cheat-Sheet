# C Debugging - gdb Command Cheat Sheet

Command | Description
:--- | :---
help | List gdb command topics.
help topic-classes | List gdb command within class.
help command | Command description. <br> eg help show to list the show commands
apropos search-word | Search for commands and command topics containing search-word.
info args | List program command line arguments
i args <br> info breakpoints | List breakpoints
info break | List breakpoint numbers.
info break breakpoint-number | List info about specific breakpoint.
info watchpoints | List breakpoints
info registers | List registers in use
info threads | List threads in use
info set | List set-able option
Break and Watch <br> break funtion-name | Suspend program at specified function of line number.
break line-number <br> break ClassName::functionName <br> break +offset | Set a breakpoint specified number of lines forward or back from the position at which execution stopped.
break -offset <br> break filename:function | Don't specify path, just the file name and function name.
break filename:line-number | Don't specify path, just the file name and line number. <br> break Directory/Path/filename.cpp:62
break *address | Suspend processing at an instruction address. Used when you do not have source.
break line-number if condition | Where condition is an expression. i.e. x > 5 <br> Suspend when boolean expression is true.
break line thread thread-number | Break in thread at specified line number. Use info threads to display thread numbers.
tbreak | "Temporary break. Break once only. Break is then removed. See ""break"" above for options."
watch condition | Suspend processing when condition is met. i.e. x > 5
clear | Delete breakpoints as identified by command option.
clear function | Delete all breakpoints in function
clear line-number | Delete breakpoints at a given line
delete | Delete all breakpoints, watchpoints, or catchpoints.
d <br> delete breakpoint-number | Delete the breakpoints, watchpoints, or catchpoints of the breakpoint ranges specified as arguments.
delete range <br> disable breakpoint-number-or-range | Does not delete breakpoints. Just enables/disables them.
enable breakpoint-number-or-range | Example: <br> Show breakpoints: info break <br> Disable: disable 2-9
enable breakpoint-number once | Enables once
continue | Continue executing until next break point/watchpoint.
c <br> continue number | Continue but ignore current breakpoint number times. Usefull for breakpoints within a loop.
finish | Continue to end of function.
Line Execution <br> step | Step to next line of code. Will step into a function.
s <br> step number-of-steps-to-perform <br> next | Execute next line of code. Will not enter functions.
n <br> next number <br> until | Continue processing until you reach a specified line number. Also: function name, address, filename:function or filename:line-number.
until line-number <br> info signals | Perform the following option when signal recieved: nostop, stop, print, noprint, pass/noignore or nopass/ignore
info handle <br> handle SIGNAL-NAME option <br> where | Shows current line number and which function you are in.
Stack <br> backtrace | Show trace of where you are currently. Which functions you are in. Prints stack backtrace.
bt <br> bt inner-function-nesting-depth <br> bt -outer-function-nesting-depth <br> backtrace full | Print values of local variables.
frame | Show current stack frame (function where you are stopped)
frame number | Select frame number. (can also user up/down to navigate frames)
f number <br> up | Move up a single frame (element in the call stack)
down | Move down a single frame
up number | Move up/down the specified number of frames in the stack.
down number <br> info frame | List address, language, address of arguments/local variables and which registers were saved in frame.
info args | Info arguments of selected frame, local variables and exception handlers.
info locals <br> info catch <br> Source Code <br> list | List source code.
l <br> list line-number <br> list function <br> list - <br> list start#,end# <br> list filename:function <br> set listsize count | Number of lines listed when list command given.
show listsize <br> directory directory-name | Add specified directory to front of source code path.
dir directory-name <br> show directories <br> directory | Clear sourcepath when nothing specified.
Machine Language <br> info line | Displays the start and end position in object code for the current line in source.
info line number | Display position in object code for a specified line in source.
disassemble 0xstart 0xend | Displays machine code for positions in object code specified (can use start and end hex memory values given by the info line command.
stepi | step/next assembly/processor instruction.
si <br> nexti <br> ni <br> x 0xaddress | Examine the contents of memory.
x/nfu 0xaddress | Examine the contents of memory and specify formatting. <br> n: number of display items to print <br> f: specify the format for the output <br> u: specify the size of the data unit (eg. byte, word, ...) <br> Example: x/4dw var
Examine Variables <br> print variable-name | Print value stored in variable.
p variable-name <br> p file-name::variable-name <br> p 'file-name'::variable-name <br> p *array-variable@length | Print first # values of array specified by length. Good for pointers to dynamicaly allocated memory.
p/x variable | Print as integer variable in hex.
p/d variable | Print variable as a signed integer.
p/u variable | Print variable as a un-signed integer.
p/o variable | Print variable as a octal.
p/t variable | Print as integer value in binary. (1 byte/8bits)
x/b address <br> x/b &variable <br> p/c variable | Print integer as character.
p/f variable | Print variable as floating point number.
p/a variable | Print as a hex address.
x/w address | Print binary representation of 4 bytes (1 32 bit word) of memory pointed to by address.
x/4b &variable <br> ptype variable | Prints type definition of the variable or declared variable type. Helpful for viewing class or struct definitions while debugging.
ptype data-type <br> GDB Modes <br> set gdb-option value | Set a GDB option
set logging on | Turn on/off logging. Default name of file is gdb.txt
set logging off <br> show logging <br> set logging file log-file <br> set print array on | Default is off. Convient readable format for arrays turned on/off.
set print array off <br> show print array <br> set print array-indexes on | Default off. Print index of array elements.
set print array-indexes off <br> show print array-indexes <br> set print pretty on | Format printing of C structures.
set print pretty off <br> show print pretty <br> set print union on | Default is on. Print C unions.
set print union off <br> show print union <br> set print demangle on | Default on. Controls printing of C++ names.
set print demangle off <br> show print demangle <br> Start and Stop <br> run | Start program execution from the beginning of the program. The command break main will get you started. Also allows basic I/O redirection.
r <br> run command-line-arguments <br> run < infile > outfile <br> continue | Continue execution to next break point.
c <br> kill | Stop program execution.
quit | Exit GDB debugger.
q <br> 

Source: [Linux Tutorial - GNU GDB Debugger Command Cheat Sheet](http://www.yolinux.com/TUTORIALS/GDB-Commands.html)