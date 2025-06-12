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

La prmère était de déployer une banderole conçue par l'équipe, avec comme contrainte de se déployer à l'avant de la table définie par la couleur de notre équipe.
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
- Dépasser la hauteur maximale en dehors des zones de constructions

### Les règles spécifiques au robot 

Le robot est soumis à des règles précises qu'il doit respecter pour etre homologué et pouvoir participer aux match, telles que : 

-Les dimensions 
-Respect des normes d'électricité 
-

### Les actionneurs et les capteurs

Pour accomplir au mieux les actions de jeu, le robot etait équipé d'actionneurs. L'actionneur chargé de soulever les planches avait été imaginé avec des ventouses. Celles-ci, accrochées par paires à l'extrémité de deux bras articulés, etaient reliées à des pompes sur la face arrière du robot. 
Pour les boites de conserve, l'action se faisait en se basant sur le magnétisme de celles-ci. Incrémentée de petits aimants, la sorte de pince se déplace de haut en bas sur un rail pour soulever les élements de jeux. 
 
