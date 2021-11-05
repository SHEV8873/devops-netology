# Домашнее задание к занятию «2.3. Ветвления в Git»
## Задание №1 – Ветвление, merge и rebase.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git branch
  fix
* main

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch main
Your branch is up to date with 'github/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/
        ../

nothing added to commit but untracked files present (use "git add" to track)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git add merge.sh rebase.sh

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch main
Your branch is up to date with 'github/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   merge.sh
        new file:   rebase.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/


G:\DevOps\HW\netology-code\02-git-03-branching\branching>git commit -m "prepare for merge and rebase"
[main 44669f1] prepare for merge and rebase
 2 files changed, 16 insertions(+)
 create mode 100644 02-git-03-branching/branching/merge.sh
 create mode 100644 02-git-03-branching/branching/rebase.sh

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git switch -c git-merge
Switched to a new branch 'git-merge'

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git brabch
git: 'brabch' is not a git command. See 'git --help'.

The most similar command is
        branch

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git branch
  fix
* git-merge
  main

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-merge
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   merge.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/

no changes added to commit (use "git add" and/or "git commit -a")

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git add merge.sh

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-merge
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   merge.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/


G:\DevOps\HW\netology-code\02-git-03-branching\branching>git commit -m "merge: @ instead *"
[git-merge b785f1f] merge: @ instead *
 1 file changed, 2 insertions(+), 2 deletions(-)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-merge
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/

nothing added to commit but untracked files present (use "git add" to track)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git log --graph --all
* commit b785f1fd6db286f98a664ebeda0967fe8f46c393 (HEAD -> git-merge)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:28:17 2021 +0300
|
|     merge: @ instead *
|
* commit 44669f174fad8fb0ce496170af13364bd61e5e93 (main)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:24:41 2021 +0300
|
|     prepare for merge and rebase
|
* commit 7b2257e9e1c9b77dfca68d0a673d74985aa15a49 (gitlab/main, github/main, bitbucket/main)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:46:21 2021 +0300
|
|     add line to README.md
|
* commit cdac92bc169c86023334c0e3f6cf72ac7572127b
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:43:02 2021 +0300
|
|     add line to README.md
|
* commit 267e456541601afec872d6c7cf463dc63ce09851
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:36:38 2021 +0300
|
|     use IDE Py Charm
|
* commit 34f5a719b97aacfbbf73668504c00bbcb0aaa18f (tag: v0.1, tag: v0.0, origin/main, origin/HEAD)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Sat Oct 30 21:32:12 2021 +0300
|
|     Corrected Terraform/README
|
* commit 7373ae6ec62e48fe9efd5f59c6b254d9cf1ddb1c
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Sat Oct 30 20:57:27 2021 +0300
|
|     Moved and deleted
|
| * commit d1c55378570a7c26f741e4bbf5821493730b9c55 (gitlab/fix, github/fix, bitbucket/fix, fix)
|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
|   Date:   Tue Nov 2 23:25:00 2021 +0300
|
|       corrected README.md
|
* commit 5e6781cac3ef6d618611ef2653d657da3049a5b3
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Sat Oct 30 20:50:36 2021 +0300

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git push -u main
fatal: 'main' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git push -u github main
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 585 bytes | 292.00 KiB/s, done.
Total 5 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/SHEV8873/devops-netology.git
   7b2257e..44669f1  main -> main
Branch 'main' set up to track remote branch 'main' from 'github'.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git push -u github git-merge
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 440 bytes | 220.00 KiB/s, done.
Total 5 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
remote:
remote: Create a pull request for 'git-merge' on GitHub by visiting:
remote:      https://github.com/SHEV8873/devops-netology/pull/new/git-merge
remote:
To https://github.com/SHEV8873/devops-netology.git
 * [new branch]      git-merge -> git-merge
Branch 'git-merge' set up to track remote branch 'git-merge' from 'github'.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git ststus
git: 'ststus' is not a git command. See 'git --help'.

The most similar command is
        status

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-merge
Your branch is up to date with 'github/git-merge'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   merge.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/

no changes added to commit (use "git add" and/or "git commit -a")

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git add merge.sh

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-merge
Your branch is up to date with 'github/git-merge'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   merge.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/


G:\DevOps\HW\netology-code\02-git-03-branching\branching>git commit -m "merge: use shift"
[git-merge 804f5b2] merge: use shift
 1 file changed, 3 insertions(+), 2 deletions(-)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-merge
