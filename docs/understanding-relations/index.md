# Comprendre les relations dans OSM

!!! note ""
	TCHAMIE Léleng Denis ([OSM Togo](https://wiki.openstreetmap.org/wiki/FR:Togo)) a traduit la page en français. Oeuvre originale de Sören Reinecke ([Trufi Association](https://trufi-association.org/))

Les relations utilisent des objets existants dans la base de données OpenStreetMap pour créer de nouvelles données à partir de données existantes en les connectant. Dans OSM, il existe plusieurs types de relations, par exemple la [Relation 9373675](https://www.openstreetmap.org/relation/9373675) est une relation de bus avec `type=route`.

---

![](streets.png)

On voit ici un tas de rues avec leurs noms (la rue --> la calle). Les rues sont représentées par une ou plusieurs voies. Nous ne pouvons pas savoir quelle itinéraire de bus passe dans quelle rue. Par exemple nous ne savons pas que le trajet du _Bus 101_ utilise les rues _Avenida Republica_ et _Avenida Oquendo_. C'est là qu'interviennent les relations. Les relations nous permettent de relier des rues à un itinéraire, de sorte que nous savons exactement quel ligne bus circule dans quelle rue.

![](busroute.png)

La ligne orange indique l'itinéraire emprunté par le _Bus 101_. Il s'agit maintenant d'ajouter ces informations dans OSM.

![](connected-streets.png)

Nous voyons ici une petite partie de la relation d'un itinéraire de bus. Et tout ce qui fait partie de la relation est marqué en rouge. Cela signifie que toutes les rues (voies) qui sont marquées en rouge appartiennent en fait à la relation : Nous avons relié la rue *Avenida Republica* avec la rue *Avenida Oquenda* dans notre relation. Une relation est donc essentiellement un ensemble de nœuds et de voies dans un ordre précis et décrit une caractéristique de haut niveau (par exemple, une ligne de bus) en combinant simplement des données existantes.

![](relation-street-list.png)

JOSM peut nous montrer les membres (rues) de la relation non seulement graphiquement mais aussi sous forme de tableau. Le tableau montre une liste ordonnée de haut en bas des voies qui font partie de la relation.

**Résumé :** Les relations dans OSM sont des fonctionnalités de haut niveau qui construisent quelque chose de nouveau (par exemple un itinéraire de bus) à partir de données OpenStreetMap existantes (par exemple, des rues (voies cartographiées)). Ainsi, les relations peuvent être utilisées pour ajouter des itinéraires de bus, beaucoup plus de détails et permettent d'utiliser une infrastructure supplémentaire.
