---
mode: agent
description: générer du code javascript a executer dans la console du navigateur pour tester une requete ajax
---

Au lancement du prompt :
- demande l'url cible : avec la réponse remplace '/ajax/mailcollector.php' par l'url cible
- demande les paramètres de la requete : avec la réponse remplace les paramètres de body ('action': 'getFoldersList', ...) par ceux fournis par l'utilisateur

tu laisses la partie qui récupère le token csrf et les headers tels quels, tu ne les modifies pas.

```javascript
fetch(
'/ajax/mailcollector.php',
{
method: 'POST',
headers: {
'Content-Type': 'application/x-www-form-urlencoded;',
'X-Requested-With': 'XMLHttpRequest',
'X-Glpi-Csrf-Token': document.querySelector('[property="glpi:csrf_token"]').attributes['content'].value,
},
body: new URLSearchParams({
'_glpi_csrf_token': document.querySelector('[property="glpi:csrf_token"]').attributes['content'].value,
'action': 'getFoldersList',
'input_id': 'mailgate_input',
'mail_server': 'host.docker.internal',
'server_port': '3143',
'server_type': '/imap',
'server_tls': '/notls',
'login': 'test',
'passwd': 'test'
}).toString()
}
).then((response) => {
return response.text();
}).then((text) => {
console.warn(text);
});
```