109-1@109-1-36 MINGW64 /c/2025-git
$ $ git config --global user.name sdg331
bash: $: command not found

109-1@109-1-36 MINGW64 /c/2025-git
$ git config --global user.name "sdg331"

109-1@109-1-36 MINGW64 /c/2025-git
$ git config --global email sdg331@dongyang.ac.kr
error: key does not contain a section: email

109-1@109-1-36 MINGW64 /c/2025-git
$ git config --global user.email sdg331@dongyang.ac.kr

109-1@109-1-36 MINGW64 /c/2025-git
$ git config --global core.autocrlf true

109-1@109-1-36 MINGW64 /c/2025-git
$ git config --global core.safecrlf false

109-1@109-1-36 MINGW64 /c/2025-git
$ git config --global core.editor 'code --wait'

109-1@109-1-36 MINGW64 /c/2025-git
$ git config --global init.defaultBranch main

109-1@109-1-36 MINGW64 /c/2025-git
$ git init stash-repo
Initialized empty Git repository in C:/2025-git/stash-repo/.git/

109-1@109-1-36 MINGW64 /c/2025-git
$ cd stash-repo

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ echo A > f

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git add f

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git comit -m
git: 'comit' is not a git command. See 'git --help'.

The most similar command is
        commit

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git commmit -m
git: 'commmit' is not a git command. See 'git --help'.

The most similar command is
        commit

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git commit -m first
[main (root-commit) 9627919] first
 1 file changed, 1 insertion(+)
 create mode 100644 f

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git log --oneline
9627919 (HEAD -> main) first

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff -staged
error: invalid option: -staged
usage: git diff [<options>] [<commit>] [--] [<path>...]
   or: git diff [<options>] --cached [--merge-base] [<commit>] [--] [<path>...]
   or: git diff [<options>] [--merge-base] <commit> [<commit>...] <commit> [--] [<path>...]
   or: git diff [<options>] <commit>...<commit> [--] [<path>...]
   or: git diff [<options>] <blob> <blob>
   or: git diff [<options>] --no-index [--] <path> <path>

common diff options:
  -z            output diff-raw with lines terminated with NUL.
  -p            output patch format.
  -u            synonym for -p.
  --patch-with-raw
                output both a patch and the diff-raw format.
  --stat        show diffstat instead of patch.
  --numstat     show numeric diffstat instead of patch.
  --patch-with-stat
                output a patch and prepend its diffstat.
  --name-only   show only names of changed files.
  --name-status show names and status of changed files.
  --full-index  show full object name on index lines.
  --abbrev=<n>  abbreviate object names in diff-tree header and diff-raw.
  -R            swap input file pairs.
  -B            detect complete rewrites.
  -M            detect renames.
  -C            detect copies.
  --find-copies-harder
                try unchanged files as candidate for copy detection.
  -l<n>         limit rename attempts up to <n> paths.
  -O<file>      reorder diffs according to the <file>.
  -S<string>    find filepair whose only one side contains the string.
  --pickaxe-all
                show all files diff when -S is used and hit is found.
  -a  --text    treat all files as text.


109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff --staged

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff HEAD

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ ehco B >> f
bash: ehco: command not found

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ echo B >> f

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git commit -am second second
fatal: paths 'second ...' with -a does not make sense

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git commit -am second
[main 1e852d3] second
 1 file changed, 1 insertion(+)

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git log --oneline
1e852d3 (HEAD -> main) second
9627919 first

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff HEAD

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff --staged

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ echo c >> f

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff
diff --git a/f b/f
index 35d242b..4484d91 100644
--- a/f
+++ b/f
@@ -1,2 +1,3 @@
 A
 B
+c

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff -staged
error: invalid option: -staged
usage: git diff [<options>] [<commit>] [--] [<path>...]
   or: git diff [<options>] --cached [--merge-base] [<commit>] [--] [<path>...]
   or: git diff [<options>] [--merge-base] <commit> [<commit>...] <commit> [--] [<path>...]
   or: git diff [<options>] <commit>...<commit> [--] [<path>...]
   or: git diff [<options>] <blob> <blob>
   or: git diff [<options>] --no-index [--] <path> <path>

