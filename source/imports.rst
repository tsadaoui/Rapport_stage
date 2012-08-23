Les imports
===========

La participation au développement des imports est une des deux principales composantes de mon stage. C'est la partie qui comprend le plus de communication avec les clients et aussi celle qui est la plus "managériale".


Process
-------

Le développement d'un import suit un process particulier qui a été affiné par des mois de pratiques et qui est maintenant bien rôdé.

Tout commence chez les commerciaux (les "sales") qui prospectent les clients, proposant des démonstrations aux clients potentiels et les accompagnant afin d'établir comment nos solutions peuvent leur être profitables. Les commerciaux négocient le contrat et le font signer au client puis passent le relai au service relation client ("Account management" ou "AM").

AM va prendre contact avec le client et trouver avec eux la meilleure façon d'intégrer nos solutions à leurs système. AM accompagne le client sur tout un ensemble de concepts qui dépassent le cadre de mes compétences; en particulier sur des aspects métiers (comment intégrer nos outils aux workflow existants des clients, comment optimiser les recrutements, ...) leur rôle est autant de faire du support que de conseiller le client.

Une fois les modalités de l'intégration établies avec le client (parfois ces discussions nécessitent des compétences techniques et il m'arrive assez régulièrement d'y participer), AM va créer les tâches correspondantes sur Jira et transmettre à l'équipe import les ressources et les contacts nécessaires à la réalisation de sa mission.

L'équipe import va tout d'abord évaluer la durée de la tâche puis la planifier en fonction des autres imports à développer et de sa charge actuelle de travail. Le développement de l'import est ensuite alloué à un développeur (la répartition des tâches est effectuée soit par Ouadia, soit par moi).

Le développeur en question va développer l'import. Cela peut éventuellement nécessiter la collaboration du client (demande d'information, nécessité de modifier ou d'adapter le système du client ...). L'objectif, à ce stade, du développeur est d'obtenir, sur son environnement de dev, un résultat proche de celui désiré en production.

Une fois le résultat en développement satisfaisant, le développeur va demander une "review" à un autre développeur responsable. Cette étape consiste tout d'abord à inspecter le code produit, y déceler des bugs et chercher des moyens de l'améliorer, de le rendre plus performant ou plus maintenable. Il est très fréquent à cette étape, que le besoin de faire des modifications soit ressenti. La tâche peut donc être réassignée au développeur. Une fois cette revue terminée, il va falloir tester l'import et le lancer sur l'environnement "staging" (qui sera plus tard proposé au client à des fins de validation). Au début je m'occupais seul des reviews, des tests et des déploiements sur le serveur de staging. La charge de travail est maintenant devenue trop importante, c'est pourquoi les reviews sont effectuées (en alternance) par Isabel, François et Bilel et les déploiements sur le serveur de staging sont effectués par Isabel. Il m'arrive encore de participer à ce processus, mais c'est de plus en plus rare.

