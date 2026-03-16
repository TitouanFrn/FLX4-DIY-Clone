# 📋 Nomenclature (BOM) : Prototype "Preuve de Concept"

Ce document liste les composants nécessaires pour valider l'architecture électronique sur plaque d'essai (Breadboard) avant la conception du circuit imprimé et l'impression 3D. 

L'objectif de cette phase est de tester la latence MIDI avec les LEDs SPI, le multiplexage analogique et la détection capacitive du Jog Wheel.

## Électronique Active & Microcontrôleur

| Composant | Quantité | Rôle dans le projet | Spécification cruciale |
| :--- | :---: | :--- | :--- |
| **Arduino Pro Micro** | 1 | Cerveau du contrôleur (USB MIDI) | Doit avoir la puce **ATmega32U4** (version 5V/16MHz). *Attention : un Arduino Nano classique ne gère pas le MIDI natif.* |
| **Module CD74HC4067** | 1 | Multiplexeur analogique (16 canaux) | Prendre la version soudée sur circuit (Breakout board). |
| **Module MPR121** | 1 | Capteur tactile capacitif (I2C) | Permettra de simuler le toucher du plateau (Jog Wheel). |
| **Ruban LED APA102** | 1 | Retour visuel Zéro Latence (SPI) | *Interdiction d'utiliser des WS2812B/NeoPixels.* Les APA102 (ou DotStar/SK9822) possèdent 4 broches (5V, GND, Data, Clock). |

## Composants Électromécaniques & Passifs

| Composant | Quantité | Rôle dans le projet |
| :--- | :---: | :--- |
| **Potentiomètre Linéaire** | 1 | Simulation d'un fader de volume (Trim ou Pitch). Valeur standard : 10k Ohms (B10K). |
| **Boutons Poussoirs** | 4 | Simulation des pads de performance (CUE, Play, etc.). De simples boutons tactiles (tact switches) suffisent. |
| **Diodes 1N4148** | 4 | Diodes de commutation rapide. Indispensables pour tester la matrice de boutons et prouver l'absence de *ghosting*. |

## Connectique de Labo

| Matériel | Quantité | Rôle |
| :--- | :---: | :--- |
| **Plaque d'essai (Breadboard)** | 1 ou 2 | Pour assembler le circuit sans soudure. |
| **Câbles Dupont** | ~40 | Mâle/Mâle pour la plaque, et Mâle/Femelle pour relier les modules. |
| **Câble Micro-USB / USB-C** | 1 | Pour relier l'Arduino au PC (doit supporter le transfert de données, pas juste la charge). |




# 📋 BOM (Bill of Materials) : Prototype Électronique

Liste complète des composants nécessaires pour le prototypage virtuel et physique du contrôleur DJ.

| 🔢 Quantité | 🧩 Composant | 📄 Description |
| :---: | :--- | :--- |
| **x1** | 🧠 Microcontrôleur | **Arduino Pro Micro** - ATmega32U4 - 5V/16MHz - USB Type C (Crucial pour le MIDI) |
| **x1** | 🔀 Multiplexeur | **CD74HC4067** - Breakout board 16 canaux (Pour lire tous les potentiomètres) |
| **x1** | 👆 Capteur Capacitif | **MPR121** - Module I2C (Pour la détection du toucher sur le Jog Wheel) |
| **x8** | 🔘 Boutons Poussoirs | **B3F-4055** - 12x12x7.3mm (Pads de performance tactiles) |
| **x8** | 🛑 Diodes | **1N4148** - Diodes de commutation (Anti-ghosting pour la matrice de boutons) |
| **x4** | 🎛️ Potentiomètres Rotatifs | **R0902N** - B103 - 10kΩ - Axe en D de 23mm (Pour les EQ High, Mid, Low, Trim) |
| **x3** | 🎚️ Potentiomètres Linéaires | **Faders 60mm** - B103 - 10kΩ - Tige de 15mm (Pour le volume des platines et le crossfader) |
| **x2** | 🔄 Encodeurs Rotatifs | **EC11** - Axe en D de 15mm - (Pour la navigation et les Jog Wheels basiques) |
| **x1** | 💡 Ruban LED | **APA102 / SK9822** - Bande de 10 à 16 LEDs (Communication SPI, zéro latence) |
| **x4** | ➖ Résistances | 1/4W - 10kΩ (Résistances de tirage / pull-up) |
| **Lot** | 🔌 Câbles | 24 AWG - Rouge (5V), Noir (GND), Bleu, Vert, Jaune (Data) |
---
*Note : Cette liste est volontairement réduite au strict nécessaire pour valider le code et les protocoles de communication. La nomenclature complète (avec les encodeurs optiques industriels, les roulements 608ZZ, etc.) sera établie lors de la Phase 4.*
