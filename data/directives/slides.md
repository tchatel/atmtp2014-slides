!SLIDE subsection ================

# DIRECTIVES


!SLIDE ===========================

# privilégier les bindings
## aux manipulations de DOM


!SLIDE ===========================

# s'appuyer sur le HTML
## plutôt que de le remplacer
### (syndrome JSF)

!NOTES ---------------------------

* AngularJS : étendre le HTML, pas le faire disparaître
* ne pas abuser des widgets


!SLIDE ===========================

# attributs HTML
# =
## interface de la directive


!SLIDE ===========================

# pas d'héritage implicite
### (données du scope parent)


!SLIDE ===========================

# contrôleur de directive
## lien directives parent / enfants


!SLIDE ===========================

# expressions dans les attributs
### (éviter les nombres
### et les noms de propriétés)

!NOTES ---------------------------

* Nombres et noms de propriétés : code smell
* Un attribut texte peut parfois être pertinent


!SLIDE ===========================

# scope isolé
## lien “=” : comme nommer un argument
## pas de pollution d'un scope externe

!NOTES ---------------------------

* Comparable au scope local d'une fonction
* Sans scope isolé, les données publiées par la directive seront accessible de l'extérieur


!SLIDE ===========================

# directive sur plusieurs éléments
## syntaxe `-start` et `-end`
### (`ng-repeat-start="..."` / `ng-repeat-end`)
<br/>
## aussi valable pour vos propres directives


!SLIDE ===========================

# élément HTML standard
## directives `input`, `form`, `script`
### plutôt que de rechercher les éléments dans la page


