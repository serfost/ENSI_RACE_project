## Doc officielle Microsoft : XInput

Doc : https://learn.microsoft.com/en-us/windows/win32/xinput/xinput-game-controller-apis-portal
Guide de programmation : https://learn.microsoft.com/en-us/windows/win32/xinput/programming-guide

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
