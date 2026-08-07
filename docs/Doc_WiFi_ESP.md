## UDP
- Faible latence,
- Simple,
- Robuste
- Perte de paquet possible mais pas très grave

Exemple :
```python
#include <WiFi.h>
#include <WiFiUdp.h>

WiFiUDP udp;

void setup() {
  WiFi.begin("SSID", "PASSWORD");

  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
  }

  udp.begin(5005);
}

void loop() {
  char packet[255];

  int len = udp.parsePacket();

  if (len) {
    udp.read(packet, 255);
    packet[len] = '\0';

    Serial.println(packet);
  }
}
```

## TCP
- Plus de latence
- Nécessite une gestion des connexions
- Chaque message est garanti, plus fiable

## WebSocket
- Plus moderne
- Connexion constante avec l'ESP
- Bi-directionnel (éventuellement pour les infos de vitesse / video / batterie / autres opti)

## Broker MQTT
- Probablement excessif pour une voiture RC
- Serveur tournant sur l'ESP, PC Client qui envoie les commandes
- Intéressant pour une archi avec plusieurs clients, pas notre cas

# Solution intéressante
- UDP avec des paquets en JSON
- Soit chaque bouton avec boolean ou float pour les joysticks / gachettes
- Soit un champ "bouton" qui définit quel bouton est pressé associé à "state" soit boolean (1, 0) soit float
    - Pour un seul boutons à la fois, nécessite une adaptation pour au moins 2 ou 3 boutons en simultané, voir si possible
