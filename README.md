# Documentation de l'équipe UniWIP

Table de contenu:
- [Documentation de l'équipe UniWIP](#documentation-de-léquipe-uniwip)
  - [Comment créer une page ?](#comment-créer-une-page-)
  - [Comment afficher un modèle 3D](#comment-afficher-un-modèle-3d)

## Comment créer une page ?

Aller dans le dossier correspondant au thème de la page, 

exemple pour l'élec du robot principal: Robot/Elec/

Créer un nouveau fichier pour votre nouvelle page.

Rajouter en haut du fichier:

```yaml
---
title: "Titre de votre page"
layout: technical
---
```
Les clés de définition doivent se trouver entre les deux `---`.
Après le deuxième `---` vous pouvez écrire le contenu de la page **en markdown**.

Vous pouvez rajouter un 
```yaml
has_children: true
```
si vous souhaitez faire de cette page une page de catégorie qui aura donc des sous-pages.

Pour mettre cette page en tant que sous-page dans une catégorie (et non à la racine) vous devez rajouter une clé `parent` et eventuellement une clé `grand_parent`:

La clé `parent` permettra de définir le parent direct de la page, la valeur doit etre le titre de la page parent.

Exemple, si vous créez une page dans la catégorie `Electronique` du `Robot` vous devrez définir la clé `parent` avec la valeur `Electronique`.

La clé `grand_parent` permettra de définir le grand parent de la page, c'est à dire la catégorie racine, la valeur doit etre le titre du grand parent.

Exemple, si vous créez une page dans la catégorie `Electronique` du `Robot` vous devrez définir la clé `grand_parent` avec la valeur `Robot`

Actuellement l'arbre des titres et catégories est:
```
Racine:
|-Accueil
|-Robot:
| |-Electronique
| |-Programmation
| |-Mécanique
|-Pami:
| |-Electronique
| |-Programmation
| |-Mécanique
```

Exemple pour créer une catégorie `Actionneurs` dans `Mécanique` sous `Robot` et ensuite créer une page `Pince`:

On crée le dossier `Robot/Meca/Actionneurs` (c'est mieux pour la lisibilité de trier les pages dans des dossiers, techniquement on pourrait tout laisser à la racine).


On crée le fichier `Robot/Meca/Actionneurs/Actionneurs.md`:
```md
---
title: Actionneurs
parent: Mécanique
grand_parent: Robot
has_children: true
layout: default
---
# Les actionneurs de notre robot
Le robot a besoin d'actionneurs pour fonctionner
```

On crée le fichier `Robot/Meca/Actionneurs/Pince.md`:
```md
---
title: Pince
parent: Actionneurs
grand_parent: Mécanique
has_children: true
layout: default
---
# La pince du robot
La pince du robot, nécessaire pour attraper.....
```

## Comment afficher un modèle 3D

Dans votre code markdown rajoutez:
```md
{{%include model3D.html alt="Texte de description du modèle 3D" model="url / chemin du modèle 3D"%}}
``` 
Le modèle 3D **doit** être en format GLTF / GLB.
