---
layout: default
title: "Déplacement"
parent: "Programmation"
---
# Les déplacements du robot

La librairie de déplacement du robot est une classe contenant plusieurs fonctions pour le déplacement du robot:
- `run`: c'est la fonction appelée à chaque loop permettant de faire tourner les moteurs, c'est également cette fonction qui reçoit les informations du lidar et applique la fonction `stop` ou la fonction `resume` en fonction de l'état du lidar
- `stop`: permet d'arreter proprement le robot
- `resume`: permet de recommencer la route du robot la ou elle s'était arrêtée
- `reachedTarget`: permet au programme principal de savoir si une action est finie pour pouvoir passer à l'action suivante
- `moveTo` et `moveToLoop`: comme indiqué dans [la documentation des stratégies et action du code principal](./Programmation.html#stratégie-et-actions) cette fonction permet de faire se déplacer le robot vers une position, elle execute donc un `turn` vers la position, puis un `forward` de la distance à parcourir puis un `turn` vers l'angle de déstination.
- `forward`: comme indiqué dans [la documentation des stratégies et action du code principal](./Programmation.html#stratégie-et-actions) cette fonction permet de faire avancer le robot sur une certaine distance et avec une certaine vitesse
- `backward`: comme indiqué dans [la documentation des stratégies et action du code principal](./Programmation.html#stratégie-et-actions) cette fonction permet de faire reculer le robot sur une certaine distance et avec une certaine vitesse
- `turn`: comme indiqué dans [la documentation des stratégies et action du code principal](./Programmation.html#stratégie-et-actions) cette fonction permet de faire tourner le robot sur un certain angle et avec une certaine vitesse
- `turnTo`: comme indiqué dans [la documentation des stratégies et action du code principal](./Programmation.html#stratégie-et-actions) cette fonction permet de faire tourner le robot vers un certain angle et avec une certaine vitesse
- `setCoord`: cette fonction permet de redéfinir les coordonnées actuelles du robot, utile par exemple à l'initialisation ou après un recalage bordure

Les déplacements du robot utilisent la librairie publique `AccelStepper` pour chacun des moteurs.