---
title: Simplicité
authors:
  - Olivier Albiez
  - Thomas Clavier
tags:
  - concept
illustration: /assets/images/articles/simplicity/kiss.jpg
---

La complexité engendre des coûts de conception, de maintenance et augmente les risques d'erreurs. De nombreuses équipes agiles utilisent les concepts de simplicité suivant. On les retrouve souvent sous forme de poster sur les murs de ces équipes.


## KISS

[KISS] est l'acronyme de _Keep It Simple, Stupide_ (Reste simple, idiot). Dans la conception d'un système, il est préconisé de commencer par des versions simples qui fonctionnent et de n'introduire de la complexité que quand on y est contraint.

Pour illustrer ce principe d'autres ont préféré détourner l'acronyme :
> _Keep it simple, stupid - Keep it stupidly simple - Keep it simple and stupid - Keep it simple, silly - Keep it small and simple - Keep it sweet and simple - Keep it simple and straightforward - Keep it short and simple - Keep it simple and smart - Keep it strictly simple - Keep it super-simple - Keep it sober and significant - Keep it short and sweet_


## DRY

[DRY] est l'acronyme de _Don't Repeat Yourself_ (Ne vous répétez pas). Ce principe cherche la simplicité par la factorisation du code. 


## YAGNI

[YAGNI] est l'acronyme _You Ain't Gonna Need It_ (Tu n'en auras pas besoin). L'idée de ce principe est de n'ajouter les fonctionnalités que quand c'est strictement nécessaire.


## Poka yoke

[Poka yoke] signifie anti-erreur en japonais, c'est la version industriel de la simplification. Il s'agit de trouver des solution pour apporter un feedback très rapide sur les erreurs ou prévoir un système résistant aux étourderies : un détrompeur, une forme asymétrique, une prise réversible. 
Dans le domain du logiciel on pourra par exemple : utiliser le typage fort, déclencher une erreur s'il manque un composant, rendre un appel de méthode idempotent, etc.


## Conslusion

En simplifiant au niveau technique ([KISS], [DRY], [Poka yoke]) et au niveau fonctionnel ([YAGNI], [Poka yoke]) on réduit les coûts de maintenance et on baisse les risques d'erreurs.
Seulement attention, faire simple implique de pouvoir amender tout ou partie du système en permanence, pour ajouter chaque nouvelle petite fonctionnalité. 
Ce qui impose d'avoir une bonne stratégie de test et s'assurer ainsi que chaque changement ne présente aucune régression.

---
Sources:

- [DRY]
- [KISS]
- [YAGNI]
- [Poka yoke]

[DRY]: https://fr.wikipedia.org/wiki/Ne_vous_r%C3%A9p%C3%A9tez_pas
[KISS]: https://fr.wikipedia.org/wiki/Principe_KISS
[YAGNI]: https://fr.wikipedia.org/wiki/YAGNI
[Poka yoke]: https://fr.m.wikipedia.org/wiki/Poka-yoke
