= <code>log(var1)</code> =

* Retourne : <code>void</code>.

Trace le contenu des variables dans la console.

= <code>//region</code> <code>//endregion</code> =

Ajoutez <code>//region</code> pour commencer une section de code que vous voulez rendre pliable, et <code>//endregion</code> pour la terminer. Ça ajoutera une flèche de pliage / dépliage.

= <code>wait(ms, callback)</code> =

* '''<code>ms</code>''', type <code>number</code> : La durée en millisecondes de l’attente.
* '''<code>callback</code>''', type <code>Function</code> : La fonction qui sera appelée quand l’attente sera terminée.
* Retourne : <code>void</code>.

= <code>parseInt(value)</code> =

* '''<code>value</code>''', type <code>any</code> : La valeur à convertir.
* Retourne : <code>void</code>.

Convertit n’importe quelle valeur en un entier.

= <code>_(text)</code> =

* '''<code>text</code>''', type <code>string</code> : Le texte à traduire.
* Retourne : <code>string</code>.

Traduit un message dans la langue choisie.

= <code>each(data, callback)</code> =

* '''<code>data</code>''', type <code>Object|Array</code> : Les données sur lesquelles itérer.
* '''<code>callback</code>''', type <code>Function</code> : La fonction appelée pour chaque élément des données. Doit retourner <code>false</code> si vous voulez arrêter l’itération. Le premier argument est l’élément courant, le second son index.
* Retourne : <code>void</code>.

Itère sur un objet ou un tableau.

Examples :

<syntaxhighlight lang="javascript">
let animals = {
    "cat": "Meow",
    "dog": "Woof",
    "bird": "Chirp"
};

each(animals, function(noise, type) {
    log(noise);
});
</syntaxhighlight>

= <code>Math</code> =

L’[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math API Math] est disponible.

{{ SystemBuilderMenu }}