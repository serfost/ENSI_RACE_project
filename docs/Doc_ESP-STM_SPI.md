## STM = Maître
- Le STM gère les actionneurs, il est préférable d'en faire le maître SPI pour qu'il puisse lire les données quand il veut
- Fréquence de transmission : 50 Hz ou 100 Hz (10 à 20 ms, déjà rapide pour une manette)
- Possible en UART : peut être plus simple
- Envoyer un snapshot de l'état de la manette (tous les boutons en un paquet) plutôt que les pressions / relachement : plus robuste
- Structure comprenant chaque bouton de la manette (boutons, analogues, gachettes... ) et envoi de toute la struct au STM sur sa demande
