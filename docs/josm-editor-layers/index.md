# Explication des _Couches_ dans l'éditeur JOSM

!!! note ""
	Kokou Elolo AMEGAYIBO - AKEAmazan ([OSM Togo](https://openstreetmap.tg/)) a traduit la page en français. Oeuvre originale de Sören Reinecke ([Trufi Association](https://trufi-association.org))

![](josm-editor-layers.png)

Vous avez peut-être déjà vu cela auparavant et vous vous demandez peut-être à quoi cela sert.

Les inscriptions qui y figurent représentent l'ordre. Le premier en haut ( _Converti de : P Se-O 2.json_ ) est celui qui sera affiché au-dessus des autres couches _Couche de données 1_ et _OpenStreetMap Carto (Standard)_.

En règle générale, pour décider du tri : La couche qui contient le plus de données est celle qui se trouve en bas de la liste (ici : OpenStreetMap Carto (Standard)_ ). La couche qui contient le moins de données est celle qui se trouve en haut de la liste (ici : _Converti de : P Se-O 2.json_).

- Les imageries comme *OpenStreetMap Carto (Standard)* sont généralement en bas de la liste parce qu'il s'agit d'un tas d'images et que les images contiennent beaucoup de données. L'imagerie est également appelée la _carte de fond_.

- Les représentations des données OSM que vous pouvez modifier et télécharger comme la _couche de données 1_ se trouvent généralement au milieu ou en haut de la liste. C'est la couche qui contient le plus de données après l'imagerie.

- Lorsque vous ajoutez des données externes que vous avez reçues des autorités à l'OSM, vous avez quelque chose comme *Converti de : P Se-O 2.json* en haut de la liste parce qu'elles ne contiennent généralement que des ensembles de données spécifiques et pas tous. Cela signifie qu'ils ne contiennent généralement pas beaucoup de données.

À l'intérieur du tableau, vous pouvez faire glisser et déposer des lignes individuelles (entrées) pour modifier leur position dans la liste ou sélectionner une entrée et cliquer ensuite sur l'un des boutons fléchés.

- Je recommande l'ordre suivant, de haut en bas :
  
  - Les ensembles de données externes reçus par les autorités.
  
  - Données déjà dans OSM
  
  - Imagerie

En sélectionnant une entrée (couche) et en cliquant sur le bouton portant le symbole _Poubelle_, on supprime la couche sélectionnée. **Attention à ne pas perdre les modifications effectuées sur les données que la couche représente.**

En cliquant sur le bouton avec le symbole _oeil_, on active/désactive la couche. Cela signifie qu'elle change sa visibilité sur la carte.


