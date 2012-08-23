========
Le stage
========

Sujet
-----

J'ai commencé par faire des imports, je suis rapidement passé à autre chose.
Mon stage a eu deux composantes principales : le management du développement des imports d'une part et le développement du système d'import d'autre part.

Le contexte
-----------

J'ai effectué mon stage dans le service import de Work4Labs. Le rôle de cette équipe est d'intégrer les systèmes d'information de nos client aux solutions proposées par Work4Labs. Concrêtement, il s'agit la plupart du temps de se connecter aux systèmes des clients pour en extraire les offres d'emploi et adapter celles-ci pour les rendre exploitables. Pour se faire, l'équipe import a développé une plate-forme et un framework pour automatiser et accélérer au maximum le développement des imports.

Dans le jargon du service, un "import" est le plugin qui permettra au système de s'interfacer avec le système du client. Ce plugin contient le code spécifique développé pour un client en particulier. Cela peut être :

* une "spider" qui parcourra le site du client en analysant son code HTML à la recherche de jobs
* du code qui exploitera un webservice (SOAP, REST ...) fourni par le client
* du code qui se connectera sur le système du client (FTP, SSH, ...) pour y récupérer un flux XML qu'il parsera pour en extraire les données
* parfois d'autres solutions développées au cas par cas pour répondre à des besoins spécifiques des clients

Les ressources du service sont donc partagées entre deux lignes directrices :

* le développement du système d'import (le framework en lui même ou la plate forme qui supporte l'exécution des imports)
* le développement des imports et leur maintenance

J'ai eu l'occasion de travailler sur ces deux aspects.


Gestion des imports
-------------------

Le développement d'imports implique plusieurs personnes de différents services : les commerciaux, les *account managers*, les clients, le service import et parfois les autres équipes techniques de Work4Labs (dans le cas où les clients ont des demandes requérant des développements spécifiques). La tâche n'est donc pas seulement technique. Assez souvent intégrer un client à nos systèmes demande plus d'efforts de communication et de coordination que d'efforts techniques.

Au début de mon stage, j'ai commencé par développer des imports, mais assez rapidement j'ai été amené à travailler sur la gestion du cycle de vie des imports (communication avec les services concernés, gestion/répartition des tâches aux développeurs, code review, supervision du processus de test, validation par le client, déploiement).


Développement de la plate-forme "Job-Pipe"
------------------------------------------

Quand je suis arrivé chez Work4Labs, le service import basait le développement de ses imports sur la plate-forme d'import de Multiposting (sa société soeur). Cela posait plusieurs problèmes :

* l'équipe n'avait aucun contrôle sur le système
* ce système est vieillissant et commençait à poser des problèmes de montée en charge (lenteur, stabilité en cas d'opération de grande envergure)

C'est pour cela que le project "Job-Pipe" a été lancé : créer une plate-forme plus moderne, plus performante et plus efficace pour servir de support au développement et à l'exécution des futurs imports.

Le développement et le management de ce projet ont été mes missions les plus importantes au cours de ce stage.
