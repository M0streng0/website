---
author: 
  name: "Henrique Oliveira"
title: Pourquoi créer un site web ?
date: 2023-11-19
type: ["posts"]
categories: ["Aléatoire"]
tags:
  - pourquoi
draft: false
---
**Voici quelques raisons:**
- Pour l'utiliser comme un portfolio
- Pour pouvoir partager du contenu
- Pour apprendre de nouvelles choses, telles que
  - Hugo (générateur de site statique)
  - Pour développer un peu mieux le HTML et le CSS
  - Me remettre à utiliser JavaScript un peu plus
  - Cloudflare (Pages)
- Pouvoir écrire et traduire dans différentes langues (FR - PT - EN)

## Comment le site a-t-il été créé ?
Maintenant que vous en savez plus sur les raisons qui m'ont poussé à créer un site web, je vais vous expliquer comment je l'ai fait...

### Hugo

J'ai toujours eu envie d'avoir un site web à mon nom, mais je n'ai jamais eu envie de créer et de modifier constamment des fichiers HTML, CSS et quelques fichiers JS chaque fois que je voulais ajouter quelque chose de nouveau...

Quelle est donc la meilleure solution ?

[**HUGO**](https://gohugo.io/) - Un générateur de site statique, ce qui signifie qu'il vous aide à créer des sites avec des fichiers HTML, CSS et JavaScript préconstruits, plutôt que de générer des pages dynamiquement sur le serveur. Il vous suffit d'utiliser Markdown pour construire chaque page web, et tout cela est très modulaire.

Une bonne vidéo que je recommande est celle de Chris Titus, qui parle de son approche avec Hugo. (Vidéo en anglais)

{{< youtube id="xMv10E561WQ" >}}

### Hugo - Apparence

Un grand avantage de l'utilisation de Hugo est que vous pouvez trouver des dizaines et des dizaines de thèmes de sites web avec tous les fichiers déjà pré-construits, ce qui est spectaculaire ! [Où vous pouvez trouver des thèmes...](https://themes.gohugo.io/)

Mais j'aime apprendre à le faire, alors j'ai pris un thème que j'aimais bien ([hello-friend-ng](https://themes.gohugo.io/themes/hugo-theme-hello-friend-ng/)), et je l'ai personnalisé à ma façon...

- J'ai changé les couleurs pour ma palette de couleurs préférée ([Nord](https://www.nordtheme.com/))
- J'ai créé de nouveaux fichiers HTML, CSS et JS afin de mieux réaliser ce que je voulais ! Par exemple :
  - Une galerie de photos qui s'adapte à la taille de chaque image.
  - Texte en colonnes (visible sur la page [Sur Moi](https://m0streng0.com/fr/about/)).
  - Ajout d'une fonctionnalité de rendu du langage mathématique.

Si vous êtes intéressé par mon thème, vous pouvez voir les fichiers sur [Github](https://github.com/M0streng0/website)

Mais l'intégralité de la page originale a été conservée, car elle était déjà très bien faite !

### Cloudflare Pages

L'étape suivante consistait à trouver où héberger le site web... J'avais déjà essayé Github Pages, hébergé sur un VPS Amazon AWS, mais je n'avais jamais essayé Cloudflare Pages.

Laissez-moi vous dire que pour un service gratuit, c'est _**INCREDIBLE**_... L'approche de Cloudflare Pages est similaire à l'expérience que j'ai eue avec Github Pages, mais avec beaucoup plus de fonctionnalités !

Encore une fois, pour en savoir plus sur la relation entre Hugo et Cloudflare Pages, je recommande une fois de plus une vidéo de Chris Titus (il mérite à 100% toute la reconnaissance qu'il peut avoir !)

{{< youtube id="Cfr4YNbKrB8" >}}