# FLX4-DIY-Clone
Conception R&amp;D et code source d'un contrôleur DJ MIDI DIY de niveau professionnel. Projet basé sur l'ergonomie du Pioneer DDJ-FLX4 (Arduino, C++, Matrice LED APA102, Impression 3D).

# 🎛️ FLX4-DIY-Clone : Projet d'Ingénierie DJ R&D

Ce dépôt documente la conception de A à Z d'un contrôleur DJ MIDI hybride "Do It Yourself" de niveau professionnel. Basé sur l'architecture open-source DJC-DIY, ce projet a été entièrement repensé pour reproduire fidèlement l'ergonomie, les fonctionnalités avancées et les dimensions du **Pioneer DDJ-FLX4**.

## 🚀 Objectifs du Projet

L'objectif est de surmonter les limites matérielles des microcontrôleurs standards (comme l'ATmega32U4) pour gérer un système mécatronique complexe intégrant plus de 60 contrôles physiques et un retour visuel haute performance, le tout sans aucune latence MIDI.

### Spécifications Techniques Clés :

* **Dimensions fidèles :** Châssis de 482 x 272.8 x 59.2 mm, imprimé en 3D (modules PETG/ABS avec inserts thermofusibles).
  
* **Multiplexage Analogique :** Utilisation de puces `74HC4067` pour gérer plus de 20 faders et potentiomètres.
  
* **Matrice Numérique Anti-Ghosting :** Matrice de boutons avec diodes `1N4148` pour un N-Key Rollover parfait (nécessaire pour le finger drumming).
  
* **Jog Wheels à Toucher Capacitif :** Intégration de capteurs `MPR121` (I2C) couplés à des encodeurs optiques industriels et des roulements à billes (608ZZ) pour le scratching.
  
* **Retour Visuel Zéro Latence :** Remplacement des LEDs WS2812B par des matrices `APA102` (SPI) pour maintenir la boucle d'interruptions USB intacte.
  
* **Firmware Orienté Objet :** Propulsé par la bibliothèque C++ `Control_Surface`.
  
* **Intégration Logicielle :** Rétro-ingénierie des fichiers XML (Rekordbox/Serato) et gestion des adresses hexadécimales pour les fonctions *Smart Fader* et *Smart CFX*.

---

## 📂 Architecture du Dépôt

Le projet est divisé en modules d'ingénierie distincts :

* 📁 **`/Docs`** : Cahier des charges, analyses de consommation électrique et nomenclature complète (BOM).
  
* 📁 **`/Electronics`** : Schémas de câblage, routage des multiplexeurs et de la matrice de diodes.
  
* 📁 **`/Hardware`** : Fichiers CAO (.STL/.STEP) du châssis modulaire et de la mécanique des Jog Wheels.
  
* 📁 **`/Firmware`** : Code source C++ embarqué sur le microcontrôleur et scripts de test unitaires.
  
* 📁 **`/Software_Mapping`** : Fichiers de configuration XML natifs et scripts de traduction MIDI pour Serato/Rekordbox.

---

## 🛠️ État d'Avancement (Roadmap)

- [ ] Phase 1 : R&D, étude de faisabilité et architecture système.
  
- [ ] Phase 2 : Preuve de concept (Breadboard) et tests unitaires de la communication MIDI.
      
- [ ] Phase 3 : Validation mécatronique du Jog Wheel capacitif.
      
- [ ] Phase 4 : Conception électronique globale (Schémas).
      
- [ ] Phase 5 : Modélisation 3D et impression du châssis.
      
- [ ] Phase 6 : Assemblage, câblage final et intégration du retour LED.

---

## 👨‍💻 Auteur

**Titouan Fourneau** - *Étudiant Ingénieur (ESIEE Paris)*
Projet réalisé dans le cadre d'un développement approfondi en mécatronique, systèmes embarqués et modélisation 3D.
