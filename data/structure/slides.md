!SLIDE subsection ================

# STRUCTURE


!SLIDE ===========================

# organiser par type ?
![](linge.gif)

!NOTES ---------------------------

* comme on fait pour le linge ?


!SLIDE ===========================

# découpage fonctionnel
### et par type au plus bas niveau


!SLIDE ===========================

    front/
        profiles/
        repositories/
        activity/
        contributions/

    back/
        statistics/

    common/


!SLIDE ===========================

# 1 fichier JS &nbsp; = &nbsp; 1 module


!SLIDE ===========================

    front/
        front.js
        profiles/
            profiles.js
            profiles-controller.js
            profiles-service.js
            profiles-directive.js
        repositories/
            repositories.js
            ...


!SLIDE ===========================

    common/
        common.js
        common-service.js
        common-filter.js
        common-directive.js


!SLIDE ===========================

## + templates, tests, images...


!SLIDE bullets ===========================

# routes :
## dans chaque branche

<br/>

* ajouter des données à la définition de la route
* récupérables dans `$route.current`

!SLIDE ===========================

# un service &nbsp;`constant()`
### utilisable dans `config()`
<br/>
## pour définir le chemin des templates


