# 📒 Mon carnet de bord

**Nom :Pinel ** 

**Prénom : Esteban ** 

**Adresse de mon site :** https://Zakiryx.pythonanywhere.com

> Modifiez ce fichier directement sur GitHub (icône crayon ✏️) pour répondre aux questions de chaque exercice.
> Écrivez avec vos propres mots : une réponse courte et juste vaut mieux qu'un long copier-coller ! 🙂

---

## 🟢 Exercice 1 — Mon premier déploiement

1. Où se trouve physiquement le code qui fabrique votre page : sur votre ordinateur, sur GitHub ou sur PythonAnywhere ?

   > _Ma réponse :_ https://zakiryx.pythonanywhere.com

2. Pourquoi votre voisin(e) peut-il voir votre site, alors que vous n'avez rien installé sur son ordinateur ?

   > _Ma réponse :_ Parce que mon site tourne sur le serveur, et que mon voisin y accède via le réseau avec son navigateur, qui joue le rôle de client. Il ne reçoit que la page web, pas l’application : je n’ai donc rien à installer chez lui.

---

## 🟢 Exercice 2 — Les URL et les routes

1. Dans l'URL `https://www.google.com/maps`, quel est le nom de domaine ? Quel est le chemin ?

   > _Ma réponse :_ Le nom de domaine est www.google.com et le chemin est /maps.

2. Que veut dire le message *Not Found* ? Qui l'a envoyé : votre navigateur ou le serveur ?

   > _Ma réponse :_ Le message Not Found signifie que la page ou la ressource demandée n’existe pas à cette adresse. C’est le serveur qui l’a envoyé, avec le code d’erreur 404, pour dire qu’il a bien reçu la requête mais qu’il ne trouve rien à ce chemin. Le navigateur ne fait que l’afficher.

