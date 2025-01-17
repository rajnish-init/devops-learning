# Error Handling in Git

## Common Errors and How I Fixed Them

### 1. Commit Amendment
**Error:** Forgot to add some files before committing.  
**Solution:** Used the following steps:
- Edited the file to make the necessary changes.
- Staged the changes with `git add <file>`.
- Amended the last commit with `git commit --amend`.

### 2. Pushed Wrong Commit
**Error:** Accidentally pushed an incorrect commit to the remote branch.  
**Solution:** 
- Corrected the issue locally.
- Amended the commit with `git commit --amend`.
- Force-pushed the changes using `git push --force`.

### 3. Merge Conflicts
**Error:** Encountered conflicts while merging branches.  
**Solution:**
- Resolved conflicts by editing the conflicting files.
- Marked the conflicts as resolved with `git add <file>`.
- Completed the merge with `git commit`.

---
**Note:** Always review changes carefully before pushing them to avoid unnecessary errors.
