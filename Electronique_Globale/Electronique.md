---
layout: technical
title: Electronique
nav_order: 3
---

Pour notre première année nous avons réalisé notre propre carte la Uniboard V1.
Basée sur un Xiao ESP32S3, un micro controlleur à le fois compacte et facile d'utilisation.
Cette carte a pour particularité d'avoir été pensé pour convenir sur trois type de robot très different:

-Le robot principal de notre équipe (UniWIP) allimenté par une batterie parkside 12V 
-Le robot principal de l'équipe UniShape allimenté par deux batterie parkside 12v en série (alimentation total de 24V)
-Les PAMIs au nombre 3 ils ont la contrainte de devoir être compacte et allimenté par leurs batterie externe en 5V

La carte devait contenir des éléments commun tels que:

-2 emplacements drivers permettant de piloter autant de moteurs pas à pas
-1 emplacement pour connecter une tirette 
-1 emplacement de micro controlleur, un xiao choisi pour les qualité cité plus haut
-2 emplacements minimum pour connecter des extension I2C et deux autres optionnels, autant d'emplecements d'alimentation
-1 diode shottky pour prévenir d'un retour de courant

Cependant au vu des différentes contraintes il fallait des emplacements optionnel en fonction du robot:

-1 emplacement capteurs, lidar pour les robots principaux ou capteur ultrason pour les PAMIs.
-Les différents convertisseur de puissance pour s'adapter à l'allimentation.
-1 emplacement de bouton d'arrêt d'urgence pour les PAMIs

<kicanvas-embed controls="full">
    <kicanvas-source src="./Carte_Fichiers_KiCad/UniBoard-Xiao.kicad_pcb"></kicanvas-source>
    <kicanvas-source src="./Carte_Fichiers_KiCad/UniBoard-Xiao.kicad_sch"></kicanvas-source>
</kicanvas-embed>

En résultats une carte de 8*8 cm documenté permettant une utilisation et une intégration simple et intuitive.
