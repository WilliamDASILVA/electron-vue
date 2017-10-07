# End-to-End Testing

electron-vue utilise les frameworks de test [Spectron](http://electron.atom.io/spectron/) et [Mocha](https://mochajs.org/) \(with [Chai](http://chaijs.com/)\) pour effectuer les tests d'intégration. L'API de Mocha & Chai, incluant `expect`, `should`, et `assert`, sont disponibles dans le scope global.

### Exécution des tests

```bash
# Démarrer Mocha
npm run e2e
```

##### Note

Avant d'exécuter les tests d'intégration, la commande `npm run pack` est appelée pour créer la build de production, qu'ensuite Spectron peut utiliser pendant les tests.

### Structure des fichiers

```
my-project
├─ test
|  ├─ e2e
│  │  ├─ specs/
│  │  ├─ index.js
└─ └─ └─ utils.js
```

**La plupart du temps, vous pouvez ignorer **`index.js`** et vous concentrer uniquement sur **`specs/`**.**

#### `specs/`

Dans ce répertoire se trouveront vos tests. Grâce au pouvoir de `babel-register`, vous avez un accès complet à ES2015.

#### `index.js`

Ce fichier agit comme l'entrée principale à Mocha, et rassemble tous les tests écrits dans `specs/` pour le test.

#### `utils.js`

Ici vous trouverez les fonctions génériques qui vous seront peut-être utiles à travers votre `specs/`. Les fonctions de base incluent `beforeEach` et `afterEach` qui se chargent de la création et destruction du processus d'electron.

### Au sujet de Spectron

Spectron est le framework de test officiel [d'electron](http://electron.atom.io), qui utilise [ChromeDriver](https://sites.google.com/a/chromium.org/chromedriver/) et [WebDriverIO](http://webdriver.io/) pour manipuler les élements du DOM.

#### Utiliser WebDriverIO

Comme dit dans la [documentation de Spectron](https://github.com/electron/spectron#client), l'accès a [WebDriverIO APIs](http://webdriver.io/api.html) peut être fait à travers `this.app.client`. Comme electron-vue utilise Mocha, le contexte de `this` est partagé entre `afterEach`, `beforeEach`, et `it`. À cause de cela, il est important de noter que les arrow functions de ES2015 ne peuvent pas être utilisées dans certaines situations, comme le contexte de `this` sera écrasé \([plus d'information](https://mochajs.org/#arrow-functions)\).
