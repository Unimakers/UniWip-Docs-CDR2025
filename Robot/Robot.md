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
- 
##Installation et homologuation

Avant de pouvoir participer à son premier match, le robot doit passer toute une batterie de tests qui va devoir réussir pour être homologué. Cette homologuation est divisée en deux parties :

-Une statique : vérification de la conformité dimensionnelle, des modules etc..
-Une dynamique : le robot doit être capable de sortir de sa zone de départ et de réaliser une action en 100s.

À savoir que, toute modification éffectuée une fois l'homologation passée doit être signalée au référé, suivi d'une nouvelle validation du robot.

### Les règles spécifiques au robot 

Le robot est soumis à des règles précises qu'il doit respecter pour etre homologué et pouvoir participer aux match, telles que : 

-Les dimensions, un périmètre  ≤ 1200mm en position repliée et  ≤ 1400mm en déployé.
-Le robot doit être entièrement autonome.
-Le respect des normes d'électricité.
-Il doit avoir un système anti-collision contre les robots adverses.
-Il doit présenter son marqueur d'identification.


## Les actionneurs et les capteurs

Pour accomplir au mieux les actions de jeu, le robot etait équipé d'actionneurs. L'actionneur chargé de soulever les planches avait été imaginé avec des ventouses. Celles-ci, accrochées par paires à l'extrémité de deux bras articulés, etaient reliées à des pompes sur la face arrière du robot. 
Pour les boites de conserve, l'action se faisait en se basant sur le magnétisme de celles-ci. Incrémentée de petits aimants, la sorte de pince se déplace de haut en bas sur un rail pour soulever les élements de jeux. 
Pour avoir une idée du processus de conception de cet actionneur, vous retrouverez ci-dessous l'image de la première version : 

 <img src="Images/v1 actio conserve.png" width=500>
 
 On retrouve dès le depart l'idée d'utiliser le magnétisme, cependant nous avons pu affiner le rendu de la pièce jusqu'à finalement arriver au rendu final suivant : 
 
 <img src="Images/vf actio conserve.png" width=500 >
