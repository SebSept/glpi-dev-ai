# Instructions pour GitHub Copilot

La finalité des agents est toujours de : 
- permettre aux developpeurs de monter en compétences
- aider à l'analyses du code, la compréhension du fonctionnement de la base de code
- la génération de code est faite uniquement à la demande du prompteur ou de quelques agents particuliers (ex: test-writer.agent.md)

## Environnement

- Le projet s'exécute dans un conteneur Docker
- Toutes les commandes PHP doivent être préfixées par `docker compose exec -T app`
- Ne jamais utiliser directement `php`, `composer` ou `npm` sans Docker

## Commandes fréquentes

- Tests unitaires : `docker compose exec -T app vendor/bin/phpunit`
- Composer : `docker compose exec -T app composer <commande>`
- Console : `docker compose exec -T app php bin/console <commande>`

## Exécution des tests

Pour exécuter les tests unitaires dans ce projet, utilisez Docker Compose :

```bash
docker compose exec -T app vendor/bin/phpunit
```

## Références

Pour lancer les commandes, tu peux te référer au fichier ./Makefile et au fichier ./.justfile

## Mises à jour de l'environnement, résolution des problèmes

Si les dépendences glpi on besoin d'être mise à jour (message dans la console "Application dependencies are not up to date.") :

Si la console à le message "The GLPI codebase has been updated. The update of the GLPI database is necessary.") :
lance la commande de mise à jour disponible dans .justfile, db_update et db_update_tests.

Si la base de données n'est pas installée, la mise à jour rate, il faut installer la base : db_install_tests (et db_install)
Si il y a une erreur de mémoire php, ajoute un paramètre à la commande php : "-d memory_limit=512M" ou 1G si nécessaire.

## Commandes terminal

Quand tu lances des commandes un terminal, ajout un espace avant pour ne pas qu'elles soient dans mon historique.
Mon terminal est fish.

## Complétions SQL

Se référer au fichier install/mysql/glpi-empty.sql pour la structure de la base de données et le nom des champs.

## Sécurité

Tout code généré doit prendre en compte les problématiques de sécurité. 

## Limites

Si tes réponses à une question sont incertaines, indique de se référer à un developpeur glpi expérimenté pour confirmer.