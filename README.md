```
    _~^~^~_
  \) /  o o  \ (/   Tom Lion · « crabzzz »
    '_   ¬   _'     STI2D SIN, puis BTS CIEL
    | '-----' |      systèmes · réseaux · self-hosting
```

Je suis en BTS CIEL et je veux bosser dans l'administration systèmes et réseaux,
de préférence dans une équipe IT où il y a des gens à qui poser des questions.
Presque tout ce que je sais vient de mon homelab, que je monte, que je casse et
que je répare. Je note ce que je fais au fur et à mesure, sinon j'oublie.

```
tom@crabzzz
-----------
role ........ apprenti sysadmin (systèmes et réseaux)
formation ... STI2D SIN, puis BTS CIEL
lab ......... Proxmox VE, conteneurs LXC et quelques VM
reseau ...... routeur MikroTik, VPN, DNS interne
stockage .... TrueNAS SCALE, sauvegardes sur Proxmox Backup Server
online ...... crabzzz.fr
```

### Le homelab

Tout tourne sur un serveur Proxmox VE. Presque tous les services sont dans des
conteneurs LXC, avec des VM seulement quand il faut un autre système (le NAS, le
standard téléphonique). Le réseau passe par un routeur MikroTik qui s'occupe du
pare-feu, du NAT et du VPN pour que je puisse accéder au lab de l'extérieur.

Les sites sont servis par un Caddy qui gère le HTTPS. Les outils d'administration
ne sont pas exposés sur internet, ils ne répondent que depuis le réseau local ou
le VPN.

Le NAS est une VM TrueNAS SCALE. Le serveur, les conteneurs et le NAS sont
sauvegardés automatiquement sur un Proxmox Backup Server. Un onduleur est relié au
serveur avec NUT, pour qu'il s'éteigne proprement si le courant coupe.

Côté supervision j'ai Grafana, InfluxDB et Telegraf, Uptime Kuma pour voir si les
services répondent et Loki pour centraliser les journaux. Les alertes arrivent sur
mon téléphone avec ntfy. J'ai aussi fait un audit complet du lab en novembre pour
repérer ce qui était fragile.

Il y a en plus un Forgejo pour mes dépôts privés, Jellyfin pour les médias, un
standard FreePBX avec une appli de téléphone que j'ai codée (Windows et Android),
et quelques outils maison : une carte interactive de l'infra, une page pour
allumer et éteindre les sites, une appli Android qui affiche l'état du lab.

### Ce que j'héberge

crabzzz.fr est mon site, et plusieurs sous-domaines servent mes projets. J'ai
monté des sites pour de petites entreprises (restauration, rénovation, bâtiment),
un outil pour Destiny 2 et magic-index, un classeur en ligne de mes decks Magic.

TL Network est ma micro-entreprise : dépannage et supervision à distance pour les
particuliers. Elle a son site, un serveur RustDesk que j'héberge moi-même et sa
propre supervision. C'est sur tlnetwork.fr.

Jarvis est mon assistant perso, dont je prépare une nouvelle version. Il tourne en
local sur mon PC, avec des modèles de langage et une voix en local, et le but est
qu'aucune donnée perso ne parte chez un tiers. À terme il doit passer sur le
serveur.

### Ce que je sais faire

| Réseau | Systèmes et virtualisation |
| :-- | :-- |
| routage, NAT, pare-feu | Proxmox VE, PBS, LXC et VM |
| VPN (WireGuard, OpenVPN) | Linux : Debian, Arch |
| MikroTik RouterOS, Cisco IOS-XE | Windows Server : AD DS, GPO, WDS |
| VLAN, DHCP, DNS | TrueNAS, Caddy, Docker |
| analyse de trafic avec Wireshark | Grafana, InfluxDB, Loki, Uptime Kuma |
| | PowerShell, Bash, Python, Node.js, C (notions) |

### Dépôts

- [homelab-proxmox-docs](https://github.com/tom-lion38/homelab-proxmox-docs) : la doc du lab, anonymisée (réseau, services, sauvegardes, supervision, pannes).
- [proxmox-scripts](https://github.com/tom-lion38/proxmox-scripts) : post-installation, création de CT, contrôle des sauvegardes, alertes.
- [phare](https://github.com/tom-lion38/phare) : interface web pour gérer les sites du lab (CT, Caddy, déploiement).
- [abysse](https://github.com/tom-lion38/abysse) : carte 3D du homelab qui bouge en direct.
- [rack-scroll](https://github.com/tom-lion38/rack-scroll) : l'animation du rack qui se construit au scroll sur tlnetwork.fr, expliquée.
- [windows-server-lab](https://github.com/tom-lion38/windows-server-lab) : AD DS, GPO, déploiement de postes par WDS en PXE.
- [it-scripts](https://github.com/tom-lion38/it-scripts) : scripts d'installation (OpenVPN, WireGuard, Samba, Plex).

Le site : [crabzzz.fr](https://crabzzz.fr) · Écrire : tom.lion@outlook.fr