common diff options:
  -z            output diff-raw with lines terminated with NUL.
  -p            output patch format.
  -u            synonym for -p.
  --patch-with-raw
                output both a patch and the diff-raw format.
  --stat        show diffstat instead of patch.
  --numstat     show numeric diffstat instead of patch.
  --patch-with-stat
                output a patch and prepend its diffstat.
  --name-only   show only names of changed files.
  --name-status show names and status of changed files.
  --full-index  show full object name on index lines.
  --abbrev=<n>  abbreviate object names in diff-tree header and diff-raw.
  -R            swap input file pairs.
  -B            detect complete rewrites.
  -M            detect renames.
  -C            detect copies.
  --find-copies-harder
                try unchanged files as candidate for copy detection.
  -l<n>         limit rename attempts up to <n> paths.
  -O<file>      reorder diffs according to the <file>.
  -S<string>    find filepair whose only one side contains the string.
  --pickaxe-all
                show all files diff when -S is used and hit is found.
  -a  --text    treat all files as text.


109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff --staged

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git diff HEAD
diff --git a/f b/f
index 35d242b..4484d91 100644
--- a/f
+++ b/f
@@ -1,2 +1,3 @@
 A
 B
+c

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git stash
Saved working directory and index state WIP on main: 1e852d3 second

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git stash list
stash@{0}: WIP on main: 1e852d3 second

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git status
On branch main
nothing to commit, working tree clean

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git status -s

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git stash apply --index
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f

no changes added to commit (use "git add" and/or "git commit -a")

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git status apply --index
error: unknown option `index'
usage: git status [<options>] [--] [<pathspec>...]

    -v, --[no-]verbose    be verbose
    -s, --[no-]short      show status concisely
    -b, --[no-]branch     show branch information
    --[no-]show-stash     show stash information
    --[no-]ahead-behind   compute full ahead/behind values
    --[no-]porcelain[=<version>]
                          machine-readable output
    --[no-]long           show status in long format (default)
    -z, --[no-]null       terminate entries with NUL
    -u, --[no-]untracked-files[=<mode>]
                          show untracked files, optional modes: all, normal, no. (Default: all)
    --[no-]ignored[=<mode>]
                          show ignored files, optional modes: traditional, matching, no. (Default: traditional)
    --[no-]ignore-submodules[=<when>]
                          ignore changes to submodules, optional when: all, dirty, untracked. (Default: all)
    --[no-]column[=<style>]
                          list untracked files in columns
    --no-renames          do not detect renames
    --renames             opposite of --no-renames
    -M, --find-renames[=<n>]
                          detect renames, optionally set similarity index


109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git stash apply --index
error: Your local changes to the following files would be overwritten by merge:
        f
Please commit your changes or stash them before you merge.
Aborting
Index was not unstashed.
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f

no changes added to commit (use "git add" and/or "git commit -a")

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git status -v
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f

no changes added to commit (use "git add" and/or "git commit -a")

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git stash apply --index
error: Your local changes to the following files would be overwritten by merge:
        f
Please commit your changes or stash them before you merge.
Aborting
Index was not unstashed.
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f

no changes added to commit (use "git add" and/or "git commit -a")

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git status -s
 M f

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git add
Nothing specified, nothing added.
hint: Maybe you wanted to say 'git add .'?
hint: Disable this message with "git config set advice.addEmptyPathspec false"

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git stash apply --index
error: Your local changes to the following files would be overwritten by merge:
        f
Please commit your changes or stash them before you merge.
Aborting
Index was not unstashed.
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   f

no changes added to commit (use "git add" and/or "git commit -a")

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ git stash lsit
fatal: subcommand wasn't specified; 'push' can't be assumed due to unexpected token 'lsit'

109-1@109-1-36 MINGW64 /c/2025-git/stash-repo (main)
$ cd ..

109-1@109-1-36 MINGW64 /c/2025-git
$ git init reset -repo
error: unknown switch `r'
usage: git init [-q | --quiet] [--bare] [--template=<template-directory>]
                [--separate-git-dir <git-dir>] [--object-format=<format>]
                [--ref-format=<format>]
                [-b <branch-name> | --initial-branch=<branch-name>]
                [--shared[=<permissions>]] [<directory>]

    --[no-]template <template-directory>
                          directory from which templates will be used
    --[no-]bare           create a bare repository
    --shared[=<permissions>]
                          specify that the git repository is to be shared amongst several users
    -q, --[no-]quiet      be quiet
    --[no-]separate-git-dir <gitdir>
                          separate git dir from working tree
    -b, --[no-]initial-branch <name>
                          override the name of the initial branch
    --[no-]object-format <hash>
                          specify the hash algorithm to use
    --[no-]ref-format <format>
                          specify the reference format to use


