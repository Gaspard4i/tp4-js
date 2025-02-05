<img src="images/readme/header-small.jpg" >

# A. Préparatifs <!-- omit in toc -->

## Sommaire <!-- omit in toc -->
- [A.1. Récupération du projet](#a1-récupération-du-projet)
- [A.2. Lancement de l'application](#a2-lancement-de-lapplication)
- [A.3. Solution du TP3](#a3-solution-du-tp3)

## A.1. Récupération du projet

**Ce repo contient une solution commentée du précédent TP.** <br>
Il va vous servir de base pour ce nouveau TP.

1. **Commencez par faire un fork du TP en vous rendant directement sur https://gitlab.univ-lille.fr/js/tp4/-/forks/new**

	Pour le `namespace` choisissez de placer le fork dans votre profil utilisateur.\
	Pour `Visibility Level` sélectionnez le **mode "private"**

	> ⚠️ _Comme ce nouveau TP est lui-même un fork du TP précédent, vous êtes **obligé·e** de passer par le lien que j'ai fourni ci-dessus, le bouton "Fork"/"Créer une divergence" ne fonctionnera pas dans ce cas et vous redirigera bêtement sur votre propre fork du précédent TP._

2. **Ajoutez votre encadrant·e de TP en tant que "reporter" pour qu'il/elle ait accès à votre code :**
	- dans le menu de gauche, cliquez sur **`Manage`** &gt; **`Members`** (`Gestion` &gt; `Membres` _si vous êtes sur la VF de gitlab_)
	- cliquez sur le bouton en haut à droite **`"Invite members"`** (`Inviter des membres`)
	- entrez comme **nom d'utilisateur** celui de votre encadrant·e de TP (`@patricia.everaere-caillier`, `@catherine.verbrugge` ou `@thomas.fritsch`)
	- ... et `"reporter"` comme **rôle**.

3. **Ouvrez ensuite un terminal et récupérez les fichiers de ce TP grâce à Git en clonant votre fork dans un dossier de votre choix** (_dans mon exemple `chemin/vers/votre/workspace/tp4`_) :
	```bash
	cd chemin/vers/votre/workspace
	git clone https://gitlab.univ-lille.fr/<votre-username>/tp4.git
	```

	> <details><summary>⚠️ <em>Si vous êtes sous <strong>Windows</strong> attention aux slashs...</em></summary>
	>
	> _ici je clone dans le dossier `chemin/vers/votre/workspace/tp3`. **Si vous êtes sous Windows faites attention aux slashs dans le chemin du dossier** : utilisez **Git bash** (qui comprend cette syntaxe) ou si vous tenez vraiment à utiliser **cmd** ou **powershell** pensez à adapter la commande en les remplaçant par des antislash `\` !_
	> </details>

	> <details><summary>ℹ️ <em>Si ce n'est pas déjà fait, il faut que vous renseigniez un mot de passe dans votre compte gitlab</em></summary>
	>
	> _Rendez-vous dans [`Preferences` > `Password`](https://gitlab.univ-lille.fr/-/profile/password/edit) pour pouvoir cloner en http._
	> </details>

	> <details><summary>ℹ️ <em>Si vous préférez <strong>cloner en SSH</strong>...</em></summary>
	>
	> _...pour ne pas avoir à taper votre mot de passe à chaque fois que vous clonerez un TP, renseignez votre clé SSH dans votre [compte utilisateur gitlab](https://gitlab.univ-lille.fr/-/profile/keys) et clonez à partir de cette URL : `git@gitlab-ssh.univ-lille.fr:votre-username/tp4.git`_
	> </details>


4. **Ouvrez le projet dans VSCodium/VSCode** (pour les différentes façon d'ouvrir le projet relisez les [instructions du TP1](https://gitlab.univ-lille.fr/js/tp1/-/blob/main/A-preparatifs.md#a5-ouvrir-le-projet-dans-vscodium) )
	```bash
	codium chemin/vers/votre/workspace/tp4
	```

5. **Installez les paquets npm nécessaires au projet** notamment le compilateur [Babel](https://babeljs.io).<br>
	Ouvrez un terminal intégré à VSCodium (<kbd>CTRL</kbd>+<kbd>J</kbd> *(PC)* / <kbd>CMD</kbd>+<kbd>J</kbd> *(Mac)*) et tapez juste :
	```bash
	npm i
	```

	> <details><summary>ℹ️ <em>Pourquoi on ne dit pas à <code>npm install</code> quels sont les paquets qu'on veut installer ?</em></summary>
	>
	> _Effectivement jusque là on a toujours utilisé `npm install nom-de-la-lib` quand on voulait installer un paquet en particulier (`npm install @babel/core`, `@babel/cli`, etc.)._
	>
	> _Là on ne précise pas les paquets à installer parce que npm va pouvoir les déterminer **automatiquement** grâce à notre fichier `package.json` et plus particulièrement aux sections `"dependencies"` et `"devDependencies"` qui indiquent quels sont les paquets qui ont été installés précédemment._
	>
	> _Cette technique permet à une personne qui rejoint le projet d'installer en une seule commande tous les paquets (les dépendances) dont a besoin notre projet (d'où l'importance de le versionner)._ \
	> **Magique !** 🙌
	> </details>

## A.2. Lancement de l'application

Dans le TP précédent nous avons [configuré webpack pour activer le Live Reload](https://gitlab.univ-lille.fr/js/tp3/-/blob/main/C-modules.md#c6-webpack-live-reload). \
La commande pour lancer le projet a donc changé par rapport aux précédents TPs : plus besoin de deux commandes (_1 pour lancer un serveur http, 1 autre pour compiler le code avec webpack et babel_), on peut maintenant lancer tout en une seule commande grâce à webpack-dev-server :

1. **Lancez webpack dev server** dans un terminal intégré de VSCodium (<kbd>CTRL</kbd>+<kbd>J</kbd> *(PC)* / <kbd>CMD</kbd>+<kbd>J</kbd> *(Mac)*) :
	```bash
	npm start
	```

2. **Pour afficher votre site, plutôt que d'ouvrir vous-même votre navigateur, utilisez la fonctionnalité de debug dans VSCode testée lors du précédent TP :**

	> _Si vous n'aviez pas pu faire cette partie pour des questions de compatibilité de Firefox, je vous invite à :_
	> 1. _suivre le tutoriel spécifique à Firefox ici : https://gitlab.univ-lille.fr/js/tp3/-/blob/main/B-debug-vscode-firefox.md_
	> 2. _prendre connaissance des différentes possibilités offertes par le debug dans vscode ici : https://gitlab.univ-lille.fr/js/tp3/-/blob/main/B-debug-vscode.md#b2-utilisation-du-mode-debug_

	Pour lancer votre site en mode "debug dans vscode", tapez <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>P</kbd> puis sélectionnez "Debug: Select and start debugging".

	Choisissez le navigateur que vous souhaitez lancer (Firefox ou Chrome), une nouvelle fenêtre de votre navigateur doit s'ouvrir (on considérera pour la suite que c'est Chrome que vous avez choisi).

4. **Vérifiez dans le navigateur qui s'est ouvert que la page `index.html` s'affiche correctement** :

	> <details><summary>🚧 <em>La page ne s'affiche pas correctement ?</em></summary>
	>
	> _Vérifiez que vous avez bien lancé votre serveur webpack `npm start` dans **le bon dossier** (c'est-à-dire celui où se trouve le fichier `index.html`)._
	>
	> _Vérifiez aussi dans la `Debug Console` de vscode qu’il n'y a pas d'erreur JS lorsque la page se charge._
	> </details>

	<img src="images/readme/screen-00.png" >


## A.3. Solution du TP3

**Avant de vous lancer dans ce TP, prenez 5 à 10 minutes pour lire le code contenu dans le dossier `/src`** et comparez le avec votre code du précédent TP.

**C'est important de bien comprendre le code qui vous est fourni car vous allez avoir à le modifier dans ce TP** : si des points ne sont pas clairs interrogez votre encadrant.e de TP !

**Attention : si vous n'aviez pas eu le temps de terminer le TP3**, portez une attention toute particulière aux classes :
- `Router`
- `View`
- et `GameListView`

Si vous n'aviez pas terminé le TP3, voici également une fonctionnalité nouvelle de JSteam : la History API et le deep linking.

Ces deux fonctionnalités permettent à votre code JS de changer l'adresse dans la barre d'adresse **SANS rechargement de page** et d'utiliser également les boutons précédent/suivant du navigateur : essayez un peu les liens du menu et la navigation avec les boutons précédent/suivant du navigateur.

<img src="images/readme/history-final.gif" />

Le code de cette fonctionnalité se trouve à la fin du `main.js` :
```js
// chargement de la vue initiale selon l'URL demandée par l'utilisateur.rice (Deep linking)
Router.navigate(window.location.pathname, true);
// gestion des boutons précédent/suivant du navigateur (History API)
window.onpopstate = () => Router.navigate(document.location.pathname, true);
```

et dans la méthode `Router.navigate` :
```js
// History API : ajout d'une entrée dans l'historique du navigateur
// pour pouvoir utiliser les boutons précédent/suivant
if (!skipPushState) {
	window.history.pushState(null, null, path);
}
```

## Étape suivante <!-- omit in toc -->
Maintenant que tout est clair et que votre site est lancé, passons au premier exercice : [B. Charger un fichier statique](B-fichier-statique.md)