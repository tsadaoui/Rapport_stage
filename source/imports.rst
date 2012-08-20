Les imports
===========

La participation au développement des imports est une des deux principales composantes de mon stage. C'est la partie qui comprend le plus de communication avec les clients et aussi celle qui est la plus "managériale".


Process
-------

Le développement d'un import suit un process particulier qui a été affiné par des mois de pratiques et qui est maintenant bien rôdé.

Tout commence chez les commerciaux (les "sales") qui prospectent les clients, leurs proposants des démonstrations aux clients potentiels et en les accompagnant afin d'établir comment nos solutions peuvent leur être profitable. Les commerciaux négocient le contrat et le font signer au client puis passent le relai au service relation client ("Account management" ou "AM").

AM va prendre en contact avec le client et trouver avec eux la meilleur façon d'intégrer nos solutions à leurs système. AM accompagnent le client sur tout un ensemble de concepts qui dépassent le cadre de mes compétences; en particulier sur des aspects métiers (comment intégrer nos outils aux workflow existants des clients, comment optimiser les recrutements, ...) leur rôle est autant de faire du support que de conseiller le client.

Une fois les modalités de l'intégrations établient avec le client (parfois ces discussions nécessite des compétences techniques, et il m'arrive assez régulièrement d'y participer), AM va créer les tâches correspondantes sur Jira et transmettre à l'équipe import les ressources et les contacts nécessaires à la réalisation de sa mission.

L'équipe import va tout d'abord évaluer la durée de la tâche puis la plannifier en fonction des autres imports à développer et de sa charge actuelle de travail. Le développement de l'import est ensuite alloué à un développeur (la répartition des tâches est effectuée soit par Ouadia, soit par moi).

Le développeur en question va développer l'import. Cela peut éventuellement nécessiter la collaboration du client (demande d'information, nécessité de modifier ou d'adapter le système du client ...). L'objectif, à ce stade, du développeur est d'obtenir, sur son environnement de dev, un résultat proche de celui désiré en production.

Une fois le résultat en développement satisfaisant, le développeur va demander une "review" à un autre développeur responsable. Cette étape consiste tout d'abord à inspecter le code produit, y déceler des bugs et chercher des moyens de l'améliorer, de le rendre plus performant ou plus maintenable. Il est très fréquent à cette étape, que le besoin de faire des modifications soit ressenti. La tâche peut donc être réassignée au développeur. Une fois cette revue terminée, il va falloir tester l'import et le lancer sur l'environnement "staging" (qui sera plus tard proposé au client à des fins de validation). Au début je m'occupais seul des reviews, des tests et des déploiement sur le serveur de staging. La charge de travail est maintenant devenue trop importante, c'est pourquoi les reviews sont effectuées (en alternance) par Isabel, François et Bilel et déploiement sur le serveur de staging sont effectués par Isabel. Il m'arrive encore de participer à ce processus, mais c'est de plus en plus rare.

Une fois l'import déployé sur le serveur de staging, la tâche est réassignée à AM, qui la proposera au client. Le client validera la page, ou nous fournir du feedback à son propos (besoin de modification, vecteurs d'amélioration pour l'avenir). La tâche peut ainsi retourner à l'étape de développement (si la page n'est pas validée par le client) ou passer à l'étape suivante: le déploiement.

Le déploiement consiste à configurer l'environnement de production pour préparer chacun des composants du service (initialisation de la base de donnée, merge des branches de staging vers les branches de production, "pull" de la dernière version du code, redémarrage des services modifiés, scheduling des nouveaux imports, et lancement des imports). Il faut ensuite vérifier les pages finale avant de réassigner la tâche à AM qui procédera à l'installation finale de nos application sur la page facebook (activation de work4us sur la page facebook du client, lancement des campagnes de pub pour les jobs, etc ...). J'ai commencé à m'occuper des mises en production quelques semaines après le début de mon stage et cela fait encore partie de mes responsabilité actuellement.


Gestion des incidents au quotidien
----------------------------------


Management
----------
