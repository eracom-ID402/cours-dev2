---
layout: page
title: Audio-vidéo
permalink: audio-video.html
---

Les balises HTML audio et video.

***

## Les formats

Support des formats audio sur le web: 

[https://caniuse.com/?search=audio](https://caniuse.com/?search=audio)

Support des formats vidéo sur le web:

[https://caniuse.com/?search=video](https://caniuse.com/?search=video)

Conclusion: Conteneur MP4 avec H264 reste le standard aujourd'hui. Pour le futur, un codec H265 se profile (mais uniquement pris ).

***

Insérer de la vidéo ou du son, les options...

Deux manières d'intégrer de la vidéo:

### 1) En HTML, avec une balise `<video>`

Un exemple:

```html
<video width="100%" height="auto" controls controlsList="nodownload" poster="video/personal-letter.jpg">
  <source src="video/personal-letter.mp4" type="video/mp4">
</video>
```

Comme on le voit, l'élément HTML `<video>` prend plusieurs attributs (par exemple `poster` pour définir l'image affichée avant la lecture).

Elle contient une balise `<source>` qui indique le fichier vidéo.

[L'article MDN donne plus d'explications](https://developer.mozilla.org/fr/docs/Web/HTML/Element/video), ainsi que la liste des attributs disponibles.

Cela donne un "lecteur par défaut" dont le style visuel est défini par le navigateur.

On peut aussi recourir à des "media player" qui vont faire un habillage visuel CSS, comme comme [Video.js](https://videojs.com/), [Plyr](https://plyr.io/), [MediaElement](http://www.mediaelementjs.com/)...

### 2) Depuis une plateforme comme Youtube, Vimeo...

Ces services d'hébergements permettent d'intégrer une vidéo avec un code. Il faut cliquer sur *Share* (*Partager*), puis choisir *Embed* (*Intégrer*).

![Intégration depuis Youtube](img/video/youtube-share-dp.gif)

Voici un exemple de code pour une vidéo Youtube:

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/68iQAo2XXtE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

Ces codes donnent pas un élément `<video>`, mais un élément `<iframe>`. Une iframe est un "cadre" qui permet d'intégrer une page HTML dans la page courante. C'est utilisé par des services comme OpenStreetMap, Google Maps, et beaucoup d'autres services permettant d'intégrer un contenu dans une page web... 

## Vidéo responsive

Techniques pour que le format s'adapte à l'écran.

Voir [https://cours-web.ch/media/video-responsive.html](https://cours-web.ch/media/video-responsive.html)


### Rendre la vidéo responsive

On voit dans l'exemple Youtube que cette vidéo a une taille fixe, en hauteur et largeur (560 sur 315 pixels).

Il est possible de rendre ce code responsive (largeur qui s'adapte, hauteur qui garde la bonne proportion) en le modifant de la manière suivante: 

```html
<iframe width="100%" style="aspect-ratio: 16 / 9;" src="https://www.youtube.com/embed/68iQAo2XXtE" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

Les changements:

- On a remplacé l'unité de largeur (width) par 100%.
- On a supprimé l'attribut de hauteur (height), et on a appliqué le style CSS `aspect-ratio: 16 / 9`.

Voir [la référence MDN Web Docs sur la propriété aspect-ratio](https://developer.mozilla.org/fr/docs/Web/CSS/aspect-ratio). C'est une propriété CSS récente supportée par les navigateurs depuis 2021.

***

## La compression vidéo

Quels réglages utiliser pour le web ?

Voir [https://cours-web.ch/media/compression-video.html](https://cours-web.ch/media/compression-video.html)

***

