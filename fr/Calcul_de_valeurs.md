Quelques opérations sont disponibles dans une valeur calculée. En utilisant des références et des variables, elles sont un bon moyen de rendre une feuille de personnage dynamique sans utiliser le ''scripting''.

= Values types =

Vous pouvez créer une ''ligne de texte'' en mettant une valeur entre guillemet (“ligne de text”). Voici les règles pour les ''lignes de texte'' :

* En utilisant <code>+</code> entre deux lignes de texte, elles seront concaténées : <code>&quot;hello&quot; + &quot; there&quot;</code> -&gt; <code>hello there</code>
* En utilisant <code>+</code> entre une ligne de texte et un nombre, le nombre sera converti en ligne de texte : <code>&quot;vous avez &quot; + 5 + &quot; PV&quot;</code> -&gt; <code>vous avez 5 PV</code> Ici <code>5</code> a été changé en <code>&quot;5&quot;</code>.
* En utilisant n’importe quelles autres opérations entre deux lignes de texte, ou entre une ligne de texte et un nombre, les lignes de texte seront convertis en nombre <code>1</code> : <code>4 - &quot;general&quot;</code> -&gt; <code>3</code> ou <code>&quot;pomme&quot;/&quot; terre&quot;</code> -&gt; <code>1</code>

= Mathematical operation =

Vous pouvez utiliser <code>+</code> (addition), <code>-</code> (soustraction), <code>/</code> (division), <code>*</code> (multiplication) dans le calcul d’une valeur.

= Fonctions =

Les fonctions prennent des termes pour leur appliquer des opérations qui ne sont pas aussi simple que les opérations mathématiques ci-dessus. Les voici résumées :

= <code>round(value)</code> =

Cette fonction donne l’arrondi à l’entier le plus proche d’un nombre. Pour rappel, l’entier le plus proche de 0,50 et 1, et l’entier le plus proche de 0,49 est 0.

= <code>floor(value)</code> =

Donne l’arrondi inférieur d’un nombre.

= <code>ceil(value)</code> =

Donne l’arrondi supérieur d’un nombre.

= <code>avg(value1, value2, ...)</code> =

Donne la moyenne de tous les nombres dans les arguments.

= <code>sum(value1, value2, ...)</code> =

Donne la somme des nombres dans les arguments.

= <code>if(comparison, then, else)</code> =

Cette fonction va comparer un nombre à un autre nombre (argument “comparison”), puis donner l’argument “then”, ou l’argument “else”.

* '''<code>comparison</code>''' : Cet argument doit contenir deux nombres, avec un comparateur entre eux. Les comparateurs sont <code>&gt;</code>, <code>&lt;</code> et <code>=</code>. 
* '''<code>then</code>''' : Cet argument peut contenir un nombre ou une ligne de texte. Il sera affiché si la comparaison est vraie (<code>5 &gt; 1</code> -&gt; vrai).
* '''<code>else</code>''' : Cet argument peut contenir un nombre ou une ligne de texte ou être vide. Il sera affiché si la comparaison est fausse (<code>6 = 2</code> -&gt; faux). S’il est vide, “else” vaut 0.

== Examples ==

On peut utiliser une référence et une variable:

<pre>round(@dexterity/2) + $proficiency</pre>

Sommer des références:

<pre>sum(@dexterity, @strength, @constitution) + 5</pre>

On peut aussi utiliser des références comme des valeurs conditionnelles :

<pre>$bonus + if(@dexterity &gt; 10, 8) </pre>

{{ SystemBuilderMenu }}