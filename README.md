# Firebase Functions with Babel config to target the correct Execution Environment

[![styled with prettier](https://img.shields.io/badge/styled_with-prettier-ff69b4.svg)](https://github.com/prettier/prettier)

Use Babel to target the correct execution environment for Cloud Functions for Firebase and use all modern tools and languages features to develop.

Here is the accompanying [Medium post](https://medium.com/@jthegedus/);

## TLDR;
Develop your Coud Functions in a different directory to the default `./functions` directory. I suggest `./firebaseFunctions`. Then use `@babel/core`, `@babel/cli` and `babel/preset-env` with some npm scripts to transpile to the Cloud Functions server runtime of NodeJS v6.11.1. The output directory is the default `./functions` directory which is created on transpilation in the deploy step (`yarn deploy`).

## Installation
```
git clone https://github.com/jthegedus/firebase-functions-babel-example
cd firebase-functions-babel-example
yarn install
```

### Login to the Firebase CLI
If you are using a global install of the `firebase-tools` CLI then skip to the *Deploy to Firebase* step.

Login to the local `firebase-tools`, this may require you to login prior to use.
```
yarn firebase login
```

## Deploy to Firebase
```
npm deploy
```
N.B.: You will need to connect the project to your Firebase project. Edit the name in [.firebaserc](https://github.com/jthegedus/firebase-functions-babel-example/blob/master/.firebaserc)

## A note on Code Compatibility
Everything was tested on Ubuntu 17.04. If you wish for Windows native support please [submit an issue](https://github.com/jthegedus/firebase-functions-babel-example/issues/new) so we can work on a Windows branch. Please report any macOS errors as I do not have access to a device to test. [My development environment can be found here](https://github.com/jthegedus/dotfiles).
