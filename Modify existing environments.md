---
dg-publish: false
example: add environment specific commands
command: \usepackage{etoolbox}
---

# Extend an existing environment 

```latex
\usepackage{etoolbox} % Append methods to environments
```

# Private environment methods

1. Declare a public global placeholder method

    ```latex
    %%%%%%%%%%%%%%%%%%%% DECLARE INTERFACE FUNCTIONS: %%%%%%%%%%%%%%%%%%%%
    \newcommand\@set⟨attribute name⟩{}
    ```
    
    - `⟨attribute name⟩`: Name of the attribute to be  set

2. Create handles to the environment to be overwritten in order to access it later on

    ```latex
    \let\@old⟨environment name⟩\⟨environment name⟩
    \let\@endold⟨environment name⟩\end⟨environment name⟩
    ```
    
    - `⟨environment name⟩`: Environment that is extended

3. Create an environment specific macro
    
    ```latex
    \renewenvironment{⟨environment name⟩}
    {
        \old⟨environment name⟩ % begin{⟨environment name⟩}
    
        % Define setter method \set⟨attribute name⟩{⟨value⟩}
        % - only accessible inside the environment (aka method)
        \renewcommand\@set⟨attribute name⟩[1]
        {
            \def\@⟨attribute name⟩{##1}
        }
        \global\let\set⟨attribute name⟩\@set⟨attribute name⟩
    }
    {
        \endold⟨environment name⟩ % end{⟨environment name⟩}
    }
    ```

    - `⟨attribute name⟩`: Name of the attribute to be  set
    - `⟨environment name⟩`: Environment that is extended


---


Sources:

Related:

Tags:
[Develop LaTeX packages](Develop%20LaTeX%20packages.md)