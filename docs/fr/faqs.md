# FAQs

* [Pourquoi j'ai une page blanche quand je fais `npm run dev`?](#why-is-my-electron-app-blank-after-running-npm-run-dev)
* [Why does my electron app show a file explorer?](#why-does-my-electron-app-show-a-file-explorer)
* [Why is `vue-devtools`/`devtron` missing?](#why-is-vue-devtoolsdevtron-missing)
* [Where do I put Static Assets?](#where-do-i-put-static-assets)
* [Why did `npm run lint` end with an error?](#why-did-npm-run-lint-end-with-an-error)
* [Why can't I load my app in a web browser?](#why-cant-i-load-my-app-in-a-web-browser)
* [How do I import `jquery`?](#how-do-import-jquery)
* [How can I debug the `main` process?](#how-can-i-debug-the-main-process)

---

## Pourquoi j'ai une page blanche quand je fais `npm run dev`?

#### TL;DR

Assurez-vous de ne pas avoir un **proxy** de configuré qui pourrait altérer le fonctionnement de `webpack-dev-server`.

## Pourquoi mon application electron m'affiche un explorateur de fichier?

#### TL;DR

Votre fichier `src/renderer` contient une ou des erreurs. Vérifiez la console, corrigez les erreurs, puis rafraichissez electron avec la commande `CommandOrControl+R`.

##### Réponse un peu plus longue

If error\(s\) are present in you `src/renderer` this creates conflicts with ESLint on first run. In turn, an INVALID webpack `renderer.js` is produced which interrupts `HtmlWebpackPlugin` from creating `index.html`. Since `webpack-dev-server` doesn't have the `index.html` ready to serve, the server falls back to the file explorer.

## Pourquoi il me manque `vue-devtools`/`devtron`?

Make sure to close and reopen the developer tools panel on first launch if they are missing. Also check your terminal check for any error messages that may occur during installation.

## Où j'ajoute mes assets statiques?

[**Using Static Assets**](/using-static-assets.md)

## Pourquoi `npm run lint` s'est terminé en produisant des erreurs?

The default nature of eslint is to print linting errors to console, and if there is any found the script will end with a non-zero exit \(which produces npm errors\). This is normal behavior.

## Pourquoi je ne peux pas ouvrir mon application sur un navigateur web?

[\#195](https://github.com/SimulatedGREG/electron-vue/issues/195)

## Comment j'importe `jquery`?

If you are wanting to use `bootstrap`, I'm going to have to stop you right there. Using both `vue` and `jquery` in the same environment is a bad practice and leads to the two frameworks colliding with each other. I would highly recommend using a `bootstrap` alternative that uses `vue` for its JavaScript functionality. Some recommendations include [`bootstrap-vue`](https://github.com/bootstrap-vue/bootstrap-vue) and [`vue-strap`](https://github.com/yuche/vue-strap). For whatever reason you must use `jquery`, seek guidance from `webpack`'s documentation about the `ProvidePlugin` or see [\#192](https://github.com/SimulatedGREG/electron-vue/issues/192).

## Comment puis-je déboguer le processus `main`?

En utilisant `electron@^1.7.2`, vous pouvez ouvrir Google Chrome, dans `chrome://inspect`, et ouvrir le processus electron à distance pendant que votre application tourne en mode développement.

[Documentation d'Electron](https://github.com/electron/electron/blob/master/docs/tutorial/debugging-main-process.md)

