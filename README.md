# Learn Git

## Git Commands

1. ``` git status```
Show the working tree status.We will use this command to show the changes in local repo.When use this we will see the branch name on which we are working.

2. To make a new branch other than master. Use
``` git branch branch-name ```

> A branch is kind of like a fork on your computer. When you have your own branch, it’s a place where you can make changes without affecting `master`.

3. ``` git add path-to-your-file ``` will allow you to pre-select the files you want to save. Add the files one at a time.

4. ```git commit -m"commit message" ``` will group your changes together into a commit. The message should be short, describe the work that you did, and include the issue number that you are working on.

5. ```git push origin name-of-branch ``` to save your commit.Git `push`takes two argument the remote i want to send changes to , and name of local branch that i want to push.

#### Configure remote that points to the upstream repository 

 ```git remote -v ``` List the current configured remote repository for your fork.

 ```git remote add upstream https://github.com/original_owner/original_repo.git ``` Specify a new remote upstream repository that will be synced with the fork.

 ---

#### Syncing a Fork

```git fetch upstream``` Fetch the branches and their respective commits from the upstream repository. Commits to `master` will be stored in a local branch, `upstream/master`.

```git checkout master ```  Check out your fork's local `master` branch.

``` git merge upstream/master``` Merge the changes from ```upstream/master``` into your local master branch. This brings your fork's `master` branch into sync with the upstream repository, without losing your local changes.

---

#### To update your fork

```
git checkout master
git rebase master
git pull upstream master
git push origin master

```

```git checkout master``` switched to the master branch. ```git remote add``` helped you create a label called “upstream” that is connected to the url for the main project. So then when you “pull” the changes down onto your hard drive, you’re pulling the code that lives at the “upstream” url for the main project. `git push origin master` makes your fork (the “origin”) be synced up with what’s on your hard drive.

But what if you also have some work that was in progress? You’re working on code that’s out of date, so how do you combine it with the most up to date code? You need to do something called a `rebase`. A rebase takes your current branch and applies the changes you made to the branch that you specify in the command (in the example below, it’s `master`).

```
git checkout branch-name
git rebase master
git pull upstream
git push origin master
```


>If we first fetch code from the origin master( it may be your fork or your your personal repo), then we directly use ```git rebase origin/master``` or `git merge upstream/master`. Actually when we use fetch command then we have a head pointer that points to `origin/master` or `upstream/master`. Otherwise you can directly use above commands.

#### To megre one branch(development) into other(master)

```
git checkout master
git merge development
git push origin master
```

#### To squash 2 recently pushed commits

```
git reset --soft HEAD^
git commit --amend
```
#### To squash n pushed commits

```git rebase -i HEAD~n```

* At the interactive screen that opens up, replace pick with squash at the top for all the commits that you want to squash.

* Save and quit your editor, you will get another editor for commit message.

* When you save abd quit, the contents of the edited file become commit message of new combined commit. After that write the command:

```git push origin master --force ```