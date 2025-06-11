---
title: "Mécanique"
parent: "Robot"
layout: technical
---
# Le robot principal

<model-viewer alt="ROBOT" src="./FichiersGLTF/ExportRobotUniWIP.glb" ar shadow-intensity="1" camera-controls touch-action="pan-y"></model-viewer>
## Introduction

### Les Objectifs

Le robot est le premier à effecuer des actions lors d'un matchs cette années il y en avait 2:

<div style="display: flex; justify-content: space-around;">
<img src="../Images/reglebanderole.png" >
<img src="../Images/regleconserve.png" >
</div>

Déployer une banderole conçu par l'équipe devant se déployer à l'avant de la table.
Prendre des planches et des conserves afin de les amener dans une zone de construction pour construire des gradin.
À la fin du match, le robot doit se trouver dans une zone à l'arrière de la table.

### Contraintes

Le robot est autorisé à :

- Manipuler les éléments de jeux.
- déployer une bannière embarquée.

Le robot n'est pas autorisé à :

- Nuire à l'adversaire.
- Détruire des constructions adverses.
- Voler des conserves dans la zone réserver à l'adversaire.
- dépasser la hauteur maximal en dehors des zones de constructions
- Heurter l'adversaire.

Dans la suite de la documentation, vous verrez les différents actionneurs, capteurs et microcontrôleurs utilisés pour le robot.