Une fois l'import déployé sur le serveur de staging, la tâche est réassignée à AM, qui la proposera au client. Le client validera la page, ou nous fournira du feedback à son propos (besoin de modification, vecteurs d'amélioration pour l'avenir). La tâche peut ainsi retourner à l'étape de développement (si la page n'est pas validée par le client) ou passer à l'étape suivante: le déploiement.

Le déploiement consiste à configurer l'environnement de production pour préparer chacun des composants du service (initialisation de la base de donnée, merge des branches de staging vers les branches de production, "pull" de la dernière version du code, redémarrage des services modifiés, scheduling des nouveaux imports, et lancement des imports). Il faut ensuite vérifier les pages finales avant de réassigner la tâche à AM qui procédera à l'installation finale de nos applications sur la page Facebook (activation de work4us sur la page Facebook du client, lancement des campagnes de pub pour les jobs, etc ...). J'ai commencé à m'occuper des mises en production quelques semaines après le début de mon stage et cela fait encore partie de mes responsabilités actuellement.


Un effort d'automatisation
--------------------------

La production des imports demande de réaliser des tâches qui peuvent être similaire d'un client à l'autre. Dans une optique d'optimisation de nos ressources (il s'agit de dégager du temps pour nous permettre de travailler sur d'autre projet) l'automatisation et l'accélération de tout ce qui peut l'être est donc un vecteur clé d'amélioration du service import. Par exemple nous nous efforçont d'écrire du code générique pour tous les principaux ATS du marché et ce qui nous permet de réutiliser des spider pré-écrites quand des clients utilisant ces ATS se présentent.

Nous essayons également, quand c'est possible, de signer de partenariat avec les éditeurs des ATS afin de nous intégrer directement avec eux. Ces intégrations sont difficiles et longues à mettre en place, et leur concretisation est à la charge du service import. Il nous faut alors écrire beaucoup de documentation et communiquer énormément avec les équipes techniques de l'ATS ciblé.

Quand c'est possible nous essayons également d'écrire des outils qui vont automatiser (générer automatiquement du code, effectuer des vérifications ...) nos tâches de programmation.


Gestion des incidents au quotidien
----------------------------------

Les imports sont des points de liaison entre nos systèmes et les systèmes des clients. Par nature, notre mission implique d'interagir avec des systèmes extérieurs à l'entreprise, sur lesquels nous n'avons aucun contrôle.

Nos clients sont les services des ressources humaines. La plupart du temps ces services sont distincts des services qui maintiennent les services d'information et la communication peut être dans certains cas malaisée voire inexistante. Les systèmes des clients peuvent donc être amené à évoluer indépendamment de notre volonté sans que nous ne soyons mis au courrant. Toute modification du système des clients peut provoquer des erreurs sur nos imports, si le site est modifié d'une façon qui n'a pas été anticipée par le développeur (souvent cette anticipation est tout simplement impossible).

Une des certitudes que nous avons en développant des imports c'est que notre code finira par échouer, qu'il y aura des erreurs, et qu'une partie d'entre elles n'aura pas été anticipée. Le système et nos imports sont donc construits dans cette optique: nous savons que notre code finira par échouer, nous ne savons pas quand, ni exactement comment mais nous voulons:

1. limiter les dégats au maximum (interruption de service minimum, compartimentation des différentes fonctions ...)
2. être tenu au courrant dès qu'une erreur survient avec assez de contexte et de détails pour cibler la source du problème
3. être capable de résoudre le problème le plus rapidement possible et déployer le "fix" sans délai

Pour respecter ces critères au maximum, nous mettons l'accent sur plusieurs vecteurs:

* nous avons établi un ensemble de bonnes pratiques spécifiques au développement de nos imports sur lesquels nous sommes particulièrement vigilant au cours des codes reviews. Ces pratiques sont issues de notre expérience et du temps passé à développer des imports très différents et à résoudre des problèmes divers et inattendus.
* nous donnons une grande importance au monitoring de nos systèmes au niveau infrastructure (fonctionnement des différents services, état du réseau, ...) et au niveau "métier" (modification du site du client, détection de données incohérentes ...)
* nos workflow sont optimisés, simplifiés, automatisés pour nous opposer le moins de friction possible et nous permettre d'être réactif et d'agir sans lourdeur
* nous développons les imports en temps qu'équipe afin que tous les imports soit compréhensible/accessible par tous les développeurs (respect de conventions de codage, documentation des informations générales nécessaires à la mise en situation et des points particuliers/inhabituels, communication au sein de l'équipe ...). Tout le monde peut intervenir sur l'intégralité de la base de code. Il n'y a pas de notion d'exclusivité.

Malgré nos efforts il arrive que des erreurs surviennent. Une partie du travail quotidien de l'équipe et d'investiguer ces erreurs et de les corriger. La correction de ces erreurs nécessite parfois des opérations en production, la difficulté est alors d'opérer de façon sure (ne pas perdre de données même en cas d'accident), avec une interruption de service la plus courte possible, et de façon à garder l'ensemble de nos données dans un état cohérent.


Gestion de projet
-----------------

Une partie de mon travail consiste à participer à l'organisation de l'équipe import. La plupart du temps Ouadia s'occupe des imports relatifs au système de Multiposting et des problèmes nécessitant un processus long (intégration avec un ATS, besoin de documentation lourde, ou de fonctionnalités custom sur d'autres produits proposés par work4labs) et je me charge des imports relatifs à Job-pipe.

Cette dimension a pris une importance particulière quand Ouadia est parti plusieurs semaines en vacances, je me suis alors occupé de la gestion de l'équipe import seul. Cela comprend:

* la réception des tâches
* les réponses aux questions qu'AM ou que les commerciaux peuvent avoir à propos d'une tâche donnée
* la planification des tâches en fonction des priorités exprimées par AM
* la répartition des tâches en fonction de la charge de travail et des compétences de chacun
* le suivi de l'avancement des tâches

Cela demande beaucoup de communication avec AM (durant cette période je faisais des points avec AM d'une heure tous les jours) et avec les développeurs. Le suivi des statuts des tâches (à base de mails et de Jira) et la gestion des problèmes courant (blocage technique, besoin de plus d'information de la part du client ou d'un projet interne avec lequel on doit s'interfacer ...) consomme également beaucoup de temps.
