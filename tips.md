## 1. Branch from the most up to date version of Origin (Master or Development)

For small changes, hotfixes etc. open a PR against Master/Main. For larger tickets and updates to the site, PR against the Development branch

Update your local with changes from origin/development.

```
git pull
```

Create a new branch from development

```
git checkout -b '123--new-branch' development
```

- See [Workflow](workflow.md) for notes on branching strategy.

- Working with Branches in Tower https://www.git-tower.com/learn/git/videos/create-checkout-branches/cli/

## 2. Squash and Rebase your Commits

Before you merge a feature branch back into your main branch (master or development), your feature branch should be squashed down to a single buildable commit, and then rebased from the up-to-date main branch.

- Read the full article [here](https://blog.carbonfive.com/always-squash-and-rebase-your-git-commits/)

- Interactive Rebase and Squashing with Tower https://www.git-tower.com/help/videos/more-productive-in-git/interactive-rebase
