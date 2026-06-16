---
mode: agent
description: nettoyer les baselines de phpstan en supprimant les erreurs qui ne sont plus présentes
---

## Prérequis

Si le fichier ./to_remove.txt n'existe pas, tu peux le génerer à partir de la commande suivante :

```bash
make phpstan > to_remove.txt
``` 

## Traitement

il y a des erreurs notées comme devant être ignorées par phpstan mais elle ne sont plus présentes et doivent être enlevées de la baseline.
supprime les de la baseline.
Elles sont notées avec "was not matched in reported errors", la liste est dans le fichier #file:to_remove.txt . Ne traite pas les autres erreurs, tu nettoyes juste la baseline.

