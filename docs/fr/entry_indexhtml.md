# L'entrée `index.html`

electron-vue utilise [**`html-webpack-plugin`**](https://github.com/ampedandwired/html-webpack-plugin) pour créer `index.html` pour la build de production. Pendant le développement, vous allez trouver un `index.ejs` dans le dossier `src/`. C'est là que vous pourrez effectuer les changements concernant les entrées de votre fichier HTML.

Si vous n'êtes pas familier avec le fonctionnement de ce plugin, alors je vous encourage à jetter un oeil à sa [documentation](https://www.npmjs.com/package/html-webpack-plugin). Mais en résumé, ce plugin va automatiquement injecter les assets de production, incluant `renderer.js` et `styles.css` au fichier `index.html` final minifié.

### `index.ejs` pendant le développement

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title><%= htmlWebpackPlugin.options.title %></title>
    <%= ... %>
  </head>
  <body>
    <div id="app"></div>
    <!-- webpack builds are automatically injected -->
  </body>
</html>
```

### `index.html` en production \(non-minifié\)

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>app</title>
    <link href="styles.css" rel="stylesheet">
  </head>
  <body>
    <div id="app"></div>
    <script type="text/javascript" src="renderer.js"></script>
  </body>
</html>
```

### Au sujet de l'usage des CDNs

Bien que l'usage des assets depuis un CDN peuvent être très bien pour la taille de la build finale de votre application, je vous en déconseille l'usage. La raison principale est qu'en le faisant, vous supposez que l'application aura toujours accès à Internet, et ce n'est pas toujours le cas avec les applications Electron. C'est un problème majeur avec les frameworks CSS comme Bootstrap, et votre application deviendra un truc dégueu sans queue ni tête visuellement.

> "Balek, je veux quand même utiliser un CDN"

Si vous êtes déterminé quand même à utiliser un CDN, vous pouvez le faire en ajoutant les tags à votre fichier `src/index.ejs`. Assurez-vous juste de bien mettre en place un flow UI/UX quand l'application est offline. 