Your branch is ahead of 'github/git-merge' by 1 commit.
  (use "git push" to publish your local commits)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/

nothing added to commit but untracked files present (use "git add" to track)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git log --graph --all
* commit 804f5b2cce4cb589ec5873fed9fe775031d9eebf (HEAD -> git-merge)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:35:05 2021 +0300
|
|     merge: use shift
|
* commit b785f1fd6db286f98a664ebeda0967fe8f46c393 (github/git-merge)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:28:17 2021 +0300
|
|     merge: @ instead *
|
* commit 44669f174fad8fb0ce496170af13364bd61e5e93 (github/main, main)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:24:41 2021 +0300
|
|     prepare for merge and rebase
|
* commit 7b2257e9e1c9b77dfca68d0a673d74985aa15a49 (gitlab/main, bitbucket/main)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:46:21 2021 +0300
|
|     add line to README.md
|
* commit cdac92bc169c86023334c0e3f6cf72ac7572127b
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:43:02 2021 +0300
|
|     add line to README.md
|
* commit 267e456541601afec872d6c7cf463dc63ce09851
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:36:38 2021 +0300
|
|     use IDE Py Charm
|
* commit 34f5a719b97aacfbbf73668504c00bbcb0aaa18f (tag: v0.1, tag: v0.0, origin/main, origin/HEAD)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Sat Oct 30 21:32:12 2021 +0300
|
|     Corrected Terraform/README
|
* commit 7373ae6ec62e48fe9efd5f59c6b254d9cf1ddb1c
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Sat Oct 30 20:57:27 2021 +0300
|
|     Moved and deleted
|
| * commit d1c55378570a7c26f741e4bbf5821493730b9c55 (gitlab/fix, github/fix, bitbucket/fix, fix)
|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
|   Date:   Tue Nov 2 23:25:00 2021 +0300

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git push -u github git-merge
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 510 bytes | 255.00 KiB/s, done.
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/SHEV8873/devops-netology.git
   b785f1f..804f5b2  git-merge -> git-merge
Branch 'git-merge' set up to track remote branch 'git-merge' from 'github'.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git checkout main
Switched to branch 'main'
Your branch is up to date with 'github/main'.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch main
Your branch is up to date with 'github/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   rebase.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/

no changes added to commit (use "git add" and/or "git commit -a")

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git add rebase.sh

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch main
Your branch is up to date with 'github/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   rebase.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/


G:\DevOps\HW\netology-code\02-git-03-branching\branching>git connit -m "changed rebase.sh to main"
git: 'connit' is not a git command. See 'git --help'.

The most similar commands are
        commit
        config

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git commit -m "changed rebase.sh to main"
[main 352ab2b] changed rebase.sh to main
 1 file changed, 5 insertions(+), 3 deletions(-)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git push -u github main
Enumerating objects: 9, done.
Counting objects: 100% (9/9), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 452 bytes | 452.00 KiB/s, done.
Total 5 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/SHEV8873/devops-netology.git
   44669f1..352ab2b  main -> main
