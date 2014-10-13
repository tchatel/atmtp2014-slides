!SLIDE subsection ================

# GENERALITÉS


!SLIDE ===========================

## attention aux composants

![](champignons.gif)

!NOTES ---------------------------

* certains sont bons, d'autres sont toxiques
* exemple du ngGrid aux performances catastrophiques


!SLIDE ===========================

# ne pas optimiser
### sauf quand c'est VRAIMENT nécessaire

!NOTES ---------------------------

* AngularJS permet d'écrire du code simple, mais si on s'embarque dans plein d'optimisations
inutiles, il peut vite devenir très complexes
* gagner 20ms lors d'un clic, ça n'a aucun intérêt
* c'est du CPU client, pas serveur


!SLIDE ===========================

# bindings sur des fonctions
### sans stocker le résultat


!SLIDE ===========================

# travaillez le modèle
## View-Model
## vrai modèle objet, pas juste du JSON

!NOTES ---------------------------

* exemple : indexer les éléments d'un tableau
* modèle riche : vrais objets avec des méthodes, pas juste des données JSON


!SLIDE ===========================

# service dans le scope
### ou une façade

!NOTES ---------------------------

* non ce n'est pas une hérésie



