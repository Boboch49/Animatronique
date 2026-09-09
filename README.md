# 🤖 Studio Animatronique

> Une solution complète et professionnelle pour piloter des robots animatroniques et des effets spéciaux via une interface Web embarquée sur ESP32.

---

## 🚀 Fonctionnalités
* **Interface Web Moderne :** Tableau de bord "Dark Mode" ergonomique pour créer, tester et enchaîner vos scènes de mouvement.
* **Contrôle Multi-Servomoteurs :** Gestion fluide via la carte I2C **PCA9685** (16 canaux).
* **Gestion Audio :** Synchronisation des mouvements avec des pistes sonores (via lecteur DY-SV17F).
* **Connexion Wi-Fi & mDNS :** Mode point d'accès de secours (`Robot-Config`) et intégration réseau local facile (`http://animatronique.local`).
* **Web Flasher Intégré :** Installation et mises à jour du firmware en un clic directement depuis le navigateur web.

---

## 🛠️ Matériel Requis
* 1x Carte **ESP32** (NodeMCU / DevKit).
* 1x Carte pilote de servos **PCA9685** (I2C 16 canaux).
* Plusieurs servomoteurs (ex: *MG996R* ou *SG90*).
* 1x Lecteur audio **DY-SV17F** (optionnel).
* 1x Alimentation externe 5V dédiée à la puissance des moteurs.

---

## ⚡ Schéma de Câblage Rapide

> ⚠️ **Attention :** Ne jamais alimenter les servomoteurs directement via la broche 5V ou 3.3V de l'ESP32. Utilisez toujours une source d'alimentation externe 5V sur la carte PCA9685.

| Composant Source | Broche / Fil | Composant Cible | Rôle |
| :--- | :--- | :--- | :--- |
| **Alimentation 5V** | Positif (+) | PCA9685 (V+) | Puissance des moteurs |
| **Alimentation 5V** | Négatif (-) | PCA9685 (GND) | Masse commune |
| **ESP32** | Pin 22 (SDA) | PCA9685 (SDA) | Données I2C |
| **ESP32** | Pin 21 (SCL) | PCA9685 (SCL) | Horloge I2C |
| **ESP32** | GND | PCA9685 / Audio (GND) | Référence de masse commune |

---

## 🚀 Installation (Web Flasher)
Inutile d'installer l'IDE Arduino ou des bibliothèques complexes pour l'utilisateur final ! 
Il suffit de :
1. Brancher l'ESP32 en USB à l'ordinateur.
2. Se rendre sur la page du [Flasheur Officiel en Ligne](#).
3. Cliquer sur **Installer le Robot** (compatible Google Chrome, Microsoft Edge ou Opera).

---

## 📖 Premiers Pas
1. Après le flashage, débranchez et rebranchez l'ESP32.
2. Connectez-vous au réseau Wi-Fi émis par le robot : `Robot-Config` (Mot de passe : `12345678`).
3. Ouvrez votre navigateur sur : `http://192.168.4.1`
4. Configurez vos identifiants Wi-Fi dans l'onglet dédié pour basculer sur votre réseau domestique.

---

## 📄 Licence
Ce projet est protégé. Voir le fichier `LICENSE` pour plus de détails sur les droits d'utilisation du code et du firmware.
