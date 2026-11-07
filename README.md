Passerelle Edge IIoT et Télémétrie Industrielle via ESP32 & MQTT
Prototype de passerelle de télémétrie industrielle pour l'Internet des Objets (IIoT), déployé sur microcontrôleur ESP32. Le système assure l'acquisition locale de grandeurs environnementales critiques et leur transmission sécurisée et légère vers un courtier Cloud MQTT pour la maintenance prédictive (Industrie 4.0).

Spécifications Techniques
Microcontrôleur Edge : ESP32 DevKit-C v4 (Dual-Core Xtensa @ 240MHz, Wi-Fi 802.11 b/g/n).

Capteur industriel : DHT22 (mesure précise de la température et de l'humidité relative).

Protocole de communication : MQTT via broker public HiveMQ (broker.hivemq.com, Port 1883).

Format de données : Trames JSON sérialisées via ArduinoJson.

Indicateur d'état : LED de statut réseau indiquant la connectivité au broker MQTT.

Fiabilité : Boucle de reconnexion automatique en cas de coupure réseau.

Structure de la Trame JSON Publiée
Topic MQTT : ingexpert/iiot/sensor_data

Payload :
{"device_id": "ESP32_EDGE_GATEWAY_01", "temperature": 26.4, "humidity": 52.8, "status": "NORMAL"}

(En cas de dépassement du seuil critique T > 45°C, le champ status passe automatiquement à ALERT_CRITICAL).

## Simulation Interactive en Direct (Wokwi)
Visualisez les trames MQTT en temps réel et simulez les variations de température :

👉 https://wokwi.com/projects/480035239852906497

Auteur
Ahmed El Ayachi

Ingénieur en Informatique Industrielle et Systèmes Embarqués
