# Débogage

### Processus principal

Quand vous exécutez votre application en mode développement, vous avez peut-être remarqué le message du processus principal `main`, indiquant un débogage distant (remote debugger). Depuis la sortie de `electron@^1.7.2`, le remote debugging à travers l'Inspect API a été introduit et peut facilement être accessible en ouvrant le lien fourni avec Google Chrome, ou à travers un autre debugger qui peut s'attacher à distance au processus en utilisant le port par défaut (5858), comme Visual Studio Code.

```bash
┏ Electron -------------------

  Debugger listening on port 5858.
  Warning: This is an experimental feature and could change at any time.
  To start debugging, open the following URL in Chrome:
      chrome-devtools://devtools/bundled/inspector.html?experiments=true&v8only=true&ws=127.0.0.1:5858/22271e96-df65-4bab-9207-da8c71117641

┗ ----------------------------
```

### Production Builds

###### Note

Même s'il est possible de déboguer votre application en production, sachez que le code en production est minifié et largement illisible comparé à ce que vous pouvez trouver pendant le développement.

##### Processus `renderer`

Il n'y a pas une si grande différence ici que lors du développement. Vous pouvez simplement invoquer les outils de développement en utilisant [`BrowserWindow` APIs](https://electron.atom.io/docs/api/web-contents/#contentsopendevtoolsoptions). En utilisant le setup initial de electron-vue, vous pouvez ajouter ce petit bout de code à l'intérieur de `src/main/index.js`, juste après la création de `new BrowserWindow`, pour forcer le dev tools à s'ouvrir.

```js
mainWindow.webContents.openDevTools()
```

##### Processus `main`

Similaire à ce qui a été mentionné au dessus, vous pouvez attacher un débogeur externe au processus `main` pour déboguer à distance votre application. Pour activer le débogeur en production, vous pouvez ajouter le bout de cote suivant après l'import de `app`, à l'intérieur de `src/main/index.js`. Puis vous pouvez naviguer dans Google Chrome sur `chrome://inspect` et vous connecter.

```js
app.commandLine.appendSwitch('inspect', '5858')
```
