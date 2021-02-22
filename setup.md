# ⚙️ Getting Setup

Initial setup can be complicated. Work with your team to ensure you are properly provisioned. 

## 1. Install Dependencies

### XCode

- [Xcode](https://apps.apple.com/us/app/xcode/id497799835?mt=12)
- Install file

### Packages

- [Yarn]()
- [NPM]()
- [N]()
- [Gatsby (?)]()

---

## 2. Configure Tools

<details>
  
  <summary><strong>Git Tower</strong> https://code.visualstudio.com/download
  
</details>

<details>
  
  <summary><strong>VSCode</strong> https://code.visualstudio.com/download</summary

---
* [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag): Automatically add HTML/XML close tag, same as Visual Studio IDE or Sublime Text

* [Auto Complete Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-complete-tag): Extension Packs to add close tag and rename paired tag automatically for HTML/XML

* [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag): Automatically rename paired HTML/XML tag, same as Visual Studio IDE does

* [Bracket Pair Colorizer 2](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2): A customizable extension for colorizing matching brackets

* [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint): Integrates ESLint JavaScript into VS Code.

* [GitHub PRs and Issues](https://marketplace.visualstudio.com/items?itemName=GitHub.vscode-pull-request-github): Pull Request and Issue Provider for GitHub

* [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens): Supercharge the Git capabilities built into Visual Studio Code — Visualize code authorship at a glance via Git blame annotations and code lens, seamlessly navigate and explore Git repositories, gain valuable insights via powerful comparison commands, and so much more

* [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one): All you need to write Markdown (keyboard shortcuts, table of contents, auto preview and more)

* [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced): Markdown Preview Enhanced ported to vscode

* [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode): Code formatter using prettier

</details>

---

## 3. Configure SSH Access (one-time step)

An SSH key is an access credential in the SSH protocol. Its function is similar to that of user names and passwords, but the keys are primarily used for automated processes and for implementing single sign-on by system administrators and power users.

[Tutorial](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)

Generate a key

```$ ssh-keygen -t rsa```

Navigate to ssh folder

```cd ~/.ssh```

View files

```ls -la```

Copy key to file

```pbcopy < ~/.ssh/id_rsa.pub```

---

## 4. Update Permissions

Ensure you have access to push updates

`sudo chown -R $USER /usr/local/lib/node_modules`

---

## 5. Create a Local build
  
### Setup environment

Create a new file in your root folder of your fork and name it `.env`

> In most cases, you require a `.env` file

> These keys are stored in Contentful. Ask your team for permission to get the key.

### Check scripts for instructions

Check the root folder for a `package.json` file. This will include any notes and install details.

### Clone the myplanet repo

See [Branching Strategy]() for more information on working with MASTER and DEVELOPMENT

#### Using Terminal

`git clone git@github.com:myplanetdigital/myplanet.com.git` 

#### Using Tower

https://www.git-tower.com/help/guides/manage-repositories/clone-remote-repository/windows

