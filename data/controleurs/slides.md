!SLIDE subsection ================

# CONTRÔLEURS


!SLIDE ===========================

# contrôleur
# =
# initialisation du scope


!SLIDE ===========================

# pas de traitements
## sur les données


!SLIDE ===========================

# lien
## entre services
## et scope


!SLIDE ===========================

# contrôleurs légers

!NOTES ---------------------------

* pas des objets propres au sens OOP


!SLIDE ===========================

# contrôleur local
## pour une zone de la vue


!SLIDE bullets ===========================

## contrôleur sur un scope répété
### pour calculer des valeurs, ou mettre un watch

    <ul>
      <li ng-repeat="item in list"
          ng-controller="ItemCtrl">
          ...
      </li>
    </ul>


!SLIDE bullets ===========================

# syntaxe “controller as ...” ?
### préconisée par Google

<br/>

* mieux pour l'héritage entre les scopes
* plus explicite dans les templates
* mais plus verbeux

