# Séparer un chemin en deux ou plusieurs

!!! note ""
	Kokou Elolo AMEGAYIBO - AKEAmazan ([OSM Togo](https://wiki.openstreetmap.org/wiki/FR:Togo)) a traduit la page en français. Oeuvre originale de Sören Reinecke ([Trufi Association](https://trufi-association.org))

Il peut être nécessaire de diviser les voies (couper une voie en deux ou plus) lorsqu'on ajoute une relation qui suit la voie pendant un certain temps et **pas** jusqu'à la fin. Ajouter un chemin à une relation sans le diviser peut avoir des effets secondaires indésirables. La division d'un chemin est également nécessaire lorsque les balises ne sont pas cohérentes en cours de route (de la position A à la position B, les balises diffèrent de celles de la position C à la position D).

![](josm-editor-splitwaysneeded.png)

Le plus sombre est notre itinéraire que nous voulons ajouter à l'OSM en tant que relation. Le rouge est la rue (chemin) que nous avons déjà dans la base de données OSM. Nous voyons qu'à un moment donné, elles ne correspondent pas. Le chemin (rue) dans OSM ne se termine pas là où notre itinéraire commence à suivre son propre chemin. Cela signifie que nous ne pouvons pas ajouter la rue à la relation dans son ensemble. Cela signifie que nous devons d'abord diviser la rue déjà dans OSM à l'endroit où notre itinéraire suit son propre chemin. 

## Séparer des chemins

Nous supposons que vous avez déjà ouvert JOSM et que vous êtes allé vers une voie que vous voulez scinder.

1. Cliquez sur le chemin que vous souhaitez scinder. Il doit devenir rouge: ![](josm-editor-splitwaysneeded.png)

2. Maintenant, maintenez la touche _SHIFT_ ( au-dessus de la touche _Ctrl_) et sélectionnez un nœud sur le chemin marqué où vous voulez diviser le chemin en deux. Habituellement, vous voulez vous séparer à l'endroit où la ligne rouge foncée suit son propre chemin (position : cercle bleu). Un nœud est représenté par un carré avec des bords jaunes comme ici.
   
   ![](josm-editor-splitwaysneeded2.png)
   
   ![](josm-editor-splitwaysneeded4.png)

	Après l'avoir sélectionné, il doit également devenir rouge.

4. Dans la barre supérieure, cliquez sur *Outils*, puis sur *Diviser*. Vous pouvez également appuyer sur la touche *P*.![](josm-topbar-tools.png)

5. Une boîte de dialogue vous invite à décider de quelle manière le segment doit conserver l'historique. Ignorez-le et cliquez sur *OK*. Désélectionnez tout en cliquant sur un espace libre sur la carte.
