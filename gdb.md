# C Debugging - gdb Command Cheat Sheet

Option | Description
:--- | :---
help | List gdb command topics.
help <i>topic-classes</i> | List gdb command within class.
help <i>command</i> | Command description. <br>eg <tt>help show</tt> to list the show commands
apropos <i>search-word</i> | Search for commands and command topics containing <i>search-word</i>.
info args<br>i args | List program command line arguments
info breakpoints | List breakpoints
info break | List breakpoint numbers.
info break <i>breakpoint-number</i> | List info about specific breakpoint.
info watchpoints | List breakpoints
info registers | List registers in use
info threads | List threads in use
info set | List set-able option
<h2>Break and Watch </h2> | 
break <i>funtion-name</i><br>break <i>line-number</i><br><tt>break <i>ClassName::functionName</i></tt> | Suspend program at specified function of line number.
break +<i>offset</i><br>break -<i>offset</i> | Set a breakpoint specified number of lines forward or back from the position at which execution stopped.
break <i>filename:function</i> | Don't specify path, just the file name and function name.
break <i>filename:line-number</i> | Don't specify path, just the file name and line number.<br><tt>break <i>Directory/Path/filename</i>.cpp:62</tt>
break *<i>address</i> | Suspend processing at an instruction address. Used when you do not have source.
break <i>line-number</i> if <i>condition</i> | Where condition is an expression. i.e. <tt>x &gt; 5</tt><br>Suspend when boolean expression is true.
break <i>line</i> thread <i>thread-number</i> | Break in thread at specified line number. Use <tt>info threads</tt> to display thread numbers.
tbreak | Temporary break. Break once only. Break is then removed. See "break" above for options.
watch <i>condition</i> | Suspend processing when condition is met. i.e. <tt>x &gt; 5</tt>
clear<br> clear <i>function</i><br> clear <i>line-number</i> | Delete breakpoints as identified by command option.<br>Delete all breakpoints in <i>function</i><br>Delete breakpoints at a given line
delete<br>d | Delete all breakpoints, watchpoints, or catchpoints.
delete <i>breakpoint-number</i><br>delete <i>range</i> | Delete the breakpoints, watchpoints, or catchpoints of the breakpoint ranges specified as arguments.
disable <i>breakpoint-number-or-range</i><br>enable <i>breakpoint-number-or-range</i> | Does not delete breakpoints. Just enables/disables them.<br>Example:<br>Show breakpoints: <tt>info break</tt><br>Disable: <tt>disable 2-9</tt>
enable <i>breakpoint-number</i> once | Enables once
continue<br>c | Continue executing until next break point/watchpoint.
continue <i>number</i> | Continue but ignore current breakpoint <i>number</i> times.<br>Usefull for breakpoints within a loop.
finish | Continue to end of function.
<h2>Line Execution </h2> | 
step<br>s<br>step <i>number-of-steps-to-perform</i> | Step to next line of code. Will step into a function.
next<br>n<br>next <i>number</i> | Execute next line of code. Will not enter functions. 
until<br>until <i>line-number</i> | Continue processing until you reach a specified line number. <br>Also: function name, address, filename:function or filename:line-number.
info signals<br>info handle<br>handle <i>SIGNAL-NAME</i> <i>option</i> | Perform the following option when signal recieved: nostop, stop, print, noprint, pass/noignore or nopass/ignore
where | Shows current line number and which function you are in.
<h2>Stack </h2> | 
backtrace<br>bt<br>bt <i>inner-function-nesting-depth</i><br>bt -<i>outer-function-nesting-depth</i> | Show trace of where you are currently. Which functions you are in. Prints stack backtrace.
backtrace full | Print values of local variables.
frame<br>frame <i>number</i><br>f <i>number</i> | Show current stack frame (function where you are stopped)<br>Select frame number. (can also user up/down to navigate frames)
up<br>down<br>up <i>number</i><br>down <i>number</i> | Move up a single frame (element in the call stack)<br>Move down a single frame<br>Move up/down the specified number of frames in the stack.
info frame | List address, language, address of arguments/local variables and which registers were saved in frame.
info args<br>info locals<br>info catch | Info arguments of selected frame, local variables and exception handlers.
<h2>Source Code </h2> | 
list<br>l<br>list <i>line-number</i><br>list <i>function</i><br>list -<br>list <i>start#,end#</i><br>list <i>filename:function</i> | List source code.
set listsize <i>count</i><br>show listsize | Number of lines listed when <tt>list command given.</tt>
directory <i>directory-name</i><br>dir <i>directory-name</i><br>show directories | Add specified directory to front of source code path.
directory | Clear sourcepath when nothing specified.
<h2>Machine Language </h2> | 
info line<br>info line <i>number</i> | Displays the start and end position in object code for the current line in source.<br>Display position in object code for a specified line in source.
disassemble <i>0xstart 0xend</i> | Displays machine code for positions in object code specified (can use start and end hex memory values given by the <tt>info line</tt> command.
stepi<br> si<br> nexti<br> ni | step/next assembly/processor instruction.
x <i>0xaddress</i><br>x/nfu <i>0xaddress</i> | Examine the contents of memory.<br>Examine the contents of memory and specify formatting.<ul><li>n: number of display items to print</li><li>f: specify the format for the output</li><li>u: specify the size of the data unit (eg. byte, word, ...)</li></ul>Example: <tt>x/4dw var</tt>
<h2>Examine Variables </h2> | 
print <i>variable-name</i><br>p <i>variable-name</i><br>p <i>file-name::variable-name</i><br>p '<i>file-name</i>'::<i>variable-name</i> | Print value stored in variable.
p *<i>array-variable</i>@<i>length</i> | Print first # values of array specified by <i>length</i>. Good for pointers to dynamicaly allocated memory.
p/x <i>variable</i> | Print as integer variable in hex.
p/d <i>variable</i> | Print variable as a signed integer.
p/u <i>variable</i> | Print variable as a un-signed integer.
p/o <i>variable</i> | Print variable as a octal.
p/t <i>variable</i><br>x/b <i>address</i><br>x/b &amp;<i>variable</i> | Print as integer value in binary. (1 byte/8bits)
p/c <i>variable</i> | Print integer as character.
p/f <i>variable</i> | Print variable as floating point number.
p/a <i>variable</i> | Print as a hex address.
x/w <i>address</i><br>x/4b &amp;<i>variable</i> | Print binary representation of 4 bytes (1 32 bit word) of memory pointed to by address.
ptype <i>variable</i><br>ptype <i>data-type</i> | Prints type definition of the variable or declared variable type. Helpful for viewing class or struct definitions while debugging.
<h2>GDB Modes </h2> | 
set <i>gdb-option</i> <i>value</i> | Set a GDB option
set logging on<br>set logging off<br>show logging<br>set logging file <i>log-file</i> | Turn on/off logging. Default name of file is <tt>gdb.txt</tt>
set print array on<br>set print array off<br>show print array | Default is off. Convient readable format for arrays turned on/off.
set print array-indexes on<br>set print array-indexes off<br>show print array-indexes | Default off. Print index of array elements.
set print pretty on<br>set print pretty off<br>show print pretty | Format printing of C structures.
set print union on<br>set print union off<br>show print union | Default is on. Print C unions.
set print demangle on<br>set print demangle off<br>show print demangle | Default on. Controls printing of C++ names.
<h2>Start and Stop </h2> | 
run<br>r<br>run <i>command-line-arguments</i><br>run &lt; <i>infile</i> &gt; <i>outfile</i> | Start program execution from the beginning of the program. <br>The command <tt>break main</tt> will get you started. Also allows basic I/O redirection.
continue<br>c | Continue execution to next break point.
kill | Stop program execution.
quit<br>q | Exit GDB debugger.

# trash

Command | Description
:--- | :---
help | List gdb command topics.
help topic-classes|List gdb command within class.
help command|Command description.<br>eg help show to list the show commands
apropos search-word|Search for commands and command topics containing search-word.
info args<br>i args|List program command line arguments
info breakpoints|List breakpoints
info break|List breakpoint numbers.
info break breakpoint-number|List info about specific breakpoint.
info watchpoints|List breakpoints
info registers|List registers in use
info threads|List threads in use
info set|List set-able option
Break and Watch|
break funtion-name<br>break line-number<br>break ClassName::functionName|Suspend program at specified function of line number.
break +offset<br>break -offset|Set a breakpoint specified number of lines forward or back from the position at which execution stopped.
break filename:function|Don't specify path, just the file name and function name.
break filename:line-number|Don't specify path, just the file name and line number.<br>break Directory/Path/filename.cpp:62
break *address|Suspend processing at an instruction address. Used when you do not have source.
break line-number if condition|Where condition is an expression. i.e. x > 5<br>Suspend when boolean expression is true.
break line thread thread-number|Break in thread at specified line number. Use info threads to display thread numbers.
tbreak|Temporary break. Break once only. Break is then removed. See "break" above for options.
watch condition|Suspend processing when condition is met. i.e. x > 5
clear<br>clear function<br>|Delete breakpoints as identified by command option.<br>Delete all breakpoints in function<br>Delete breakpoints at a given line
delete<br>d|Delete all breakpoints, watchpoints, or catchpoints.
delete breakpoint-number<br>delete range|Delete the breakpoints, watchpoints, or catchpoints of the breakpoint ranges specified as arguments.
disable breakpoint-number-or-range<br>enable breakpoint-number-or-range|Does not delete breakpoints. Just enables/disables them.<br>Example:<br>Show breakpoints: info break<br>Disable: disable 2-9
enable breakpoint-number once|Enables once
continue<br>c|Continue executing until next break point/watchpoint.
continue number|Continue but ignore current breakpoint number times. Usefull for breakpoints within a loop.
finish|Continue to end of function.
<h1>Line Execution</h1>|
step<br>s<br>step number-of-steps-to-perform|Step to next line of code. Will step into a function.


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