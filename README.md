# Learn Git

## Git Commands

1. ``` git status```
Show the working tree status.We will use this command to show the changes in local repo.When use this we will see the branch name on which we are working.

2. To make a new branch other than master. Use
``` git branch branch-name ```

... > A branch is kind of like a fork on your computer. When you have your own branch, it’s a place where you can make changes without affecting `master`.

3. ``` git add path-to-your-file ``` will allow you to pre-select the files you want to save. Add the files one at a time.

4. ```git commit -m"commit message" ``` will group your changes together into a commit. The message should be short, describe the work that you did, and include the issue number that you are working on.

5. ```git push origin name-of-branch ``` to save your commit.

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

