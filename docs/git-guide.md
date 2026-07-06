# Kékeuçé la plateforme GitHub ?

Le dépôt (repository / repo pour les intimes) girhub est le lieu de collaboration

Le repo contient : 
- Les codes sources qui seront destinés à la voiture (ESP, STM et appli PC / android)
- La documentation
- Le suivi des tâches (gantt, tâches, rôles, avancement, problèmes, bugs...) -> C'est une partie importante pour s'y retrouver et respecter les deadlines (et pour la note ça rend bien)

# Issues

les différentes tâches à accomplir. Peut être une tâche générale ou simplement une requête d'aide pour la résolution d'un bug

# Branches

Permettent de travailler sur une fonctionnalité sans modifier directement la branche principale (main)

Une branche par fonctionnalité et par personne pour le partage des tâches

# Push

Envoi des modifications vers le repo github

# Pull

Récupération des modifications des autres ( synchronisation avec la version locale sur le PC )

# Pull Request (PR)

Proposer une modification et la soumettre à validation avant de modifier le main

Permet d'éviter de tout casser parce que Michel a pas fait gaffe. Elles sont ici obligatoires pour modifier le main.

# Project

Tableau permettant de suivre l'avancement du projet : gantt, liste des tâches, activité du repo dans le temps

# Kékeuçé Git ?

Déjà Github = Microsoft et Git = Linus GOATvalds

Pas obligatoire, l'application de bureau github peut aussi faire tout cela, dépend des préférences

Ressemble à un bash linux, on peut faire les commandes classiques : 
- cd <name> : Change Directory ( changer de dossier )
- ls : Voir les fichiers / dossiers du dossier actuel ( -l : affichage détaillé )
- mkdir <name> : MaKe DIRectory ( Créer un dossier )
- rm <name> : remove (supprimer)

# Pour travailelr sur le repo github

possible via git ou via l'application de bureau github

On commence par pull, c-à-d récupérer les fichiers du repo sur son PC :
- git pull
- sur l'app : Fetch origin -> Pull origin

On sur met sur une autre branche : 
- git checkout feature/xbox-controller
- sur l'app : current branch -> Change branch

ou on en créé une nouvelle : 
- git checkout -b feature/ma-fonctionnalité
- sur l'app : current branch -> New branch

On peut utiliser à tout moment "git status" pour voir l'état des fichiers modifiés

Pour renvoyer les modifications sur GitHub (push) : 

D'abbord constituer la liste de ce que l'on veut push
- git add . (ajouter tous les fichiers), ou 
- git add main.c (ajouter le fichier main.c)

puis enregistrer ces modifications (commit) avec ou sans commentaire (-m) ( c'est mieux avec quand même pour traçer ) : 
- git commit
- git commit -m "Ajout du fichier toto.c, en cours de développement" 

- sur l'app : remplir la partie summary avec la description et commit

Enfin, on peut push : 
- git push
- sur l'app : push origin

Pour l'historique des commits : 
- git log


# Rappel des bonnes pratiques

git pull avant de commencer
Se placer dans la branche correspondant à ce sur quoi on travaille
faire des commits réguliers et COMMENTÉS
Supprimer la branche après acceptation de la pull request et fusion

# Exemple complet 


git pull

git checkout -b feature/xbox-controller

( Développement... )

git add .

git commit -m "Ajout de la lecture du joystick"

git push

Puis sur github : pull request, review, merge
