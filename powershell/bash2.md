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


<h2 id="echo">Echo</h2>
<p>Write text to the screen.</p>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash">echo <span style="color:#e6db74">"Hello, World!"</span>
echo -e <span style="color:#e6db74">"Hello, \t World!"</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell">Write-Output <span style="color:#e6db74">'Hello, World!'</span>
Write-Output <span style="color:#e6db74">"Hello, </span><span style="color:#ae81ff">`t</span><span style="color:#e6db74"> World!"</span>
<span style="color:#75715e"># Alias is also echo</span>
echo <span style="color:#e6db74">'Hello, World!'</span>
</code></pre></div><h2 id="execute-a-script">Execute a Script</h2>
<p>Save and execute a script with bash and PowerShell.</p>
<p><strong>Bash</strong></p>
<p>Assume that <code>echo1.sh</code> has the following contents.</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>echo <span style="color:#e6db74">"Hello, World!"</span>
</code></pre></div><p>You would the execute it with the following command line.</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash">bash echo1.sh
</code></pre></div><p><strong>PowerShell</strong></p>
<p>Assume <code>echo1.ps1</code> has the following contents.</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
Write-Host <span style="color:#e6db74">"Hello, World!"</span>
</code></pre></div><p>You would then execute it with the following command line.</p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell">pwsh echo1.ps1
</code></pre></div><h2 id="comments">Comments</h2>
<p>Comments are the same in PowerShell and bash.</p>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e"># My Comment!</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e"># My Comment!</span>
</code></pre></div><h2 id="multiline-comments">Multiline Comments</h2>
<p>Multiline comments are different between bash and PowerShell.</p>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>: <span style="color:#e6db74">'Multi
</span><span style="color:#e6db74">line
</span><span style="color:#e6db74">comment'</span>
echo <span style="color:#e6db74">"42"</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
<span style="color:#75715e">&lt;# 
</span><span style="color:#75715e">Multi
</span><span style="color:#75715e">line
</span><span style="color:#75715e">comment
</span><span style="color:#75715e">#&gt;</span>
Write-Host <span style="color:#e6db74">"42"</span>
</code></pre></div><h2 id="while-loop">While Loop</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>valid<span style="color:#f92672">=</span>true
count<span style="color:#f92672">=</span><span style="color:#ae81ff">1</span>
<span style="color:#66d9ef">while</span> <span style="color:#f92672">[</span> $valid <span style="color:#f92672">]</span>
<span style="color:#66d9ef">do</span>
echo $count
<span style="color:#66d9ef">if</span> <span style="color:#f92672">[</span> $count -eq <span style="color:#ae81ff">5</span> <span style="color:#f92672">]</span>;
<span style="color:#66d9ef">then</span>
break
<span style="color:#66d9ef">fi</span>
<span style="color:#f92672">((</span>count++<span style="color:#f92672">))</span>
<span style="color:#66d9ef">done</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
$count = 0
<span style="color:#66d9ef">while</span>($true) {
  Write-Host $count
  <span style="color:#66d9ef">if</span> ($count <span style="color:#f92672">-eq</span> 5) {
      <span style="color:#66d9ef">break</span>
  }
  $count++
}
</code></pre></div><h2 id="for-loop">For Loop</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span><span style="color:#66d9ef">for</span> <span style="color:#f92672">((</span> counter<span style="color:#f92672">=</span>10; counter&gt;0; counter-- <span style="color:#f92672">))</span>
<span style="color:#66d9ef">do</span>
echo -n <span style="color:#e6db74">"</span>$counter<span style="color:#e6db74"> "</span>
<span style="color:#66d9ef">done</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
<span style="color:#66d9ef">for</span>($counter = 10; $counter <span style="color:#f92672">-gt</span> 0; $counter--) {
    Write-Host $counter
}
</code></pre></div><h2 id="get-user-input">Get User Input</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>echo <span style="color:#e6db74">"Enter Your Name"</span>
read name
echo <span style="color:#e6db74">"Welcome, </span>$name<span style="color:#e6db74">!"</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
$name = Read-Host <span style="color:#e6db74">"Enter Your Name"</span>
Write-Host <span style="color:#e6db74">"Welcome, $name!"</span>
</code></pre></div><h2 id="if-statement">If Statement</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>n<span style="color:#f92672">=</span><span style="color:#ae81ff">10</span>
<span style="color:#66d9ef">if</span> <span style="color:#f92672">[</span> $n -lt <span style="color:#ae81ff">10</span> <span style="color:#f92672">]</span>;
<span style="color:#66d9ef">then</span>
echo <span style="color:#e6db74">"It is a one digit number"</span>
<span style="color:#66d9ef">else</span>
echo <span style="color:#e6db74">"It is a two digit number"</span>
<span style="color:#66d9ef">fi</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
$n = 10
<span style="color:#66d9ef">if</span> ($n <span style="color:#f92672">-lt</span> 10) {
    Write-Host <span style="color:#e6db74">"It is a one digit number"</span>
} <span style="color:#66d9ef">else</span> {
    Write-Host <span style="color:#e6db74">"It is a two digit number"</span>
}
</code></pre></div><h2 id="if-with-and-logic">If with And Logic</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>
echo <span style="color:#e6db74">"Enter username"</span>
read username
echo <span style="color:#e6db74">"Enter password"</span>
read password

