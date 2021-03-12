# 🤝 Workflow

Note: The following documents steps using terminal. See [tools](tools.md) for more information on GUIs.

Every team is different but the following covers steps to access, edit and push updates to any repository.<br>Discuss process with your team before making any changes. 

See [Myplanet Dev Docs: Git Tips](https://github.com/myplanetdigital/dev-docs/blob/master/wiki/GitTips.md) for more.
<br><br>

<details>
  <summary><strong>Working on issues</strong></summary>

## Create a new issue

Issues can be used to keep track of bugs, enhancements, or other requests. If an issue for the bug identified does not exist, create one

[TBD Issue Template Link]()

## Create a new branch to work on the issue(s)

For small changes, hotfixes etc. open a PR against Master/Main. For larger tickets and updates to the site, PR against the Development branch

1. Update your local with changes from origin/development.

`git pull`

1. Create a new branch from development

`git checkout -b '123--new-branch' development`


> A new branch should be created (from master) for each unique issue.

> Reference the issue number in the name of the new branch you will create

> Ensure Master is updated before branching

> Replace 123--new-branch with the issue number and the desired branch name

> Branches should be named clearly based on the context of the issue. 


### More options

```
# View your branches
git branch

# View Remote branches
git remote -v

# Switch branches
git checkout 123--new-branch

# Delete a branch
git branch -D 123--new-branch

# Switch to master
git checkout master
```

---
</details>

<details>
  <summary><strong>Test locally</strong></summary>

* Before running the build, check for new packages on upstream/master (from other dev tickets for eg.)

`yarn install`

* Remove shared cache files.

`yarn cache clean`

* Build the site.

`yarn build`

* Start the server.

`yarn start`

---
</details>

<details>
  <summary><strong>Updating Files</strong></summary>

## Make changes to desired file(s)
* Open Project folder in text editor (Atom)
* Locate target file and make changes as needed

Once changes have been made, run/refresh the build to test using the steps in the [previous section](workflow.md)

## Add changes
Once you have modified existing files or added new files to the project, you can add them to your local repository, which we can do with the git add command. Let’s add the -A flag to add all changes that we have made:

* Check the status of the working directory

`git status`

* Add all changes in working dir.

`git add -A`

`git add .`

`git add src`

* Compare branches

`git diff`

* Add specific files. Only that file is added to commit

`git add file_name`

* Revert/Reset to last commit

`git reset head`

See [Troubleshooting](https://github.com/jacquesramphal/ui-dev-docs/wiki/Troubleshooting) steps to rebase branch and fix commit issues where multiple commits are displayed in error.

## Commit Changes
Next, we’ll want to record the changes that we made to the repository

`git commit`

## Adding Commit Message
The commit message is an important aspect of your code contribution; it helps the other contributors fully understand the change you have made, why you made it, and how significant it is. Additionally, commit messages provide a historical record of the changes for the project at large, helping future contributors along the way.

If we have a very short message, we can record that with the `-m` flag and the message in quotes:

`git commit -m 'commit message here'`


## Verify Commit Details
Once you have saved and exited the commit message text file, you can verify what git will be committing with the following command:

`git status`

---
</details>

<details>
  <summary><strong>Pushing commit(s) to GitHub</strong></summary>

At this point you can use the git push command to push the changes to the current branch of your forked repository:

```
git pull
git push
```

If pushing a new branch for the FIRST TIME, use:

`git push -u upstream 123--new-branch`

---
</details>

<details>
  <summary><strong>Open a Pull Request (PR)</strong></summary>

## GitHub Pull Request Etiquette & Template

Source: [Myplanet Dev Doc: PR Template](https://github.com/myplanetdigital/dev-docs/Practice Areas/Site Reliability & DevOps/GitHub Pull Request (PR) Template.md)

1. Go to github branch master
1. Find your branch
1. Confirm COMMITS
1. Add description
1. Link related issues/PRs

[Read more](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request)

---
</details>
<br>

## Misc.

<details>
  <summary>CSS Modifers</summary>

### CSS Modifiers
look for modifiers in layout.scss
`$--padding { padding: 0 40px; }`

$ inserts the name of the class above
add the new class to the main component.js or style.js (double check where styles are) file



with a media query

`$--mobile-padding {
    @include breakpoint('medium', true) {
    padding: 0 40px;
    }
    @include breakpoint('small', true) {
    padding: 0 20px;
}`


checkout responsive.scss for media queries

variables.scss

@mixin

mixins are functions in SASS. research this

---
</details>

<details>
  <summary>Inspecting and updating a remote branch</summary>

Source: [Myplanet Dev Docs: Git Tips](https://github.com/myplanetdigital/dev-docs/blob/master/wiki/GitTips.md#add-remote-forks)

## Add Remote Forks

If you want to review other people's branches/PR you can add their forks locally:

```
git remote add Sheril git@github.com:Sheril/ecx-portal.git
```

Fetch that user to update all of that user's branch

```
git fetch Sheril
```

Check out that user's branch

```
git checkout Sheril/ECX-XXX--branch
```

## Pushing to Remote Branches

In the case you want to push to somebody else's repo or upstream:

```
git push remote local-branch:remote-branch
```

If I want to push to Sheril's ECX-XXX--branch I would do this:

```
git push sheril My-ECX-XXX:ECX-XXX--branch
```
---
</details>
