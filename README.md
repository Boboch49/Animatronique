# 🤖 Studio Animatronique

> Une solution professionnelle, clé en main et "tout-en-un" pour piloter des robots animatroniques et des effets spéciaux via une interface Web embarquée sur ESP32.

---

## 🎯 Présentation du Projet

**Studio Animatronique** a été conçu pour éliminer la complexité technique liée au code et au téléversement traditionnel (comme l'IDE Arduino). Il s'adresse aux passionnés, aux créateurs et aux professionnels qui souhaitent installer, configurer et piloter un robot facilement sans compétences en programmation. 

Le système repose sur un firmware sécurisé (distribué sous forme de binaire) combiné à un serveur web local intégré et à un outil de flashage en un clic directement depuis le navigateur.

---

## 🚀 Fonctionnalités Clés
* **Web Flasher Intégré :** Installation et mises à jour du micrologiciel en un clic directement depuis un navigateur compatible (Chrome, Edge, Opera) via l'API Web Serial.
* **Interface Web Embarquée ("Dark Mode") :** Un tableau de bord ergonomique pour créer, tester et enchaîner vos scènes de mouvement.
* **Contrôle Multi-Servomoteurs :** Gestion fluide et précise de 16 canaux via la carte I2C **PCA9685**.
* **Synchronisation Audio :** Intégration d'un lecteur audio **DY-SV17F** pour lier facilement des pistes sonores aux mouvements.
* **Effets Lumineux :** Support natif des anneaux/rubans de LED **WS2812B** pour les yeux ou les ambiances lumineuses.
* **Réseau Flexible :** Mode point d'accès de secours (`Robot-Config`) au premier démarrage et intégration transparente au réseau local via **mDNS** (`http://animatronique.local`).
* **Import / Export :** Sauvegarde et chargement de vos scènes et paramètres au format JSON.

---

## 🛠️ Matériel Requis
* **1x Carte ESP32** (Modèle standard NodeMCU ou DevKit).
* **1x Carte pilote de servos PCA9685** (I2C 16 canaux).
* **Plusieurs servomoteurs** (ex: *MG996R* ou *SG90* selon votre structure mécanique).
* **1x Lecteur audio DY-SV17F** (pour la voix et les effets sonores).
* **Ruban ou LED WS2812B** (optionnel, pour l'éclairage des yeux).
* **1x Alimentation externe 5V** dédiée à la puissance des moteurs.
* **1x Câble USB** de qualité pour relier l'ESP32.

---

## ⚡ Schéma de Câblage Rapide

> ⚠️ **Sécurité :** Ne jamais alimenter les servomoteurs directement via la broche 5V ou 3.3V de l'ESP32. Utilisez toujours une source d'alimentation externe 5V dédiée connectée sur la carte PCA9685.

| Composant Source | Broche / Fil | Composant Cible | Rôle |
| :--- | :--- | :--- | :--- |
| **Alimentation 5V** | Positif (+) | PCA9685 (V+) | Puissance des moteurs |
| **Alimentation 5V** | Négatif (-) | PCA9685 (GND) | Masse commune |
| **ESP32** | Pin 22 (SDA) | PCA9685 (SDA) | Données I2C |
| **ESP32** | Pin 21 (SCL) | PCA9685 (SCL) | Horloge I2C |
| **ESP32** | GND | PCA9685 / Audio / LED (GND) | Référence de masse commune |

---

## 🚀 Installation (Web Flasher)
1. Branchez votre carte ESP32 à l'ordinateur via un câble USB.
2. Rendez-vous sur la page officielle du **Flasheur en Ligne**.
3. Cliquez sur le bouton d'installation pour flasher automatiquement le micrologiciel en quelques secondes.

---

## 📖 Premiers Pas & Utilisation
1. Après le flashage, débranchez et rebranchez l'ESP32.
2. Sur votre smartphone ou votre PC, connectez-vous au réseau Wi-Fi émis par le robot : `Robot-Config` (Mot de passe : `12345678`).
3. Ouvrez votre navigateur web et rendez-vous sur l'adresse de secours : `http://192.168.4.1`
4. Allez dans l'onglet **Wi-Fi** pour enregistrer les identifiants de votre box internet. Le robot redémarrera et sera accessible directement sur votre réseau via son adresse mDNS personnalisée (ex: `http://animatronique.local`).

---

## 📄 Licence
Ce projet et son firmware binaire sont protégés. Tous droits réservés. L'utilisation, la copie ou la redistribution non autorisée du code source compilé sont strictement interdites.
