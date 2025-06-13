---
title: "Robot"
nav_order: 1
layout: technical
---
# Le robot principal

<model-viewer alt="ROBOT" src="./Meca/FichiersGLTF/ExportRobotUniWIP.glb" ar style="width:80%; height:400px" shadow-intensity="1" camera-controls min-field-of-view="2deg"></model-viewer>
## Introduction

### Les Objectifs

Le robot est le premier à effecuer des actions lors d'un matchs. Cette annéa on pouvait compter 2 actions principales:

<div style="display: flex; justify-content: space-around; flex-wrap: wrap;">
<img src="Images/reglebanderole.png" >
<img src="Images/regleconserve.png" >
</div>


La première était de déployer une banderole conçue par l'équipe, avec comme contrainte de se déployer à l'avant de la table définie par la couleur de notre équipe.
La seconde conciste à prendre des planches et des conserves placés précisemment sur la table, afin de les amener dans une zone de construction définie pour construire des gradin d'un ou plusieurs étages.

À la fin du match, le robot doit terminer sa trajéctoire dans une zone à l'arrière de la table définie encore une fois par la couleur de notre équipe.

### Contraintes

Le robot est autorisé à :

- Manipuler les éléments de jeux (conserves et planches).
- déployer une bannière embarquée.

Le robot n'est pas autorisé à :

- Nuire à l'adversaire.
- Détruire des constructions adverses.
- Voler des conserves dans la zone réservée à l'adversaire.
- Dépasser la hauteur maximale en dehors des zones de constructions.
  

