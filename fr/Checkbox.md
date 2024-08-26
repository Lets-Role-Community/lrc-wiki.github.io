Une simple case à cocher.

= Options =

== Label ==

Ce que vous écrivez dans ce champ se retrouvera à droite de la case à cocher. Cliquer sur ce label cochera ou décochera la case.

= Computed =

== Retour du composant lors d’une référence ==

Quand vous faites référence à une case à cocher, la référence aura soit la valeur ''“false”'', soit la valeur ''“true”'', soit la valeur ''1'', soit la valeur ''0''.

* Si la case est cochée et que :
** La référence est seule, la valeur sera ''true''. 
** La référence est à l’intérieur d’un calcul numérique, la valeur sera ''1''. (exemple : <code>1+@id_de_la_case</code> =&gt; 2) 
** La référence est à l’intérieur d’une phrase créée par concaténation, elle sera égale à ''true''. (exemple : <code>&quot;Ceci est &quot;+@id</code> =&gt; ''Ceci est true'' ) 
** La référence est précédée et suivie de calculs et de concaténations, ce sera le terme qui suit la référence qui influencera sa valeur (exemple 1 : <code>&quot;Ceci est &quot;+ @id + 1</code> =&gt; ''Ceci est 2'' | exemple 2 : <code>1+ @id + &quot;Ceci est &quot;</code> =&gt; ''1trueCeci est'') 

* Si la case est décochée et que : 
** La référence est seule, la valeur sera ''false''. 
** La référence est à l’intérieur d’un calcul numérique, la valeur sera ''0''. 
** La référence est à l’intérieur d’une phrase créée par concaténation, elle sera égale à ''false''. 
** La référence est précédée et suivie de calculs et de concaténations, ce sera le terme qui suit la référence qui influencera sa valeur.

{{ SystemBuilderMenu }}