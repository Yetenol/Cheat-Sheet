# [⌂](../README.md) › [Powershell](../README.md#powershell) › **Bash equivalents** - Table of Contents
- examples of bash commands and how to do the same thing in PowerShell

1. [Echo](#echo)
1. [Execute a Script](#execute-a-script)
1. [Comments](#comments)
1. [Multiline Comments](#multiline-comments)
1. [While Loop](#while-loop)
1. [For Loop](#for-loop)
1. [Get User Input](#get-user-input)
1. [If Statement](#if-statement)
1. [If with And Logic](#if-with-and-logic)
1. [If with Or Logic](#if-with-or-logic)
1. [If Else Statements](#if-else-statements)
1. [Case Statement](#case-statement)
1. [Command Line Arguments](#command-line-arguments)
1. [Named Command Line Arguments](#named-command-line-arguments)
1. [Concatenating Strings](#concatenating-strings)
1. [Substring of a String](#substring-of-a-string)
1. [Functions](#functions)
1. [Functions with Parameters](#functions-with-parameters)
1. [Use the Return value of a Function](#use-the-return-value-of-a-function)
1. [Make a Directory](#make-a-directory)
1. [Make Directory if it doesn’t exist](#make-directory-if-it-doesnt-exist)
1. [Read a File](#read-a-file)
1. [Delete a File](#delete-a-file)
1. [Append to a File](#append-to-a-file)
1. [Wait for a Process](#wait-for-a-process)
1. [Sleep](#sleep)
1. [Download Files](#download-files)
1. [Search a File for a String](#search-a-file-for-a-string)



## Echo
Write text to the screen.

### Bash

```bash
echo "Hello, World!"
echo -e "Hello, \t World!"
```

### PowerShell

```powershell
Write-Output 'Hello, World!'
Write-Output "Hello, `t World!"
# Alias is also echo
echo 'Hello, World!'
```


## Execute a Script
Save and execute a script with bash and PowerShell.

### Bash

Assume that `echo1.sh` has the following contents.

```bash
#!/bin/bash
echo "Hello, World!"
```

You would the execute it with the following command line.

```bash
bash echo1.sh
```

### PowerShell

Assume `echo1.ps1` has the following contents.

```powershell
#!/usr/bin/env pwsh
Write-Host "Hello, World!"
```

You would then execute it with the following command line.

```powershell
pwsh echo1.ps1
```


## Comments
Comments are the same in PowerShell and bash.

### Bash

```bash
# My Comment!
```

### PowerShell

```powershell
# My Comment!
```


## Multiline Comments
Multiline comments are different between bash and PowerShell.

### Bash

```bash
#!/bin/bash
: 'Multi
line
comment'
echo "42"
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
&lt;# 
Multi
line
comment
#&gt;
Write-Host "42"
```


## While Loop

### Bash

```bash
#!/bin/bash
valid=true
count=1
while [ $valid ]
do
echo $count
if [ $count -eq 5 ];
then
break
fi
((count++))
done
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
$count = 0
while($true) {
  Write-Host $count
  if ($count -eq 5) {
      break
  }
  $count++
}
```


## For Loop

### Bash

```bash
#!/bin/bash
for (( counter=10; counter&gt;0; counter-- ))
do
echo -n "$counter "
done
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
for($counter = 10; $counter -gt 0; $counter--) {
    Write-Host $counter
}
```


## Get User Input

### Bash

```bash
#!/bin/bash
echo "Enter Your Name"
read name
echo "Welcome, $name!"
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
$name = Read-Host "Enter Your Name"
Write-Host "Welcome, $name!"
```


## If Statement

### Bash

```bash
#!/bin/bash
n=10
if [ $n -lt 10 ];
then
echo "It is a one digit number"
else
echo "It is a two digit number"
fi
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
$n = 10
if ($n -lt 10) {
    Write-Host "It is a one digit number"
} else {
    Write-Host "It is a two digit number"
}
```


## If with And Logic

### Bash

```bash
#!/bin/bash

echo "Enter username"
read username
echo "Enter password"
read password

if [[ ( $username == "admin" &amp;&amp; $password == "secret" ) ]]; then
echo "valid user"
else
echo "invalid user"
fi
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
$UserName = Read-Host "Enter username"
$Password = Read-Host "Enter password"

if ($username -eq 'admin' -and $password -eq 'secret') {
    Write-Host 'valid user'
} else {
    Write-Host 'invalid user'
}
```


## If with Or Logic

### Bash

```bash
#!/bin/bash

echo "Enter any number"
read n

if [[ ( $n -eq 15 || $n  -eq 45 ) ]]
then
echo "You won the game"
else
echo "You lost the game"
fi
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
[int]$n = Read-Host "Enter any number"

if ($n -eq 15 -or $n -eq 45) {
    Write-Host "You won the game"
} else {
    Write-Host "You lost the game"
}
```


## If Else Statements

### Bash

```bash
#!/bin/bash

echo "Enter your lucky number"
read n

if [ $n -eq 101 ];
then
echo "You got 1st prize"
elif [ $n -eq 510 ];
then
echo "You got 2nd prize"
elif [ $n -eq 999 ];
then
echo "You got 3rd prize"

else
echo "Sorry, try for the next time"
fi
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
[int]$n = Read-Host "Enter your lucky number"

if ($n -eq 101) {
    Write-Host "You got 1st prize"
} elseif ($n -eq 510) {
    Write-Host "You got 2nd prize"
} elseif ($n -eq 999) {
    Write-Host "You got 3rd prize"
} else {
    Write-Host "Sorry, try for the next time"
}
```


## Case Statement

### Bash

```bash
#!/bin/bash

echo "Enter your lucky number"
read n
case $n in
101)
echo echo "You got 1st prize" ;;
510)
echo "You got 2nd prize" ;;
999)
echo "You got 3rd prize" ;;
*)
echo "Sorry, try for the next time" ;;
esac
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
[int]$n = Read-Host "Enter your lucky number"
switch($n) {
    101 { Write-Host "You got 1st prize" }
    510 { Write-Host "You got 2nd prize" }
    999 { Write-Host "You got 3rd prize" }
    default { Write-Host "Sorry, try for the next time" }
}
```


## Command Line Arguments

### Bash

```bash
#!/bin/bash
echo "Total arguments : $#"
echo "1st Argument = $1"
echo "2nd argument = $2"
```

### PowerShell

```powershell
Write-Host "Total arguments: $($args.Length)"
Write-Host "1st Argument: $($args[0])"
Write-Host "2nd Argument: $($args[1])"
```


## Named Command Line Arguments

### Bash

```bash
#!/bin/bash
for arg in "$@"
do
index=$(echo $arg | cut -f1 -d=)
val=$(echo $arg | cut -f2 -d=)
case $index in
X) x=$val;;

Y) y=$val;;

*)
esac
done
((result=x+y))
echo "X+Y=$result"
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
param([int]$X, [int]$Y)

$Result = $X + $Y
Write-Host "X+Y=$Result"
```


## Concatenating Strings

### Bash

```bash
#!/bin/bash

string1="Linux"
string2="Hint"
echo "$string1$string2"
string3=$string1+$string2
string3+=" is a good tutorial blog site"
echo $string3
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
$string1 = "Ironman"
$string2 = "Software"
Write-Host "$string1 $string2"
$string3 = $string1+$string2
$string3 +=" makes good software"
Write-Host $string3
```


## Substring of a String

### Bash

```bash
#!/bin/bash
Str="Learn Linux from LinuxHint"
subStr=${Str:6:5}
echo $subStr
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
$Str = 'Learn PowerShell from Ironman Software'
$subStr = $Str.Substring(6, 10)
Write-Host $subStr
```


## Functions

### Bash

```bash
#!/bin/bash
function F1()
{
echo 'I like bash programming'
}

F1
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
function F1 {
    Write-Host "I like PowerShell programming"
}
F1
```


## Functions with Parameters

### Bash

```bash
#!/bin/bash

Rectangle_Area() {
area=$(($1 * $2))
echo "Area is : $area"
}

Rectangle_Area 10 20
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
function RectangleArea {
    $Area = $Args[0] * $Args[1]
    Write-Host "Area is: $Area"
}
RectangleArea 10 20
```


## Use the Return value of a Function

### Bash

```bash
#!/bin/bash
function greeting() {

str="Hello, $name"
echo $str

}

echo "Enter your name"
read name

val=$(greeting)
echo "Return value of the function is $val"
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
function Greeting {
    "Hello, $Name"
}

$Name = Read-Host "Enter your name"
$Val = Greeting
Write-Host "Return value of the function is $val"
```


## Make a Directory

### Bash

```bash
#!/bin/bash
echo "Enter directory name"
read newdir
`mkdir $newdir`
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
$newdir = Read-Host "Enter directory name"
New-Item $newdir -ItemType Directory
# mkdir also works
mkdir $newdir
```


## Make Directory if it doesn’t exist

### Bash

```bash
#!/bin/bash
echo "Enter directory name"
read ndir
if [ -d "$ndir" ]
then
echo "Directory exist"
else
`mkdir $ndir`
echo "Directory created"
fi
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
$newdir = Read-Host "Enter directory name"
if (Test-Path $newdir)
{
    Write-Host "Directory exists"
} else {
    New-Item $newdir -ItemType Directory
}

# shorter syntax
$newdir = Read-Host "Enter directory name"
if (gi $newdir -ea si)
{
    echo "Directory exists"
} else {
    mkdir $newdir
}
```


## Read a File

### Bash

```bash
#!/bin/bash
file='book.txt'
while read line; do
echo $line
done &lt; $file
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
Get-Content 'book.txt'
```


## Delete a File

### Bash

```bash
#!/bin/bash
echo "Enter filename to remove"
read fn
rm -i $fn
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
$fn = Read-Host "Enter a file to remove"
Remove-Item $fn

# Shorter syntax
$fn = Read-Host "Enter a file to remove"
rm $fn
```


## Append to a File

### Bash

```bash
#!/bin/bash

echo "Before appending the file"
cat book.txt

echo "Learning Laravel 5"&gt;&gt; book.txt
echo "After appending the file"
cat book.txt
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
Write-Host "Before appending the file"
Get-Content book.txt

"Learning Laravel 5" &gt;&gt; book.txt
Write-Host "After appending the file"
Get-Content book.txt
```


## Wait for a Process

### Bash

```bash
#!/bin/bash
echo "Wait command" &amp;
process_id=$!
wait $process_id
echo "Exited with status $?"
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
Start-Process notepad -Wait
Get-Process -Id $ProcessId | Wait-Process
```


## Sleep

### Bash

```bash
#!/bin/bash

echo “Wait for 5 seconds”
sleep 5
echo “Completed”
```

### PowerShell

```powershell
#!/usr/bin/env pwsh
Write-Host "Wait for 5 seconds"
Start-Sleep 5 
#shorter syntax
sleep 5
Write-Host "Completed"
```


## Download Files

### Bash

```bash
curl -o newname.txt http://www.het.brown.edu/guide/UNIX-password-security.txt
```

### PowerShell

```powershell
Invoke-WebRequest http://www.het.brown.edu/guide/UNIX-password-security.txt -OutFile .\newname.txt
# shorter syntax
iwr http://www.het.brown.edu/guide/UNIX-password-security.txt -o newname.txt
```


## Search a File for a String

### Bash

```bash
# Search a file
grep error log.txt

# Search a directory
grep error *

# Recursively search a directory
grep -r error *

# List matching files
grep -l error *

# Measure number of objects
grep -c error *

# Display lines before and after
grep -C 2 error *
```

### PowerShell

```powershell
# Search a file
Select-String error log.txt

# Search a Directory
Select-String error *

# Recursively search a directory
Get-ChildItem * -Recurse | Select-String error

# List matching files
Select-String error * | Select-Object path

# Count Matches
Select-String error * | Measure-Object

# Display lines before and after
Select-String error * 
```


# Sources

- 2021-12-09: [Bash vs PowerShell Cheat Sheet](https://blog.ironmansoftware.com/daily-powershell/bash-powershell-cheatsheet/)
- 2021-12-09: [30 Bash Script Examples](https://linuxhint.com/30_bash_script_examples/)