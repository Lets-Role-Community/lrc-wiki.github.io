Représente le résultat d’un jet de dé effectué soit par un joueur soit pas un MJ.

= Propriétés =

== <code>title</code> ==

* Retourne : <code>string</code>.

Seulement disponible dans le premier résultat.

== <code>expression</code> ==

* Retourne : <code>string</code>.

Seulement disponible dans le premier résultat.

== <code>visibility</code> ==

* Retourne : <code>string</code>.

La visibilité du jet de dé en cours. Les valeurs possibles sont <code>visible</code> (tout le monde voit le jet), <code>gm</code> (le joueur et le MJ voit le jet) ou <code>gmonly</code> (seul le MJ voit le jet). Seulement disponible dans le premier résultat.

== <code>type</code> ==

* Retourne : <code>string</code>.

Récupère le type du jet courant. Les valeurs possibles sont <code>number</code>, <code>dice</code> ou <code>comparison</code>.

== <code>total</code> ==

* Retourne : <code>number</code>.

Pour un jet de type :
* <code>dice</code> = le total des valeurs des dés
* <code>number</code> = le résultat de l’opération
* <code>comparison</code> = le nombre de succès

== <code>tags</code> ==

* Retourne : <code>string[]</code>.

Récupère les tags du jet courant. Si vous souhaitez tous les tags en incluant ceux des enfant, utilisez <code>.allTags</code>.

== <code>allTags</code> ==

* Retourne : <code>string[]</code>.

Récupère tous les tags du jet, notamment celui des enfants

== <code>all</code> ==

* Retourne : <code>SingleDiceResult[]</code>.

Récupère tous les résultats du jet en incluant ses enfants. <code>SingleDiceResult</code> est un objet composé de :
* <code>dimension</code>, type <code>number</code> = le nombre de face du dé
* <code>value</code>, type <code>number</code> = la valeur du dé
* <code>discarded</code>, type <code>boolean</code> = <code>true</code> si le dé est rejeté (par exemple quand <code>keeph</code> est utilisé)

== <code>children</code> ==

* Retourne : <code>DiceResult[]</code>.

Récupère les enfants du jet courant.

== <code>size</code> ==

* Retourne : <code>number</code>.

Le nombre de dés lancés. Par exemple 3d6 retourne 3.
Retourne <code>null</code> si le jet n’est pas du type <code>dice</code>.

== <code>dimension</code> ==

* Retourne : <code>number</code>.

Le nombre de faces du dé. Par exemple 3d6 retourne 6.
Retourne <code>null</code> si le jet n’est pas du type <code>dice</code>.

== <code>values</code> ==

* Retourne : <code>number[]</code>.

Les résultats du jet. N’inclut pas les valeurs rejetées.
Retourne <code>null</code> si le jet n’est pas du type <code>dice</code>.

== <code>discarded</code> ==

* Retourne : <code>number[]</code>.

Les résultats rejetés du jet.

== <code>left</code> ==

* Retourne : <code>DiceResult</code>.

La partie gauche d’une comparaison.
Retourne <code>null</code> si le jet n’est pas du type <code>comparison</code>.

== <code>right</code> ==

* Retourne : <code>DiceResult</code>.

La partie droite d’une comparaison.
Retourne <code>null</code> si le jet n’est pas du type <code>comparison</code>.

== <code>success</code> ==

* Retourne : <code>number</code>.

Le nombre de succès lors d’une comparaison.
Retourne <code>null</code> si le jet n’est pas du type <code>comparison</code>.

== <code>failure</code> ==

* Retourne : <code>number</code>.

Le nombre d’échecs lors d’une comparaison.
Retourne <code>null</code> si le jet n’est pas du type <code>comparison</code>.

= Méthodes =

== <code>containsTag(tag)</code> ==

* '''<code>tag</code>''', type <code>string</code> : Le tag à rechercher.
* Retourne : <code>boolean</code>.

Vérifie si le jet courant ou ses enfants contient ce tag.

{{ SystemBuilderMenu }}