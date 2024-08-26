Ces fonctions doivent être définies avec une portée globale.
Si vous ne souhaitez pas utiliser une de ces fonctionnalités, ne définissez simplement pas la fonction.

= <code>init(sheet)</code> =

* '''<code>sheet</code>''', type <code>Sheet</code> : La feuille à initialiser.
* Retourne : <code>void</code>.

Initialise une feuille, comme une feuille de personnage ou de craft.
Vous pouvez obtenir le type de feuille via <code>sheet.id()</code>.

Les onglets de tabs ne sont pas initialisés individuellement, et devraient être initialisés comme s’ils faisaient partie de la vue parente.

Exemple :

<syntaxhighlight lang="javascript">
init = function(sheet) {
    if (sheet.id() === "main") {
        initMain(sheet);
    } 
    else if (sheet.id() === "weapon") {
        initWeapon(sheet);
    }
};

const initMain = function(sheet) {
    // initialize the main sheet
    sheet.get("hp");  // ...
};

const initWeapon = function(sheet) {
    // initialize the weapon sheet
    // ...
};
</syntaxhighlight>

= <code>drop(from, to)</code> =

* '''<code>from</code>''', type <code>Sheet</code> : La feuille source.
* '''<code>to</code>''', type <code>Sheet</code> : La feuille de destination.
* Retourne : <code>void|string</code>.

Cette fonction est appelée quand vous glissez-déposez un craft sur une feuille de personnage.

Si vous voulez simplement ajouter les données à un repeater, retournez l’id de ce repeater.
Sinon, vous devrez manipuler les données de la feuille de destination.

Pour le moment, il est seulement possible de déposer un craft dans une feuille de personnage.

Exemples :

<syntaxhighlight lang="javascript">
drop = function(from, to) {
    if (from.id() === "weapon" && to.id() === "main") {
        return "weapons";  // "weapons" is a repeater id
    }
};
</syntaxhighlight>
<syntaxhighlight lang="javascript">
drop = function(from, to) {
    if (from.id() === "heal" && to.id() === "main") {
        to.get("hp").value(
            from.get("maxhp").value()
        );  // set the target's hp to the source maxhp
    }
};
</syntaxhighlight>

= <code>dropDice(result, to)</code> =

* '''<code>result</code>''', type <code>DiceResult</code> : Le résultat d’un jet de dé dans le Dice Log.
* '''<code>sheet</code>''', type <code>Sheet</code> : La feuille de destination.
* Retourne : <code>void</code>.

Pour certains systèmes, il peut être utile de glisser-déposer un résultat de jet de dé dans la feuille. Avec cette fonction, vous pouvez créer une interaction entre le Dice Log et une feuille de personnage ou un craft.

Exemple :

<syntaxhighlight lang="javascript">
dropDice = function(result, sheet) {
    if (result.containsTag("heal")) {
        let hp = sheet.get("hp");
        hp.value(hp.value() + result.total);  // le personnage est soigné du total du jet de dé
    }
};
</syntaxhighlight>

= <code>initRoll(result, callback)</code> =

* '''<code>result</code>''', type <code>DiceResult</code> : Le résultat d’un jet de dé dans le Dice Log.
* '''<code>callback</code>''', type <code>Function</code> : Une fonction callback pour afficher le résultat du jet.
* Retourne : <code>void</code>.

Cette fonction vous permet de personnaliser l’affichage du résultat d’un jet de dé. Vous devrez appeler cette fonction '''callback''' avec ces deux arguments :
* '''<code>view</code>''', type <code>string</code> : L’identifiant de la vue que vous voulez utiliser pour afficher le résultat du jet
* '''<code>onRender</code>''', type <code>Function</code> : Une fonction appelée lorsque la vue s’affichera, dans laquelle vous pouvez changer les données de cette vue. Merci de noter que la vue est aussi initialisée dans la fonction globale '''init()'''.

Exemple :

<syntaxhighlight lang="javascript">
initRoll = function(result, callback) {
    callback('diceresult', function(sheet) {  // diceresult est l'identifiant de la vue que vous voulez utiliser
        sheet.get('total').text(result.total);  // appliquez différents changements à la vue
        
        if (result.total > 20) {
            sheet.get('total').addClass('text-large');
        }
    });
};
</syntaxhighlight>

= <code>getReferences(sheet)</code> =

* '''<code>sheet</code>''', type <code>Sheet</code> : La feuille avec ses références.
* Retourne : <code>Object</code>.

Si vous souhaitez créer des références par programmation (références avec '@' dans un Label "computed"), vous pouvez utiliser cette méthode.
Retourne un objet avec les identifiants des références comme clé et le contenu de la référence comme valeur. Les valeurs sont interprétées. Cette fonction n’est appelée automatiquement qu’une fois à l’init d’une vue. Même si vous l’appelez à nouveau (pour rafraîchir la valeur de la référence par exemple), cela ne fonctionnera pas.

Exemple :

<syntaxhighlight lang="javascript">
getReferences = function(sheet) {
    return {
        "halfHp": sheet.get("hp").value() / 2,  // numeric value
        "defaultBonus": "5 + 8",  // simple reference,
        "bonus": "@strength + @defaultBonus"  // reference others
    };
};
</syntaxhighlight>

= <code>getBarAttributes(sheet)</code> =

* '''<code>sheet</code>''', type <code>Sheet</code> : La feuille à laquelle seront rattachées les barres de son token.
* Retourne : <code>Object</code>.

Les joueurs peuvent connecter les barres de leur token aux attributs de leur personnage avec cette fonction. Elle requière d’avoir une valeur et une valeur maximale. Cette méthode retourne un <code>Object</code> avec les titres des barres comme clés, et un <code>Array(2)</code> (tableau de deux éléments) où le premier élément est la valeur courante, et le second, la valeur maximale de la barre.

La barre du token se met à jour quand la feuille est changée, et la feuille se met à jour quand la valeur de la barre est modifiée

Exemple :

<syntaxhighlight lang="javascript">
getBarAttributes = function (sheet) {  // [triggered when dropping a token onto a scene] adds options to the "Connect to" dropdown menu. The selected field will be displayed as a dynamic gauge on the token
   if (sheet.id() === "main") {  // limits the code to the cases where it's a character being dropped onto the scene, as opposed to a craft for example.
      return {
         "Hunger": ['counter_hunger', 5],
         "Willpower": ["counter_willpower", "counter_willpower_max"],
         "Health": ['counter_health', 'counter_health_max']
      };
   }
   if (sheet.id() === "monster") {
        return {
            "HP": ["hp", "hpmax"],
            "Mana": ["mana", 30]  // you can use numbers directly for maximums
        };
    }
};
</syntaxhighlight>

[[Fichier:113360624-6ec1f500-934a-11eb-9b00-31f33a1198a0.png]]

{{ SystemBuilderMenu }}