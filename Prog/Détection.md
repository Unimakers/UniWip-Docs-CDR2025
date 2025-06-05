---
title: Détection
parent: Programmation
layout: default
---
# Détection par LIDAR (Robot principal) ou UltraSon (PAMIs)
Afin de ne pas percuter un robot adverse, les robots doivent être muni d'une technique de détection.
Dans l'objectif de ne pas ralentir l'éxécution du code, cette stratégie de détection tourne sur le 2e coeur du microcontrolleur, et communique avec le premier coeur à l'aide d'un booléen pointé.

Lorsque le coeur de détection apperçoit un obstacle (lorsqu'un point est inférieur à une certaine distance) il définit la valeur du booléen sur `true` et ne la redéfinit sur `false` qu'après 3 secondes sans aucune détection d'obstacle, le *cooldown* est recommencé à chaque détection d'obstacle (ainsi le robot attendra 3 secondes après sa dernière détection d'obstacle avant de pouvoir recommencer à se déplacer)