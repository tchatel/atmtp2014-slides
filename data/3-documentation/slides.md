!SLIDE subsection ================

# Documentation dans le code


!SLIDE ===========================

<img src="data/3-documentation/800px-Bonanjo_-_Centre_de_documentation_et_information_urbanisme_(CUD)_04.JPG" width="40%">
## pas de documentation externe


!SLIDE ===========================

# les commentaires

!NOTES ---------------------------
Sujet qui fâche, sur lequel les développeurs ont souvent mauvaise conscience.


!SLIDE ===========================

### commenter,
### ou ne pas commenter ?


!SLIDE ===========================

<img src="data/3-documentation/bad-157437_640.png" width="10%">


!SLIDE ===========================

## obsolètes
<br/>
<img src="data/3-documentation/typewriter-28701_1280.png" width="30%">


!SLIDE ===========================

## inutiles

    // Increment i
    i++;


!SLIDE ===========================

## _“Don’t comment bad code — rewrite it.”_
<img src="data/3-documentation/Brian_kernighan2.gif" width="15%">
### Brian W. Kernighan and P. J. Plaugher



!SLIDE ===========================

<img src="data/3-documentation/good-157436_640.png" width="10%">
## qu'est-ce qu'un bon commentaire ?


!SLIDE smallercode ===========================

    function compute(n) {
        var size = 1000;
        var ok = 0;
        for (var i = 0 ; i < n ; i++) {
            var ax = Math.random() * size;
            var ay = Math.random() * size;
            var bx = Math.random() * size;
            var by = Math.random() * size;
            var dx = bx - ax;
            var dy = by - ay;
            var s = Math.sqrt(dx * dx + dy * dy);
            bx = ax + (bx - ax) / s;
            if (Math.floor(ax) != Math.floor(bx)) {
                ok++;
            }
        }
        return 2 * n / ok;
    }
    compute(100000000);


!SLIDE bullets ===========================

## révéler l'intention

* le _“comment”_ est écrit dans le code
* le _“pourquoi”_ est perdu


!SLIDE ===========================

# le nommage

!NOTES ---------------------------
- c'est le premier des commentaires
- qui peut aussi être obsolète
    * (ex en formation, copier-coller sans changer le nommage)
- curieusement personne ne demande s'il faut ou non nommer les variables


!SLIDE ===========================

## vocabulaire commun
### _“métaphore”_ (XP), _“ubiquitous language”_ (DDD)
<img src="data/3-documentation/dictionary-390055_1280.jpg" width="40%">

!NOTES ---------------------------
- importance d'un accord sur les mots et leur sens
- réf Borges : Pierre Ménard, auteur du Quichotte


!SLIDE ===========================

## nommer plutôt que commenter
### fonctions, variables


!SLIDE smallcode ===========================

     boolean isConstructor() {
         return !isPartial() && "<init>".equals(name);
     }
     boolean isMethod() {
         return !isPartial() && !isConstructor()
             && !"<clinit>".equals(name);
     }



!SLIDE smaller ===========================

TODO : variable pour le nommage ?


!SLIDE bullets ===========================

# tests unitaires


!SLIDE bullets ===========================

* spécifications... **à jour** !
* favorisent le refactoring












