# 🌱 GreenLand - Système d'Arrosage Automatique Intelligent

**Projet PFE** : Application IoT pour l'optimisation de l'irrigation des plantes avec ESP32 et React Native.

## 🚀 Fonctionnalités
- 📊 **Monitoring temps réel** de l'humidité du sol
- ⚡ **Contrôle intelligent** : Arrosage automatique basé sur :
  - Humidité du sol
  - Prévisions météo (API OpenWeatherMap)
- 📱 **Application mobile** :
  - Authentification (Email/Google)
  - Visualisation graphique
  - Commande manuelle
- 🔌 **Matériel** :
  - ESP32 + Capteur capacitif
  - Pompe 5V + Module relais

## 🛠️ Architecture Technique
```mermaid
flowchart TD
    A[Capteur] --> B(ESP32)
    B --> C{Firebase}
    C --> D[App Mobile]
    D --> E[API Météo]
    B --> F[Pompe]

📦 Composants
Matériel
ESP32-WROOM-32

Capteur d'humidité capacitif

Pompe à eau 5V

Module relais 5V

Logiciel
Composant	Technologie
Application mobile	React Native + Expo
Backend	Firebase (Auth/Firestore)
Communication	HTTP REST/MQTT
Visualisation	Victory Native

🔧 Installation
ESP32 (Arduino IDE)
Installer les bibliothèques :
#include <WiFi.h>
#include <WebServer.h>

Configurer les pins :

#define SENSOR_PIN 34
#define RELAY_PIN 26

# Cloner le dépôt
git clone https://github.com/votre-user/GreenLand.git

# Installer les dépendances
npm install

# Lancer l'application
expo start

🌦️ Intégration Météo
L'application utilise l'API OpenWeatherMap :

const API_KEY = "votre_cle_api";
const response = await fetch(`https://api.openweathermap.org/data/2.5/weather?q=Casablanca&appid=${API_KEY}`);
