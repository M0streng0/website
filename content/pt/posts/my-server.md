---
author: 
  name: "Henrique Oliveira"
title: O meu Servidor - Raspberry Pi 4
date: 2024-02-09T15:48:20+01:00
type: ["posts"]
categories: ["Linux", "Server"]
tags:
  - servidor
  - raspberrypi
# math: katex
draft: false
---
{{< image src="/images/posts/2024/02-2024/my-server/raspberrypi4.webp" alt="Raspberry Pi 4 modelo B SoC, fotografia por Jeff Geerling" position="center" style="border-radius: 8px; margin-top: 20px;" >}}

## Porquê um Raspberry Pi 4?
Optei por utilizar o Raspberry Pi 4 (antes do lançamento do 5º) porque sabia o quão pequeno é e o quão eficiente em termos de energia é!
Eu sei que, dentro da faixa de preço (um pouco mais de 100€ com tudo, sem contar com um HDD), poderia comprar um PC usado e ter uma máquina mais potente e, provavelmente, até mais barata. No entanto, algo que considero realmente importante ao configurar um servidor é o consumo de energia. E realmente, dificilmente alguma máquina consome menos do que um Raspberry Pi.

Portanto, preferi escolher um Raspberry Pi 4 (perfeito para o meu caso de uso).

### Especificações do Servidor
- Um Raspberry Pi 4 - 8GB (sim, um Raspberry Pi)
- Uma Caixa Flirc para o Raspberry Pi
- Um simples cartão SD de 32GB - para inicialização e pequenos ficheiros
- Um disco externo de 4TB para armazenar ficheiros maiores, como ficheiros média
- Um cabo Ethernet para ligação ao meu router
- E a fonte de alimentação para alimentar o Pi

## O Nascimento do Projeto
Decidi criar o meu próprio servidor à medida que me tornei mais preocupado com a minha privacidade digital e com a forma como os meus dados são geridos, e provavelmente partilhados com outras entidades (_certo??_).

Assim, a melhor solução para tal problema é simplesmente abandonar os serviços que o preocupam e hospedar você mesmo software de código aberto. E devo dizer, é muito mais simples do que pode parecer!

### O Que Hospedo por Conta Própria?
O processo de hospedagem própria é um processo em evolução. Comecei com software que hoje em dia já não utilizo, porque não encontrei mais nenhum caso de uso para ele. É um processo personalizado, que se ajusta às necessidades e preferências de cada pessoa que hospeda por conta própria.

#### Serviços que Hospedo por Conta Própria:
{{< text-columns >}}
- **Media (Média)**
  - [Homer Dashboard](https://github.com/bastienwirtz/homer)
  - [AudioBookShelf](https://github.com/advplyr/audiobookshelf)
  - [Jellyfin](https://github.com/jellyfin/jellyfin)
  - [Komga](https://github.com/gotson/komga)
  - [Navidrome](https://github.com/navidrome/navidrome)
  - Random TED Videos (Custom App)

- **Productivity (Produtividade)**
  - [Bitwarden (Vaultwarden)](https://github.com/dani-garcia/vaultwarden)
  - [Jelu](https://github.com/bayang/jelu)
  - [Syncthing](https://github.com/syncthing/syncthing)

- **Automation (Automatização)**
  - [Deluge](https://github.com/deluge-torrent/deluge)
  - [Mylar](https://github.com/mylar3/mylar3)
  - [Prowlarr](https://github.com/Prowlarr/Prowlarr)
  - [Radarr](https://github.com/Radarr/Radarr)
  - [Sonarr](https://github.com/Sonarr/Sonarr)

- **IT Management (Gestão de TI)**
  - [Nginx Proxy Manager](https://github.com/NginxProxyManager/nginx-proxy-manager)
  - [Portainer](https://github.com/portainer/portainer)
{{< /text-columns >}}
{{< image src="/images/posts/2024/02-2024/my-server/homer.webp" alt="Captura de ecrã do Painel Homer, mostrando todos os serviços que utilizo no meu servidor" position="center" style="border-radius: 8px; margin-top: 20px;" >}}

Todos os serviços estão dentro de contentores Docker, pois gosto da facilidade de gestão e da containerização de cada aplicação.

### Como acedo a todos os serviços?
O servidor está apenas hospedado localmente (localhost); no entanto, configurei uma VPN para me ligar a partir do exterior da Rede do Servidor. Todos os serviços estão por trás do Nginx Proxy Manager, um servidor proxy reverso que gere a certificação SSL para todas as aplicações (proporcionando-lhes uma ligação HTTPS - certificada pelo Let's Encrypt).

Explicarei em mais detalhe o próprio software, as configurações do Docker e a configuração geral do servidor numa publicação futura. Para ser vinculado aqui no futuro...