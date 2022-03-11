---
layout: page
title: GIT - intro
permalink: git1.html
---

Premier volet du cours sur GIT.

## Questions fondamentales Git

### Qu'est-ce que Git ?

Git est un logiciel de gestion de versions décentralisé. C'est un puissant outil de collaboration, indispensable dans tous les types de projets informatiques.

### D'ou vient GIT

Git a été créé en 2005 par [Linus Torvalds](https://fr.wikipedia.org/wiki/Linus_Torvalds) (le créateur de Linux).

### Que signifie le mot Git ?

Selon Wikipédia: « quand on lui a demandé pourquoi il avait appelé son logiciel “git”, qui est à peu près l'équivalent de “connard” en argot britannique, Linus Torvalds a répondu “je ne suis qu'un sale égocentrique, donc j'appelle tous mes projets d'après ma propre personne. D'abord Linux, puis Git.” ».

### À quoi sert Git ?

- Permet de synchroniser un projet entre plusieurs collaborateurs. 
- Permet de fusionner des modifications de plusieurs personnes.
- Offre un historique précis de toutes les modifications d'un projet. On peut revenir facilement à un état précédent.
- Aide à la collaboration.

Git a été inventé pour gérer des projets informatiques – du code. Mais ses avantages ont aussi été utilisés pour :

- écrire de la documentation
- gérer des documents légaux comme [les textes de loi](http://bundestag.github.io/gesetze/) du gouvernement d'Allemagne
- des données médicales, comme p.ex. [les données Covid](https://github.com/openZH/covid_19) (direction de santé du canton de Zurich)

#### Exemples de ce que Git permet d'éviter

Quand on s'échange par email les versions successives d'un document Word...

![](img/git/final-doc.gif)

Voilà ce que ça donnerait si on nommait ainsi les issues de secours:

![](img/git/file-names-on-fire.jpeg)

C'est pour éviter ces problèmes qu'on a inventé les logiciels de gestion de versions.

#### Ce que Git ne fait pas très bien:

- La gestion de données "binaires", des fichiers audio (WAV, MP3...) ou vidéo (MP4, MOV...).

## Comment fonctionne Git ?

Git est un logiciel pouvant fonctionner en ligne de commande, on lui "parle" en utilisant des commandes, telles que `pull`, `push`, `clone`, `add`, `commit`...

Le principe: 

1. En utilisant des commandes Git, on enregistre des "snapshots" qui conservent l'état du projet à un point précis.
2. On synchronise les modifications locales avec un serveur distant. Git s'occupe de fusionner les modifications.

### La notion de commit

La commande **git commit** est centrale dans Git: c'est cette commande qui crée un nouvel "instantané" de l'état de votre projet, dans son intégralité. 

Comme le dit David Demaree dans *Git for Humans*: 

- Un commit enregistre les modifications apportées aux fichiers figurant dans la base de données de Git: il indique par exemple qu'un fichier est passé de la version A à la version B.
- Chaque commit est autonome: il ne référence pas seulement ce qui a changé, mais aussi tout ce qui compose l'état de votre projet à un moment donné.

### Les états des fichiers

Le livre "*Pro Git*" donne une bonne explication des "trois états" dans lesquels peuvent se trouver les fichiers:

Git gère **trois états** dans lesquels les fichiers peuvent résider : `modifié`, `indexé` et `validé`.

- **Modifié** (*Modified*) signifie que vous avez modifié le fichier mais qu’il n’a pas encore été validé (*committed*).
- **Indexé** (*Staged*) signifie que vous avez marqué un fichier modifié dans sa version actuelle pour qu’il fasse partie du prochain instantané du projet.
- **Validé** (*Committed*) signifie que les données sont stockées en sécurité dans votre base de données locale.

Ceci nous mène aux **trois sections principales** d’un projet Git : le **répertoire de travail** (*working directory*), la **zone d’index** (*staging area*) et le **répertoire Git** (*Git directory*).

![](img/git/areas.png)

- Le **répertoire de travail** (*working tree* ou *working directory*) : votre espace de travail, sur votre ordinateur. En langage Git: "c'est une extraction unique d’une version du projet. Ces fichiers sont extraits depuis la base de données compressée dans le répertoire Git et placés sur le disque pour pouvoir être utilisés ou modifiés". 
- La **zone d’index** (*staging area*). On l’appelle aussi des fois la zone de préparation. On y ajoute des fichiers avec la commande "git add": ils sont désormais indexés. Cette zone stocke tout ce qui fera partie du prochain instantané (commit). La zone d'index n'est pas synchronisée ni partagée, elle n'existe que sur votre ordinateur.
- Le **répertoire Git** (*Git directory*) est l’endroit où Git stocke les méta-données et la base de données des objets de votre projet. C’est la partie la plus importante de Git, et c’est ce qui est copié lorsque vous clonez un dépôt depuis un autre ordinateur.

On pourrait encore ajouter deux sections:

- Le **répertoire Git distant** : il s'agit du serveur, par exemple sur Github (ou Gitlab, Framagit). 
- Le **stash** : des modifications "mises de côté". Permet de sauvegarder temporairement des changements apportés à votre copie de travail pour que vous puissiez effectuer d'autres tâches, puis revenir et les réappliquer par la suite.

L’utilisation standard de Git se passe comme suit :

1. vous modifiez des fichiers dans votre répertoire de travail (état = modifié).
2. vous **indexez** (*stage*) les fichiers modifiés, ce qui ajoute des instantanés de ces fichiers dans la zone d’index (état = indexé).
3. vous **validez** (*do a commit*), ce qui a pour effet de basculer les instantanés des fichiers de l’index dans la base de données du répertoire Git (état = validé).

### Quelques termes et commandes

Les clips vidéo proviennent de la présentation *[Git is Science-Fiction](https://wordpress.tv/2015/12/13/morten-rand-hendriksen-github-for-the-rest-of-us/)*, par Morten Rand-Hendriksen.

`repository`

C'est un dossier de travail géré avec Git. Le dossier où se trouvent tous les fichiers. Il peut s'agir d'un repository **local** (sur votre ordinateur) ou **distant** (*remote*) - par exemple sur Github.

<video width="640" height="360" controls>
  <source src="video/repo.mp4" type="video/mp4">
</video>

`git commit`

Ajoute un **commit** (instantané) comprenant toutes les modifications indexées.

<video width="640" height="360" controls>
  <source src="video/git-commit.mp4" type="video/mp4">
</video>

`git branch <nombranche> [<commit>]`

Crée une **branche** sous ce nom qui démarre au commit actuel (ou au commit que vous aurez spécifié, si vous avez indiqué un ID de commit).

<video width="640" height="360" controls>
  <source src="video/git-branch.mp4" type="video/mp4">
</video>

`git merge <autrebranche>`

**Fusionne** "autrebranche" dans la branche actuelle, s'il n'y a pas de conflit. En cas de conflit, vous devez le résoudre (décider quelle version conserver).

<video width="640" height="360" controls>
  <source src="video/merge-conflict.mp4" type="video/mp4">
</video>

#### push, pull, fetch

`git push`

Pousse l'état actuel de "nombranche" dans le repository distant.

`git fetch`

Copie tout le contenu du repository distant vers votre copie locale.

<video width="640" height="360" controls>
  <source src="video/push-pull.mp4" type="video/mp4">
</video>

`git pull`

Copie tout le contenu du repository distant vers votre copie locale (comme `fetch`), **et** tente de le **fusionner** (`merge`) dans votre branche actuelle.

`readme.md`

Le README est un fichier standard se trouvant à la base de votre repository. Github va afficher automatiquement son contenu. Le contenu peut être écrit en syntaxe "[Markdown](https://cours-web.ch/markdown/)", d'où la terminaison "md".

`.gitignore`

Permet de spécifier des fichiers qui doivent être ignorés - des images TIFF, PSD, des fichiers temporaires, des fichiers cachés de MacOS...

## Liens utiles: 

Support de cours dédié à GIT: [https://cours-web.ch/git/](https://cours-web.ch/git/)

Une vidéo d'introduction: *Débuter avec Git et Github en 30 min*

<iframe width="560" height="315" src="https://www.youtube.com/embed/hPfgekYUKgk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>