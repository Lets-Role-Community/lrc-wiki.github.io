Les variables contextuelles sont utilisables en deux endroits :

* La vue affichage d’un '''Repeaters''', où les données de la vue éditable sont disponibles.
* Les vues '''“Bindings”''', où les données qui sont dans le script sont disponibles.

Les variables contextuelles sont appelées avec un <code>#</code> suivi du nom de la variable.

Par exemple, vous avez un ''repeater'' avec un champ nommé <code>spellName</code> dans la vue modifiable. Sur la vue affichage, vous pouvez configurer un ''label'' ''computed'', avec la valeur <code>#spellName</code>. Le nom du sort sera affiché dans le ''label''.

{{ SystemBuilderMenu }}