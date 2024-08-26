Une vue est l’élément principal d’une [[Fiche|fiche]], d’un [[Crafts|craft]], d’un élément de la fiche (comme le contenu d’un [[Tabs|onglet]] ou un [[repeater]]) ou d’un [[API de demandes|prompt]]. Elle se trouve au sommet de l’arborescence. Il est possible d’en créer de nouvelles en cliquant sur le + au dessus de “''source editor''”. On les supprime avec un clic droit et on les modifie comme les autres composants, grâce aux champs sur la droite de l’écran.

= Les types de vues/views =

== Main View ==

C’est le type destiné à la feuille de personnage, car c’est la vue/view de ce type qui sera utilisée lors de la création d’un nouveau personnage. '''Il ne peut y avoir qu’une seule ''Main View''.'''

== SubComponent View ==

Les ''SubComponent Views'' peuvent être utilisée comme des parties d’autres vues/views. Par exemple, les vues de ce type associées à un [[Tabs|onglet]] seront affichées dans la vue où ce dernier se trouve. Ce type de vue est aussi utilisé dans les [[crafts]], les [[repeater]] et les [[API de demandes|prompts]].

= Options =

== Type ==

Vous pouvez changer le type de vue après création.

== Craft ==

Cocher la case rend disponible la vue en tant que [[Crafts|craft]] dans le ''content crafting''.

== Width, Height ==

Ce sont les dimensions de la vue en pixels. Elles s’affichent en pointillés dans le mode preview du système builder. Le minimum est 400x275, le maximum 950x600.

== Tokenizable ==

Seules les vues craftable peuvent cocher cette case leur permettant d’être glissée-déposée sur la carte par le maître de jeu depuis le ''content crafting''. On l’utilise notamment pour les monstres et les personnages non joueurs. La vue doit aussi contenir un composant [[avatar]] pour que cela fonctionne (vous pourrez cochez la cases, mais sans avatar, aucun token n’apparaîtra).

== Droppable ==

Disponible seulement pour les [[crafts]], cette case permet au maître de jeu de glisser-déposer le ''craft'' depuis le ''content crafting'' vers une fiche de personnage ou un autre ''craft''. Un script qui dicte ce qu’il doit se passer quand le craft est déposé est requis.

== Avatar’s id ==

On y renseigne l’identifiant du composant ''avatar'' qui correspond à la vue.

{{ SystemBuilderMenu }}