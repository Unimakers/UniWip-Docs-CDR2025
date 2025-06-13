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
  
## Installation et homologation

Avant de pouvoir participer à son premier match, le robot doit passer toute une batterie de tests qui va devoir réussir pour être homologué. Cette homologuation est divisée en deux parties :

-Une statique : vérification de la conformité dimensionnelle, les normaes de sécurité.

-Une dynamique : le robot doit être capable de sortir de sa zone de départ et de réaliser une action en 100s.

À savoir que, toute modification éffectuée une fois l'homologation passée doit être signalée au référé, suivi d'une nouvelle validation du robot.

### Les règles spécifiques au robot 

Le robot est soumis à des règles précises qu'il doit respecter pour etre homologué et pouvoir participer aux match, telles que : 

-Les dimensions, un périmètre  ≤ 1200mm en position repliée et  ≤ 1400mm en déployé.
-Le robot doit être entièrement autonome.
-Le respect des normes d'électricité.
-Il doit avoir un système anti-collision contre les robots adverses.
-Il doit présenter son marqueur d'identification.

