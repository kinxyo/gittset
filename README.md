# Collaborating with Git

Ways to smoothly work on same the file when the need be.

![image](https://github.com/kinxyo/gittset/assets/90744941/94384f6b-f1d2-4ae6-9783-8b7301f95faa)

## 2 methods are used in different scenarios:

### Stash it

```git
git stash
git pull origin <branch_name>
git stash apply
```

This method is suitable when you have ongoing changes that are not ready to be committed. `git stash` will save your changes without committing them, allowing you to pull the latest changes from the remote repository. After pulling, git stash apply will reapply your stashed changes.

### Commit first

```git
git add .
git commit -m "msg"
git pull origin <branch_name>
```

This method is suitable when your changes are complete and ready to be committed. After committing your changes, you can safely pull the latest changes from the remote repository. If there are any conflicts between your commit and the latest changes, you'll need to resolve them manually.

---

In summary, use the first method when your changes are not ready to be committed, and use the second method when your changes are ready to be committed.

## Divergent Branch Error

The message you may see that your local branch and the remote branch have diverged, means they have commits that the other doesn't have. This can happen if you've made commits on your local branch that aren't on the remote branch, or if someone else has pushed commits to the remote branch that you haven't pulled yet.

In such case, always first try:

```git
git pull --rebase origin <branch_name>
```

otherwise, 

> [!NOTE]
> Yet to experiment.

```git
git merge origin/<branch_name>
```
