!SLIDE subsection ================

# FILTRES


!SLIDE ===========================

# ne jamais modifier
## les données en entrée


!SLIDE ===========================

# parser / évaluer des expressions
### plutôt que de prendre des noms de propriétés

    users | orderBy:'profile.name':false


!NOTES ---------------------------

* C'est important de respecter les habitudes et conventions.
* Usage naturel, correspond à ce qui est attendu, moins de temps perdu.


!SLIDE ===========================

# $parser

    var getter = $parser(expr);

    var value = getter(context);


!SLIDE ===========================

    item in list | filter:search

    (list | filter:search).length

### plutôt :

    item in filtered = (list | filter:search)

    filtered.length