109-1@109-1-36 MINGW64 /c/2025-git
$ git init reset -repo
error: unknown switch `r'
usage: git init [-q | --quiet] [--bare] [--template=<template-directory>]
                [--separate-git-dir <git-dir>] [--object-format=<format>]
                [--ref-format=<format>]
                [-b <branch-name> | --initial-branch=<branch-name>]
                [--shared[=<permissions>]] [<directory>]

    --[no-]template <template-directory>
                          directory from which templates will be used
    --[no-]bare           create a bare repository
    --shared[=<permissions>]
                          specify that the git repository is to be shared amongst several users
    -q, --[no-]quiet      be quiet
    --[no-]separate-git-dir <gitdir>
                          separate git dir from working tree
    -b, --[no-]initial-branch <name>
                          override the name of the initial branch
    --[no-]object-format <hash>
                          specify the hash algorithm to use
    --[no-]ref-format <format>
                          specify the reference format to use


109-1@109-1-36 MINGW64 /c/2025-git
$ git init reset-repo
Initialized empty Git repository in C:/2025-git/reset-repo/.git/

109-1@109-1-36 MINGW64 /c/2025-git
$ cd reset-repo

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ echo apple > ft

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git add ft

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git commit -m 'add apple'
[main (root-commit) 21f4365] add apple
 1 file changed, 1 insertion(+)
 create mode 100644 ft

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git log --oneline
21f4365 (HEAD -> main) add apple

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ echo banana >> ft

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git commit -am 'add banana'
[main 57c72cc] add banana
 1 file changed, 1 insertion(+)

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git log --oneline
57c72cc (HEAD -> main) add banana
21f4365 add apple

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git status
On branch main
nothing to commit, working tree clean

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git status -s

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git revert HEAD --no-edit
[main 2580149] Revert "add banana"
 Date: Mon Dec 1 11:19:26 2025 +0900
 1 file changed, 1 deletion(-)

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git log --oneline
2580149 (HEAD -> main) Revert "add banana"
57c72cc add banana
21f4365 add apple

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git status
On branch main
nothing to commit, working tree clean

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git log --oneline
2580149 (HEAD -> main) Revert "add banana"
57c72cc add banana
21f4365 add apple

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ cat ft
apple

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git diff

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git diff HEAD

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git revert HEAD --no-edit
[main d00b306] Reapply "add banana"
 Date: Mon Dec 1 11:21:21 2025 +0900
 1 file changed, 1 insertion(+)

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git log --oneline
21f4365 add apple

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ cat ft
apple

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git diff

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git diff HEAD

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git revert HEAD --no-edit
[main d00b306] Reapply "add banana"
 Date: Mon Dec 1 11:21:21 2025 +0900
 1 file changed, 1 insertion(+)

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git log --oneline
21f4365 add apple

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git config --global alias.lg1 'log --oneline'

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ git lg1
d00b306 (HEAD -> main) Reapply "add banana"
2580149 Revert "add banana"
57c72cc add banana
21f4365 add apple

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ cd..
bash: cd..: command not found

109-1@109-1-36 MINGW64 /c/2025-git/reset-repo (main)
$ cd ..

109-1@109-1-36 MINGW64 /c/2025-git
$ git init reset2-repo
Initialized empty Git repository in C:/2025-git/reset2-repo/.git/

109-1@109-1-36 MINGW64 /c/2025-git
$ cd reset2-repo

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ echo car > a.txt

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git add a.txt

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git commit -m A
[main (root-commit) 144b2bb] A
 1 file changed, 1 insertion(+)
 create mode 100644 a.txt

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ echo bike >> a.txt

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git commit -am B
[main f694d94] B
 1 file changed, 1 insertion(+)

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ echo ship >> a.txt

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git add a.txt

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ echo plain >> a.txt

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git diff
diff --git a/a.txt b/a.txt
index 36dd988..4340cbe 100644
--- a/a.txt
+++ b/a.txt
@@ -1,3 +1,4 @@
 car
 bike
 ship
+plain

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git diff --staged
diff --git a/a.txt b/a.txt
index 261f125..36dd988 100644
--- a/a.txt
+++ b/a.txt
@@ -1,2 +1,3 @@
 car
 bike
+ship

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git diff HEAD
diff --git a/a.txt b/a.txt
index 261f125..4340cbe 100644
--- a/a.txt
+++ b/a.txt
@@ -1,2 +1,4 @@
 car
 bike
+ship
+plain

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git lg1
f694d94 (HEAD -> main) B
144b2bb A

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git reset -hard
error: did you mean `--hard` (with two dashes)?

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git reset --hard
HEAD is now at f694d94 B

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git reset --hard HEAD~
HEAD is now at 144b2bb A

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git lg1
144b2bb (HEAD -> main) A

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ cat a.txt
car

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git diff --staged

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$ git diff HEAD

109-1@109-1-36 MINGW64 /c/2025-git/reset2-repo (main)
$