<span style="color:#66d9ef">if</span> <span style="color:#f92672">[[</span> <span style="color:#f92672">(</span> $username <span style="color:#f92672">==</span> <span style="color:#e6db74">"admin"</span> <span style="color:#f92672">&amp;&amp;</span> $password <span style="color:#f92672">==</span> <span style="color:#e6db74">"secret"</span> <span style="color:#f92672">)</span> <span style="color:#f92672">]]</span>; <span style="color:#66d9ef">then</span>
echo <span style="color:#e6db74">"valid user"</span>
<span style="color:#66d9ef">else</span>
echo <span style="color:#e6db74">"invalid user"</span>
<span style="color:#66d9ef">fi</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
$UserName = Read-Host <span style="color:#e6db74">"Enter username"</span>
$Password = Read-Host <span style="color:#e6db74">"Enter password"</span>

<span style="color:#66d9ef">if</span> ($username <span style="color:#f92672">-eq</span> <span style="color:#e6db74">'admin'</span> <span style="color:#f92672">-and</span> $password <span style="color:#f92672">-eq</span> <span style="color:#e6db74">'secret'</span>) {
    Write-Host <span style="color:#e6db74">'valid user'</span>
} <span style="color:#66d9ef">else</span> {
    Write-Host <span style="color:#e6db74">'invalid user'</span>
}
</code></pre></div><h2 id="if-with-or-logic">If with Or Logic</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>
echo <span style="color:#e6db74">"Enter any number"</span>
read n

<span style="color:#66d9ef">if</span> <span style="color:#f92672">[[</span> <span style="color:#f92672">(</span> $n -eq <span style="color:#ae81ff">15</span> <span style="color:#f92672">||</span> $n  -eq <span style="color:#ae81ff">45</span> <span style="color:#f92672">)</span> <span style="color:#f92672">]]</span>
<span style="color:#66d9ef">then</span>
echo <span style="color:#e6db74">"You won the game"</span>
<span style="color:#66d9ef">else</span>
echo <span style="color:#e6db74">"You lost the game"</span>
<span style="color:#66d9ef">fi</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
<span style="color:#66d9ef">[int]</span>$n = Read-Host <span style="color:#e6db74">"Enter any number"</span>

<span style="color:#66d9ef">if</span> ($n <span style="color:#f92672">-eq</span> 15 <span style="color:#f92672">-or</span> $n <span style="color:#f92672">-eq</span> 45) {
    Write-Host <span style="color:#e6db74">"You won the game"</span>
} <span style="color:#66d9ef">else</span> {
    Write-Host <span style="color:#e6db74">"You lost the game"</span>
}
</code></pre></div><h2 id="if-else-statements">If Else Statements</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>
echo <span style="color:#e6db74">"Enter your lucky number"</span>
read n

<span style="color:#66d9ef">if</span> <span style="color:#f92672">[</span> $n -eq <span style="color:#ae81ff">101</span> <span style="color:#f92672">]</span>;
<span style="color:#66d9ef">then</span>
echo <span style="color:#e6db74">"You got 1st prize"</span>
<span style="color:#66d9ef">elif</span> <span style="color:#f92672">[</span> $n -eq <span style="color:#ae81ff">510</span> <span style="color:#f92672">]</span>;
<span style="color:#66d9ef">then</span>
echo <span style="color:#e6db74">"You got 2nd prize"</span>
<span style="color:#66d9ef">elif</span> <span style="color:#f92672">[</span> $n -eq <span style="color:#ae81ff">999</span> <span style="color:#f92672">]</span>;
<span style="color:#66d9ef">then</span>
echo <span style="color:#e6db74">"You got 3rd prize"</span>