Branch 'main' set up to track remote branch 'main' from 'github'.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git log --oneline
352ab2b (HEAD -> main, github/main) changed rebase.sh to main
44669f1 prepare for merge and rebase
7b2257e (gitlab/main, bitbucket/main) add line to README.md
cdac92b add line to README.md
267e456 use IDE Py Charm
34f5a71 (tag: v0.1, tag: v0.0, origin/main, origin/HEAD) Corrected Terraform/README
7373ae6 Moved and deleted
5e6781c Prepare to delete and move
87d2624 Added gitignore
30c8abe First commit
4fb52da Add files via upload
a19d36d Create README.md
0a9d6fa Add files via upload
a925873 Create README.md
141a563 Create README.md

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git checkout 44669f1
Note: switching to '44669f1'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 44669f1 prepare for merge and rebase

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git log --graph --all
* commit 352ab2b357107cd7531ab4f11bd3cbc84f53c9b4 (github/main, main)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:39:45 2021 +0300
|
|     changed rebase.sh to main
|
| * commit 804f5b2cce4cb589ec5873fed9fe775031d9eebf (github/git-merge, git-merge)
| | Author: Eduard Shashin <eddik.2010@yandex.ru>
| | Date:   Fri Nov 5 20:35:05 2021 +0300
| |
| |     merge: use shift
| |
| * commit b785f1fd6db286f98a664ebeda0967fe8f46c393
|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
|   Date:   Fri Nov 5 20:28:17 2021 +0300
|
|       merge: @ instead *
|
* commit 44669f174fad8fb0ce496170af13364bd61e5e93 (HEAD)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:24:41 2021 +0300
|
|     prepare for merge and rebase
|
* commit 7b2257e9e1c9b77dfca68d0a673d74985aa15a49 (gitlab/main, bitbucket/main)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:46:21 2021 +0300
|
|     add line to README.md
|
* commit cdac92bc169c86023334c0e3f6cf72ac7572127b
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:43:02 2021 +0300
|
|     add line to README.md
|
* commit 267e456541601afec872d6c7cf463dc63ce09851
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:36:38 2021 +0300
|
|     use IDE Py Charm
|
* commit 34f5a719b97aacfbbf73668504c00bbcb0aaa18f (tag: v0.1, tag: v0.0, origin/main, origin/HEAD)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Sat Oct 30 21:32:12 2021 +0300
|
|     Corrected Terraform/README
|
* commit 7373ae6ec62e48fe9efd5f59c6b254d9cf1ddb1c
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Sat Oct 30 20:57:27 2021 +0300

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git branch git-rebase

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git switch -c git-rebase
fatal: A branch named 'git-rebase' already exists.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git branch
* (HEAD detached at 44669f1)
  fix
  git-merge
  git-rebase
  main

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git checkout git rebase
error: pathspec 'git' did not match any file(s) known to git
error: pathspec 'rebase' did not match any file(s) known to git

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git checkout git-rebase
Switched to branch 'git-rebase'

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git branch
  fix
  git-merge
* git-rebase
  main

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-rebase
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   rebase.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/

no changes added to commit (use "git add" and/or "git commit -a")

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git add rebase.sh

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-rebase
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   rebase.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/


G:\DevOps\HW\netology-code\02-git-03-branching\branching>git commit -m "git-rebase 1"
[git-rebase 2bd3d1b] git-rebase 1
 1 file changed, 5 insertions(+), 3 deletions(-)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git log --graph --all
* commit 2bd3d1b83ede107ecd831d280cfb1515a94748db (HEAD -> git-rebase)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:47:36 2021 +0300
|
|     git-rebase 1
|
| * commit 352ab2b357107cd7531ab4f11bd3cbc84f53c9b4 (github/main, main)
|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
|   Date:   Fri Nov 5 20:39:45 2021 +0300
|
|       changed rebase.sh to main
|
| * commit 804f5b2cce4cb589ec5873fed9fe775031d9eebf (github/git-merge, git-merge)
| | Author: Eduard Shashin <eddik.2010@yandex.ru>
| | Date:   Fri Nov 5 20:35:05 2021 +0300
| |
| |     merge: use shift
| |
| * commit b785f1fd6db286f98a664ebeda0967fe8f46c393
|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
|   Date:   Fri Nov 5 20:28:17 2021 +0300
|
|       merge: @ instead *
|
* commit 44669f174fad8fb0ce496170af13364bd61e5e93
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:24:41 2021 +0300
|
|     prepare for merge and rebase
|
* commit 7b2257e9e1c9b77dfca68d0a673d74985aa15a49 (gitlab/main, bitbucket/main)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:46:21 2021 +0300
|
|     add line to README.md
|
* commit cdac92bc169c86023334c0e3f6cf72ac7572127b
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:43:02 2021 +0300
|
|     add line to README.md
|
* commit 267e456541601afec872d6c7cf463dc63ce09851
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:36:38 2021 +0300
|
|     use IDE Py Charm
|
* commit 34f5a719b97aacfbbf73668504c00bbcb0aaa18f (tag: v0.1, tag: v0.0, origin/main, origin/HEAD)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Sat Oct 30 21:32:12 2021 +0300

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-rebase
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   rebase.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/

no changes added to commit (use "git add" and/or "git commit -a")

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git add rebase.sh

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-rebase
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   rebase.sh

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/


G:\DevOps\HW\netology-code\02-git-03-branching\branching>git commit -m "git-rebase 2"
[git-rebase 152b2a5] git-rebase 2
 1 file changed, 1 insertion(+), 1 deletion(-)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git push -u github git-rebase
