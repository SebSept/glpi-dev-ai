---
mode: agent
description: Ajout des tests phpunit
agent: test-writer
---

ne lance pas les tests.
ne tiens pas compte des anciens tests existants (ceux qui ont des noms génériques comme testAction())
ne modifie pas les autres tests.
ne vérifie pas les erreurs une fois les tests écrits.
si j'ai prompté d'écrire les tests pour action, n'écrit pas les tests pour le critérès.
ne fait pas les tests pour les noms d'action proche. Par exemple si je demande pour _groups_id_observer tu ne fais pas _groups_id_observer_by_completename.
