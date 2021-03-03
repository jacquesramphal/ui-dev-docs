_Note: need to update to include ssh setup for tower and tool usage_



# ⚙️ Getting Setup

Initial setup can be complicated. Work with your team to ensure you are properly provisioned. 

## 1. Install XCode

- [Xcode](https://apps.apple.com/us/app/xcode/id497799835?mt=12)
- Once downloaded, install XCode

## 2. Install Dependencies

[`n`](https://github.com/tj/n) is used to to manage versions of `node` as it is an npm package that can be installed rather than [`nvm`](https://github.com/creationix/nvm) which requires you to run a shell script. You can use either if you want.
The `.nvmrc` file is used by Netlify to set their environment to the specific version we want and we use the value inside this file to set the version locally using `n` in the `install.sh` script.

### Using a script

```
./install.sh
```

If errors regarding `xcode` or `sharp` occur, try running the command a second time.

### Manually

NPM is distributed with Node.js- which means that when you download Node.js, you automatically get NPM installed on your computer.[Download Node.js and NPM](https://nodejs.org/en/)

#### Check that you have node and npm installed

To check if you have Node.js installed, run this command in your terminal:

``` 
node -v 
```

To confirm that you have npm installed you can run this command in your terminal:

``` 
npm -v 
```

#### Install Yarn

``` 
npm install --global yarn 
```

#### Install Dependencies

```
yarn install
```

If errors regarding `xcode` or `sharp` occur, try running the command a second time.

Set `node` version

```
n $(< .nvmrc)
```

Set the environment variables

```
source .env
```

### Developing

Run

```
yarn start
```

With the exception of all `gatsby-*.js` files in the root of the repo, all source files live in `src`.

- The `env` config and webpack plugins are in `gatsby-config`.
- The generation of pages is configured in `gatsby-node.js`.
- The high level page html structure is defined in `gatsby-browser.js`


Changes to most files will trigger livereload in the browser.


---

## 2. Configure Tools

See [Tools](tools.md) for guidance on installation and configuration.

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

- Check the root folder for a `package.json` file. This will include any notes and install details.

### Clone the myplanet repo

- See [Branching Strategy](https://github.com/myplanetdigital/myplanet.com#branching-strategy) for more information on working with MASTER and DEVELOPMENT

#### Using Terminal

```
git clone git@github.com:myplanetdigital/myplanet.com.git
``` 

#### Using Tower

https://www.git-tower.com/help/guides/manage-repositories/clone-remote-repository/windows

