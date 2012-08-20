Activités de Work4Labs
======================

Work4Labs a pour ambition de proposer aux services RH de ses clients d'exploiter la puissance des réseaux sociaux dans leur effort de recrutement.
Actuellement la principale plates-forme utilisée est Facebook.


Marché
------

Le marché ciblé est principalement le marché des grosses entreprises américaines, d'une part parce que, culturellement, elles sont plus enclines à adopter de nouveaux usages (comme l'est l'utilisation des réseaux sociaux pour appuyer les efforts de recrutement) et d'autre part car elles sont plus nombreuses et de taille plus importantes offrant ainsi plus d'opportunités commerciales.


Work4Us
-------

Work4Us est l'application phare de Work4Labs, quasiment toutes les autres applications inter-réagissent avec Work4Us d'une manière ou d'une autre.
Le but de Work4Us est de permettre aux entreprises d'ajouter facilement des fonctionnalités de recrutement sur Facebook. Les clients peuvent ainsi poster des jobs sur Work4Us et ajouter l'application sur leur page Facebook d'entreprise. Les jobs seront ainsi visible sur facebook et pourront bénéficier de toutes les possibilités qui font la spécificité de facebook (les offres peuvent être publiées sur la *time line* de l'entreprise, puis elles pourront être partagées par les utilisateurs ou être "likées", ...)


Jobs4me
-------

Jobs4Me est similaire à Work4Us sur de nombreux aspects. La principale différence étant la cible. Work4Us est fait pour être installé sur les pages facebook d'entreprise et pour présenter des offres (le client propose des offres d'emplois), alors que Jobs4me a pour objectif de proposer des listes de jobs qui leur correspondent à des candidats (le client recherche des offres d'emplois). Jobs4me est essentiellement utilisé par les écoles et les universités.


Work4Ads
--------

Work4Ads est la plate-forme de publicité sur Facebook proposée par Work4Labs. Le but est de permettre aux clients de lancer des campagnes de pubs sur Facebook en ciblant les candidats le plus précisément possible. Par exemple, admettons qu'un client recherche un ingénieur en informatique à Paris. Work4Ads va lancer une campagne de pub en ciblant les profils sortant d'une école d'ingénieur qui possède une branche informatique, ou aillant occupé un poste similaire étant localisé dans les envirrons de Paris. La publicité sera générée automatiquement à partir de la description du job, et diffusées auprès de tous les utilisateurs de Facebook correspondants aux critères.


ERP - Engines
-------------

Les engines est le nom donné en interne au moteur de recommandations. Cette application va analyser les jobs contenu en base de donnée d'une part, le profil d'un utilisateur d'autre part, pour ensuite présenter à l'utilisateur la liste des jobs qui peuvent l'intéresser.

Par exemple un utilisateur peut aller sur la page facebook d'une entreprise quelconque, cliquer sur l'onglet work4us et cliquer sur le bouton "See jobs matching your profile", le moteur de recommandation proposera ensuite les offres de l'entreprise qui pourrait correspondre.

Autre application existante: quand un utilisateur est sur une page work4us, il peut voir une liste de jobs qui pourraient intéresser ses amis.


Analytics
---------

Les analytics est un service dont l'intérêt est interne à Work4Labs. Il s'agit d'analyser les usages que les clients ont de nos services, d'étudier les données de nos services et d'en tirer des conclusions qui sont utilisable au niveau business.

Imports
-------

Le service d'import est celui dans lequel j'ai fait mon stage. L'objectif de ce service et de servir de jonction entre le monde extérieur et les autres produits de Work4Labs. La plupart de nos clients ont déjà des systèmes en places pour gérer leurs recrutements (des ATS => outils les aidants à gérer les offres d'emplois et les candidatures), des sites carrières ou des job boards. Ces clients ne souhaite pas saisir manuellement des offres d'emplois pour profiter de nos services et nous demandent donc de nous intégrer à leurs systèmes pour y extraire les données que nous pourrions y exploiter.

Concretement les clients nous exposent un web service, un flux XML, ou nous fournissent un lien vers leur site carrière. Notre service va ensuite développer un plugin pour s'interfacer avec le système du client si nécessaire, puis lancer un import qui extraira à intervalle régulier (typiquement une fois par jour) les jobs pour ensuite les adapter à notre système et les rendres exploitable par les autres services.

Les imports servent de point d'entrée pour les données qui seront ensuite exploitées par toute l'entreprise, ce qui nous amène à inter-réagir avec tous les services, ainsi qu'avec les clients et leurs fournisseurs.
