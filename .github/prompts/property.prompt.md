---
mode: agent
description: completer ou crééer la phpdoc @property de $fields
---

Complète la phpdoc @property de $fields du fichier passer dans le prompt.

## Instructions générales
 * Les champs sont dans le fichier install/mysql/glpi-empty.sql
 * ne lit pas les fichiers glpi-xxx-empty.sql (ce sont des versions anciennes de la base de données)
* la forme est de type `@property array{id: int, name: string, entities_id: int, ...} $fields`
* cette annotation doit être écrite dans la phpdoc juste avant la déclaration de la classe
* tu dois juste compléter $fields pas les autres champs, c'est juste une ligne

## Typage

* Les types tinyint sont a typer en booléen
* les types sql unsigned sont à typer en positive-int
 * au besoin, si la doc 'native' n'est pas assez précise, utilise des types phpstan