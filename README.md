# 🌐 Simulateur de Réseau LAN – STP

## 🇫🇷 Présentation  
Simulateur de réseau en **C** modélisant un **LAN** avec stations (terminaux) et commutateurs (switches).  
Implémentation du **protocole STP (Spanning Tree Protocol)** et de la commutation Ethernet — apprentissage des adresses MAC, transmission de trames, tables MAC, gestion des ports, etc.  

## 🇬🇧 Overview  
A **C** network simulator modeling a **LAN** with terminals and switches.  
Implements **STP (Spanning Tree Protocol)** and Ethernet switching — MAC learning, frame forwarding, switch tables, port management, etc.

---

## 🛠️ Construit avec / Built with  
- **Langage** : C (C99)  
- **Compilation** : GCC avec Makefile (flags `-Wall -Wextra -Werror`)  
- **Interface** : Terminal (affichage texte, couleurs ANSI possibles)  

---

## 🚀 Fonctionnalités / Features

### 🇫🇷  
- Protocole **STP** : calcul automatique d’un arbre couvrant, blocage/déblocage de ports selon la topologie  
- Commutation Ethernet : apprentissage dynamique des adresses MAC, tables MAC, flooding si destination inconnue, forwarding direct si connue  
- Simulation de trames : création de trames complètes, propagation selon la topologie, affichage du chemin et des étapes (apprentissage, envoi)  
- Affichage et visualisation :  
  - Tables MAC de chaque switch  
  - État des ports STP (actifs / bloqués)  
  - Matrice d’adjacence représentant la topologie réseau  

### 🇬🇧  
- **STP protocol**: automatic spanning tree calculation, port blocking/unblocking based on network topology  
- **Ethernet switching**: dynamic MAC learning, MAC tables, flooding when destination unknown, direct forwarding when known  
- **Frame simulation**: full Ethernet frames creation, network propagation based on topology, detailed display of path and processing steps (learning, forwarding)  
- **Display & visualization**:  
  - MAC tables for each switch  
  - STP port status (active/blocked)  
  - Adjacency matrix showing network topology  

---

## 📁 Structure du projet / Project structure  
```

simulateur_reseau/
├── include/         # Headers (équipements, réseau, trame, STP, commutation, affichage…)
├── src/             # Sources (main, STP, commutation, trames, réseau…)
├── Makefile         # Pour compilation et nettoyage
├── reseau_config.txt  # Exemple de fichier de configuration
└── README.md        # Ce fichier

````

---

## ⚙️ Installation & Exécution / Build & Run  

```bash
# Cloner le dépôt
git clone <url-du-repo>
cd <nom-du-repo>

# Compiler
make

# Lancer le simulateur (option 1)
make run

# Lancer le simulateur directement (option 2)
./bin/simulateur_reseau reseau_config.txt

# Nettoyer les fichiers compilés
make clean
````

---

## 📄 Format de configuration / Config file format

* **Switch** :
  `2;<MAC>;<nombre_ports>;<priorité>`
  Exemple : `2;01:45:23:a6:f7:01;8;1024`

* **Station** :
  `1;<MAC>;<IP>`
  Exemple : `1;54:d6:a6:82:c5:01;192.168.1.10`

* **Lien** :
  `0;<id_equip1>;<id_equip2>;<poids>`
  Exemple : `0;1;4;5`

L’en-tête comporte : `<nb_switches> <nb_stations>`

Exemple de fichier `reseau_config.txt` :

```
5 3
2;01:45:23:a6:f7:01;8;1024
2;01:45:23:a6:f7:02;8;1024
1;54:d6:a6:82:c5:01;192.168.1.10
1;54:d6:a6:82:c5:02;192.168.1.11
1;54:d6:a6:82:c5:03;192.168.1.12
0;0;2;1
0;1;2;1
0;1;3;2
```

---

