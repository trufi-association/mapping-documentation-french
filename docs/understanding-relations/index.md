# Documentation

## Understanding OSM relations

Relations use existing objects in the OpenStreetMap database to create new data out of existing data by connecting them. In OSM several types of relations exist e.g. the [Relation 9373675](https://www.openstreetmap.org/relation/9373675) is a bus relation with `type=route`. 

# Documentation

## Comprendre les relations dans OSM

Les relations utilisent des objets existants dans la base de données OpenStreetMap pour créer de nouvelles données à partir de données existantes en les connectant. Dans OSM, il existe plusieurs types de relations, par exemple la [Relation 9373675](https://www.openstreetmap.org/relation/9373675) est une relation de bus avec `type=route`.

---

![](streets.png)

We see here a bunch of streets with their names (the street --> la calle). Streets are represented by one or more ways. On its own we cannot get to know which bus line is on which street e.g. we do not know that the route of _Bus 101_ uses the streets  _Avenida Republica_ and _Avenida Oquendo_. This is where relations come in. Relations allow us to connect streets to a route so we know exactly which bus drives in which street.

On voit ici un tas de rues avec leurs noms (la rue --> la calle). Les rues sont représentées par une ou plusieurs voies. Nous ne pouvons pas savoir à elle seule quelle ligne de bus se trouve dans quelle rue, par exemple nous ne savons pas que le trajet du _Bus 101_ utilise les rues _Avenida Republica_ et _Avenida Oquendo_. C'est là qu'interviennent les relations. Les relations nous permettent de relier des rues à un itinéraire, de sorte que nous savons exactement quel bus circule dans quelle rue.

![](busroute.png)

The orange line shows the route _Bus 101_ is driving. What do we now is adding this information to OSM. 

La ligne orange indique l'itinéraire emprunté par le _Bus 101_. Il s'agit maintenant d'ajouter ces informations dans OSM.

![](connected-streets.png)

We see a small part of the bus relation here. And everything that is part of the relation is marked red. That means all streets (ways) that are marked red actually belong to the relation: We connected the street *Avenida Republica* with the street *Avenida Oquenda* in our relation. So a relation is basically a set of nodes and ways in a specified order and describes a high level feature (e.g. bus route) by just combining existing data.

Nous voyons ici une petite partie de la relation de ligne de bus. Et tout ce qui fait partie de la relation est marqué en rouge. Cela signifie que toutes les rues (voies) qui sont marquées en rouge appartiennent en fait à la relation : Nous avons relié la rue *Avenida Republica* avec la rue *Avenida Oquenda* dans notre relation. Une relation est donc essentiellement un ensemble de nœuds et de voies dans un ordre précis et décrit une caractéristique de haut niveau (par exemple, une ligne de bus) en combinant simplement des données existantes.

![](relation-street-list.png)

JOSM can show us the members (streets) of the relation not just graphical but also tabular. The table shows an ordered list from top to bottom of the ways that are part of the relation.

JOSM peut nous montrer les membres (rues) de la relation non seulement graphiquement mais aussi sous forme de tableau. Le tableau montre une liste ordonnée de haut en bas des voies qui font partie de la relation.

**Summary:** Relations in OSM are high level feature that build something new (e.g. a bus route) upon existing OpenStreetMap data (e.g, streets (mapped ways)). So relations can be used to add bus routes and much more complexity and makes use of added infrastructure.

**Résumé :** Les relations dans OSM sont des fonctionnalités de haut niveau qui construisent quelque chose de nouveau (par exemple une ligne de bus) à partir de données OpenStreetMap existantes (par exemple, des rues (voies cartographiées)). Ainsi, les relations peuvent être utilisées pour ajouter des itinéraires de bus et beaucoup plus de détails et permettent d'utiliser une infrastructure supplémentaire.
