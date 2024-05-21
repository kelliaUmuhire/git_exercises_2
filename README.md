## Part 1

### Exercise 1

```bash
git_exercises_2> git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

nothing added to commit but untracked files present (use "git add" to track)
git_exercises_2> git add test4.md
git_exercises_2> git commit --amend -m "chore: Create third and fourth files"
[main 26f3740] chore: Create third and fourth files
 Date: Mon May 20 19:23:35 2024 +0200
 create mode 100644 test3.md
 create mode 100644 test4.md
```

### Exercise 2

```bash
git_exercises_2> git rebase -i HEAD~2
git_exercises_2> git commit --amend -m "chore: Create second file"
[detached HEAD be28b31] chore: Create second file
 Date: Mon May 20 19:23:25 2024 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
 git_exercises_2> git rebase --continue
 Successfully rebased and updated refs/heads/main.
```

### Exercise 3

```bash
git_exercises_2> git rebase -i --root
```

### Exercise 4

```bash
git_exercises_2> git rebase -i HEAD~3
git_exercises_2> git reset HEAD~
git_exercises_2> git add .\test3.md
git_exercises_2> git commit -m "chore: Create third file"
git_exercises_2> git add .\test4.md
git_exercises_2> git commit -m "chore: Create fourth file"
git_exercises_2> git rebase --continue
```

### Exercise 5

```bash
git_exercises_2> git rebase -i HEAD~3
```

### Exercise 6

```bash
git_exercises_2> git add .\unwanted.txt
git_exercises_2> git commit -m "Unwanted commit"
[main 0c5e030] Unwanted commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 unwanted.txt
git_exercises_2> git rebase -i
Successfully rebased and updated refs/heads/main.
```

### Exercise 7

```bash
git_exercises_2> git rebase -i
Successfully rebased and updated refs/heads/main.
```

### Exercise 8

```bash
git_exercises_2> git checkout -b ft/branch
git_exercises_2> git add .\test5.md
git_exercises_2> git commit -m 'chore: Implemented test 5'
[ft/branch 17c1dd2] chore: Implemented test 5
 1 file changed, 1 insertion(+)
git_exercises_2> git checkout ft/branch
git_exercises_2> git log --oneline
17c1dd2 (HEAD -> ft/branch) chore: Implemented test 5
94cb2ff (main) chore: Create second file
83e7085 chore: Create third and fourth files
git_exercises_2> git checkout main
Your branch and 'origin/main' have diverged,
and have 2 and 2 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)
git_exercises_2> git cherry-pick 17c1dd2
[main 1c43a49] chore: Implemented test 5
 Date: Tue May 21 10:38:07 2024 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md
```

### Exercise 9

```bash
git_exercises_2> git log --graph
* commit 1c43a49917d88ceaec8a29207db5dc8e66288d03 (HEAD -> main)
| Author: kelliaUmuhire <kellumuhire@gmail.com>
| Date:   Tue May 21 10:38:07 2024 +0200
|
|     chore: Implemented test 5
|
* commit 94cb2ff8f6b9aa67d2de34a35257c0ae902b05a4
| Author: kelliaUmuhire <kellumuhire@gmail.com>
| Date:   Mon May 20 19:23:25 2024 +0200
......
```

### Exercise 10

```bash
git_exercises_2> git reflog
1c43a49 (HEAD -> main) HEAD@{0}: cherry-pick: chore: Implemented test 5
94cb2ff HEAD@{1}: checkout: moving from ft/branch to main
17c1dd2 (ft/branch) HEAD@{2}: checkout: moving from main to ft/branch
....
```
