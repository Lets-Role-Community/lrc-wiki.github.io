Le DiceBuilder est une API fluide pour créer des lancers de dés.

= Exemples =

Usage basique :

<syntaxhighlight lang="javascript">
let dice = Dice.create(8).add(5);  // 8 + 5
</syntaxhighlight>
<syntaxhighlight lang="javascript">
let dice = Dice.create("3d6").add(5);  // 3d6 + 5
let dice = Dice.create("3d6").add('@dexterity');  // 3d6 + @dexterity
let dice = (new DiceBuilder("3d6")).add(5);  // 3d6 + 5
</syntaxhighlight>
<syntaxhighlight lang="javascript">
let dice = Dice.create("3d6");  // 3d6
let extra = Dice.create("2d8").minus(5);  // 2d8 - 5
let final = dice.add(extra);  // 3d6 + (2d8 - 5)
</syntaxhighlight>

En utilisant les fonctions :

<syntaxhighlight lang="javascript">
let dice = Dice.create("1d20")
    .add(5)
    .divide(2)
    .round();
    // round((1d20 + 5)/2)
</syntaxhighlight>

Example avancé :

<syntaxhighlight lang="javascript">
let dice = Dice.create("3d6")
    .compare(">", 10)
    .ternary("1d20", "1d10")
    .tag("fire", "attack")
    // (3d6 > 10 ? 1d20 : 1d10)[fire, attack]
</syntaxhighlight>

Les instances du <code>DiceBuilder</code> peuvent être directement passées à la méthode <code>Dice.roll()</code> :

<syntaxhighlight lang="javascript">
init = function(sheet) {
    sheet.get('attack').on('click', function() {
        let dice = Dice.create('2d20')  // 2d20
            .keeph() // retient le meilleur
            .tag('advantage');  // ajoute le tag "advantage"

        Dice.roll(sheet, dice, 'My attack with advantage');
    });
};
</syntaxhighlight>

= Methods =

Voici les méthodes disponibles :

* <code>.add(value)</code>
* <code>.minus(value)</code>
* <code>.multiply(value)</code>
* <code>.divide(value)</code>
* <code>.tag(tag1, tag2, ...)</code>
* <code>.compare(type, right, weights)</code>
* <code>.round()</code>
* <code>.ceil()</code>
* <code>.floor()</code>
* <code>.keeph(max)</code>
* <code>.keepl(max)</code>
* <code>.remh(max)</code>
* <code>.reml(max)</code>
* <code>.expl(explode1, explode2, ...)</code>
* <code>.expladd(explode1, explode2, ...)</code>
* <code>.mul(multiplier)</code>
* <code>.reroll(reroll1, reroll2, ...)</code>
* <code>.rerolln(reroll1, reroll2, ..., max)</code>
* <code>.ternary(then, else)</code>

{{ SystemBuilderMenu }}