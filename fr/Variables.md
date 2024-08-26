Dans l’onglet '''Table''', vous pouvez trouver une table nommée ''variables''. Vous pouvez ajouter des variables dans cette table et les utiliser ensuite dans des valeurs et des label calculées/computed, d’autres variables, et même des jet de dés.<br />
Dans la colonne <code>id</code> se trouve les nom des variables (sans le $), et leur valeur sont contenu dans la colonne <code>value</code>.

Attention, seuls les valeurs mathématiques peuvent être utilisés dans une variable, vous ne pouvez pas stocker des <code>string</code> (ligne de text) ou des <code>object</code>.

Pour utiliser une variable, utiliser le prefix <code>$</code>. Le nom de la variable ne doit contenir que des lettres et des underscores <code>_</code> (tiré du huit) et nous vous recommandons vivement de ne pas utiliser de majuscules.

Vous pouvez définir la valeur de la variable comme un simple nombre :

<pre>23</pre>
Vous pouvez également appelé d’autres variables et composants dans ''value''. On peu donné la valeur suivante pour <code>bonus</code> par exemple :

<pre>@dexterity + 3</pre>
Ainsi, dans un label, vous pouvez utiliser la formule de jet de dés suivante :

<pre>3d6 + $bonus</pre>
Ainsi, si la valeur de <code>@dexterity</code> est 5, le jet dans cet exemple doit être <code>3d6 + 8</code>.

La variable <code>$bonus</code> peut également être utilisée dans un jet manuel effectué dans la boîte de tchat, en utilisant par exemple <code>/roll 4d6 + $bonus</code>.

{{ SystemBuilderMenu }}

Vous pouvez également définir une variable comme une linge de texte (''string''), en utilisant des guillemets :

<pre>&quot;hello there&quot;</pre>