[![Build Status](https://travis-ci.com/myplanetdigital/myplanet.com.svg?token=GPokVjxyumt4Xqbkqfxw&branch=master)](https://travis-ci.com/myplanetdigital/myplanet.com)

# myplanet.com

+ [Intro](#intro)
+ [Branching Strategy](#branching-strategy)
+ [Local development](#local-development)
	+ [Installation](#installation)
	+ [Developing](#developing)
	+ [Spacing](#spacing)
+ [CI/CD](#cicd)
	+ [Quick reference](#quick-reference)
	+ [Full description](#full-description)
+ [Building with Netlify environment](#building-with-netlify-environment)
+ [Misc](#misc)
	+ [Generating the TOC for this file](#generating-the-toc-for-this-file)
## Intro

This project uses the static site generator "[Gatsby](https://www.gatsbyjs.org/)".

See the [Docs](https://www.gatsbyjs.org/docs/) to get familiar with how it works.

## Branching Strategy

All development will be done against `development` branch via a forked repo. Releases will be cut from `master`.

## Local development

### Installation

[`n`](https://github.com/tj/n) is used to to manage versions of `node` as it is an npm package that can be installed rather than [`nvm`](https://github.com/creationix/nvm) which requires you to run a shell script. You can use either if you want.
The `.nvmrc` file is used by Netlify to set their environment to the specific version we want and we use the value inside this file to set the version locally using `n` in the `install.sh` script.

#### Using a script

```
./install.sh
```

If errors regarding `xcode` or `sharp` occur, try running the command a second time.

#### Manually

Install dependencies

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

### Touch devices (mostly iOS)

[react-fastclick](https://github.com/JakeSidSmith/react-fastclick) is used to resolve the touch delay that is [resolved by all browsers](https://developers.google.com/web/updates/2013/12/300ms-tap-delay-gone-away) by using any of `initial-scale=1, minimum-scale=1, maximum-scale=1, shrink-to-fit=no, user-scalable=no` in the `viewport` meta tag.... unless the browser is Safari on iOS, as they do so in favour of improved accessibility. No link for you :trollface:.

- [The Annoying Mobile Double-Tap Link Issue | CSS-Tricks](https://css-tricks.com/annoying-mobile-double-tap-link-issue/)
- [css - disable viewport zooming iOS 10+ safari? - Stack Overflow](https://stackoverflow.com/questions/37808180/disable-viewport-zooming-ios-10-safari/37859168#37859168)

### Spacing

In almost every case, `padding` and `margin` properties are defined using the *spacing scale* within the site [Theme]() and is set for each breakpoint (also defined in the Theme file).

This approach relies on the use of [Grid Styled](https://github.com/jxnblk/grid-styled) - specifically, the "Spacing Scale" part of the [Theming section](https://github.com/jxnblk/grid-styled#theming).

The spacing scale we use is based on Grid Style's which is actually an implementation of the [8pt grid system](https://spec.fm/specifics/8-pt-grid). The specific values from `theme.js` are as follows:

```js
const spacing = [
  0,
  4,
  8,
  16,
  24,
  32,
  48,
  64,
  96,
  128,
  192,
  256
]
```

For example, if you want to set the `margin-bottom` property to `24px` at the first and second breakpoint, and `48px` for the third, on a `<Box>` component, you would simply write the following:

```jsx
<Box mb={[ 4, 4, 6 ]}>
```

There's a [full list of the props](https://github.com/jxnblk/grid-styled#props) for the `<Box>` component.

There are also Sass variables that mirror these in the `_variables.scss` file and can be used throughout the scss files like so:

```scss
.class {
  margin-bottom: space(4)

  @include breakpoint('large') {
    margin-bottom: space(6);
  }
}
```

In Sass, to set the value to zero using this approach, just write out `0` without the `space` function as Sass lists can't be read like arrays (starting at zero) so the spacing value starts at 4. This way, the values line up and you don't need to use two different numbers to get the same value.

## CI/CD

### Quick reference

#### Env vars

```
CONTENTFUL_API_KEY=
CONTENTFUL_PREVIEW_API_KEY=
BUILDING=false
```

#### Install and build

`yarn install && yarn run build`

---

### Full description

#### Set environment variables

Set the environment variables from `.env` in your CI/CD service.

```
CONTENTFUL_API_KEY=
CONTENTFUL_PREVIEW_API_KEY=
BUILDING=false
```

#### Install dependencies

Most services auto-detect the project type (`node` in this case) and automatically run the `yarn install` but you can set this same command manually if you need to.

#### Build

`npm run build` will compile the site into a directory named `public/`.

#### Serve

Simply serve the content of `public` from your the server or CDN.

## Building with Netlify environment

You can replicate the same environment that Netlify uses by using the [Netlify Build Image](https://github.com/netlify/build-image).

If you don't already have Docker, [install it](https://www.docker.com/community-edition).

Get the latest Netlify docker image

```
docker pull netlify/build
```

Clone the Netlify Build Image repo

```
git clone https://github.com/netlify/build-image.git
```

Change working directory to the build image repo

```
cd build-image
```

Run the image command

```
./test-tools/start-image.sh path/to/my/repo
```

You are now inside the Netlify Build Image container.

To build, run:

```
export CONTENTFUL_API_KEY=<secret_key> CONTENTFUL_PREVIEW_API_KEY=<secret_key> BUILDING=false ; build npm run build
```

Yes, the `build npm run build` command has two `build`s. The first is Netlify's and the second is just the name of our npm script.

## Misc

### Generating the TOC for this file

```
markdown-toc README.md --no-firsth1 --maxdepth 2 --bullets "+"
```

Need to change double spaces from output to tabs to render properly.

## Troubleshooting

When building, errors such as "WebpackError: Cannot read property 'headline' of null" or erros referencing `window` are usually due to the fact that the server side rendering (SSR) is trying to access `window` when it does not exist. ([Docs](https://www.gatsbyjs.org/docs/debugging-html-builds/)).

The other thing that can go wrong is if you create a page in Contentful but don't have a page built for it an error will be thrown. THis is most confusing when you have a branch (PR) with work on it that references content in Contentful but another branch does not. The branch that does not have the code to display the Contentful content will get errors when building.