<span style="color:#66d9ef">else</span>
echo <span style="color:#e6db74">"Sorry, try for the next time"</span>
<span style="color:#66d9ef">fi</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
<span style="color:#66d9ef">[int]</span>$n = Read-Host <span style="color:#e6db74">"Enter your lucky number"</span>

<span style="color:#66d9ef">if</span> ($n <span style="color:#f92672">-eq</span> 101) {
    Write-Host <span style="color:#e6db74">"You got 1st prize"</span>
} <span style="color:#66d9ef">elseif</span> ($n <span style="color:#f92672">-eq</span> 510) {
    Write-Host <span style="color:#e6db74">"You got 2nd prize"</span>
} <span style="color:#66d9ef">elseif</span> ($n <span style="color:#f92672">-eq</span> 999) {
    Write-Host <span style="color:#e6db74">"You got 3rd prize"</span>
} <span style="color:#66d9ef">else</span> {
    Write-Host <span style="color:#e6db74">"Sorry, try for the next time"</span>
}
</code></pre></div><h2 id="case-statement">Case Statement</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>
echo <span style="color:#e6db74">"Enter your lucky number"</span>
read n
<span style="color:#66d9ef">case</span> $n in
101<span style="color:#f92672">)</span>
echo echo <span style="color:#e6db74">"You got 1st prize"</span> ;;
510<span style="color:#f92672">)</span>
echo <span style="color:#e6db74">"You got 2nd prize"</span> ;;
999<span style="color:#f92672">)</span>
echo <span style="color:#e6db74">"You got 3rd prize"</span> ;;
*<span style="color:#f92672">)</span>
echo <span style="color:#e6db74">"Sorry, try for the next time"</span> ;;
<span style="color:#66d9ef">esac</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
<span style="color:#66d9ef">[int]</span>$n = Read-Host <span style="color:#e6db74">"Enter your lucky number"</span>
<span style="color:#66d9ef">switch</span>($n) {
    101 { Write-Host <span style="color:#e6db74">"You got 1st prize"</span> }
    510 { Write-Host <span style="color:#e6db74">"You got 2nd prize"</span> }
    999 { Write-Host <span style="color:#e6db74">"You got 3rd prize"</span> }
    <span style="color:#66d9ef">default</span> { Write-Host <span style="color:#e6db74">"Sorry, try for the next time"</span> }
}
</code></pre></div><h2 id="command-line-arguments">Command Line Arguments</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>echo <span style="color:#e6db74">"Total arguments : </span>$#<span style="color:#e6db74">"</span>
echo <span style="color:#e6db74">"1st Argument = </span>$1<span style="color:#e6db74">"</span>
echo <span style="color:#e6db74">"2nd argument = </span>$2<span style="color:#e6db74">"</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell">Write-Host <span style="color:#e6db74">"Total arguments: </span>$($args.Length)<span style="color:#e6db74">"</span>
Write-Host <span style="color:#e6db74">"1st Argument: </span>$($args[0])<span style="color:#e6db74">"</span>
Write-Host <span style="color:#e6db74">"2nd Argument: </span>$($args[1])<span style="color:#e6db74">"</span>
</code></pre></div><h2 id="named-command-line-arguments">Named Command Line Arguments</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span><span style="color:#66d9ef">for</span> arg in <span style="color:#e6db74">"</span>$@<span style="color:#e6db74">"</span>
<span style="color:#66d9ef">do</span>
index<span style="color:#f92672">=</span><span style="color:#66d9ef">$(</span>echo $arg | cut -f1 -d<span style="color:#f92672">=</span><span style="color:#66d9ef">)</span>
val<span style="color:#f92672">=</span><span style="color:#66d9ef">$(</span>echo $arg | cut -f2 -d<span style="color:#f92672">=</span><span style="color:#66d9ef">)</span>
<span style="color:#66d9ef">case</span> $index in
X<span style="color:#f92672">)</span> x<span style="color:#f92672">=</span>$val;;

Y<span style="color:#f92672">)</span> y<span style="color:#f92672">=</span>$val;;

