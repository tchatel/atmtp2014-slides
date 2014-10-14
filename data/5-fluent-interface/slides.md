!SLIDE subsection ================

# Fluent Interface


!SLIDE ===========================

# du code
### comme
## du langage courant


!SLIDE smallercode ===========================

    private void makeNormal(Customer customer) {
        Order o1 = new Order();
        customer.addOrder(o1);
        OrderLine line1 = new OrderLine(6, Product.find("TAL"));
        o1.addLine(line1);
        OrderLine line2 = new OrderLine(5, Product.find("HPK"));
        o1.addLine(line2);
        OrderLine line3 = new OrderLine(3, Product.find("LGV"));
        o1.addLine(line3);
        line2.setSkippable(true);
        o1.setRush(true);
    }



!SLIDE smallcode ===========================

    private void makeFluent(Customer customer) {
        customer.newOrder()
                .with(6, "TAL")
                .with(5, "HPK").skippable()
                .with(3, "LGV")
                .priorityRush();
    }


!SLIDE bullets ===========================

<img src="data/5-fluent-interface/formes.jpg" width="260px">

* vérification par le langage <span class="small">(si typé)</span>
* vérification par le lecteur <span class="small">(erreurs flagrantes)</span>

!NOTES ---------------------------

Penser à la lisibilité quand on conçoit l'API.