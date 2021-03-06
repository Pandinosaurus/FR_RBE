# Les closures

Les closures en Rust, également appelées « lambdas », sont des fonctions qui peuvent capturer l'environnement qui les entoure. Par exemple, voici une closure qui capture la variable `x` :

```rust,ignore
|val| val + x
```


La syntaxe ainsi que les capacités des closures les rendent adéquates aux déclarations et utilisations à la volée. Appeler une closure se fait de la même manière qu'une fonction classique. En revanche, les types reçus en entrée (i.e. les types des paramètres passés) et le type de renvoi peuvent être [inférés][inference] et les identificateurs des paramètres *doivent* être spécifiés.

D'autres caractéristiques spécifiques aux closures :

* L'utilisation du couple `||` plutôt que de `()` pour entourer les paramètres;
* La délimitation `{}` du corps de la closure optionnelle pour une seule expression (sinon obligatoire);
* La capacité à capturer des variables appartenant au contexte dans lequel la closure est imbriquée.

{{#playpen source/closuressource0.rs}}

[inference]: https://fr.wikipedia.org/wiki/Inférence_de_types
