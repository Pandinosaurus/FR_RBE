# Le casting

Rust ne permet pas la conversion implicite des types primitifs (coercition). En revanche, une conversion explicite (casting) peut être entreprise à l'aide du mot-clé `as`.

Les règles régissant la conversion entre les types littéraux s'inspirent, principalement, des [conventions du langage C][c] à l'exception des cas où le C réserve des comportements imprévisibles.

{{#playpen source/castingsource0.rs}}

[c]: https://en.wikipedia.org/wiki/Type_conversion#C-like_languages
