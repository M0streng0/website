---
author: 
  name: "Henrique Oliveira"
title: My Server - Raspberry Pi 4
date: 2024-02-09T13:53:26+01:00
type: ["posts"]
categories: ["Linux", "Server"]
tags:
  - server
  - raspberrypi
# math: katex
draft: false
---
{{< image src="/images/posts/2024/02-2024/my-server/raspberrypi4.webp" alt="Raspberry Pi 4 model B SoC, photo by Jeff Geerling" position="center" style="border-radius: 8px; margin-top: 20px;" >}}

## Why a Raspberry Pi 4?
I chose to use the Raspberry Pi 4 (before the launch of the 5th) because I knew how small it is and how power-efficient it is!
I know that in the price range (a bit more than 100€ with everything, not counting with an HDD), I could buy some used PC and have a more powerful machine, and probably even cheaper. But, a thing I consider really important when setting up a server is power consumption. And really, hardly any machine consumes less than a Raspberry Pi.

_So, I preferred to choose a Raspberry Pi 4 (perfect for my use case)._

### Server specs
- A Raspberry Pi 4 - 8GB (yes, a Raspberry Pi)
- A Flirc Case for the Raspberry Pi
- A simple 32GB SD card - for boot and small files
- An external 4TB to store larger files, such as media files
- An Ethernet cable to connect to my router
- And the power supply for powering the Pi

## The Birth of the Project
I decided to create my own server as I became more preoccupied with my digital privacy and how my data is managed, and probably shared with other parties (_right??_).

So the best solution to such a problem is to simply ditch the services that you're worried about and self-host open-source software. And I must say, it's way simpler than it might look!

### What I Self-Host?
The process of self-hosting is an evolving process. I started with software that today I don't use anymore because I didn't find any more use-case for it. It's a customized process that fits the needs and preferences of every self-hoster.

#### Services I Self-Host:
{{< text-columns >}}
- **Media**
  - [Homer Dashboard](https://github.com/bastienwirtz/homer)
  - [AudioBookShelf](https://github.com/advplyr/audiobookshelf)
  - [Jellyfin](https://github.com/jellyfin/jellyfin)
  - [Komga](https://github.com/gotson/komga)
  - [Navidrome](https://github.com/navidrome/navidrome)
  - Random TED Videos (Custom App)

- **Productivity**
  - [Bitwarden (Vaultwarden)](https://github.com/dani-garcia/vaultwarden)
  - [Jelu](https://github.com/bayang/jelu)
  - [Syncthing](https://github.com/syncthing/syncthing)

- **Automation**
  - [Deluge](https://github.com/deluge-torrent/deluge)
  - [Mylar](https://github.com/mylar3/mylar3)
  - [Prowlarr](https://github.com/Prowlarr/Prowlarr)
  - [Radarr](https://github.com/Radarr/Radarr)
  - [Sonarr](https://github.com/Sonarr/Sonarr)

- **IT Management**
  - [Nginx Proxy Manager](https://github.com/NginxProxyManager/nginx-proxy-manager)
  - [Portainer](https://github.com/portainer/portainer)
{{< /text-columns >}}
{{< image src="/images/posts/2024/02-2024/my-server/homer.webp" alt="Screenshot of Homer Dashboard, showing all the services I use on my server" position="center" style="border-radius: 8px; margin-top: 20px;" >}}

All of the services are inside Docker containers, as I like the ease of management and the containerization of each app.

### How do I access all the services?
The server is only hosted locally (localhost); however, I have a VPN setup to connect from outside the Server Network. All the services are behind the Nginx Proxy Manager, a reverse proxy that manages SSL certification for all the apps (giving them an HTTPS connection - certified by Let's Encrypt).

I will explain in more detail the software itself, the Docker configs, and the overall setup of the server in a future post. To be linked here in the future...