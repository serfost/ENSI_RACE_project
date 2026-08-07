## Doc officielle Microsoft : XInput

[Doc officielle microsoft](https://learn.microsoft.com/en-us/windows/win32/xinput/xinput-game-controller-apis-portal)

[Guide de programmation](https://learn.microsoft.com/en-us/windows/win32/xinput/programming-guide)

Exemple (très utile) de [Lecture de la manette avec pygame](https://github.com/SimonSchirber/Xbox_Controller_Input/blob/main/xbox_ctrl_general.py)

Fonctions principales : 
XInputGetState() : 
XInputSetState()
XInputGetCapabilities()

Possible d'utiliser la library PyGame qui définit déjà des constantes pour les boutons :
- JOYBUTTONUP
- JOYBUTTONDOWN
- JOYAXISMOTION
- JOYHATMOTION (croix directionnelle)

## Exemple :

```python
import pygame

pygame.init()
pygame.joystick.init()

joy = pygame.joystick.Joystick(0)
joy.init()

while True:
  pygame.event.pump()
  
  if joy.get_button(0):
    print("A")
```

## Wireless
- Xbox One / Series : BLE ou Xbox Wireless (protocole radio propriétaire Microsoft, nécessite un dongle adaptateur)
- Nécessite un polling : le programme attend et l'humain connecte lui même la manette au bluetooth
- Nécessite de détecter les pertes de connexion de la manette au cas ou
- Possible (mais pas très important car WiFi nécessaire) d'utiliser le projet Bluepad32 qui connecte directement une manette à un ESP32 (ou autre) en Bluetooth

Exemple d'attente de connexion :
```python
import pygame
import time

pygame.init()
pygame.joystick.init()

print("Attente de la manette...")

while pygame.joystick.get_count() == 0:
    pygame.joystick.quit()
    pygame.joystick.init()
    time.sleep(1)

joy = pygame.joystick.Joystick(0)
joy.init()

print("Manette connectée :", joy.get_name())
```
