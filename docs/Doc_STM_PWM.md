## PWM

### PWM se fait à une certaine fréquence :
- Utiliser les timers hardware du STM
- Fréquence élevée (20 kHz)

### Nécessite un driver adapté :
- Petits moteurs : TB6612FNG
- Plus robuste : BTS7960
- Brushless : ESC RC

### Nécessite des rampes d'adaptation :
Gachette préssée à 100% d'un coup : on veut pas envoyer direct 100% dans les moteurs
- Utiliser un "step" petit (2%) qui incrémente à la commande réelle à chaque cycle (10 ms pour les 100 Hz du SPI) en fonction de si la consigne est plus grande ou petite

### Prévoir un watchdog
Perte de communication avec l'ESP32 de plus de 500 ms : arrêt contrôlé des moteurs

### Modes de conduite
Possibilité d'avoir des modes (lent, rapide, Schumacher) avec une limitation de la vmax (40%, 70%, 100%)

### Mesure de vitesse
La mesure de vitesse permettrait de la prendre en donnée d'entrée et faire de la régulation par rapport à la consigne pour y coller de manière propre

