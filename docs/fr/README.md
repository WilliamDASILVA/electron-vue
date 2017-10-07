![](../images/logo.png)

> Le boilerplate pour créer des applications electron avec VueJS.

[![Status de la build](https://semaphoreci.com/api/v1/simulatedgreg/electron-vue/branches/master/badge.svg)](https://semaphoreci.com/simulatedgreg/electron-vue)

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

[![forthebadge](http://forthebadge.com/images/badges/built-with-love.svg)](http://forthebadge.com) [![forthebadge](http://forthebadge.com/images/badges/uses-js.svg)](http://forthebadge.com) [![forthebadge](http://forthebadge.com/images/badges/makes-people-smile.svg)](http://forthebadge.com)

## Vue d'ensemble

The aim of this project is to remove the need of manually setting up electron apps using vue. electron-vue takes advantage of `vue-cli` for scaffolding, `webpack` with `vue-loader`, `electron-packager` or `electron-builder`, some of the most used plugins like `vue-router`, `vuex`, and so much more.

#### Allez voir la documentation [here](https://simulatedgreg.gitbooks.io/electron-vue/content/index.html).

Ce que vous allez trouver dans ce boilerplate...

* Une structure de projet basique avec **un seul** `package.json`
* Une [documentation](https://simulatedgreg.gitbooks.io/electron-vue/content/) détaillée
* Project scaffolding using [vue-cli](https://github.com/vuejs/vue-cli)
* Ready to use Vue plugins \([axios](https://github.com/mzabriskie/axios), [vue-electron](https://github.com/SimulatedGREG/vue-electron), [vue-router](https://github.com/vuejs/vue-router), [vuex](https://github.com/vuejs/vuex)\)\*
* Installed [vue-devtools](https://github.com/vuejs/vue-devtools) and [devtron](https://github.com/electron/devtron) tools for development
* Ability to easily package your application using [electron-packager](https://github.com/electron-userland/electron-packager) or [electron-builder](https://github.com/electron-userland/electron-builder)\*
* `appveyor.yml` and `.travis.yml` configurations for automated deployments with [electron-builder](https://github.com/electron-userland/electron-builder)\*
* Ability to produce web output for browsers
* Handy [NPM scripts](/npm_scripts.md)
* Use of [webpack](https://github.com/webpack/webpack) and [vue-loader](https://github.com/vuejs/vue-loader) with Hot Module Replacement
* Process restarting when working in electron's `main` process
* HTML/CSS/JS pre-processor support with [vue-loader](https://github.com/vuejs/vue-loader/)
* ES6 with [`stage-0`](https://babeljs.io/docs/plugins/preset-stage-0/) by default
* Use of [`babili`](https://github.com/babel/babili) to remove the need of transpiling completely down to ES5
* ESLint \(with support for [`standard`](https://github.com/feross/standard) and [`airbnb-base`](https://github.com/airbnb/javascript)\)\*
* Unit Testing \(with Karma + Mocha\)\*
* End-to-end Testing \(with Spectron + Mocha\)\*

\*Customizable during `vue-cli` scaffolding

### Commencer

This boilerplate was built as a template for [`vue-cli`](https://github.com/vuejs/vue-cli) and includes options to customize your final scaffolded app. The use of `node@^7` or higher is required. electron-vue also officially recommends the [`yarn`](https://yarnpkg.org) package manager as it handles dependencies much better and can help reduce final build size with `yarn clean`.

```bash
# Installer vue-cli et utiliser le boilerplate
npm install -g vue-cli
vue init simulatedgreg/electron-vue my-project

# Installer les dépendences et démarrer votre application
cd my-project
yarn # ou npm install
yarn run dev # ou npm run dev
```

##### Vous êtes un utilisateur de Windows?

Make sure to check out [**A Note for Windows Users**](https://simulatedgreg.gitbooks.io/electron-vue/content/en/getting_started.html#a-note-for-windows-users) to make sure you have all the necessary build tools needed for electron and other dependencies.

##### Vous souhaitez utiliser Vue 1.x?

Just point to the `1.0` branch. Please note that electron-vue has officially deprecated the usage of `vue@^1`, so project structure, features, and documentation will reflect those changes \([**legacy documentation**](https://github.com/SimulatedGREG/electron-vue/tree/1.0/docs)\).

```bash
vue init simulatedgreg/electron-vue#1.0 my-project
```

### Prochaines étapes

Make sure to take a look at the [documentation](https://simulatedgreg.gitbooks.io/electron-vue/content/). Here you will find useful information about configuration, project structure, and building your app. There's also a handy [FAQs](https://simulatedgreg.gitbooks.io/electron-vue/content/en/faqs.html) section.

## Fait avec electron-vue

Matez un peu les projets incroyables fait avec electron-vue. Vous voulez voir votre projet ci-dessosu? N'hésitez pas à faire une pull-request pour l'ajouter.

* [**Surfbird**](https://github.com/surfbirdapp/surfbird): Un client Twitter fait avec Electron et Vue
* [**Lulumi-browser**](https://github.com/qazbnm456/lulumi-browser): Lulumi-browser est un navigateur léger codé avec Vue.js 2 et Electron
* [**Space-Snake**](https://github.com/ilyagru/Space-Snake): Un jeu de bureau crée avec Electron et Vue.js.
* [**Forrest**](https://github.com/stefanjudis/forrest): An npm scripts desktop client
* [**miikun**](https://github.com/hiro0218/miikun): Un simple éditeur de Markdown
* [**Dakika**](https://github.com/Madawar/Dakika): A minute taking application that makes writing minutes a breeze
* [**Dynamoc**](https://github.com/ieiayaobb/dynamoc): Dynamoc is a GUI client for dynamodb-local, dynalite and AWS dynamodb
* [**Dockeron**](https://github.com/dockeron/dockeron): A dockeron project, built on Electron + Vue.js for Docker
* [**Easysubs**](https://github.com/matiastucci/easysubs): Download subtitles in a very fast and simple way
* [**adminScheduler**](https://github.com/danieltoorani/adminScheduler): An application leveraging electron for cross platform compatibility, Vue.js for lightning fast UI and full-calendar.io to deliver a premium calendar interface.



