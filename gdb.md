# C Debugging - gdb Command Cheat Sheet

Command | Description
:--- | :---
help;List gdb command topics.
help topic-classes;List gdb command within class.
help command;Command description.<br>eg help show to list the show commands
apropos search-word;Search for commands and command topics containing search-word.
info args<br>i args;List program command line arguments
info breakpoints;List breakpoints
info break;List breakpoint numbers.
info break breakpoint-number;List info about specific breakpoint.
info watchpoints;List breakpoints
info registers;List registers in use
info threads;List threads in use
info set;List set-able option
Break and Watch;
break funtion-name<br>break line-number<br>break ClassName::functionName;Suspend program at specified function of line number.
break +offset<br>break -offset;Set a breakpoint specified number of lines forward or back from the position at which execution stopped.
break filename:function;Don't specify path, just the file name and function name.
break filename:line-number;Don't specify path, just the file name and line number.<br>break Directory/Path/filename.cpp:62
break *address;Suspend processing at an instruction address. Used when you do not have source.
break line-number if condition;Where condition is an expression. i.e. x > 5<br>Suspend when boolean expression is true.
break line thread thread-number;Break in thread at specified line number. Use info threads to display thread numbers.
tbreak;Temporary break. Break once only. Break is then removed. See "break" above for options.
watch condition;Suspend processing when condition is met. i.e. x > 5
clear<br>clear function<br>;Delete breakpoints as identified by command option.<br>Delete all breakpoints in function<br>Delete breakpoints at a given line
delete<br>d;Delete all breakpoints, watchpoints, or catchpoints.
delete breakpoint-number<br>delete range;Delete the breakpoints, watchpoints, or catchpoints of the breakpoint ranges specified as arguments.
disable breakpoint-number-or-range<br>enable breakpoint-number-or-range;Does not delete breakpoints. Just enables/disables them.<br>Example:<br>Show breakpoints: info break<br>Disable: disable 2-9
enable breakpoint-number once;Enables once
continue<br>c;Continue executing until next break point/watchpoint.
continue number;Continue but ignore current breakpoint number times. Usefull for breakpoints within a loop.
finish;Continue to end of function.
<h1>Line Execution</h1>;
step<br>s<br>step number-of-steps-to-perform;Step to next line of code. Will step into a function.


next<br>n<br>next number;Execute next line of code. Will not enter functions.
until;Continue processing until you reach a specified line number. Also: function name, address, filename:function or filename:line-number.
until line-number;
info signals;Perform the following option when signal recieved: nostop, stop, print, noprint, pass/noignore or nopass/ignore
info handle;
handle SIGNAL-NAME option;
where;Shows current line number and which function you are in.
Stack;
backtrace;Show trace of where you are currently. Which functions you are in. Prints stack backtrace.
bt;
bt inner-function-nesting-depth;
bt -outer-function-nesting-depth;
backtrace full;Print values of local variables.
frame;Show current stack frame (function where you are stopped)
frame number;Select frame number. (can also user up/down to navigate frames)
f number;
up;Move up a single frame (element in the call stack)
down;Move down a single frame
up number;Move up/down the specified number of frames in the stack.
down number;
info frame;List address, language, address of arguments/local variables and which registers were saved in frame.
info args;Info arguments of selected frame, local variables and exception handlers.
info locals;
info catch;
Source Code;
list;List source code.
l;
list line-number;
list function;
list -;
list start#,end#;
list filename:function;
set listsize count;Number of lines listed when list command given.
show listsize;
directory directory-name;Add specified directory to front of source code path.
dir directory-name;
show directories;
directory;Clear sourcepath when nothing specified.
Machine Language;
info line;Displays the start and end position in object code for the current line in source.
info line number;Display position in object code for a specified line in source.
disassemble 0xstart 0xend;Displays machine code for positions in object code specified (can use start and end hex memory values given by the info line command.
stepi;step/next assembly/processor instruction.
si;
nexti;
ni;
x 0xaddress;Examine the contents of memory.
x/nfu 0xaddress;Examine the contents of memory and specify formatting.
;n: number of display items to print
;f: specify the format for the output
;u: specify the size of the data unit (eg. byte, word, ...)
;Example: x/4dw var
Examine Variables;
print variable-name;Print value stored in variable.
p variable-name;
p file-name::variable-name;
p 'file-name'::variable-name;
p *array-variable@length;Print first # values of array specified by length. Good for pointers to dynamicaly allocated memory.
p/x variable;Print as integer variable in hex.
p/d variable;Print variable as a signed integer.
p/u variable;Print variable as a un-signed integer.
p/o variable;Print variable as a octal.
p/t variable;Print as integer value in binary. (1 byte/8bits)
x/b address;
x/b &variable;
p/c variable;Print integer as character.
p/f variable;Print variable as floating point number.
p/a variable;Print as a hex address.
x/w address;Print binary representation of 4 bytes (1 32 bit word) of memory pointed to by address.
x/4b &variable;
ptype variable;Prints type definition of the variable or declared variable type. Helpful for viewing class or struct definitions while debugging.
ptype data-type;
GDB Modes;
set gdb-option value;Set a GDB option
set logging on;Turn on/off logging. Default name of file is gdb.txt
set logging off;
show logging;
set logging file log-file;
set print array on;Default is off. Convient readable format for arrays turned on/off.
set print array off;
show print array;
set print array-indexes on;Default off. Print index of array elements.
set print array-indexes off;
show print array-indexes;
set print pretty on;Format printing of C structures.
set print pretty off;
show print pretty;
set print union on;Default is on. Print C unions.
set print union off;
show print union;
set print demangle on;Default on. Controls printing of C++ names.
set print demangle off;
show print demangle;
Start and Stop;
run;Start program execution from the beginning of the program. The command break main will get you started. Also allows basic I/O redirection.
r;
run command-line-arguments;
run < infile > outfile;
continue;Continue execution to next break point.
c;
kill;Stop program execution.
quit;Exit GDB debugger.
q;


Source: [Linux Tutorial - GNU GDB Debugger Command Cheat Sheet](http://www.yolinux.com/TUTORIALS/GDB-Commands.html)