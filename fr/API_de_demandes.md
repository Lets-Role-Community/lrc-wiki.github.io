L’API Prompt vous permet de demander à l’utilisateur de remplir un petit formulaire avant une action. Par exemple, si vous avez besoin d’un modificateur avant un lancer de dé, vous pouvez afficher une petite fenêtre pour demander la valeur du modificateur.

Le prompt lui-même possède un titre, un identifiant de la vue à afficher, une fonction callback avec les données collectées depuis la vue. La vue est initialisée dans la fonction globale <code>init(sheet)</code>.

Exemple :

<syntaxhighlight lang="javascript">
sheet.get('attack').on('click', function() {
    sheet.prompt('Modifiers ?', 'rollprompt', function(result) { // rollprompt is the id of the view
        // result is an object of the data of the view
        // after the user clicks "continue".
        // if the user cancel the prompt, the function is not called
        if (result.advantage) {
            Dice.roll(sheet, 'keeph(2d20)'); 
        } else {
            Dice.roll(sheet, '1d20');
        }
    });
});
</syntaxhighlight>

= <code>sheet.prompt(title, view, callback, callbackInit)</code> =

* '''<code>title</code>''', type <code>string</code> ''<code>required</code>'' : Le titre du prompt.
* '''<code>view</code>''', type <code>string</code> ''<code>required</code>'' : L’identifiant de la vue à utiliser. 
* '''<code>callback</code>''', type <code>Function</code> ''<code>required</code>'' : La fonction callback pour récupérer les données une fois que le joueur clique sur le bouton “next”. Le premier argument est l’objet données de la vue prompt. 
* '''<code>callbackInit</code>''', type <code>Function</code> : La fonction callback appelée quand le prompt s’ouvre qui vous permet de modifier les éléments de la vue du prompt à partir d’informations provenant de la feuille qui appelle <code>sheet.prompt(...)</code>. Le premier argument est la vue du prompt, c’est à dire une instance de la vue <code>view</code>. Vous pouvez la manipuler avec les fonctions habituelles de vues, par exemple si vous la nommez <code>promptView</code>, vous pouvez en cacher des composants avec <code>promptView.get('componentId').hide()</code>.

Exemple :

<syntaxhighlight lang="javascript">
sheet.get('attack').on('click', function() {
    sheet.prompt('Modifiers ?', 'rollprompt', function(result) { // rollprompt is the id of the view
        // result is an object of the data of the view
        // after the user clicks "continue".
        // if the user cancel the prompt, the function is not called
        if (result.advantage) {
            Dice.roll(sheet, 'keeph(2d20) + ' + result.prompt_modifier); 
        } else {
            Dice.roll(sheet, '1d20 + ' + result.prompt_modifier);
        }
    }, function(promptView){ // callbackInit
        // la fonction callbackInit peut acceder a la feuille qui appelle le prompt et a la feuille du prompt
        const dex_modifier = sheet.get('dex_modifier').value(); // dex_modifier est sur la feuille de personnage
        promptView.get('prompt_modifier').value(dex_modifier); // prompt_modifier est sur la feuille du prompt
    });
});
</syntaxhighlight>

= <code>Prompt(title, view, callback)</code> =

'''&gt;&gt; This stand-alone function has been deprecated, use sheet.prompt() instead!'''

* '''<code>title</code>''', type <code>string</code> ''<code>required</code>'' : Le titre du prompt.
* '''<code>view</code>''', type <code>string</code> ''<code>required</code>'' : L’identifiant de la vue à utiliser.
* '''<code>callback</code>''', type <code>Function</code> ''<code>required</code>'' : La fonction callback pour récupérer les données une fois que le joueur clique sur le bouton “next”. Le premier argument est l’objet données de la vue prompt. 
* Retourne : <code>void</code>.

{{ SystemBuilderMenu }}