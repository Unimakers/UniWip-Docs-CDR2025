---
layout: default
title: "Programmation"
---

# Programmation du robot
Pour la programmation du robot, nous avons fait le choix de créer un programme très modulaire et permettant de créer très facilement des stratégie, de sorte que n'importe qui puisse créer une stratégie, même quelqu'un n'ayant pas forcément des compétences en programmation.


## Structure du code

Le code est découpé en plusieurs fichiers:
- `constante.h`, le fichier des variables du robot, voir [Généralisation du code](#généralisation-du-code) pour plus d'information.

- `RobotMove.cpp` et `RobotMove.h`, c'est la librairie de mouvement du robot, regardez la page [déplacement](./Déplacement.html) pour plus d'informations sur les fonctions de déplacement.

- `lidar.cpp` et `lidar.h`, c'est la librairie de détection du lidar, regardez la page [détection](./Détection.html)

- `main.cpp`, c'est le code principal, voir [Code principal](#code-principal) pour plus d'informations.


## Généralisation du code
Le fichier `constante.h` permet de modifier des valeurs telles que les pins correspondant à certains composants, la largeur du robot, le nombre de pas par tour pour les moteurs, etc.

Cela permet d'avoir une base de code utilisable sur presque n'importe quel robot ayant 2 roue comme notre robot.

Nous avons donc pour simplifié l'upload créé une variable booléenne PAMI dans le fichier `constante.h` permettant de switcher facilement entre les PAMIs ou le Robot Principal (pour les valeurs de la taille mais également pour les stratégies ou certaines sécurité dans certaines fonctions d'actionneur par exemple).

## Code principal

C'est le code central du fonctionnement du robot.

Il fait interface entre les différents code tout en rajoutant un grand nombre de fonctionnalités.

C'est dans le code principal que sont défini les stratégies.

Dans le code principal sont également défini les fonctions permettant de créer facilement des stratégies, les types d'actions, les états, le fonctionnement des actionneurs, les procédures d'initialisation du robot, l'utilisation des fonctions de la librairie lidar et l'interaction avec les fonctions de la librairie mouvement.

### Stratégie et actions

Afin de pouvoir simplifier la création de stratégie nous avons créé une structure `etape` contenant le type d'action et les variables associées à cette action (la distance, l'angle, la vitesse etc.) interpretable grâce à la fonction `actioncall` et un type `strategie` correspondant à une liste d' `etape`.

Pour simplifier la création d' `etape` nous avons créé des fonctions pour chaque type d'action avec comme seul argument les variables nécessaire à cette action. Cela permet par exemple pour une action `FORWARD` de passer de `{.action=A::FORWARD,.distance=5000,.vitesse=DEFAULT_SPEED}` à `FORWARD(5000)` ce qui permet de simplifier encore plus la création de stratégie.

Les types d'actions possibles sont:
- `FORWARD`: faire avancer le robot sur une certaine distance, un argument vitesse est possible mais par défaut sur DEFAULT_SPEED
- `BACKWARD`: faire reculer le robot sur une certaine distance, un argument vitesse est possible mais par défaut sur DEFAULT_SPEED
- `TURN`: faire tourner le robot sur une certain angle, un argument vitesse est possible mais par défaut sur DEFAULT_SPEED
- `TURNTO`: faire tourner le robot vers un certain angle, un argument vitesse est possible mais par défaut sur DEFAULT_SPEED
- `MOVETO`: faire se déplacer le robot vers une certaine position sur le terrain de jeu, un argument vitesse est possible mais par défaut sur DEFAULT_SPEED
- `FERMER_AIMANTS`: fermer les aimants permettant de relacher les boîtes de conserves
- `OUVRIR_AIMANTS`: ouvrir les aimants permettant d'attraper des boites de conserves
- `MONTER_CANNETTE_2E_ETAGE`: monter l'élevateur en position très haute permettant de soulever une structure et de ne pas percuter une autre structure lorsqu'on souhaite réaliser un étage
- `MONTER_ACTIONNEUR`: mettre l'élévateur en position haute permettant de poser une structure sur une autre structure pour réaliser un étage (cette action ne doit donc être appelée qu'après `MONTER_CANNETTE_2E_ETAGE` et en étant sur que l'actionneur est actuellement au dessus d'une structure)
- `MONTER_BANDEROLE`: met l'élevateur en position assez haute pour que la banderole ne touche pas le sol, n'est utilisé que dans l'initialisation banderole, pour pouvoir relacher la banderole depuis l'actionneur.
- `MILIEU_ACTIONNEUR`: permet de mettre l'élevateur en position par défaut, utile pour l'initialisation et pour les recalage bordure.
- `DESCENDRE_ACTIONNEUR`: permet de mettre l'élevateur en position basee, position qui permet d'attraper les boites de conserve pour faire une structure (pour être sur que l'on prend bien une planche avec les 2 boites de conserve, il faut remonter l'actionneur au moins avec `MILIEU_ACTIONNEUR` après être sur que l'actionneur a pris des boites de conserve).
- `MONTER_BRAS`: range les bras dans le robot, c'est la position d'initialisation pour que le robot rentre dans le périmètre de départ
- `DESCENDRE_BRAS`: descend les bras afin de pouvoir prendre des du dessus ou reposer des planches sur des boites de conserve (à utiliser avec `ACTIVER_POMPE` et `DESACTIVER_POMPE`)
- `MILIEU_BRAS`: met les bras en position semi haute permettant de se déplacer avec une planche
- `ACTIVER_POMPE`: active la pompe permettant de prendre une planche à l'aide des ventouses présentent sur les bras
- `DESACTIVER_POMPE`: desactive la pompe permettant de relacher une planche
- `WAIT` fait attendre le code pendant un certain temps en seconde
- `ACTIONNEUR_POS` permet de mettre l'élevateur à une position précise (rarement voire jamais utilisé).
- `WAIT_END` permet d'attendre presque la fin du match, par exemple pour se mettre en proximité de la zone de fin et attendre la fin du match pour y entrer, ce qui permet de ne pas bloquer le chemin des PAMIs