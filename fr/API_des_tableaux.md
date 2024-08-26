Vous pouvez accéder aux tables créées dans le System Builder.

= Tables =

Utilisez la constante <code>Tables</code> pour obtenir une instance de <code>Table</code>.

== <code>get(id)</code> ==

* '''<code>id</code>''', type <code>string</code> : L’identifiant de la table.
* Retourne : <code>Table|null</code>.

Retourne une instance de <code>Table</code>, ou <code>null</code> si la table n’existe pas.

= Table =

Représente une table.

== <code>get(id)</code> ==

* '''<code>id</code>''', type <code>string</code> : L’identifiant de la ligne.
* Retourne : <code>Object|null</code>.

Exemple :

<syntaxhighlight lang="javascript">
let line = Tables.get("attributes").get('dexterity');
// Object { id: "dexterity", name: "Dexterity", short: "DEX" }
</syntaxhighlight>

== <code>each(callback)</code> ==

* '''<code>callback</code>''', type <code>Function</code> : La fonction appelée pour chaque ligne de la table.
* Retourne : <code>void</code>.

Exemple :

<syntaxhighlight lang="javascript">
Tables.get("attributes").each(function(attribute) {
    log(attribute.name);
});
// Strength
// Dexterity
// Constitution
// ...
</syntaxhighlight>

== <code>random(callback)</code> ==

== <code>random(count, callback)</code> ==

* '''<code>callback</code>''', type <code>Function</code> : La fonction callback appelée avec la ligne aléatoirement sélectionnée (ou les lignes aléatoirement sélectionnées).
* '''<code>count</code>''', type <code>number</code> : Le nombre de lignes à sélectionner aléatoirement. Ne doit pas être plus grand que le nombre de lignes de la table.
* Retourne : <code>void</code>.

Récupère les lignes de la table en utilisant la génération aléatoire cryptographiquement sécurisée du serveur.
Si <code>count</code> n’est pas spécifié ou est égal à 1, l’objet correspondant à la ligne est passé à la fonction callback. Sinon, un tableau des objets de chaque ligne est passé à la fonction callback.

<syntaxhighlight lang="javascript">
Tables.get("attributes").random(function(attribute) {
    log(attribute.name);
});
// Charisma
</syntaxhighlight>
<syntaxhighlight lang="javascript">
Tables.get("attributes").random(3, function(attributes) {
    each(attributes, function(attribute) {
        log(attribute.name);
    });
});
// Strength
// Wisdom
// Dexterity
</syntaxhighlight>

{{ SystemBuilderMenu }}