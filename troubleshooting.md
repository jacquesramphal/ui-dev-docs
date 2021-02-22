# 🤦‍ Troubleshooting

<details>
  <summary><strong>How to undo your last commit and re-push</strong></summary>
  
1. Go to your branch

`git checkout your-branch-name`

2. Revert the commit this goes back to before your commit

`git reset HEAD~1`

#### Note

    Use ~ most of the time — to go back a number of generations, usually what you want
    Use ^ on merge commits — because they have two or more (immediate) parents

    Tilde ~ is almost linear in appearance and wants to go backward in a straight line
    Caret ^ suggests an interesting segment of a tree or a fork in the road


3. Check changed/staged files (not yet committed)

`git status`

3b. you can either just commit the X number of files you want or undo the specifc file with

`git checkout fileName.js`

4. Once changes have been made/reverted, commit everything again

`git add *`

`git commit -m "XXX: Your New Commit Message"`

5. Force push updates since you’re erasing commits from before

`git push -f`

6. Check `git log` or review commits on Github to confirm update

</details>

<details>
  <summary><strong>Renaming a local and remote branch</strong></summary>

Follow the steps below to rename a Local and Remote Git Branch:

    Start by switching to the local branch which you want to rename:

    git checkout <old_name>

    Rename the local branch by typing:

    git branch -m <new_name>

    At this point, you have renamed the local branch.

    If you’ve already pushed the <old_name> branch to the remote repository , perform the next steps to rename the remote branch.

    Push the <new_name> local branch and reset the upstream branch:

    git push origin -u <new_name>

    Delete the <old_name> remote branch:

    git push origin --delete <old_name>

That’s it. You have successfully renamed the local and remote Git branch.
https://linuxize.com/post/how-to-rename-local-and-remote-git-branch/
</details>

<details>
 <summary><strong>Multiple external commits displayed on PR.</strong></summary>
 
If you've pushed to master and are seeing commit history on the comparison page, you need to reset and cherry-pick the commit you want to push.

### Reset to Upstream Development
`git reset --hard origin/development`

> Running this command will revert all the work on the current branch. Make sure to back up your changes beforehand.

### Cherry-pick desired commit (you must cherry-pick each commit separately when using terminal)
`git cherry-pick (commit id from github)`

### Force push to GitHub
`git push -f`

Refresh the draft PR page -- now only one commit should show on the browser compare ui
</details>

<details>
 <summary><strong>My branch isnt showing the most recent version of MASTER</strong></summary>

Always branch from master

```
git fetch upstream

git rebase upstream/master
```

> If you branch from another branch you can pull in other commits by mistake. 

[REBASE vs RESET](https://stackoverflow.com/questions/11225293/what-is-the-difference-between-git-reset-vs-git-rebase)


</details>

<details>
 <summary><strong>How do I resolve Merge Conflicts?</strong></summary>



## Rebasing

[Source: Myplanet Dev Docs](https://github.com/myplanetdigital/dev-docs/blob/master/wiki/GitTips.md#rebasing)

1. Rebase!
```
git checkout [your_branch_that_you_wanna_update]
git rebase origin-development
 
(or master depending on what you're working on)
```

2. Resolve conflicts: if there are conflicts you'll have to
- edit and save the files to resolve the conflicts
- `git add all`
- `git rebase --continue`

---
https://stackoverflow.com/questions/134882/undoing-a-git-rebase

git rebase --quit

https://stackoverflow.com/questions/3685001/git-how-to-fix-corrupted-interactive-rebase

get someone to show you how to do this safely
https://stackoverflow.com/questions/6934752/combining-multiple-commits-before-pushing-in-git
</details>

<details>
 <summary><strong>My Contentful updates aren't showing up.</strong></summary>

Contentful musted be refetched by rebuilding the site.

```
yarn build
yarn start
```
</details>

<details>
 <summary><strong>Undoing last commit</strong></summary>
 
### Option A
If you've made a mistake in a commit, the best way to fix it is with **another** commit which addresses the previous issue. 

### Option B
To clear the last commit see [this link](https://sethrobertson.github.io/GitFixUm/fixup.html)

`git reset --hard HEAD^`

---
</details>

<details>
 <summary><strong>How do I get command prompt back in terminal?</strong></summary>

### Option A:

Press `Ctrl + C` to terminate the program and get back to the shell prompt.

### Option B:

Just open a new tab by pressing Cmd-T , or a new window (using Cmd-N ).

## How to exit GIT LOG of GIT DIFF

You're in the less program, which makes the output of git log scrollable.
* Type `q` to exit this screen. Type `h` to get help.

---
</details>


