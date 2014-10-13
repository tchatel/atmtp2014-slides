!SLIDE subsection ================

# SERVICES


!SLIDE bullets ===========================

## chaque fonctionnalité
# isolée dans un service

<br/>

* rien qu'une fonctionnalité
* mais dans son intégralité

!SLIDE bullets ===========================

# tout le code métier

* pas de traitements dans les contrôleurs
* pas de règles métier dans les templates


!SLIDE ===========================

    ng-class="{alert: quantity(row) >= 100}"

### plutôt :

    ng-class="{alert: orderSrv.isAlert(row)}"


!SLIDE ===========================

# conserver des données
### service = données + traitements


!SLIDE ===========================

## services asynchrones
# renvoyer des promesses


!SLIDE ===========================

# découper les services
## en couches


!SLIDE bullets ===========================

## erreurs et notifications

* un intercepteur $http
* surcharge du service $exceptionHandler
* un service pour les erreurs
* un service de log serveur
* un service de notification


!SLIDE ===========================

## utilisateur connecté
# 1. créer un service

<br/>

### pour injecter dans des services, des contrôleurs


!SLIDE ===========================
## utilisateur connecté
# 2. publier le service dans le scope

<br/>

### intégralement, partiellement, ou une façade
### uniquement pour les templates

!NOTES ---------------------------

* si un contrôleur va le chercher dans le scope, ça complique les tests unitaires


