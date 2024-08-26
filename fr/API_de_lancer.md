L’API Dice vous permet de faire des lancers de dés. Elle est disponible au travers de l’objet global <code>Dice</code>.

Example:

<syntaxhighlight lang="javascript">
init = function(sheet) {
    if (sheet.id() === "main") {
        initMain(sheet);
    }
};

initMain = function(sheet) {
    sheet.get('charisma').on('click', function() {
        Dice.roll(sheet, "3d6", "Charisma Check!");
    });
};
</syntaxhighlight>

== <code>Dice.roll(sheet, expression, title, visibility, actions)</code> ==

* '''<code>sheet</code>''', type <code>Sheet</code> ''<code>required</code>'' : La feuille à laquelle est attachée le lancer. 
* '''<code>expression</code>''', type <code>string</code>|<code>DiceBuilder</code> ''<code>required</code>'' : L’expression ou une instance de Dice Builder. 
* '''<code>title</code>''', type <code>string</code> : Le titre du lancer. 
* '''<code>visibility</code>''', type <code>string</code> default <code>all</code> : La visibilité du lancer. Les valeurs possibles sont :
** <code>all</code> = le lancer sera visible par tout le monde. 
** <code>gm</code> = le lancer sera visible par le propriétaire de la fiche et le MJ. 
** <code>gmonly</code> = le lancer sera visible seulement par le MJ.
* '''<code>actions</code>''', type <code>Object</code> : Actions additionnelles pour le lancer. Les actions sont affichées comme des boutons dans l’affichage du résultat à l’écran et dans le Dice Log. 
* Retourne : <code>void</code>.

Effectue le lancer de dés en lui-même.

== <code>Dice.create(expression)</code> ==

* '''<code>expression</code>''', type <code>string</code> : Une expression de base pour le Dice Builder.
* Retourne : <code>DiceBuilder</code>

Crée une instance du <code>DiceBuilder</code>.

== Actions ==

Les actions vous permettent de créer des lancers interactifs en créant un ou plusieurs boutons dans la fenêtre de résultat. Le paramètre <code>actions</code> est un <code>Object</code> avec le titre du bouton comme clé, et la fonction callback en valeur.

Exemple :

<syntaxhighlight lang="javascript">
Dice.roll(sheet, "1d20+2", "Attack", "all", {
    "Roll Damages": function(dice) {
        Dice.roll(sheet, "3d6[fire]", "Fireball");  // jet effectué quand le joueur clique sur "Roll Damages"
    }
});
</syntaxhighlight>

{{ SystemBuilderMenu }}