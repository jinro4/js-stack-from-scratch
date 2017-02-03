# 01 - Node, Yarn, and `package.json`

In this section we will set up Node, Yarn, a basic `package.json` file, and try a package.

## Node

> 💡 **[Node.js](https://nodejs.org/)** is a JavaScript runtime environment. It is mostly used for Back-End development, but also for general scripting. In the context of Front-End development, it can be used to perform a whole bunch of tasks like linting, testing, and assembling files.

We will to use Node for basically everything in this tutorial, so you're going to need it. Head to the [download page](https://nodejs.org/en/download/current/) for macOS or Windows binaries, or the [package manager installations page](https://nodejs.org/en/download/package-manager/) for Linux distributions.

For instance, on **Ubuntu / Debian**, you would run the following commands to install Node:

```bash
curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
sudo apt-get install -y nodejs
```

You want any version of Node > 6.5.0.

## NVM

If Node is already installed, or if you want more flexibility, install NVM ([Node Version Manager](https://github.com/creationix/nvm)), and make NVM install and use the latest version of Node for you.

## NPM

NPM is the default package manager for Node. It is automatically installed alongside with Node. Package managers are used to install and manage packages (modules of code that you or someone else wrote). We are going to use a lot of packages in this tutorial, but we'll use Yarn, another package manager.

## Yarn

> 💡 **[Yarn](https://yarnpkg.com/)** is a Node.js package manager which is much faster than NPM, has offline support, and fetches dependencies [more predictably](https://yarnpkg.com/en/docs/yarn-lock).

Since it [came out](https://code.facebook.com/posts/1840075619545360) in October 2016, it received a very quick adoption and is becoming the new package manager of choice of the JavaScript community. If you want to stick to NPM you can simply replace all `yarn add` and `yarn add --dev` commands of this tutorial by `npm install --save` and `npm install --dev`.

- Install Yarn by following the [instructions](https://yarnpkg.com/en/docs/install). You can likely install it with `npm install -g yarn` or `sudo npm install -g yarn` (yeah, we're using NPM to install Yarn, much like you would use Internet Explorer or Safari to install Chrome!).

## `package.json`

> 💡 **[package.json](https://yarnpkg.com/en/docs/package-json)** is the file used to describe and configure your JavaScript project. It contains general information (your project's name, version, contributors, license, etc), configuration options for tools you use, and even a section to run *tasks*.

- Create a new folder to work in, and `cd` in it.
- Run `yarn init` and answer the questions (`yarn init -y` to skip all questions), to generate a `package.json` file automatically.

## Hello World

- Create an `index.js` file containing `console.log('Hello world');`.
- Run `node .` in this folder (`index.js` is the default file Node looks for in the current folder). It should print "Hello world".

## `start` script

Running `node .` to execute our program is a bit too low-level. We are going to use an NPM/Yarn script to trigger the execution of that code instead. That will give us a nice abstraction to be able to always use `yarn start`, even when our program gets more complicated.

- In `package.json`, add a `scripts` object to the root object like so:

```json
"scripts": {
  "start": "node ."
}
```

`start` is the name we give to the *task* that will run our program. We are going to create a lot of different tasks in this `scripts` object throughout this tutorial. `start`, `stop`, `test`, are examples of standard names that you can run directly with `yarn start`, `yarn stop`, or `yarn test`. If you use non-standard task names, like `makecoffee`, you need to add `run` to the command like so: `yarn run makecoffee`.

`package.json` must be a valid JSON file, which means that you cannot have trailing commas. So be careful when editing manually your `package.json` file.

- Run `yarn start`. It should print `Hello world`.

## Git and `.gitignore`

- Initialize a Git repository with `git init`.

- Create a `.gitignore` file and add the following to it:

```gitignore
npm-debug.log
yarn-error.log
```

These files appear when your package manager encounters an error, we don't want them versioned in our repository.

## Installing and using a package

In this section we will install and use a package. A "package" is simply a piece of code that someone else wrote, and that you can use in your own code. It can be anything. Here, we're going to try a package that helps you manipulate colors for instance.

- Install the community-made package called `color` by running `yarn add color`.

Open `package.json` to see how Yarn automatically added `color` in  `dependencies`.

A `node_modules` folder has been created to store the package.

- Add `node_modules/` to your `.gitignore`.

You will also notice that a `yarn.lock` file got generated by Yarn. You should commit this file to your repository, as it will ensure that everyone in your team uses the same version of your packages. If you're sticking to NPM instead of Yarn, the equivalent of this file is the *shrinkwrap*.

Write the following to your `index.js` file:

```javascript
const Color = require('color');

const redHexa = Color({r: 255, g: 0, b: 0}).hexString();
console.log(redHexa);
```

- Run `yarn start`. It should print `#FF0000`.

Congratulations, you installed and used a package!

`color` is just used in this section to teach you how to use a simple package. We won't need it anymore, so you can uninstall it:

- Run `yarn remove color`

## Two kinds of dependencies

There are two kinds of package dependencies, `"dependencies"` and `"devDependencies"`:

**Dependencies** are libraries you need for your application to function (React, Redux, Lodash, jQuery, etc). You install them with `yarn add [package]`.

**Dev Dependencies** are libraries used during development or to build your application (Webpack, SASS, linters, testing frameworks, etc). You install those with `yarn add --dev [package]`.

Next section: [02 - Babel, ES6, ESLint, Flow](/tutorial/02-babel-es6-eslint-flow)

Back to the [table of contents](https://github.com/verekia/js-stack-from-scratch#table-of-contents).