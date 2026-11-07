# Passerelle Edge IIoT et Télémétrie Industrielle via ESP32 & MQTT

Prototype de passerelle de télémétrie industrielle pour l'Internet des Objets (IIoT), déployé sur microcontrôleur ESP32. Le système assure l'acquisition locale de grandeurs environnementales critiques et leur transmission sécurisée et légère vers un courtier Cloud MQTT pour la maintenance prédictive (Industrie 4.0).

---

## ⚙️ Spécifications Techniques
- **Microcontrôleur Edge** : ESP32 DevKit-C v4 (Dual-Core Xtensa @ 240MHz, Wi-Fi 802.11 b/g/n).
- **Capteur industriel** : DHT22 (mesure précise de la température et de l'humidité relative).
- **Protocole de communication** : MQTT (Message Queuing Telemetry Transport) via le courtier public `broker.hivemq.com` (Port 1883).
- **Format de données** : Trames JSON sérialisées via la bibliothèque `ArduinoJson`.
- **Indicateur d'état** : LED de statut réseau indiquant la connectivité au broker MQTT.
- **Fiabilité** : Boucle de reconnexion automatique en cas de perte de signal Wi-Fi ou de déconnexion MQTT.

---

## 📊 Structure de la Trame JSON Publiée
Les données sont publiées toutes les 5 secondes sur le topic `ingexpert/iiot/sensor_data` :
```json
{
  "device_id": "ESP32_EDGE_GATEWAY_01",
  "temperature": 26.4,
  "humidity": 52.8,
  "status": "NORMAL"
}
