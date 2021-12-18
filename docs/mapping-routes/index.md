# Cartographie des lignes de bus informelles

!!! note ""
	Kokou Elolo AMEGAYIBO - AKEAmazan ([OSM Togo](https://openstreetmap.tg/)) a traduit la page en français. Oeuvre originale de Sören Reinecke ([Trufi Association](https://trufi-association.org))

Ce tutoriel montre comment ajouter des lignes de bus informelles à OpenStreetMap. Pour que ce tutoriel soit efficace, vous devez avoir [JOSM installé](../installing-josm-on-linux/index.md) et l'outil [de cartographie personnalisée](../installing-mapping-tool/index.md) (si votre communauté l'exige). Pour télécharger vos modifications dans OSM, vous avez également besoin de votre installation JOSM [synchronisée] (../oauth-josm/index.md) avec votre compte OpenStreetMap.

## Préparer notre lieu de travail

1. Ouvrez JOSM (ce tutoriel suppose que vous l'avez déjà). ![](josm-logo.png)

2. Une fenêtre devrait s'ouvrir comme suit ![](josm-startpage.png)

3. Nous devons d'abord charger les données que vous avez reçues de votre communauté. Cliquez sur _Fichier_ dans la barre supérieure:![](josm-topbar.png)

4. On clique ensuite sur _Ouvrir_ dans le menu: ![](josm-file-menu.png)

5. Une boîte de dialogue apparaît et vous invite à sélectionner le fichier que vous avez reçu de votre communauté. Allez à l'endroit où vous avez enregistré le fichier `*.geojson`, cliquez sur ce fichier et ensuite _Ouvrir_:![](josm-opendialog.png)

6. Attendez la fin du processus de chargement. Une fois le chargement terminé, l'interface utilisateur change considérablement. Ce que nous voyons maintenant est notre éditeur : ![](josm-editor-overview.png)

7. Avant de pouvoir commencer la cartographie, nous devons préparer l'éditeur et y charger les données OSM. Commençons par charger les données de l'OSM. Cliquez à nouveau sur _Fichier_ dans la barre supérieure: ![](josm-topbar.png)

8. Et puis _Télécharger les données..._: ![](josm-file-menu-downloaddata.png)

9. Nous commençons à aimer les popups. Dans celui-ci, nous n'avons probablement pas besoin de modifier la boîte de délimitation que vous voyez dans la carte affichée parce que JOSM l'a fait pour nous car nous avons chargé le fichier `*.geojson`: ![](josm-downloaddialog.png)

10. Cliquez sur _Télécharger comme nouvelle couche_. Si la zone sélectionnée est trop grande, redimensionnez-la en revenant à cette boîte de dialogue, cliquez et faites glisser la souris sur une partie plus petite de la zone précédemment sélectionnée. Relâchez la souris pour créer une nouvelle boîte de délimitation. Répétez cette étape jusqu'à ce que le système soit satisfait :)

11. Cela semble plus prometteur: ![](josm-editor-osmdataloaded.png)

12. Mais nous ne sommes pas encore heureux, n'est-ce pas ? Pour le rendre encore plus beau, nous devons ajouter les tuiles OSM. Nous allons sur _Imagery_ dans la barre supérieure et nous sélectionnons _OpenStreetMap Carto (Standard)_. C'est beau, n'est-ce pas ?

13. Jetons un coup d'oeil rapide à la section _Couches_ en haut à droite de l'éditeur.
    
    ![](josm-editor-layers.png)
    
    Au fait : Vous pouvez redimensionner les sections en cliquant sur les limites respectives et en les faisant glisser jusqu'à la position de votre choix.

14. Cliquez avec le bouton droit de la souris sur l'entrée portant l'extension de fichier `.geojson` ou `.json`. Puis cliquez sur _Convertir en couche GPX_: ![](josm-editor-layers-togpx.png)

15. Le nom de l'entrée a changé et ressemble à ceci: ![](josm-editor-layers-aftertogpx.png)

16. Nous faisons un nouveau clic droit sur l'entrée et sélectionnons
    
    - _Personnaliser la couleur_ dans un premier temps,
    
    - _Téléchargement depuis OSM le long de la piste_ dans un second temps
    
    - et _Précachez les tuiles d'imagerie le long de cette piste_ enfin.

17. En outre, nous cliquons à nouveau sur l'entrée et sélectionnons _Personnaliser le dessin des pistes_ et un nouveau popup apparaît: ![](josm-layers-customizedrawing.png)

18. Dans le champ de texte à côté de _Largeur de dessin des lignes GPX_, saisissez la largeur en px. Je recommande de taper `5`. Cliquez ensuite sur _Ok_.

19. Appuyez sur ALT+SHIFT+F1 pour arrêter le téléchargement automatique des données pendant le déplacement de la carte. Vous pouvez également cliquer sur _Fichier_ dans la barre supérieure, puis sur _Télécharger les données OSM en continu_. C'est un bascule. Ensuite, naviguez à l'intérieur de la carte jusqu'au bout de la ligne. Pour naviguer dans la carte, vous devez maintenir la touche droite de la souris enfoncée tout en déplaçant la souris. Utilisez la molette de votre souris pour faire un zoom avant ou arrière. **La ligne a deux extrémités : _fin_ et _début_. Sélectionnez celle d'où viennent les flèches et non la fin vers laquelle elles pointent.**
    
    - Fin <-- Début
    
    - ![](josm-editor-arrowrule.png)

## Préparation des données OSM le long de l'itinéraire que nous voulons ajouter

Avant de commencer, nous devons travailler sur les données de OSM lui-même. Sur la dernière image, vous voyez la ligne de couleur rouge foncé et la ligne bleue. La première ligne représente la ligne de bus et la seconde la rue dans laquelle le bus circule dans OSM. Cette partie du tutoriel explique comment transformer la première ligne en données utiles.

Appuyez sur ALT+SHIFT+F1 pour arrêter/démarrer automatiquement le téléchargement des données tout en déplaçant la carte. Vous pouvez également cliquer sur *Fichier* dans la barre supérieure, puis sur *Télécharger les données OSM en continu*. C'est un bascule. Lorsque vous déplacez la carte vers une section où aucune donnée n'est disponible, vous pouvez activer le téléchargement continu de données OSM. Si vous utilisez la fonction de zoom de manière intensive, désactivez _Télécharger les données OSM en continu_.

1. Sélectionnez la ligne qui n'est pas la plus foncée mais qui est alignée sur celle-ci: ![](josm-editor-selectedstreet.png)

2. Nous ne voyons pas que toute la ligne devient rouge. Ce qui est pour nous une ligne (la ligne bleue) n'en est pas une aux yeux de l'ordinateur. La ligne a été divisée à l'endroit où _Calle Campinas_ croise la ligne que nous avons sélectionnée.

3. Nous voulons créer une route, donc nous cliquons sur *Préréglages* (dans la barre de menu supérieure) --> *Transport* --> *Public Transport* --> *Public Transport Route (Bus)*: ![](josm-symbolbar-busroute.png)

4. Une fenêtre contextuelle vous invite à saisir les données que vous avez reçues de votre communauté. Tapez les données dans les champs correspondants et cliquez sur _Ok_. Une nouvelle fenêtre s'ouvre et donne un aperçu: ![](josm-createrelation-overview.png)

5. Sur le coté droit, vous voyez une liste de tous les objets (rues) que vous avez sélectionnés dans l'éditeur JOSM. Sur le coté gauche, vous voyez une liste de tous les objets (rues) déjà ajoutés à la relation. **Ne fermez pas cette boîte de dialogue, nous en avons besoin !**

6. Sélectionnez d'autres rues le long de la ligne rouge foncé, allez à nouveau dans la boîte de dialogue et cliquez sur l'entrée surlignée en rouge où la dernière ligne de quatre lignes au total est sélectionnée pour ajouter la sélection à la liste des itinéraires sur le coté droit.![](josm-createrelation-addafterlastmember.png)Vous pouvez sélectionner plus d'une rue en appuyant et en maintenant la touche que vous utilisez pour commencer une nouvelle phrase par une lettre majuscule (SHIFT). 

7. Répétez l'étape _6_ après avoir constaté la situation suivante: ![](josm-editor-splitwaysneeded.png)

8. _Newton, nous avons un problème ! _ Ce que nous allons faire ensuite, c'est diviser la route. Alors on clique sur la carte pour désélectionner notre sélection. Assurez-vous d'ajouter toutes les rues, sauf la rue en question, à l'itinéraire comme à l'étape _6_..

9. Sélectionnez la rue (chemin) en question. Zoomez jusqu'au point où vous avez besoin de la division: ![](josm-editor-splitwaysneeded2.png)Zoom avant (vue coupée):![](josm-editor-splitwaysneeded3.png)

10. Sélectionnez la rue (ici en bleu).

11. Maintenez enfoncée la touche (SHIFT) que vous utilisez pour écrire une lettre majuscule au début d'une nouvelle phrase. Sélectionnez le carré (JOSM le surligne en jaune) tout en maintenant la touche enfoncée.![](josm-editor-splitwaysneeded4.png)

12. Dans la barre supérieure, cliquez sur _Outils_ puis sur _Séparer le chemin_. Vous pouvez également appuyer sur la touche _P_. Une boîte de dialogue vous invite à décider quel segment de voie doit préserver l'historique. Ignorez-le et cliquez sur _OK_. Désélectionnez tout en cliquant sur un espace libre de la carte.

13. Continuez avec l'étape _6_ jusqu'à la fin de la ligne foncée.

14. Lorsque vous avez atteint la fin de la ligne sombre, cela signifie que vous avez presque terminé. Il nous faut maintenant valider votre travail. Pour cela, nous allons dans le dialogue que vous devez laisser ouvert tout le temps pendant la cartographie.

15. Si vous n'êtes pas familier avec la validation, vous devriez consulter quelqu'un qui en a la charge. C'est un élément essentiel. Jetez un coup d'œil aux différentes options que le dialogue vous propose.
    
    - Sélectionnez une entrée dans la liste sur le coté gauche. Faites un clic droit dessus et cliquez sur _Zoom sur_ pour zoomer sur cet objet sur la carte. Utilisez cette méthode pour réparer les objets ayant le symbole suivant ou un symbole similaire :![](josm-createvalidation-routelist-error.png)
    
    - Utilisez la fonction _Zoom sur_ et la carte pour trouver les chemins manquants (rues). et survolez les boutons de la zone rouge surlignée à côté du tableau _selection_ pour obtenir ce qu'ils font de la sélection.![](josm-createselection-validate.png)
    
    - Le noir est votre ami :) Tout ce qui est noir dans la ligne de validation signifie que les données sont correctes.![](josm-createrelation-validate2.png)
    
    - La première et la dernière entrée montrent toujours un symbole rouge dans la ligne de validation parce qu'une extrémité n'est pas connectée à une autre voie (rue). C'est logique. Une ligne de bus se termine généralement quelque part.

16. Dans le dialogue de la liste des itinéraires, cliquez sur _OK_ pour créer cet itinéraire. Faites-le quand vous pensez avoir terminé.

17. Cliquez sur l'icône _Télécharger_ dans la barre de symboles située juste en dessous de la barre supérieure : ![](josm-symbolbar-upload.png)

18. Ignorez le dialogue _Données suspectes trouvées_ lorsqu'il s'affiche ou corrigez les problèmes. Informez votre communauté à ce sujet et dites-lui ce que vous avez modifié.

19. Un nouveau pop-up apparaît: ![](josm-uploaddialog.png)

20. Remplissez les informations demandées et cliquez ensuite sur _Télécharger les modifications_ pour terminer le processus de téléchargement.
