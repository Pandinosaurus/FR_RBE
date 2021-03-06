# Système de durée de vie

Une « lifetime » est une construction utilisée par le compilateur pour s'assurer que tous les emprunts (i.e. références immuables/mutables) sont valides. Plus précisément, la durée de vie d'une variable commence lorsqu'elle est créée et se termine une fois cette dernière détruite.

**Note** : Bien que les lifetimes et les contextes soient très souvent cités ensembles cela reste, malgré tout, deux concepts bien distincts.

```rust
// La création et destruction des lifetimes sont illustrées ci-dessous par des lignes.
// `i` possède la plus grande lifetime car son contexte englobe 
// `borrow1` et `borrow2`. La durée de vie de `borrow1` ne peut pas être 
// comparée à celle de `borrow2` car elle ne se trouve pas dans le 
// même contexte.
fn main() {
    let i = 3; // Lifetime for `i` starts. ────────────────┐
    //                                                     │
    { //                                                   │
        let borrow1 = &i; // `borrow1` lifetime starts. ──┐│
        //                                                ││
        println!("borrow1: {}", borrow1); //              ││
    } // `borrow1 ends. ──────────────────────────────────┘│
    //                                                     │
    //                                                     │
    { //                                                   │
        let borrow2 = &i; // `borrow2` lifetime starts. ──┐│
        //                                                ││
        println!("borrow2: {}", borrow2); //              ││
    } // `borrow2` ends. ─────────────────────────────────┘│
    //                                                     │
}   // Lifetime ends. ─────────────────────────────────────┘
```

Notez qu'aucun nom ou type n'est assigné aux labels de lifetimes. Nous allons apprendre, dans la prochaine section, à nous servir des durées de vie (et appréhender l'utilisation des labels).
