<h1>GIT: COMMENT NOMMER SES COMMITS ? </h1>

<i>
 Tu utilises Git et tu te poses des questions sur comment nommer tes commits, cet article est fait pour toi. 

 Cet article est une adaptation écrite de mes recherches personnelles concernant ce sujet. Au moment de cet article, je suis en formation de développement web chez The Hacking Project. 
</i>
<hr>
<h2>Git… C’est Super !</h2>
<hr>
Je suppose que depuis que tu utilises git, tu as réalisé qu’il est un outil indispensable pour nos projets, une fois que l’on a pris l’habitude de l’utiliser sur quelques projets, on ne peut plus s’en passer
Git est utilisé pour : 
<br>


<ul>
 <li><b> Gérer les différentes versions et étapes du projet (même sans connexion) </b></li>
 <li><b> Développer des fonctionnalités en parallèle</b></li>
 <li><b> Revenir en arrière, à une version précise</b></li>
 <li><b> Collaborer sur un même projet</b></li>
</ul>

Il est vrai que ces quatre points ne donnent qu’une envie, c’est de l’utiliser. Je le vous recommande si ce n’est pas déjà fait.

Cependant, comme pour n’importe quel outil, l’utiliser c’est bien, mais l’utiliser avec de <b>bonnes pratiques</b>, c’est mieux. 
Nous allons nous attarder sur le premier point : <b>Gérer les différentes versions/étapes du projet</b>

