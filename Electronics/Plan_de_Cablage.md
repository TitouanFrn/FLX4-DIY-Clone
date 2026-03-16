# ⚡ Architecture Électronique et Plan de Routage (Pinout)

Ce document définit l'attribution des broches (GPIO) de l'Arduino Pro Micro (ATmega32U4) pour le prototype. L'objectif est d'optimiser les bus matériels (SPI, I2C) pour garantir une latence nulle.



## 1. Alimentation Commune (Power Bus)
Tous les modules doivent partager la même référence de masse pour que les signaux logiques soient interprétés correctement.
* **GND (Arduino)** ➡️ Ligne de masse (GND) de la Breadboard
* **VCC (Arduino - 5V)** ➡️ Ligne d'alimentation (5V) de la Breadboard

---

## 2. Bus I2C : Capteur Capacitif (MPR121)
Le protocole I2C nécessite les broches matérielles dédiées de l'Arduino.
* **SDA (Data)** ➡️ Broche **2** de l'Arduino
* **SCL (Clock)** ➡️ Broche **3** de l'Arduino
* *Note : Alimenter le MPR121 en 3.3V ou 5V selon le module exact acheté.*

---

## 3. Bus SPI : Ruban LED (APA102 / DotStar)
Pour éviter de bloquer le processeur (interruptions), on utilise le bus SPI matériel.
* **DI (Data In)** ➡️ Broche **16** (MOSI) de l'Arduino
* **CI (Clock In)** ➡️ Broche **15** (SCK) de l'Arduino

---

## 4. Multiplexage Analogique (CD74HC4067)
Ce composant agit comme un aiguillage pour lire jusqu'à 16 potentiomètres en n'utilisant qu'une seule entrée analogique.
* **SIG (Signal Out)** ➡️ Broche **A0** de l'Arduino (Lecture analogique)
* **S0, S1, S2, S3** ➡️ Broches **4, 5, 6, 7** de l'Arduino (Adressage binaire)
* **EN (Enable)** ➡️ **GND** (Pour activer la puce en permanence)



---

## 5. Encodeur Rotatif (EC11)
Pour ne rater aucun cran lors de la rotation (navigation fluide), on privilégie les broches supportant les interruptions matérielles.
* **Pin A** ➡️ Broche **0** (RX) de l'Arduino
* **Pin B** ➡️ Broche **1** (TX) de l'Arduino
* **GND** ➡️ GND

---

## 6. Boutons Poussoirs (Matrice ou Direct)
Pour le prototype initial, on connecte 4 boutons en direct avec la résistance de tirage interne (PULLUP) de l'Arduino. L'autre patte du bouton va au GND.
* **Bouton 1 (Play)** ➡️ Broche **8**
* **Bouton 2 (Cue)** ➡️ Broche **9**
* **Bouton 3 (Shift)** ➡️ Broche **10**
* **Bouton 4 (Sync)** ➡️ Broche **14** (MISO)
