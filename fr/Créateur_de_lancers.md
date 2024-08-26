L'API Roll Builder permet de créer un jet de dés grâce à une interface fluide.

== Initialisation ==

<syntaxhighlight lang="javascript">
let roller = new RollBuilder(sheet);
</syntaxhighlight>

Où '''sheet''' est une instance de <code>Sheet</code>.

== Example ==

<syntaxhighlight lang="javascript">
let roll = new RollBuilder(sheet);

roll.expression("2d20")
    .visibility("visible")
    .addAction("Roll Damage", function() {
        Dice.roll(sheet, "3d6");
    })
    .onRoll(function(result) {
        sheet.get("rollresult").value("Total : " + result.total.toString());
    })
    .roll();
</syntaxhighlight>

== API Methods ==

=== <code>constructor(sheet)</code> ===

* '''<code>sheet</code>''', type <code>Sheet</code> : La [[fiche]] liée au jet.
* Retourne : <code>RollBuilder</code>.

=== <code>roll()</code> ===

* Retourne : <code>void</code>.

Soumet le lancé de dés.

=== <code>expression(expr)</code> ===

* '''<code>expr</code>''', type <code>string</code>|<code>DiceBuilder</code> : La formule du jet de dés ou une instance <code>DiceBuilder</code>.
* Retourne : <code>RollBuilder</code>.

=== <code>title(title)</code> ===

* '''<code>title</code>''', type <code>string</code> : Titre du jet.
* Retourne : <code>RollBuilder</code>.

=== <code>visibility(visibility)</code> ===

* '''<code>visibility</code>''', type <code>string</code> : La visibilité du jet (<code>visible</code>, <code>gm</code> ou <code>gmonly</code>).
* Retourne : <code>RollBuilder</code>.

=== <code>addAction(title, callback)</code> ===

* '''<code>title</code>''', type <code>string</code> : Nom de l'action à ajouter.
* '''<code>callback</code>''', type <code>Function</code> : La fonction appelée lors du click sur « l'action ».
* Retourne : <code>RollBuilder</code>.

=== <code>removeAction(title)</code> ===

* '''<code>title</code>''', type <code>string</code> : Nom de l'action à enlever.
* Retourne : <code>RollBuilder</code>.

=== <code>onRoll(callback)</code> ===

* '''<code>callback</code>''', type <code>Function</code> : La fonction appelée après avoir effectué le jet de dés. Le premier paramètre de la fonction est une instance <code>DiceResult</code>.
* Retourne : <code>RollBuilder</code>.

{{SystemBuilderMenu}}