3. Que se passe-t-il si deux fonctions portent le même nom dans `flask_app.py` ? (Indice : essayez, puis lisez l'Error log.)

   > _Ma réponse :_ Flask affiche une erreur et le site ne démarre pas, car il utilise le nom de la fonction comme identifiant de la route, et deux fonctions ne peuvent pas avoir le même nom.

---

## 🔵 Exercice 3 — Le langage HTML

1. Quelle est la différence entre ce que le serveur **envoie** et ce que le navigateur **affiche** ?

   > _Ma réponse :_ Le serveur envoie du code (HTML, CSS, JavaScript) sous forme de texte, et le navigateur lit ce code pour construire et afficher la page que je vois : titres, couleurs, boutons, images.

2. À quoi servent les balises `<h1>`, `<p>`, `<ul>` et `<li>` ?

   > _Ma réponse :_ <h1> sert à écrire un titre principal, <p> un paragraphe de texte, <ul> une liste à puces, et <li> chaque élément de cette liste.

3. Pourquoi l'image s'affiche-t-elle alors qu'elle n'est pas sur votre serveur ?

   > _Ma réponse :_ Parce que la balise <img> contient l’adresse (l’URL) de l’image, et le navigateur va la télécharger directement depuis le serveur qui l’héberge, puis l’affiche dans ma page.

---

## 🔵 Exercice 4 — Les templates

1. Pourquoi est-ce une bonne idée de séparer le code Python et le HTML ? (Pensez à une équipe avec un développeur et un graphiste.)

   > _Ma réponse :_ Parce que chacun peut travailler sur son propre fichier sans gêner l’autre : le développeur s’occupe du code Python (la logique), et le graphiste modifie le HTML (l’apparence) sans avoir besoin de comprendre ni de risquer de casser le code.

2. Les `{{ prenom }}` sont-ils remplacés par le serveur ou par le navigateur ? Comment l'avez-vous vérifié ?

   > _Ma réponse :_ Ils sont remplacés par le serveur : Flask (avec Jinja2) remplit les {{ prenom }} avant d’envoyer la page. Je l’ai vérifié en affichant le code source de la page dans le navigateur (clic droit, « Afficher le code source de la page ») : on y voit directement le prénom à la place des {{ }}, ce qui prouve que le navigateur a reçu la page déjà remplie.

---

## 🔵 Exercice 5 — Le CSS et les liens

1. Quelle est la différence de rôle entre le HTML et le CSS ?

   > _Ma réponse :_ Le HTML décrit le contenu et la structure de la page (titres, paragraphes, images), et le CSS décrit son apparence (couleurs, tailles, polices, mise en page).

2. Pour afficher votre page `/presentation`, combien de fichiers le navigateur doit-il télécharger ? (Vous pourrez le vérifier à l'exercice suivant !)

   > _Ma réponse :_ Au minimum deux : le fichier HTML, puis le fichier CSS que la page demande. S'il y a une image, ça fait un fichier de plus.

3. Pourquoi faut-il parfois faire **Ctrl + F5** pour voir les changements de CSS ?

   > _Ma réponse :_ Parce que le navigateur garde en mémoire (cache) l'ancienne version du fichier CSS pour aller plus vite. Ctrl + F5 le force à retélécharger les fichiers depuis le serveur.

---

## 🟣 Exercice 6 — Espionner le navigateur

1. Que signifie HTTP ? Qui envoie la **requête** et qui envoie la **réponse** ?

   > _Ma réponse :_ HTTP signifie HyperText Transfer Protocol (protocole de transfert d'hypertexte). Le navigateur envoie la requête, et le serveur envoie la réponse.

2. Combien de requêtes votre page `/presentation` a-t-elle déclenchées ? Lesquelles ?

   > _Ma réponse :_ Ma page /presentation a déclenché 3 requêtes : la page HTML /presentation, le fichier CSS, et l’image.

3. Que signifie le code `200` ? Et le code `404` de la favicon ?

   > _Ma réponse :_ Le code 200 signifie que la requête a réussi et que le serveur a renvoyé la ressource. Le code 404 de la favicon signifie que le serveur ne trouve pas ce fichier, car je n’ai pas créé d’icône pour mon site.

4. Pourquoi les modifications faites dans l'onglet Éléments ne sont-elles pas visibles par les autres visiteurs ?

   > _Ma réponse :_ Parce que l’onglet Éléments modifie seulement la copie de la page qui est chargée dans mon navigateur, pas les fichiers sur le serveur. Dès que je recharge la page, tout revient à l’état d’origine.

---

## 🟣 Exercice 7 — Envoyer des informations dans l'URL

1. Dans l'URL `https://www.youtube.com/results?search_query=chat`, quel est le nom du paramètre ? Quelle est sa valeur ?

   > _Ma réponse :_ Le nom du paramètre est search_query et sa valeur est chat.

2. Pourquoi le serveur plante-t-il avec `a=bonjour` ? Que faudrait-il faire pour l'éviter ?

   > _Ma réponse :_ Le serveur plante parce que le code essaie de convertir ou de calculer avec `a` comme si c'était un nombre, alors que « bonjour » est du texte, ce qui provoque une erreur. Pour l'éviter, il faudrait vérifier que la valeur est bien un nombre avant de l'utiliser, et renvoyer un message d'erreur clair si ce n'est pas le cas.

3. Pourquoi est-il dangereux d'afficher **tel quel** ce que l'utilisateur envoie ?

   > _Ma réponse :_ Parce qu'un utilisateur malveillant peut envoyer du code (par exemple du JavaScript) à la place du texte, et si je l'affiche tel quel, le navigateur des autres visiteurs va l'exécuter. C'est ce qu'on appelle une faille XSS.

---

## 🟣 Exercice 8 — Les formulaires

1. Quelle est la différence visible entre GET et POST ?

   > _Ma réponse :_ Avec GET, les données apparaissent dans l’URL (après le ?), alors qu’avec POST elles sont envoyées dans le corps de la requête et ne sont pas visibles dans l’URL.

2. Pour un formulaire de **recherche**, quelle méthode choisiriez-vous ? Et pour un formulaire de **connexion avec mot de passe** ? Pourquoi ?

   > _Ma réponse :_ Je choisirais GET pour une recherche, car la requête apparaît dans l'URL et peut être partagée ou mise en favori. Je choisirais POST pour une connexion, car le mot de passe ne doit pas s'afficher dans l'URL, ni rester dans l'historique du navigateur.

3. Les données envoyées en POST sont-elles vraiment « secrètes » ? (Pensez à ce que vous avez vu dans l'onglet Réseau.)

   > _Ma réponse :_ Non, elles ne sont pas secrètes : elles ne sont juste pas visibles dans l'URL. Dans l'onglet Réseau, je peux voir le contenu envoyé en POST, et sans HTTPS, quelqu'un sur le réseau pourrait le lire. Pour vraiment protéger un mot de passe, il faut utiliser HTTPS, qui chiffre les échanges.

---

## 🔴 Exercice 9 — Les codes de statut

1. Quelle est la différence entre une erreur `4xx` et une erreur `5xx` ? Qui est « fautif » dans chaque cas ?

   > _Ma réponse :_ Une erreur 4xx est une erreur côté client : la requête est incorrecte (par exemple une page introuvable, 404), donc le fautif est le navigateur ou l'utilisateur. Une erreur 5xx est une erreur côté serveur : la requête était correcte mais le serveur a planté (par exemple 500), donc le fautif est le serveur.

2. Comment fonctionne une redirection ? Qui fait la deuxième requête : le serveur ou le navigateur ?

   > _Ma réponse :_ Le serveur répond avec un code 3xx (comme 302) et une adresse dans l'en-tête Location, qui dit au navigateur d'aller voir ailleurs. C'est le navigateur qui fait la deuxième requête, automatiquement, vers cette nouvelle adresse.

3. Donnez un exemple de situation où un vrai site utilise une redirection.

   > _Ma réponse :_ Quand je me connecte à un site avec mon mot de passe, le serveur me redirige automatiquement vers ma page d'accueil ou mon espace personnel.

---

## 🔴 Exercice 10 — Ce que le serveur sait de vous

1. Citez trois informations que le serveur connaît sur vous, sans que vous ayez rien rempli.

   > _Ma réponse :_ 

2. À quoi peut servir l'en-tête `Accept-Language` pour un site comme Wikipédia ?

   > _Ma réponse :_ 

3. Dans l'Access log, retrouvez une requête qui a reçu un code `404`. Quelle page était demandée ?

   > _Ma réponse :_ 

4. Après cet exercice, que pensez-vous de la notion de « navigation anonyme » ?

   > _Ma réponse :_ 

---

## 🔴 Exercice 11 — Le Web des machines : API et JSON

1. Quelle est la différence entre une page HTML et une réponse JSON ? À qui chacune est-elle destinée ?

   > _Ma réponse :_ 

2. Dans la page `/horloge`, quel code s'exécute sur le **serveur** et quel code s'exécute dans le **navigateur** ?

   > _Ma réponse :_ 

3. Citez une application de votre téléphone qui, selon vous, utilise une API. Quelles données échange-t-elle ?

   > _Ma réponse :_ 

---

## 🏁 Pour conclure

En quelques phrases, expliquez à un ami ce qui se passe entre le moment où il tape une adresse dans son navigateur et celui où la page s'affiche :

> _Ma réponse :_ 
