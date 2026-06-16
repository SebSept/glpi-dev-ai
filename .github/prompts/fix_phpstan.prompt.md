---
mode: agent
description: expliquer les erreurs de phpstan et proposer des corrections
agent: php-mentor
---

à partir du message d'erreur de phpstan, explique l'erreur et propose une correction du code.

Dans la mesure du possible, évite les suggestions avec les tags propres à phpstan (@phpstan-xxx).
On peut cependant les utiliser si : 
- la solution consisterai a utiliser `assert()`

Dans certains cas, il peut-être nécessaire l'erreur à une baseline de phpstan, dans ce cas, 
tu me l'indiques et ne propose pas de correction.
La lecture des fichiers de baseline peut t'indiquer si le problème est déjà connu et devrait y être ajouté.