---
author: 
  name: "Henrique Oliveira"
title: Mon Serveur
date: 2024-02-09T15:56:28+01:00
type: ["posts"]
categories: ["Linux", "Server"]
tags:
  - serveur
  - raspberrypi
# math: katex
draft: false
---
{{< image src="/images/posts/2024/02-2024/my-server/raspberrypi4.webp" alt="Raspberry Pi 4 modèle B SoC, photo de Jeff Geerling" position="center" style="border-radius: 8px; margin-top: 20px;" >}}

## Pourquoi un Raspberry Pi 4 ?
J'ai choisi d'utiliser le Raspberry Pi 4 (avant le lancement du 5e) parce que je savais à quel point il est petit et économe en énergie !
Je sais que dans la fourchette de prix (un peu plus de 100 € avec tout, sans compter avec un disque dur), je pourrais acheter un PC d'occasion et avoir une machine plus puissante, et probablement même moins chère. Mais, une chose que je considère vraiment importante lors de la configuration d'un serveur est la consommation d'énergie. Et vraiment, presque aucune machine ne consomme moins qu'un Raspberry Pi.

Ainsi, j'ai préféré choisir un Raspberry Pi 4 (parfait pour mon cas d'utilisation).

### Caractéristiques du serveur
- Un Raspberry Pi 4 - 8 Go (oui, un Raspberry Pi)
- Un boîtier Flirc pour le Raspberry Pi
- Une simple carte SD de 32 Go - pour le démarrage et les petits fichiers
- Un disque dur externe de 4 To pour stocker des fichiers plus volumineux, tels que des fichiers multimédias
- Un câble Ethernet pour se connecter à mon routeur
- Et l'alimentation pour alimenter le Pi

## La Naissance du Projet
J'ai décidé de créer mon propre serveur car je me suis de plus en plus préoccupé par ma vie privée numérique et la manière dont mes données sont gérées, et probablement partagées avec d'autres parties (_n'est-ce pas?_).

Donc, la meilleure solution à un tel problème est tout simplement d'abandonner les services qui vous préoccupent et d'héberger vous-même des logiciels open source. Et je dois dire que c'est bien plus simple que cela pourrait paraître !

### Ce que j'héberge moi-même ?
Le processus d'auto-hébergement est en constante évolution. J'ai commencé avec des logiciels que je n'utilise plus aujourd'hui parce que je n'ai plus trouvé d'utilisation pour eux. C'est un processus personnalisé qui s'adapte aux besoins et aux préférences de chaque personne pratiquant l'auto-hébergement.

#### Services que j'héberge moi-même :
{{< text-columns >}}
- **Media (Média)**
  - [Homer Dashboard](https://github.com/bastienwirtz/homer)
  - [AudioBookShelf](https://github.com/advplyr/audiobookshelf)
  - [Jellyfin](https://github.com/jellyfin/jellyfin)
  - [Komga](https://github.com/gotson/komga)
  - [Navidrome](https://github.com/navidrome/navidrome)
  - Random TED Videos (Custom App)

- **Productivity (Productivité)**
  - [Bitwarden (Vaultwarden)](https://github.com/dani-garcia/vaultwarden)
  - [Jelu](https://github.com/bayang/jelu)
  - [Syncthing](https://github.com/syncthing/syncthing)

- **Automation (Automatisation)**
  - [Deluge](https://github.com/deluge-torrent/deluge)
  - [Mylar](https://github.com/mylar3/mylar3)
  - [Prowlarr](https://github.com/Prowlarr/Prowlarr)
  - [Radarr](https://github.com/Radarr/Radarr)
  - [Sonarr](https://github.com/Sonarr/Sonarr)

- **IT Management (Gestion informatique)**
  - [Nginx Proxy Manager](https://github.com/NginxProxyManager/nginx-proxy-manager)
  - [Portainer](https://github.com/portainer/portainer)
{{< /text-columns >}}
{{< image src="/images/posts/2024/02-2024/my-server/homer.webp" alt="Capture d'écran du tableau de bord Homer, montrant tous les services que j'utilise sur mon serveur" position="center" style="border-radius: 8px; margin-top: 20px;" >}}

Tous les services sont à l'intérieur de conteneurs Docker, car j'aime la facilité de gestion et la conteneurisation de chaque application.

### Comment accéder à tous les services ?
Le serveur est hébergé localement (localhost); cependant, j'ai mis en place un VPN pour me connecter depuis l'extérieur du réseau du serveur. Tous les services sont derrière Nginx Proxy Manager, un proxy inverse qui gère la certification SSL pour toutes les applications (leur fournissant une connexion HTTPS - certifiée par Let's Encrypt).

Je vais expliquer en détail le logiciel lui-même, les configurations Docker et la configuration générale du serveur dans un futur article. À lier ici dans le futur...