Enumerating objects: 14, done.
Counting objects: 100% (14/14), done.
Delta compression using up to 8 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (10/10), 870 bytes | 290.00 KiB/s, done.
Total 10 (delta 3), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (3/3), completed with 1 local object.
remote:
remote: Create a pull request for 'git-rebase' on GitHub by visiting:
remote:      https://github.com/SHEV8873/devops-netology/pull/new/git-rebase
remote:
To https://github.com/SHEV8873/devops-netology.git
 * [new branch]      git-rebase -> git-rebase
Branch 'git-rebase' set up to track remote branch 'git-rebase' from 'github'.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git log --graph --all
* commit 152b2a576a4d43b02e5fb264244c449091b5e1dc (HEAD -> git-rebase, github/git-rebase)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:50:17 2021 +0300
|
|     git-rebase 2
|
* commit 2bd3d1b83ede107ecd831d280cfb1515a94748db
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:47:36 2021 +0300
|
|     git-rebase 1
|
| * commit 352ab2b357107cd7531ab4f11bd3cbc84f53c9b4 (github/main, main)
|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
|   Date:   Fri Nov 5 20:39:45 2021 +0300
|
|       changed rebase.sh to main
|
| * commit 804f5b2cce4cb589ec5873fed9fe775031d9eebf (github/git-merge, git-merge)
| | Author: Eduard Shashin <eddik.2010@yandex.ru>
| | Date:   Fri Nov 5 20:35:05 2021 +0300
| |
| |     merge: use shift
| |
| * commit b785f1fd6db286f98a664ebeda0967fe8f46c393
|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
|   Date:   Fri Nov 5 20:28:17 2021 +0300
|
|       merge: @ instead *
|
* commit 44669f174fad8fb0ce496170af13364bd61e5e93
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:24:41 2021 +0300
|
|     prepare for merge and rebase
|
* commit 7b2257e9e1c9b77dfca68d0a673d74985aa15a49 (gitlab/main, bitbucket/main)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:46:21 2021 +0300
|
|     add line to README.md
|
* commit cdac92bc169c86023334c0e3f6cf72ac7572127b
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:43:02 2021 +0300
|
|     add line to README.md
|
* commit 267e456541601afec872d6c7cf463dc63ce09851
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:36:38 2021 +0300

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git checkout main
Switched to branch 'main'
Your branch is up to date with 'github/main'.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git branch
  fix
  git-merge
  git-rebase
* main

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git merge git-merge
Merge made by the 'recursive' strategy.
 02-git-03-branching/branching/merge.sh | 5 +++--
 1 file changed, 3 insertions(+), 2 deletions(-)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git push github
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 8 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (4/4), 414 bytes | 207.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/SHEV8873/devops-netology.git
   352ab2b..2f89d4c  main -> main

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git log
pick 2bd3d1b git-rebase 1
fixup 152b2a5 git-rebase 2

# Rebase 2f89d4c..152b2a5 onto 2f89d4c (2 commands)
#
# Commands:
# p, pick <commit> = use commit
# r, reword <commit> = use commit, but edit the commit message
# e, edit <commit> = use commit, but stop for amending
# s, squash <commit> = use commit, but meld into previous commit
# f, fixup [-C | -c] <commit> = like "squash" but keep only the previous
#                    commit's log message, unless -C is used, in which case
#                    keep only this commit's message; -c is same as -C but
#                    opens the editor
# x, exec <command> = run command (the rest of the line) using shell
# b, break = stop here (continue rebase later with 'git rebase --continue')
# d, drop <commit> = remove commit
# l, label <label> = label current HEAD with a name
# t, reset <label> = reset HEAD to a label
# m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
# .       create a merge commit using the original merge commit's
# .       message (or the oneline, if no original merge commit was
# .       specified); use -c <commit> to reword the commit message
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         G:/DevOps/HW/netology-code/.git/rebase-merge/git-rebase-todo[+] [unix] (21:43 05/11/2021)          2,5 All"G:/DevOps/HW/netology-code/.git/rebase-merge/git-rebase-todo" [unix] 30L, 1331B written
G:\DevOps\HW\netology-code\02-git-03-branching\branching>git staatus
git: 'staatus' is not a git command. See 'git --help'.

The most similar command is
        status

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch main
Your branch is up to date with 'github/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/