*<span style="color:#f92672">)</span>
<span style="color:#66d9ef">esac</span>
<span style="color:#66d9ef">done</span>
<span style="color:#f92672">((</span>result<span style="color:#f92672">=</span>x+y<span style="color:#f92672">))</span>
echo <span style="color:#e6db74">"X+Y=</span>$result<span style="color:#e6db74">"</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
<span style="color:#66d9ef">param</span>(<span style="color:#66d9ef">[int]</span>$X, <span style="color:#66d9ef">[int]</span>$Y)

$Result = $X + $Y
Write-Host <span style="color:#e6db74">"X+Y=$Result"</span>
</code></pre></div><h2 id="concatenating-strings">Concatenating Strings</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>
string1<span style="color:#f92672">=</span><span style="color:#e6db74">"Linux"</span>
string2<span style="color:#f92672">=</span><span style="color:#e6db74">"Hint"</span>
echo <span style="color:#e6db74">"</span>$string1$string2<span style="color:#e6db74">"</span>
string3<span style="color:#f92672">=</span>$string1+$string2
string3<span style="color:#f92672">+=</span><span style="color:#e6db74">" is a good tutorial blog site"</span>
echo $string3
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
$string1 = <span style="color:#e6db74">"Ironman"</span>
$string2 = <span style="color:#e6db74">"Software"</span>
Write-Host <span style="color:#e6db74">"$string1 $string2"</span>
$string3 = $string1+$string2
$string3 +=<span style="color:#e6db74">" makes good software"</span>
Write-Host $string3
</code></pre></div><h2 id="substring-of-a-string">Substring of a String</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>Str<span style="color:#f92672">=</span><span style="color:#e6db74">"Learn Linux from LinuxHint"</span>
subStr<span style="color:#f92672">=</span><span style="color:#e6db74">${</span>Str:6:5<span style="color:#e6db74">}</span>
echo $subStr
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
$Str = <span style="color:#e6db74">'Learn PowerShell from Ironman Software'</span>
$subStr = $Str.Substring(6, 10)
Write-Host $subStr
</code></pre></div><h2 id="functions">Functions</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span><span style="color:#66d9ef">function</span> F1<span style="color:#f92672">()</span>
<span style="color:#f92672">{</span>
echo <span style="color:#e6db74">'I like bash programming'</span>
<span style="color:#f92672">}</span>

F1
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
<span style="color:#66d9ef">function</span> F1 {
    Write-Host <span style="color:#e6db74">"I like PowerShell programming"</span>
}
F1
</code></pre></div><h2 id="functions-with-parameters">Functions with Parameters</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>
Rectangle_Area<span style="color:#f92672">()</span> <span style="color:#f92672">{</span>
area<span style="color:#f92672">=</span><span style="color:#66d9ef">$((</span>$1 <span style="color:#f92672">*</span> $2<span style="color:#66d9ef">))</span>
echo <span style="color:#e6db74">"Area is : </span>$area<span style="color:#e6db74">"</span>
<span style="color:#f92672">}</span>

Rectangle_Area <span style="color:#ae81ff">10</span> <span style="color:#ae81ff">20</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
<span style="color:#66d9ef">function</span> RectangleArea {
    $Area = $Args[0] * $Args[1]
    Write-Host <span style="color:#e6db74">"Area is: $Area"</span>
}
RectangleArea 10 20
</code></pre></div><h2 id="use-the-return-value-of-a-function">Use the Return value of a Function</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span><span style="color:#66d9ef">function</span> greeting<span style="color:#f92672">()</span> <span style="color:#f92672">{</span>

str<span style="color:#f92672">=</span><span style="color:#e6db74">"Hello, </span>$name<span style="color:#e6db74">"</span>
echo $str

<span style="color:#f92672">}</span>

echo <span style="color:#e6db74">"Enter your name"</span>
read name

val<span style="color:#f92672">=</span><span style="color:#66d9ef">$(</span>greeting<span style="color:#66d9ef">)</span>
echo <span style="color:#e6db74">"Return value of the function is </span>$val<span style="color:#e6db74">"</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
<span style="color:#66d9ef">function</span> Greeting {
    <span style="color:#e6db74">"Hello, $Name"</span>
}

