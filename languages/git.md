# [⌂](../README.md) ([#](../README.md#languages)) › [**Git**](../README.md#languages)

- software for tracking changes in any set of files
- works best for non-binary text files

## Git remove folder from commit history
- _rewrite all effected commits to erase a folder/file from their changes_
- significatly decreases the repo size
- large folders/files with resources or binaries shouldn't be in the repo
- non recommended for collaboration as it rewrites many commits
- replace `PATH/TO_ITEM` with the folder/file path e.g: `resources/setup.zip`
- remove file
    ```
    git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch \"PATH/TO_ITEM\"' --prune-empty --tag-name-filter cat -- --all
    ```
- recursively remove folder
    ```
    git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch -r \"PATH/TO_ITEM\"' --prune-empty --tag-name-filter cat -- --all
    ```