nothing added to commit but untracked files present (use "git add" to track)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git checkout git-rebase
Switched to branch 'git-rebase'
Your branch is up to date with 'github/git-rebase'.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git rebase -i main
error: could not apply 2bd3d1b... git-rebase 1
Resolve all conflicts manually, mark them as resolved with
"git add/rm <conflicted_files>", then run "git rebase --continue".
You can instead skip this commit: run "git rebase --skip".
To abort and get back to the state before "git rebase", run "git rebase --abort".
Could not apply 2bd3d1b... git-rebase 1
Auto-merging 02-git-03-branching/branching/rebase.sh
CONFLICT (content): Merge conflict in 02-git-03-branching/branching/rebase.sh

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
interactive rebase in progress; onto 2f89d4c
Last command done (1 command done):
   pick 2bd3d1b git-rebase 1
# This is a combination of 2 commits.
# This is the 1st commit message:

Merge branch 'git-merge'

# The commit message #2 will be skipped:

# git-rebase 2

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Fri Nov 5 21:39:33 2021 +0300
#
# interactive rebase in progress; onto 2f89d4c
# Last commands done (2 commands done):
#    pick 2bd3d1b git-rebase 1
#    fixup 152b2a5 git-rebase 2
# No commands remaining.
# You are currently rebasing branch 'git-rebase' on '2f89d4c'.
#
# Changes to be committed:
#       modified:   02-git-03-branching/branching/merge.sh
#       modified:   02-git-03-branching/branching/rebase.sh
#
# Untracked files:
#       .idea/
#
~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         ~                                                                                                         G:/DevOps/HW/netology-code/.git/COMMIT_EDITMSG [unix] (21:53 05/11/2021)                           1,1 All"G:/DevOps/HW/netology-code/.git/COMMIT_EDITMSG" [unix] 28L, 745B written
[detached HEAD d3ad939] Merge branch 'git-merge'
 Date: Fri Nov 5 21:39:33 2021 +0300
Successfully rebased and updated refs/heads/git-rebase.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-rebase
Your branch and 'github/git-rebase' have diverged,
and have 4 and 2 different commits each, respectively.
  (use "git pull" to merge the remote branch into yours)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/

nothing added to commit but untracked files present (use "git add" to track)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git log --graph --all
*   commit d3ad9391866f7160a451e33d5690dd006c11ef19 (HEAD -> git-rebase)
|\  Merge: 352ab2b 804f5b2
| | Author: Eduard Shashin <eddik.2010@yandex.ru>
| | Date:   Fri Nov 5 21:39:33 2021 +0300
| |
| |     Merge branch 'git-merge'
| |
| | * commit 2f89d4c14a1e2acdb4e18a59f281fc9a981495b1 (github/main, main)
| |/| Merge: 352ab2b 804f5b2
|/|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
| |   Date:   Fri Nov 5 21:39:33 2021 +0300
| |
| |       Merge branch 'git-merge'
| |
| * commit 804f5b2cce4cb589ec5873fed9fe775031d9eebf (github/git-merge, git-merge)
| | Author: Eduard Shashin <eddik.2010@yandex.ru>
| | Date:   Fri Nov 5 20:35:05 2021 +0300
| |
| |     merge: use shift
| |
| * commit b785f1fd6db286f98a664ebeda0967fe8f46c393
| | Author: Eduard Shashin <eddik.2010@yandex.ru>
| | Date:   Fri Nov 5 20:28:17 2021 +0300
| |
| |     merge: @ instead *
| |
* | commit 352ab2b357107cd7531ab4f11bd3cbc84f53c9b4
|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
|   Date:   Fri Nov 5 20:39:45 2021 +0300
|
|       changed rebase.sh to main
|
| * commit 152b2a576a4d43b02e5fb264244c449091b5e1dc (github/git-rebase)
| | Author: Eduard Shashin <eddik.2010@yandex.ru>
| | Date:   Fri Nov 5 20:50:17 2021 +0300
| |
| |     git-rebase 2
| |
| * commit 2bd3d1b83ede107ecd831d280cfb1515a94748db
|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
|   Date:   Fri Nov 5 20:47:36 2021 +0300
|
|       git-rebase 1
|
* commit 44669f174fad8fb0ce496170af13364bd61e5e93
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:24:41 2021 +0300
|
|     prepare for merge and rebase
|
* commit 7b2257e9e1c9b77dfca68d0a673d74985aa15a49 (gitlab/main, bitbucket/main)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git push -u github git-rebase
To https://github.com/SHEV8873/devops-netology.git
 ! [rejected]        git-rebase -> git-rebase (non-fast-forward)
