!SLIDE subsection ================

# TESTS


!SLIDE ===========================

# soigner le code
# des tests ?


!SLIDE ===========================

# il faut le maintenir


!SLIDE ===========================

# imbriquer un _describe_
## pour factoriser dans un _beforeEach_


!SLIDE ===========================

### Protractor :
## factoriser des ElementFinder
## et des fonctions


!SLIDE ===========================

    rows = element.all(
        by.repeater('row in rows')
    );

    getQuantityOnFirstRow = function () {
        var firstRow = rows.get(0);
        var input = firstRow.$('input.quantity');
        return input.getAttribute('value');
    }


