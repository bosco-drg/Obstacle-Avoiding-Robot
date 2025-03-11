# Robot Éviteur d'Obstacles
## Présentation du Projet

Le Robot Éviteur d'Obstacles est un projet de robotique autonome conçu pour naviguer efficacement dans des environnements en détectant et en évitant les obstacles. Développé dans le cadre d'un projet de deuxième année de BUT GEII (Génie Électrique et Informatique Industrielle).

<br>
<div align="center">
  <figure>
    <img src="docs/robot_photo.png" alt="Robot Éviteur d'Obstacles" width="500" style="max-width: 100%;">
    <p><em>Vue d'ensemble du Robot Éviteur d'Obstacles</em></p>
  </figure>
</div>
<br>

## Objectifs du Projet

1. **Concevoir un robot mobile autonome** capable de détecter et d'éviter les obstacles en temps réel
2. **Implémenter des algorithmes de navigation intelligente** adaptés à différents environnements et situations
3. **Développer une interface graphique de contrôle** permettant de visualiser les données des capteurs et d'envoyer des commandes au robot
4. **Mettre en place une communication Bluetooth fiable** entre le robot et l'interface de contrôle
5. **Intégrer un système de contrôle manuel** via une manette compatible ou un controleur bluethouth

## Caractéristiques Matérielles

Le robot est construit autour des composants suivants :

- **Microcontrôleur** : PIC utilisé pour le traitement central et la prise de décision
- **Capteurs de distance** : Capteurs infrarouges pour la détection d'obstacles
- **Module Bluetooth** : ESP32 configuré en mode esclave pour la communication sans fil
- **Système de locomotion** : Moteurs à courant continu avec encodeurs pour un contrôle précis
- **Alimentation** : Batteries rechargeables offrant une autonomie de plusieurs heures

## Programmation du Robot

Le robot est programmé en utilisant l'environnement MPLAB en C++ :

La programmation est de bas niveau, exploitant directement les registres du microcontrôleur pour configurer les différents modules tels que les convertisseurs analogique-numérique (ADC), numérique-analogique (DAC), les hacheurs pour le contrôle PWM des moteurs, et autres périphériques.

Le programme utilise des structures avancées pour optimiser la vitesse d'exécution et l'utilisation de la mémoire :
- Buffers circulaires pour le traitement efficace des données des capteurs
- Timers à plusieurs niveaux pour la gestion précise des tâches
- Structures de données optimisées pour le stockage et l'accès rapide aux informations

### Architecture Logicielle

Le code source est structuré en plusieurs modules distincts qui interagissent entre eux :

#### Module de Détection
- Gestion des capteurs infrarouges
- Filtrage et traitement des signaux pour éliminer le bruit
- Calcul des distances et identification des obstacles
- Cartographie simple de l'environnement proche

#### Module de Locomotion
- Contrôle précis des moteurs via PWM
- Gestion des encodeurs pour le suivi de position
- Algorithmes de décélération et d'accélération progressive
- Contrôle différentiel pour les virages précis

#### Module de Décision
- Algorithmes d'évitement d'obstacles
- Planification de trajectoire à court terme
- Systèmes de priorité pour la prise de décision

#### Module de Communication
- Protocole Bluetooth pour le contrôle à distance
- Gestion des commandes entrantes
- Envoi des données télémétriques
- Système de contrôle de flux pour éviter la saturation

## Interface de Contrôle C# via Bluetooth

Le robot peut être contrôlé et surveillé grâce à une application Windows développée en C# :

- **Contrôle en temps réel** : Pilotage manuel du robot via des commandes directionnelles avec retour visuel immédiat
- **Visualisation des données capteurs** : Affichage graphique des distances mesurées et représentation de l'environnement
- **Paramétrage du comportement autonome** : Ajustement des seuils de détection, des distances de sécurité et des comportements d'évitement
- **Enregistrement des données** : Possibilité de sauvegarder les parcours et les données des capteurs pour analyse ultérieure
- **Mode automatique/manuel** : Basculement facile entre les modes de fonctionnement du robot


### Communication Bluetooth

Le système utilise un ESP32 configuré en mode esclave pour établir une connexion série sans fil avec l'ordinateur. Le protocole de communication inclut :

- Commandes de déplacement (avancer, reculer, tourner à droite/gauche, arrêter)
- Requêtes d'état des capteurs (distances, vitesse)
- Commandes de paramétrage (réglage des seuils, des vitesses, des modes)
- Support pour le contrôle via une manette de jeu (comme une manette PS4)

---

© 2024 Robot Éviteur d'Obstacles. Développé par Bosco.