$Name = Read-Host <span style="color:#e6db74">"Enter your name"</span>
$Val = Greeting
Write-Host <span style="color:#e6db74">"Return value of the function is $val"</span>
</code></pre></div><h2 id="make-a-directory">Make a Directory</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>echo <span style="color:#e6db74">"Enter directory name"</span>
read newdir
<span style="color:#e6db74">`</span>mkdir $newdir<span style="color:#e6db74">`</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
$newdir = Read-Host <span style="color:#e6db74">"Enter directory name"</span>
New-Item $newdir -ItemType Directory
<span style="color:#75715e"># mkdir also works</span>
mkdir $newdir
</code></pre></div><h2 id="make-directory-if-it-doesnt-exist">Make Directory if it doesn’t exist</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>echo <span style="color:#e6db74">"Enter directory name"</span>
read ndir
<span style="color:#66d9ef">if</span> <span style="color:#f92672">[</span> -d <span style="color:#e6db74">"</span>$ndir<span style="color:#e6db74">"</span> <span style="color:#f92672">]</span>
<span style="color:#66d9ef">then</span>
echo <span style="color:#e6db74">"Directory exist"</span>
<span style="color:#66d9ef">else</span>
<span style="color:#e6db74">`</span>mkdir $ndir<span style="color:#e6db74">`</span>
echo <span style="color:#e6db74">"Directory created"</span>
<span style="color:#66d9ef">fi</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
$newdir = Read-Host <span style="color:#e6db74">"Enter directory name"</span>
<span style="color:#66d9ef">if</span> (Test-Path $newdir)
{
    Write-Host <span style="color:#e6db74">"Directory exists"</span>
} <span style="color:#66d9ef">else</span> {
    New-Item $newdir -ItemType Directory
}

<span style="color:#75715e"># shorter syntax</span>
$newdir = Read-Host <span style="color:#e6db74">"Enter directory name"</span>
<span style="color:#66d9ef">if</span> (gi $newdir -ea si)
{
    echo <span style="color:#e6db74">"Directory exists"</span>
} <span style="color:#66d9ef">else</span> {
    mkdir $newdir
}
</code></pre></div><h2 id="read-a-file">Read a File</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>file<span style="color:#f92672">=</span><span style="color:#e6db74">'book.txt'</span>
<span style="color:#66d9ef">while</span> read line; <span style="color:#66d9ef">do</span>
echo $line
<span style="color:#66d9ef">done</span> &lt; $file
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
Get-Content <span style="color:#e6db74">'book.txt'</span>
</code></pre></div><h2 id="delete-a-file">Delete a File</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>echo <span style="color:#e6db74">"Enter filename to remove"</span>
read fn
rm -i $fn
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
$fn = Read-Host <span style="color:#e6db74">"Enter a file to remove"</span>
Remove-Item $fn

<span style="color:#75715e"># Shorter syntax</span>
$fn = Read-Host <span style="color:#e6db74">"Enter a file to remove"</span>
rm $fn
</code></pre></div><h2 id="append-to-a-file">Append to a File</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>
echo <span style="color:#e6db74">"Before appending the file"</span>
cat book.txt

echo <span style="color:#e6db74">"Learning Laravel 5"</span>&gt;&gt; book.txt
echo <span style="color:#e6db74">"After appending the file"</span>
cat book.txt
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
Write-Host <span style="color:#e6db74">"Before appending the file"</span>
Get-Content book.txt

<span style="color:#e6db74">"Learning Laravel 5"</span> &gt;&gt; book.txt
Write-Host <span style="color:#e6db74">"After appending the file"</span>
Get-Content book.txt
</code></pre></div><h2 id="wait-for-a-process">Wait for a Process</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>echo <span style="color:#e6db74">"Wait command"</span> &amp;
process_id<span style="color:#f92672">=</span>$!
wait $process_id
echo <span style="color:#e6db74">"Exited with status </span>$?<span style="color:#e6db74">"</span>
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
Start-Process notepad -Wait
Get-Process -Id $ProcessId | Wait-Process
</code></pre></div><h2 id="sleep">Sleep</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e">#!/bin/bash
</span><span style="color:#75715e"></span>
echo “Wait <span style="color:#66d9ef">for</span> <span style="color:#ae81ff">5</span> seconds”
sleep <span style="color:#ae81ff">5</span>
echo “Completed”
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e">#!/usr/bin/env pwsh</span>
Write-Host <span style="color:#e6db74">"Wait for 5 seconds"</span>
Start-Sleep 5 
<span style="color:#75715e">#shorter syntax</span>
sleep 5
Write-Host <span style="color:#e6db74">"Completed"</span>
</code></pre></div><h2 id="download-files">Download Files</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash">curl -o newname.txt http://www.het.brown.edu/guide/UNIX-password-security.txt
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell">Invoke-WebRequest http<span style="color:#960050;background-color:#1e0010">:</span>//www.het.brown.edu/guide/UNIX-password-security.txt -OutFile .\newname.txt
<span style="color:#75715e"># shorter syntax</span>
iwr http<span style="color:#960050;background-color:#1e0010">:</span>//www.het.brown.edu/guide/UNIX-password-security.txt -o newname.txt
</code></pre></div><h2 id="search-a-file-for-a-string">Search a File for a String</h2>
<p><strong>Bash</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-bash" data-lang="bash"><span style="color:#75715e"># Search a file</span>
grep error log.txt

<span style="color:#75715e"># Search a directory</span>
grep error *

<span style="color:#75715e"># Recursively search a directory</span>
grep -r error *

<span style="color:#75715e"># List matching files</span>
grep -l error *

<span style="color:#75715e"># Measure number of objects</span>
grep -c error *

<span style="color:#75715e"># Display lines before and after</span>
grep -C <span style="color:#ae81ff">2</span> error *
</code></pre></div><p><strong>PowerShell</strong></p>
<div class="highlight"><pre tabindex="0" style="color:#f8f8f2;background-color:#272822;-moz-tab-size:4;-o-tab-size:4;tab-size:4"><code class="language-powershell" data-lang="powershell"><span style="color:#75715e"># Search a file</span>
Select-String error log.txt

<span style="color:#75715e"># Search a Directory</span>
Select-String error *

<span style="color:#75715e"># Recursively search a directory</span>
Get-ChildItem * -Recurse | Select-String error

<span style="color:#75715e"># List matching files</span>
Select-String error * | Select-Object path

<span style="color:#75715e"># Count Matches</span>
Select-String error * | Measure-Object

<span style="color:#75715e"># Display lines before and after</span>
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
<span class="resp-sharing-button resp-sharing-button--facebook resp-sharing-button--small">
<span aria-hidden="true" class="resp-sharing-button__icon resp-sharing-button__icon--solid"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:32px"><path d="M18.77 7.46H14.5v-1.9c0-.9.6-1.1 1-1.1h3V.5h-4.33C10.24.5 9.5 3.44 9.5 5.32v2.15h-3v4h3v12h5v-12h3.85l.42-4z"></path></svg>
</span>
</span>
</a>
<a class="resp-sharing-button__link" href="https://twitter.com/intent/tweet/?hashtags=dailypowershell,powershell&amp;text=Bash%20vs%20PowerShell%20Cheat%20Sheet&amp;url=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f" target="_blank" rel="noopener" aria-label="">
<span class="resp-sharing-button resp-sharing-button--twitter resp-sharing-button--small">
<span aria-hidden="true" class="resp-sharing-button__icon resp-sharing-button__icon--solid"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:32px"><path d="M23.44 4.83c-.8.37-1.5.38-2.22.02.93-.56.98-.96 1.32-2.02-.88.52-1.86.9-2.9 1.1-.82-.88-2-1.43-3.3-1.43-2.5.0-4.55 2.04-4.55 4.54.0.36.03.7.1 1.04-3.77-.2-7.12-2-9.36-4.75-.4.67-.6 1.45-.6 2.3.0 1.56.8 2.95 2 3.77-.74-.03-1.44-.23-2.05-.57v.06c0 2.2 1.56 4.03 3.64 4.44-.67.2-1.37.2-2.06.08.58 1.8 2.26 3.12 4.25 3.16C5.78 18.1 3.37 18.74 1 18.46c2 1.3 4.4 2.04 6.97 2.04 8.35.0 12.92-6.92 12.92-12.93.0-.2.0-.4-.02-.6.9-.63 1.96-1.22 2.56-2.14z"></path></svg>
</span>
</span>
</a>
<a class="resp-sharing-button__link" href="mailto:?subject=Bash%20vs%20PowerShell%20Cheat%20Sheet&amp;body=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f" target="_self" rel="noopener" aria-label="">
<span class="resp-sharing-button resp-sharing-button--email resp-sharing-button--small">
<span aria-hidden="true" class="resp-sharing-button__icon resp-sharing-button__icon--solid"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:32px"><path d="M22 4H2C.9 4 0 4.9.0 6v12c0 1.1.9 2 2 2h20c1.1.0 2-.9 2-2V6c0-1.1-.9-2-2-2zM7.25 14.43l-3.5 2c-.08.05-.17.07-.25.07-.17.0-.34-.1-.43-.25-.14-.24-.06-.55.18-.68l3.5-2c.24-.14.55-.06.68.18.14.24.06.55-.18.68zm4.75.07c-.1.0-.2-.03-.27-.08l-8.5-5.5c-.23-.15-.3-.46-.15-.7.15-.22.46-.3.7-.14L12 13.4l8.23-5.32c.23-.15.54-.08.7.15.14.23.07.54-.16.7l-8.5 5.5c-.08.04-.17.07-.27.07zm8.93 1.75c-.1.16-.26.25-.43.25-.08.0-.17-.02-.25-.07l-3.5-2c-.24-.13-.32-.44-.18-.68s.44-.32.68-.18l3.5 2c.24.13.32.44.18.68z"></path></svg>
</span>
</span>
</a>
<a class="resp-sharing-button__link" href="https://www.linkedin.com/shareArticle?mini=true&amp;url=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f&amp;title=Bash%20vs%20PowerShell%20Cheat%20Sheet&amp;source=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f" target="_blank" rel="noopener" aria-label="">
<span class="resp-sharing-button resp-sharing-button--linkedin resp-sharing-button--small">
<span aria-hidden="true" class="resp-sharing-button__icon resp-sharing-button__icon--solid"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:32px"><path d="M6.5 21.5h-5v-13h5v13zM4 6.5C2.5 6.5 1.5 5.3 1.5 4s1-2.4 2.5-2.4c1.6.0 2.5 1 2.6 2.5.0 1.4-1 2.5-2.6 2.5zm11.5 6c-1 0-2 1-2 2v7h-5v-13h5V10s1.6-1.5 4-1.5c3 0 5 2.2 5 6.3v6.7h-5v-7c0-1-1-2-2-2z"></path></svg>
</span>
</span>
</a>
<a class="resp-sharing-button__link" href="https://reddit.com/submit/?url=https%3a%2f%2fblog.ironmansoftware.com%2fdaily-powershell%2fbash-powershell-cheatsheet%2f&amp;resubmit=true&amp;title=Bash%20vs%20PowerShell%20Cheat%20Sheet" target="_blank" rel="noopener" aria-label="">
<span class="resp-sharing-button resp-sharing-button--reddit resp-sharing-button--small">
<span aria-hidden="true" class="resp-sharing-button__icon resp-sharing-button__icon--solid"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" style="height:32px"><path d="M24 11.5c0-1.65-1.35-3-3-3-.96.0-1.86.48-2.42 1.24-1.64-1-3.75-1.64-6.07-1.72.08-1.1.4-3.05 1.52-3.7.72-.4 1.73-.24 3 .5C17.2 6.3 18.46 7.5 20 7.5c1.65.0 3-1.35 3-3s-1.35-3-3-3c-1.38.0-2.54.94-2.88 2.22-1.43-.72-2.64-.8-3.6-.25-1.64.94-1.95 3.47-2 4.55-2.33.08-4.45.7-6.1 1.72C4.86 8.98 3.96 8.5 3 8.5c-1.65.0-3 1.35-3 3 0 1.32.84 2.44 2.05 2.84-.03.22-.05.44-.05.66.0 3.86 4.5 7 10 7s10-3.14 10-7c0-.22-.02-.44-.05-.66 1.2-.4 2.05-1.54 2.05-2.84zM2.3 13.37C1.5 13.07 1 12.35 1 11.5c0-1.1.9-2 2-2 .64.0 1.22.32 1.6.82-1.1.85-1.92 1.9-2.3 3.05zm3.7.13c0-1.1.9-2 2-2s2 .9 2 2-.9 2-2 2-2-.9-2-2zm9.8 4.8c-1.08.63-2.42.96-3.8.96-1.4.0-2.74-.34-3.8-.95-.24-.13-.32-.44-.2-.68.15-.24.46-.32.7-.18 1.83 1.06 4.76 1.06 6.6.0.23-.13.53-.05.67.2.14.23.06.54-.18.67zm.2-2.8c-1.1.0-2-.9-2-2s.9-2 2-2 2 .9 2 2-.9 2-2 2zm5.7-2.13c-.38-1.16-1.2-2.2-2.3-3.05.38-.5.97-.82 1.6-.82 1.1.0 2 .9 2 2 0 .84-.53 1.57-1.3 1.87z"></path></svg>
</span>
</span>
</a>
</p>
</div>
<hr>
</div>