Pour sauvegarder chaque étape du projet, nous faisons ce qui s’appelle <b>un commit</b>. <br>
Cela permet d’enregistrer les modifications effectuées depuis le dernier commit, et de pouvoir y revenir par la suite, imaginons, ce que l’on a fait après ce commit ne nous convient pas, on peut y revenir sans devoir spam le <b>Ctrl + Z</b>. Ca c’est super !  <br>
Lorsque l’on <b>commit</b>, le commit se voit attribuer automatiquement une sorte de <b>matricule</b> comme par exemple`18f801d`. Celui-ci est très utile pour pouvoir lui indiquer dans notre terminal, quel commit nous visons lorsque nous tapons telle ou telle commande, `$ git reset 18f801d` par exemple. Imagine-nous avec des dizaines ou même des centaines de commits ayant uniquement ce matricule pour les différencier, ce serait un enfer. <br>
Mais heureusement, pour que l’on puisse reconnaître cette version rapidement, on peut nommer nos commits. C’est très pratique, mais parfois, je ne sais pas pour toi, il m’est difficile de trouver un nom signification à mes commits. Le nommer juste pour le nommer ça ne sert à rien :  <br>
![historique-moche](https://user-images.githubusercontent.com/59894954/82759121-7a1fc800-9deb-11ea-92f0-1f2c231b7542.png)

<hr>
<h2>Comment m’y prendre ?</h2>
<hr>
<br>
J’ai alors fait mes petites recherches. 

Ce qui nous est recommandé est d’établir des <b>conventions</b> de nommage pour nos commits. Dans le monde professionnel, lorsque l’on arrivera sur un projet déjà en cours, les conventions seront déjà pensées et utilisées, il suffira de les suivre. 
 <br>
 Mais qu’en est-il des projets que l’on commence actuellement ? 
 <br>
Des projets sur lesquelles l’on travaille peut-être en groupe, et sur lesquelles il nous faudrait effectivement des conventions solides pour que chacun et chacune puisse nommer les commits de la même façon pour mieux s’y retrouver. Ou même dans le cas où l’on est seul, cela nous servira pour s’y retrouver ou pour les futurs arrivant sur le projet. 

Alors, comme dit ci-dessus, dans le monde professionnel, on va devoir suivre des conventions déjà normées, alors pourquoi ne pas commencer dès maintenant. Allons voir sur <b>Github</b> les historiques de commits de différents projets. 

Il y a quelques jours, j'ai regardé une vidéo d’un développeur et youtubeur nommé Louistiti dans laquelle il parlait d’un de ses projets : Leon, un assistant personnel open source. 

Allons y jetter un oeil, pour voir quelles sont ses conventions utilisées sur son projet [Leon](https://github.com/leon-ai/leon).

L’organisation est cool, c’est directement plus lisible qu’un historique mal organisé. 

![leongithub](https://user-images.githubusercontent.com/59894954/82759170-e995b780-9deb-11ea-85de-37b7489f6ce2.png)


Il utilise un squelette tel que celui-ci : 
<p> <b>
 type(portée): sujet <br>
  description<br>
 footer
  </b>
</p>

C’est un squelette que l’on retrouve un peu partout sur Github.
Avec les règles suivantes : 

<ul>
 <li><b>Type</b> définit le type de commit
  <ul>
   <li><b>build:</b> Système de build (example : gulp, webpack, npm)</li>
   <li><b>ci:</b> Intégration continue (example scopes: Travis, Circle, BrowserStack, SauceLabs)</li>
   <li><b>docs:</b> Documentation</li>
   <li><b>feat:</b> Ajout d'une fonctionnalité</li>
   <li><b>fix:</b> Correction de bogue</li>
   <li><b>perf:</b> Amélioration des performances</li>
   <li><b>refactor:</b> Changement du code qui ne change rien au fonctionnement</li>
   <li><b>style:</b> Changement du style du code (sans changer la logique)</li>
   <li><b>test:</b> Modification des tests</li>
  </ul>
 </li>
 <li><b>Portée</b> définit quelle partie de votre librairie / application est affectée par le commit (cette information est optionnelle)</li>
 <li><b>Sujet</b> contient une description succinte des changements
  <ul>
    <li>En utilisant l'impératif présent ("change", et non pas "changed" ou "changes")</li>
    <li>Sans majuscule au début</li>
    <li>Pas de "." à la fin de la description</li>
   </ul>
 </li>
 <li><b>Description</b> permet de détailler plus en profondeur les motivations derrière le changement. Les règles sont les mêmes que pour la partie Sujet. </li>
  <li><b>Footer</b> contient les changements importants (Breaking Changes) et les références à des issues GitHub / GitLab ou autre.   </li>
</ul>


Les règles sont censées recouvrir un grand nombre de situations, peut-être même toutes les situations.

<hr>
<h2>Comment mettre une description  ? Ou même un footer ?</h2>
<hr>
<br>
C'est une question que je me pose.
Puisque si tu as appris à utiliser Git comme moi, tu sais que la commande permettant de commit est la suivante :


![command-commit](https://user-images.githubusercontent.com/59894954/82759239-60cb4b80-9dec-11ea-85d1-138de06b5fc6.png)

Le problème est que lorsque l’on souhaite mettre les différentes parties de la conventions, comment faire ? J’ai trouvé cette commande sur Stack Overflow : 

![command-commit-complet](https://user-images.githubusercontent.com/59894954/82759244-688af000-9dec-11ea-911c-95d94c80e70c.png)


On en arrive donc à avoir un commit qui ressemble à cela sur github. 
![commit-github](https://user-images.githubusercontent.com/59894954/82759254-7c365680-9dec-11ea-9591-29384c35a771.png)


Voilà, nous sommes désormais tous les deux armés pour avoir un historique professionnel. C’est quelque chose qui peut paraître banal au premier abort, mais l’organisation est importante dans le monde du dévelopment web. Et ces petites recherches vont permettre à toi et moi d’avoir un projet organisé. 

<hr>
<h2>Aller plus loin :</h2> 
<hr>
<br>
<a href="https://github.com/angular/angular/blob/master/CONTRIBUTING.md" style="diplay: inline;">- Angular</a> est une des inspirations concernant les conventions de nommage des commits.


Pour aller plus loin dans ton utilisation de git, je te propose d’aller te renseigner si ce n’est pas déjà fait sur les conventions d’utilisation des branches, on n’arrête jamais avec les conventions. 

J’ai trouvé cette <a href="https://github.github.com/training-kit/downloads/fr/github-git-cheat-sheet.pdf" style="diplay: inline;"> cheatsheet</a> qui peut t’aider dans ton utilisation de git. 


C’est article est une mission pour la formation The Hacking Project. 


<h3>Mes sources :</h3>
<br>
-- Grafikart a fait une <a href="https://www.grafikart.fr/tutoriels/nommage-commit-1009" style="diplay: inline;">vidéo</a> sur comment nommer ses commits.

-- Le projet d'exemple utilisé <a href="https://github.com/leon-ai/leon" style="diplay: inline;">Leon</a>. 

-- Cet <a href="https://buzut.net/git-bien-nommer-ses-commits/" style="diplay: inline;">article</a> sur le nommage des commits.

-- Cet <a href="https://delicious-insights.com/fr/articles/git-workflows-conventions/" style="diplay: inline;">article</a> sur le workflow git.

<h3> Contexte : </h3>

-- Mission réalisée durant la formation <a href="https://www.thehackingproject.org/" style="diplay: inline;">The Hacking Project</a>

<h3> 👤  Auteur(s) : </h3>

-- Chris Blassiaux → 
[<img src="http://pngimg.com/uploads/github/github_PNG40.png" width="25" >](https://github.com/ChrisBlassiaux )[<img src="https://user-images.githubusercontent.com/59894954/79057092-9281bc00-7c5d-11ea-9392-783b52f9dae4.png" width="25" >](https://chrisb.fr/)  [<img src="https://www.crossfitchelles.com/wp-content/uploads/2019/03/linkedin-icon-logo-png-transparent.png" width="25" >  ](https://www.linkedin.com/in/christopher-blassiaux-802891198/)  [<img src="https://upload.wikimedia.org/wikipedia/commons/4/45/New_Logo_Gmail.svg" width="25" >](chrisblassiaux@gmail.com)   [<img src="https://www.toomed.com/blog/wp-content/uploads/2018/09/new-instagram-logo-png-transparent.png" width="25" > ](https://www.instagram.com/chris.blassiaux/) 


