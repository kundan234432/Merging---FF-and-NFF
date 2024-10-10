# Practical No. 8: No Fast-Forward Merge

## Types of Merge:
1. **FF (Fast Forward)**: The feature branch is simply advanced to point to the same commit as the main branch. No merge commit is created.
2. **NFF (No Fast Forward)**: A merge commit is created to preserve the history, even when a fast-forward merge is possible.

---

## Scenario (No Fast-Forward Merge Concept)

### Problem Statement: 
You are working on a feature in the feature-branch, while your colleague has made significant updates to the main branch. You want to merge the changes from the main branch into your feature branch without using fast-forward, ensuring the commit history is preserved clearly with a merge commit. After merging, you encounter a push rejection due to conflicts with someone else’s recent push.

### Question:
1. How can you merge the main branch into the feature branch without fast-forwarding, ensuring the commit history shows the merge?

---

### Solution:

#### Step-by-Step Commands:
1. Create a file and make a commit in the main branch:
   ```bash
   $ cat >> ff1.txt
   this is one line
   $ git add .
   $ git commit -am "First commit"
   ```

2. Create and switch to the feature branch (`ff1`):
   ```bash
   $ git checkout -b ff1
   ```

3. Make changes in the feature branch and commit:
   ```bash
   $ cat >> ff1.txt
   this is second line
   $ git add .
   $ git commit -am "Second Commit"
   ```

4. Switch back to the `master` branch:
   ```bash
   $ git checkout master
   ```

5. Merge the feature branch into `master` **without fast-forward**:
   ```bash
   $ git merge --no-ff ff1
   ```

   This ensures that a merge commit is created.

6. View the commit history to verify the merge:
   ```bash
   $ git log --oneline --decorate --graph --all
   ```

7. Push the changes to the remote repository:
   ```bash
   $ git remote add origin https://github.com/kundan234432/Merging---FF-and-NFF.git
   $ git branch -M main
   $ git push -u origin main
   ```

   If you encounter a rejection due to conflicts, resolve the conflicts locally, then:
   ```bash
   $ git add .
   $ git commit
   $ git push
   ```

---

This file now provides a clear overview of the task, with well-formatted commands and explanations. Would you like any more edits or additions?
