---
example: Delete binary from history
command: git clone git@github.com:Yetenol/⟨repository⟩.git
---

Git is a software for tracking changes in any set of files.
It works best for non-binary text files

## Manage multiple repositories

- **find** all child repositories
    ```powershell
    Get-ChildItem -Path "." -Directory -Recurse | 
    foreach { $_.FullName } | foreach {
        if (Test-Path -Path "$_\.git") {
            Write-Output $_
        }
    }
    ```
- **pull** all child repositories
    ```powershell
    Get-ChildItem -Path "." -Directory -Recurse | 
    foreach { $_.FullName } | foreach {
        if (Test-Path -Path "$_\.git") {
            Write-Host "$_`t" -f Cyan -NoNewline
            git -C $_ pull
        }
    }
    ```

## Upload feature

- `rebase`: review all feature commits 
  - `reword`: rename commits
  - `fixup`: combine commits into a single one
- `push`: upload current branch to remote
- `push`: integrate current branch into remote's main branch
- `fetch`: download remote branches
```powershell
$currentBranch = (git branch --show-current).trim()
$mainBranch = (git symbolic-ref --short refs/remotes/origin/HEAD).replace("origin/","").trim()
git rebase --interactive origin/$mainBranch
if ($LASTEXITCODE -ne 0) {
    git rebase --abort
} else {
    git push origin $currentBranch":"$mainBranch
    git pull origin $mainBranch":"$mainBranch
}
```
In case main changed and changes have to be merged, do so and run
```powershell
git rebase --continue
git push origin $currentBranch":"$mainBranch
git pull origin $mainBranch":"$mainBranch
```

## Branch handling

- **squash** multiple commits into one before pushing
    ```powershell
    git rebase --interactive origin/HEAD
    ```
    
- **push** my branch to remote's **main** branch    
    see [git publish script](https://github.com/Yetenol/alias/blob/main/git-publish.ps1)
    ```powershell
    $currentBranch = (git branch --show-current).trim()
    $mainBranch = (git symbolic-ref --short refs/remotes/origin/HEAD).replace("origin/","").trim()
    git rebase --interactive origin/$mainBranch
    git push origin $currentBranch":"$mainBranch
    git pull origin $mainBranch":"$mainBranch
    ```
    ```powershell
    git push origin current:main
    git fetch origin main:main
    ```
    > Dirty one-liner:  
    > `git push origin $($(git branch --show-current).trim()+":"+(git symbolic-ref --short refs/remotes/origin/HEAD).replace("origin/",""))`


## Remove binaries from history
> **Shrinks** the **repository size** by excluding files or folders from the commit history.  
> **Rewrites** all **effected** commits and their children to erase a folder/file from their changes.  
> Avoid when collaborating, as it rewrites many commits.  
- exclude a **file**
    ```bash
    git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch \"PATH/TO_ITEM\"' --prune-empty --tag-name-filter cat -- --all
    ```
- exclude a **folder** and its content
    ```bash
    git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch -r \"PATH/TO_ITEM\"' --prune-empty --tag-name-filter cat -- --all
    ```

# Useful commands

- **Amend all changes** to previous commit
	```bash
	alias gitamend='git commit --amend --no-edit'
	``` 

- Show git graph  
    ```
    git log --graph \
    	--abbrev-commit \
    	--pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset'
    ```


# Alias

- alias **internal command**  
	```bash
	git config --global alias.<shortcut> <command>
	```
	and call it using `git amend`

- alias **external command**    
	```shell
	git config --global alias.sourcetree '!/executable'
	```


---
Sources:
- 2022-12-14: [Creating Git shortcuts](https://blog.frankel.ch/creating-git-shortcuts/)

Related:

Tags:
[Languages and Encodings](../notes/Languages%20and%20Encodings.md)