#GIT - COMMENT NOMMER SES COMMITS ?

> Tu utilises Git et tu te poses des questions sur comment nommer tes commits, cet article est fait pour toi. 

> Cet article est une adaptation écrite de mes recherches personnelles concernant ce sujet. Au moment de cet article, je suis en formation de développement web chez The Hacking Project. 

Git… C’est Super ! 
Je suppose que depuis que tu utilises git, tu as réalisé qu’il est un outil indispensable pour un projet, une fois que l’on a pris l’habitude de l’utiliser sur quelques projets, on ne peut plus s’en passer
Git est utilisé pour : 
*Gérer les différentes versions et étapes du projet (même sans connexion)
*Développer des fonctionnalités en parallèle
*Revenir en arrière, à une version précise
*Collaborer sur un même projet

Il est vrai que ces quatre points ne donnent qu’une envie, c’est de l’utiliser. Je le vous recommande si ce n’est pas déjà fait.

Cependant, comme pour n’importe quel outil, l’utiliser c’est bien, mais l’utiliser avec de bonnes pratiques, c’est mieux. 
Nous allons nous attarder sur le premier point : Gérer les différentes versions/étapes du projet

Pour sauvegarder chaque étape du projet, nous faisons ce qui s’appelle `un commit`. Cela permet d’enregistrer les modifications effectuées depuis le dernier commit, et de pouvoir y revenir par la suite, imaginons, ce que l’on a fait après ce commit ne nous convient pas, on peut y revenir sans devoir spam le Ctrl + Z. Ca c’est super ! 
Lorsque l’on ‘commit’, le commit se voit attribuer automatiquement une sorte de matricule comme par exemple`18f801d`. Celui-ci est très utile pour pouvoir lui indiquer dans notre terminal, quel commit nous visons lorsque nous tapons telle ou telle commande, `$ git reset 18f801d` par exemple. Imagine-nous avec des dizaines ou même des centaines de commits ayant uniquement ce matricule pour les différencier, ce serait un enfer.
Mais heureusement, pour que l’on puisse reconnaître cette version rapidement, on peut nommer nos commits. C’est très pratique, mais parfois, je ne sais pas pour toi, il m’est difficile de trouver un nom signification à mes commits. Le nommer juste pour le nommer ça ne sert à rien : 
![historique-moche](https://user-images.githubusercontent.com/59894954/82759121-7a1fc800-9deb-11ea-92f0-1f2c231b7542.png)

Comment m’y prendre ? J’ai alors fait mes petites recherches. 

Ce qui nous est recommandé est d’établir des conventions de nommage pour nos commits. Dans le monde professionnel, lorsque l’on arrivera sur un projet déjà en cours, les conventions seront déjà pensées et utilisées, il suffira de les suivre. Mais qu’en est-il des projets que l’on commence actuellement ? Des projets sur lesquelles l’on travaille peut-être en groupe, et sur lesquelles il nous faudrait effectivement des conventions solides pour que chacun et chacune puisse nommer les commits de la même façon pour mieux s’y retrouver. Ou même dans le cas où l’on est seul, cela nous servira pour s’y retrouver ou pour les futurs arrivant sur le projet. 

Alors, comme dit ci-dessus, dans le monde professionnel, on va devoir suivre des conventions déjà normées, alors pourquoi ne pas commencer dès maintenant. Allons voir sur Github les historiques de commits de différents projets. 

Quelques jours avant mes recherches, j’avais regardé une vidéo d’un développeur et youtubeur nommé Louistiti dans laquelle il parlait d’un de ses projets : Leon, un assistant personnel open source. 

Allons y jetter un oeil, pour voir quelles sont ses conventions utilisées sur son projet [Leon](https://github.com/leon-ai/leon).

L’organisation est cool, c’est directement plus lisible qu’un historique mal organisé. 

![leongithub](https://user-images.githubusercontent.com/59894954/82759170-e995b780-9deb-11ea-85de-37b7489f6ce2.png)


Il utilise un squelette tel que celui-ci : 
<type>(<portée>): <sujet>
<description>
<footer>

C’est un squelette que l’on retrouve un peu partout sur Github.
Avec les règles suivantes : 

*Type définit le type de commit
  *build: Système de build (example : gulp, webpack, npm)
  *ci: Intégration continue (example scopes: Travis, Circle, BrowserStack, SauceLabs)
  *docs: Documentation
  *feat: Ajout d'une fonctionnalité
  *fix: Correction de bogue
  *perf: Amélioration des performances
  refactor: Changement du code qui ne change rien au fonctionnement
  *style: Changement du style du code (sans changer la logique)
  *test: Modification des tests
*Portée définit quelle partie de votre librairie / application est affectée par le commit (cette information est optionnelle)
*Sujet contient une description succinte des changements
  *En utilisant l'impératif présent ("change", et non pas "changed" ou "changes")
  *Sans majuscule au début
  *Pas de "." à la fin de la description
*Description permet de détailler plus en profondeur les motivations derrière le changement. Les règles sont les mêmes que pour la partie Sujet.
*Footer contient les changements importants (Breaking Changes) et les références à des issues GitHub / GitLab ou autre.

Les règles sont censées recouvrir un grand nombre de situations, peut-être même toutes les situations.

Une question que je me pose : Comment mettre une description  ? Ou même un footer ? 
Puisque si tu as appris à utiliser Git comme moi, tu sais que la commande permettant de commit est la suivante :

![command-commit](https://user-images.githubusercontent.com/59894954/82759239-60cb4b80-9dec-11ea-85d1-138de06b5fc6.png)

Le problème est que lorsque l’on souhaite mettre les différentes parties de la conventions, comment faire ? J’ai trouvé cette commande sur Stack Overflow : 

![command-commit-complet](https://user-images.githubusercontent.com/59894954/82759244-688af000-9dec-11ea-911c-95d94c80e70c.png)


On en arrive donc à avoir un commit qui ressemble à cela sur github. 
![commit-github](https://user-images.githubusercontent.com/59894954/82759254-7c365680-9dec-11ea-9591-29384c35a771.png)


Voilà, nous sommes désormais tous les deux armés pour avoir un historique professionnel. C’est quelque chose qui peut paraître banal au premier abort, mais l’organisation est importante dans le monde du dévelopment web. Et ces petites recherches vont permettre à toi et moi d’avoir un projet organisé. 


###Aller plus loin : 
[Angular](https://github.com/angular/angular/blob/master/CONTRIBUTING.md) est une des inspirations concernant les conventions de nommage des commits.


Pour aller plus loin dans ton utilisation de git, je te propose d’aller te renseigner si ce n’est pas déjà fait sur les conventions d’utilisation des branches, on n’arrête jamais avec les conventions. 

J’ai trouvé cette [cheatsheet](https://github.github.com/training-kit/downloads/fr/github-git-cheat-sheet.pdf) qui peut t’aider dans ton utilisation de git. 


C’est article est une mission pour la formation The Hacking Project. 


###Mes sources :
Leur donner une description et mette autrement les liens 
https://www.grafikart.fr/tutoriels/nommage-commit-1009
https://buzut.net/git-bien-nommer-ses-commits/
https://delicious-insights.com/fr/articles/git-workflows-conventions/
https://github.com/leon-ai/leon


Auteur : ChrisBlassiaux
