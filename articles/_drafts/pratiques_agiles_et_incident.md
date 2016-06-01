---
title: Réduire la charge de la production grace à l'agilité
authors:
  - Thomas Clavier
tags:
  - pratiques
---

## Contexte

Récemment, une équipe que nous accompagnons a fait un bilan des apports de la transformation agile en cours. Pour cela, ils ont réuni autour d'une table le product owner, quelques utilisateurs, le srum master, le manager de l'équipe de production (ops) et moi même.

Les utilisateurs ont observé tous les effets d'une bonne collaboration entre développeur et product owner : plus de valeur, moins cher, une plus grande réactivité, confiance et implication des équipes. De son coté, la production a constaté avec surprise 27% d'incidents en moins.

Nous avons alors corrélé les types d'incidents et les pratiques agiles déployées, pour guider les améliorations à venir.

## Des pratiques

Dans le cadre de notre accompagnement, les équipes ont décidé de faire émerger un certain nombre de pratiques, elles ne sont pas toutes en place ou mérite d'être approfondi : 

* Un responsable produit correctement identifié dont le rôle est bien compris par tout le monde.
* Réduire les histoires utilisateurs pour livrer plus vite de petits morceaux sur lesquelles l'utilisateur peut donner très vite un avis.
* Travailler avec les utilisateurs pour que l'expression des tests automatiques leur soit suffisamment claire (BDD).
* Penser test avant de produire du code (TDD, BDD), pour obtenir une application testé automatiquement à chaque commit y compris les tests de charges et les tests de résistance aux modifications d'environnements.
* Livrer très vite en automatique et plusieurs fois par jour, de tout petits incréments de logiciel pour avoir un feedback rapide des utilisateurs, c'est le déploiement continu
* Pratiquer le "trunc base" pour voir au plus tôt les problèmes d'intégration et éviter autant que possible les problèmes de report entre versions.
* Faire participer les utilisateurs, la production et les équipes aux ateliers d'affinage du backlog.
* Mettre en place une bonne métrologie capable de remonter rapidement les liens de cause à effet permettant d'une part de simplifier une partie de l'analyse d'impacte et d'autre part de voir le problème avant l'incident pour le corriger au plus vite.
* Avoir des tests fonctionnel automatique applicable en production
* Gérer l'infrastructure comme du code pour automatiser la création d'environnements par les développeurs ou pour faire face à la montée en charge.

## Taxonomie ITIL

Classer, trier les demandes et les incidents pour analyser et corriger les problèmes les plus importants en priorité est une des grandes forces d'ITIL. Voici l'arbre de classement des incidents et des demandes que nous avons utilisé :

* Incidents
  * Logiciel
  * Livraison
  * Processus
* Demandes
  * Application
  * Demande d'accès
  * Gestion de données

### Incidents

#### Logiciel

Cette catégorie regroupe les incidents dont l'origine est supposé être l'application. Ce qui regroupe :

* les incidents mettant en évidence l'inadéquation entre le logiciel et le besoin;
* les incidents lié à une mauvaise analyse d'impact inter applications : un changement dans l'application génère un bug dans une autre application;
* les incidents lié au manque de robustesse de l'application : un changement dans l'environnement (coupure réseau, disque plein, reboot d'un service distant, etc.) qui bloque ou stoppe l'application;
* les incidents mettant en avant des bugs ou des régressions;
* les incidents lié à la fluctuation de la charge.

Cette catégorie, malgré la baisse de 21% d'incidents, présente de nombreuses pistes d'améliorations entre autre sur la robustesse de l'application face aux très nombreux web services qu'elle utilise

#### Livraison

Dans cette catégorie, on retrouve l'ensemble des incidents de livraison : package incomplet ou mal construit, problème de configuration applicative, erreur dans une procédure de livraison, etc.

Cette catégorie, suite à l'automatisation des déploiements présente une baisse spectaculaire, plus de 64%. Éradiquer les incidents de cette catégorie est un des objectifs de l'équipe.

#### Processus

Dans cette catégorie, nous trouvons tous les incidents mettant en cause les processus et les outils. Brièvement, dans ITIL, une action répétitive doit au minimum être documenté dans une procédure que l'opérateur pourra suivre pas à pas avec un certains nombre d'outils.
Tous les incidents mettant en cause la procédure, que ce soit parce qu'elle est absente ou pas à jour. Par exemple, une procédure qui ne fait pas référence à une nouvelle fonctionnalité rentre de facto dans cette catégorie.

Si un outil utilisé par la production ne fait pas correctement le travail par manque de configuration ou manque de fonctionnalité, alors l'incident rentre aussi dans cette catégorie.
La supervision faisant parti des outils, une grande partie des problèmes de supervision (sonde en décalage avec le code applicatif, problème de configuration, etc.) rentrent dans cette catégorie.

Cette catégorie n'avait que peu baissé, moins de 8%.

### Demandes

En complément des incidents, la production est confronté à un certain nombre de demandes :

* des lancement de fonction, des mise à jour de paramètres applicatifs, installation de composants, relivraison urgente, etc. Tous ces cas de figure rentre dans la catégorie "Demandes applicatives".
* Toutes les créations, mise à jour ou suppression des droits qui ne peuvent pas être réalisé par les utilisateurs rentrent dans la catégorie "Gestion des accès"
* Enfin, toutes les demandes de manipulation de données (exécution de requêtes SQL, mise à jour de fichiers, extractions, demandes de dumps, de synchro de base, etc. ) rentrent dans la catégorie "Gestion des données"

Alors qu'aucune baisse n'a été réellement observé dans cette catégorie, 2 types de demandes remontent régulièrement et occupent une personne à temps plein. 
Sans compter le temps perdu par tous les intermédiaires.
L'échange qui a eu lieu autour de la table à montré que le responsable produit n'était pas conscient de ce besoin, deux nouvelles histoires utilisateurs ont émergé de cette discutions et dans quelques semaines, la personne compétente et qualifié qui déroule des demandes répétitive pourra apporter beaucoup plus de valeur à l'entreprise.

## Conclusion

Au final, 27% de baisse globale, c'est très bien. 
Mais tout le monde était convaincu qu'il était encore possible de réduire le nombre d'incidents de moitié, non pas pour réduire la taille de l'équipe de production, mais pour leur permettre de se focaliser sur des taches à bien plus forte valeur ajouté pour les utilisateurs. 
Des taches déjà identifiés pour la plus part mais systématiquement repoussés pour faire face à la charge de travail actuelle.
