!SLIDE subsection ================

# Documentation...<br/> dans le code


!SLIDE ===========================

<img src="data/3-documentation/800px-Bonanjo_-_Centre_de_documentation_et_information_urbanisme_(CUD)_04.JPG" width="400px">
## pas de documentation externe


!SLIDE ===========================

# les commentaires

!NOTES ---------------------------

Sujet qui fâche, sur lequel les développeurs ont souvent mauvaise conscience.


!SLIDE ===========================

### commenter,
### ou ne pas commenter ?


!SLIDE ===========================

<img src="data/3-documentation/bad-157437_640.png" width="200px">


!SLIDE ===========================

## obsolètes
<br/>
<img src="data/3-documentation/typewriter-28701_1280.png" width="350px">

!NOTES ---------------------------

- Comme pour la doc, on oublie souvent de mettre à jour les commentaires.
- Les commentaires obsolètes peuvent être trompeurs, c'est pire que pas de commentaires du tout.
- La vérité est dans le code, pas dans le commentaire.


!SLIDE smallcode ===========================

## inutiles

<br/>

    // Increment i
    i++;

!NOTES ---------------------------

- Ajoutent du volume et font perdre du temps à la lecture


!SLIDE ===========================

### _“Don’t comment bad code — rewrite it.”_

</br/>
<div class="left">
<img src="data/3-documentation/Brian_kernighan2.gif" width="150px"></br/>
Brian W. Kernighan and P. J. Plaugher
</div>



!SLIDE ===========================

<img src="data/3-documentation/good-157436_640.png" width="200px">
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
<img src="data/3-documentation/dictionary-390055_1280.jpg" width="400px">

!NOTES ---------------------------

- importance d'un accord sur les mots et leur sens
- réf Borges : Pierre Ménard, auteur du Quichotte


!SLIDE ===========================

## nommer plutôt que commenter
### fonctions, variables


!SLIDE smallcode ===========================

     boolean isConstructor() {
         return !isPartial()
             && "<init>".equals(name);
     }

     boolean isMethod() {
         return !isPartial()
             && !isConstructor()
             && !"<clinit>".equals(name);
     }



!SLIDE smallercode ===========================

    hasClass: function( selector ) {
        var className = " " + selector + " ",
            i = 0,
            l = this.length;
        for ( ; i < l; i++ ) {
            if ( this[i].nodeType === 1
                    && (" " + this[i].className + " ")
                        .replace(rclass, " ")
                        .indexOf( className ) > -1 ) {
                return true;
            }
        }
        return false;
    }


!SLIDE smallercode ===========================

    hasClass: function( selector ) {
        var className = " " + selector + " ",
            i = 0,
            l = this.length;
        for ( ; i < l; i++ ) {
            var isTag = this[i].nodeType === 1;
            var isTagWithThatClass = isTag
                    && (" " + this[i].className + " ")
                        .replace(rclass, " ")
                        .indexOf( className ) > -1;
            if (isTagWithThatClass) {
                return true;
            }
        }
        return false;
    }


!SLIDE bullets ===========================

# tests unitaires


!SLIDE bullets ===========================

* spécifications... **à jour** !
* favorisent le refactoring












