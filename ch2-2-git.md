---
layout: page
title: GIT - suite
permalink: git2.html
---

Deuxième volet du cours sur GIT.

## Utilisation de Git

### La profession du Type Design (design de fontes typographiques)

Git est très utilisé dans le domaine du design typographique. Exemples: chez Google Fonts, chaque fonte est gérée dans Github. Des fonderies digitales (Velvetyne, OSP) ont souvent recours à Git pour le versionnage:

- Velvetyne Type Foundry: https://www.velvetyne.fr/
- Dépôt de la fonte Compagnon: https://gitlab.com/velvetyne/compagnon
- Dépôt de la fonte Façade: https://github.com/eleonorefines/Facade-font
- Open Source Publishing (OSP): https://osp.kitchen/foundry/
- Dépôt de la fonte Google Fonts Space Grotesk: https://github.com/floriankarsten/space-grotesk

## Petits détails: README et .gitignore

### Le README

Ce fichier permet d'avoir une "Page de présentation" sur Github. Voir les exemples des fontes Façade et Space Grotesk ci-dessus.

Il faut créer un fichier nommé README.md. Le formatage se fait dans la syntaxe Markdown - voir [la documentation Markdown](https://cours-web.ch/markdown/).

### Le .gitignore

Ce fichier permet de désigner tout ce que Git doit "ignorer".  

Exemple, [le .gitignore du Repository de Space Grotesk](https://github.com/floriankarsten/space-grotesk/blob/master/.gitignore):

```
# file manager empty files
.DS_Store
.empty
.sparkleshare
# temporary files
*(Autosaved).glyphs
*.vfbak
# minisite files
/docs/node_modules
/docs/package-lock.json
```


## Sujet important: les branches

Fonctionnalité très importante: Git vous permet de créer des branches, qui sont des "versions parallèles" d'un projet.

On peut:

- Passer facilement d'une branche à l'autre.
- Fusionner des branches : commande "git merge".

On est libre de choisir la manière de travailler et d'utiliser les branches. Chaque fonctionnalité nouvelle peut être gérée dans une branche pour être isolée du projet "stable".

Chaque projet git commence avec une branche principale, à laquelle Github donne le nom "main" par défaut. Jusqu'en 2020, ce nom par défaut était "master" – ce terme historiquement connoté a été changé en réponse au mouvement social "Black Lives Matter".



## Le Challenge #5

Le but de ce challenge est de pratiquer la collaboration avec Github :

- Définissez une amélioration à apporter.
- Ecrivez ce que vous souhaitez dans l'onglet *Issues*.
- Vous allez tenter de résoudre une *issue* d'une autre personne.

Procédure Github:

- Clonez le projet de l'autre élève (bouton vert Code > Open with Github Desktop)
- Créez une branche pour votre fonctionnalité.
- Faites de votre mieux pour remplir la demande.
- Faites une Pull Request vers le projet original.

Dans le devoir, envoyez-moi **le lien vers la Pull Request**. Vous le trouvez dans l'onglet "Pull Requests" du projet Github. Exemple d'une Pull Request (sur la fonte typographique Karmilla): [https://github.com/ms-studio/karmilla/pull/57](https://github.com/ms-studio/karmilla/pull/57)


## Liens utiles: 

Support de cours dédié à GIT: [https://cours-web.ch/git/](https://cours-web.ch/git/)

