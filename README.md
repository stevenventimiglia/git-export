# Git Export
Bash script for exporting all files included within a series of commits, retaining the directory structure.
## Directions
Verify/Checkout the relative branch:
```
git status
git checkout [branch_name]
```
View your log, copy down the two Commit IDs you'd like to export files from:
```
git log
```
Run the script, by placing your two Commit IDs at the end of the command:
```
source .exportCommits [commit-id_001] [commit-id_002]
```
## Results
1. A directory named `./_exports/` will be created, if it doesn't already exist.
2. A sub-directory (ex. `./_exports/0000-00-00_00:00:00`) will be created to store your exported files.
3. A temporary list of files is created, using `git diff`.
4. File paths are recreated within the defined sub-directory, if they don't already exist.
5. Each file is copied to its relative directory within the defined sub-directory.
6. If files or directories no longer exist between new and old commits, they are listed during the process.
7. The temporary list of files is deleted (`./exportFileList.TMP`).
8. The path in which your exported files and directories are located is printed to the screen.