error: failed to push some refs to 'https://github.com/SHEV8873/devops-netology.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git push -u github git-rebase -f
Enumerating objects: 13, done.
Counting objects: 100% (13/13), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 474 bytes | 474.00 KiB/s, done.
Total 5 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/SHEV8873/devops-netology.git
 + 152b2a5...d3ad939 git-rebase -> git-rebase (forced update)
Branch 'git-rebase' set up to track remote branch 'git-rebase' from 'github'.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git log --graph --all
*   commit d3ad9391866f7160a451e33d5690dd006c11ef19 (HEAD -> git-rebase, github/git-rebase)
|\  Merge: 352ab2b 804f5b2
| | Author: Eduard Shashin <eddik.2010@yandex.ru>
| | Date:   Fri Nov 5 21:39:33 2021 +0300
| |
| |     Merge branch 'git-merge'
| |
| | * commit 2f89d4c14a1e2acdb4e18a59f281fc9a981495b1 (github/main, main)
| |/| Merge: 352ab2b 804f5b2
|/|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
| |   Date:   Fri Nov 5 21:39:33 2021 +0300
| |
| |       Merge branch 'git-merge'
| |
| * commit 804f5b2cce4cb589ec5873fed9fe775031d9eebf (github/git-merge, git-merge)
| | Author: Eduard Shashin <eddik.2010@yandex.ru>
| | Date:   Fri Nov 5 20:35:05 2021 +0300
| |
| |     merge: use shift
| |
| * commit b785f1fd6db286f98a664ebeda0967fe8f46c393
| | Author: Eduard Shashin <eddik.2010@yandex.ru>
| | Date:   Fri Nov 5 20:28:17 2021 +0300
| |
| |     merge: @ instead *
| |
* | commit 352ab2b357107cd7531ab4f11bd3cbc84f53c9b4
|/  Author: Eduard Shashin <eddik.2010@yandex.ru>
|   Date:   Fri Nov 5 20:39:45 2021 +0300
|
|       changed rebase.sh to main
|
* commit 44669f174fad8fb0ce496170af13364bd61e5e93
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Fri Nov 5 20:24:41 2021 +0300
|
|     prepare for merge and rebase
|
* commit 7b2257e9e1c9b77dfca68d0a673d74985aa15a49 (gitlab/main, bitbucket/main)
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:46:21 2021 +0300
|
|     add line to README.md
|
* commit cdac92bc169c86023334c0e3f6cf72ac7572127b
| Author: Eduard Shashin <eddik.2010@yandex.ru>
| Date:   Wed Nov 3 00:43:02 2021 +0300
|
|     add line to README.md
|
* commit 267e456541601afec872d6c7cf463dc63ce09851

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git status
On branch git-rebase
Your branch is up to date with 'github/git-rebase'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        ../../.idea/

nothing added to commit but untracked files present (use "git add" to track)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git checkout main
Switched to branch 'main'
Your branch is up to date with 'github/main'.

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git log --oneline
2f89d4c (HEAD -> main, github/main) Merge branch 'git-merge'
352ab2b changed rebase.sh to main
804f5b2 (github/git-merge, git-merge) merge: use shift
b785f1f merge: @ instead *
44669f1 prepare for merge and rebase
7b2257e (gitlab/main, bitbucket/main) add line to README.md
cdac92b add line to README.md
267e456 use IDE Py Charm
34f5a71 (tag: v0.1, tag: v0.0, origin/main, origin/HEAD) Corrected Terraform/README
7373ae6 Moved and deleted
5e6781c Prepare to delete and move
87d2624 Added gitignore
30c8abe First commit
4fb52da Add files via upload
a19d36d Create README.md
0a9d6fa Add files via upload
a925873 Create README.md
141a563 Create README.md

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git merge git-rebase
Merge made by the 'recursive' strategy.
 02-git-03-branching/branching/rebase.sh | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)

G:\DevOps\HW\netology-code\02-git-03-branching\branching>git push -u
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 231 bytes | 231.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/SHEV8873/devops-netology.git
   2f89d4c..6e7ed8e  main -> main
Branch 'main' set up to track remote branch 'main' from 'github'.