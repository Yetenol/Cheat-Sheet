# Table of Contents

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

In this blog post, we’ll look at examples of bash scripts and how to do the same thing in PowerShell.
<p>Many of the bash commands found in this post where sourced from <a href="https://linuxhint.com/30_bash_script_examples/">LinuxHint</a>
<p>We also have a <a href="https://blog.ironmansoftware.com/powershell-vs-python/">Python vs PowerShell Cheat Sheet</a>.</p>


```


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
</code></pre></div><p>You would then execute it with the following command line.</p>
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
</code></pre></div>
<div class="alert alert-light" role="alert" style="text-align:center">
<p>Find this useful? Please consider sharing this article. Have a question about
PowerShell?
<a href="https://ironmansoftware.com/contact-us">Contact us and we'll write a
post
about it.</a> Want to support us with a tip? Support via
<a href="https://www.blockchain.com/btc/address/bc1q84d7w23ks7hsmc2dfm68kf8uysx3x4zdf0tktd">Bitcoin</a> or <a href="https://www.blockchain.com/eth/address/0x8ef27b92Edf3831be9422399Abb99Eb348d7FF85">Ethereum</a>
</p>
<p>
<a class="resp-sharing-button__link" href="https://facebook.com/sharer/sharer.php?u=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f" target="_blank" rel="noopener" aria-label="">

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:32px"><path d="M18.77 7.46H14.5v-1.9c0-.9.6-1.1 1-1.1h3V.5h-4.33C10.24.5 9.5 3.44 9.5 5.32v2.15h-3v4h3v12h5v-12h3.85l.42-4z"></path></svg>


</a>
<a class="resp-sharing-button__link" href="https://twitter.com/intent/tweet/?hashtags=dailypowershell,powershell&amp;text=Bash%20vs%20PowerShell%20Cheat%20Sheet&amp;url=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f" target="_blank" rel="noopener" aria-label="">

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:32px"><path d="M23.44 4.83c-.8.37-1.5.38-2.22.02.93-.56.98-.96 1.32-2.02-.88.52-1.86.9-2.9 1.1-.82-.88-2-1.43-3.3-1.43-2.5.0-4.55 2.04-4.55 4.54.0.36.03.7.1 1.04-3.77-.2-7.12-2-9.36-4.75-.4.67-.6 1.45-.6 2.3.0 1.56.8 2.95 2 3.77-.74-.03-1.44-.23-2.05-.57v.06c0 2.2 1.56 4.03 3.64 4.44-.67.2-1.37.2-2.06.08.58 1.8 2.26 3.12 4.25 3.16C5.78 18.1 3.37 18.74 1 18.46c2 1.3 4.4 2.04 6.97 2.04 8.35.0 12.92-6.92 12.92-12.93.0-.2.0-.4-.02-.6.9-.63 1.96-1.22 2.56-2.14z"></path></svg>


</a>
<a class="resp-sharing-button__link" href="mailto:?subject=Bash%20vs%20PowerShell%20Cheat%20Sheet&amp;body=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f" target="_self" rel="noopener" aria-label="">

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:32px"><path d="M22 4H2C.9 4 0 4.9.0 6v12c0 1.1.9 2 2 2h20c1.1.0 2-.9 2-2V6c0-1.1-.9-2-2-2zM7.25 14.43l-3.5 2c-.08.05-.17.07-.25.07-.17.0-.34-.1-.43-.25-.14-.24-.06-.55.18-.68l3.5-2c.24-.14.55-.06.68.18.14.24.06.55-.18.68zm4.75.07c-.1.0-.2-.03-.27-.08l-8.5-5.5c-.23-.15-.3-.46-.15-.7.15-.22.46-.3.7-.14L12 13.4l8.23-5.32c.23-.15.54-.08.7.15.14.23.07.54-.16.7l-8.5 5.5c-.08.04-.17.07-.27.07zm8.93 1.75c-.1.16-.26.25-.43.25-.08.0-.17-.02-.25-.07l-3.5-2c-.24-.13-.32-.44-.18-.68s.44-.32.68-.18l3.5 2c.24.13.32.44.18.68z"></path></svg>


</a>
<a class="resp-sharing-button__link" href="https://www.linkedin.com/shareArticle?mini=true&amp;url=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f&amp;title=Bash%20vs%20PowerShell%20Cheat%20Sheet&amp;source=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f" target="_blank" rel="noopener" aria-label="">

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:32px"><path d="M6.5 21.5h-5v-13h5v13zM4 6.5C2.5 6.5 1.5 5.3 1.5 4s1-2.4 2.5-2.4c1.6.0 2.5 1 2.6 2.5.0 1.4-1 2.5-2.6 2.5zm11.5 6c-1 0-2 1-2 2v7h-5v-13h5V10s1.6-1.5 4-1.5c3 0 5 2.2 5 6.3v6.7h-5v-7c0-1-1-2-2-2z"></path></svg>


</a>
<a class="resp-sharing-button__link" href="https://reddit.com/submit/?url=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f&amp;resubmit=true&amp;title=Bash%20vs%20PowerShell%20Cheat%20Sheet" target="_blank" rel="noopener" aria-label="">

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:32px"><path d="M24 11.5c0-1.65-1.35-3-3-3-.96.0-1.86.48-2.42 1.24-1.64-1-3.75-1.64-6.07-1.72.08-1.1.4-3.05 1.52-3.7.72-.4 1.73-.24 3 .5C17.2 6.3 18.46 7.5 20 7.5c1.65.0 3-1.35 3-3s-1.35-3-3-3c-1.38.0-2.54.94-2.88 2.22-1.43-.72-2.64-.8-3.6-.25-1.64.94-1.95 3.47-2 4.55-2.33.08-4.45.7-6.1 1.72C4.86 8.98 3.96 8.5 3 8.5c-1.65.0-3 1.35-3 3 0 1.32.84 2.44 2.05 2.84-.03.22-.05.44-.05.66.0 3.86 4.5 7 10 7s10-3.14 10-7c0-.22-.02-.44-.05-.66 1.2-.4 2.05-1.54 2.05-2.84zM2.3 13.37C1.5 13.07 1 12.35 1 11.5c0-1.1.9-2 2-2 .64.0 1.22.32 1.6.82-1.1.85-1.92 1.9-2.3 3.05zm3.7.13c0-1.1.9-2 2-2s2 .9 2 2-.9 2-2 2-2-.9-2-2zm9.8 4.8c-1.08.63-2.42.96-3.8.96-1.4.0-2.74-.34-3.8-.95-.24-.13-.32-.44-.2-.68.15-.24.46-.32.7-.18 1.83 1.06 4.76 1.06 6.6.0.23-.13.53-.05.67.2.14.23.06.54-.18.67zm.2-2.8c-1.1.0-2-.9-2-2s.9-2 2-2 2 .9 2 2-.9 2-2 2zm5.7-2.13c-.38-1.16-1.2-2.2-2.3-3.05.38-.5.97-.82 1.6-.82 1.1.0 2 .9 2 2 0 .84-.53 1.57-1.3 1.87z"></path></svg>


</a>
</p>
</div>
<hr>
</div>