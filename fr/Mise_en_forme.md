La mise en forme sur le ''Systeme builder'' utilise un système de '''''“classes”'''''.

Les classes sont des petites commandes que l’on ajoutes à un composant pour le faire changer de son apparence par défaut. On écrit ses commandes dans le champs “Classes” du composant. Tout les composants possède ce champs.

Vous pouvez donner plusieurs classes à un composant ; elles devraient toutes être séparées par un espace, et il ne devrait y a voir aucun espace inutile après une classe.

Nous utilisons les classes de Bootstrap 4 comme base pour les classes de Let’role. Donc toutes les classes disponibles dans [https://getbootstrap.com/docs/4.4/utilities/spacing/ les outils bootstrap] sont aussi disponibles dans le Systeme Builder.

Cela étant dit, vous devriez essayer de ne pas trop changer la conception par défaut de Let’s Role. C’est particulièrement important si vous souhaitez que votre feuille soit officialisée.

= Couleur de fond =

Les classes <code>highlight-1</code> et <code>highlight-2</code> sont utilisées pour une mise en avant du composant (changent la couleur de fond).

Autres couleurs :
* <code>bg-primary</code> = bleu
* <code>bg-secondary</code> = gris
* <code>bg-success</code> = vert
* <code>bg-danger</code> = rouge
* <code>bg-warning</code> = orange
* <code>bg-info</code> = cyan
* <code>bg-light</code> = clair
* <code>bg-dark</code> = fonçé
* <code>bg-white</code> = blanc
* <code>bg-transparent</code> = transparent

À noter qu'il est aussi possible d'appliquer cela aux bordures des composants avec les classes : <code>border border-*</code>
+ ajouter <code>rounded</code> pour des coins arrondis.

= Espacement =

Par défaut, il n’y a pas d’espace entre les composants, ils sont donc collés les un aux autres. Les classes d’espacement permettent de donner un peu d’ordre et d’oxygène. Il y a deux type d’espacement : 
* Les '''marges''' : elles sont l’espacement exterieur du composant. Les autres composants ne pourront pas s’approcher d’un composant avec des marges. 
* Les “'''padding'''” : traduisez rembourage ou mattelasure, sont des espaces intérieurs au composant. Les composants à l’intérieur ne pourront pas toucher les bords du composant qui les contient avec un padding.

Ces classes on une nomenclature un peu spcécial, mais facile à comprendre grâce à cette [https://getbootstrap.com/docs/4.4/utilities/spacing/ documentation].<br />
En voici un bref résumé : <code>m[coté]-[n][chiffre]</code> :
* La première lettre est soit <code>m</code> pour marge soit <code>p</code> pour padding ;
* La deuxième lettre désigne le coté ou appliquer l’espacement : gauche, droite, gauche et droite, haut, bas, haut et bas, associer respectivement au lettres <code>l, r, x, t, b, y</code>. S’il n’y a pas de lettre, l’espacement est de tout les cotés ;
* Un tiret sépare l’endroit de l’espacement de sa valeur ;
* On peu ajouter un <code>n</code> devant le chiffre, pour appliquer un marge négative : au lieu de se séparer, les composants de superposeront (ne fonctionne pas avec les padding) ;
* Et enfin un chiffre entre 0 et 5 qui caractérise la taille de l’espace (on peux mettre <code>auto</code> à la place d’un chiffre pour les marges).

= Mise en forme de text =

On utilise les classes suivantes essentiellement dans les ''label'' et dans les ''choices''.

Les classes <code>text-tiny</code>, <code>text-small</code>, <code>text-medium</code>, <code>text-large</code>, <code>text-giant</code>, <code>text-gargantuan</code> donnent une taille différente au texte (de gauche à droite, du plus petit au plus grand).

== Titre ==

La classe <code>text-title</code> donne l’aspect d’un titre au texte.

== Mettre en gras ==

La classe <code>text-bold</code> met le texte en gras.

== Figer l’espace ==

La classe <code>text-monospace</code> remplace la police de texte par une autre dons les espacements sont fixes.
Simule une police supplémentaire pour votre feuille. Utile pour une belle interface.

== Mettre en couleur ==

Certaines couleurs sont accéssible via les classes suivantes :
* <code>text-primary</code> = bleu
* <code>text-secondary</code> = gris fonçé
* <code>text-success</code> = vert
* <code>text-danger</code> = rouge
* <code>text-warning</code> = orange
* <code>text-info</code> = cyan
* <code>text-light</code> = clair
* <code>text-dark</code> = fonçé
* <code>text-body</code> = noir
* <code>text-muted</code> = gris clair
* <code>text-white</code> = blanc
* <code>text-black-50</code> et <code>text-white-50</code> = gris

= Largeur et Hauteur =

Vous pouvez donner une largeur et/ou une hauteur fixes (en pixel) à un composant grâce aux commandes <code>w-[nombre]px</code> et <code>h-[nombre]px</code>.
* “<code>w</code>” pour ''width'' qui signifie largeur,
* et “<code>h</code>” pour ''height'' qui signifie hauteur.

Les nombres de pixels que vous pouvez choisir en largeur sont 25, 50, 75, 100, 125 150, 175, 200 et 300 (exemple <code>w-25px</code>). Les autre nombres (comme 80 ou 101) ne fonctionneront pas.

Les nombres de pixels que vous pouvez choisir en hauteur sont tous ceux de la largeur, plus 400, 500, 600 et 700 (exemple <code>h-700px</code>).

= Cacher des composants =

Il y a deux classes pour cela, avec une petite nuance entre elles deux : 
* La classe <code>d-none</code> cache le composant comme s’il n’existait pas. Il ne prend ainsi plus aucun espace. 
* La classe <code>invisible</code> cache le composant en conservant sa place et ses espacements. Pratique si vous voulez ajuster l’alignement entre deux lignes contenants des éléments différents.

Ces deux classes ne fonctionnent pas sur les ''containers''.

= Montrer qu’un objet est cliquable =

La class <code>clickable</code> affiche le curseur main et change le texte en orange lorsque vous survolez le composant. Exactement le même effet visuel que lorsque vous cochez l’option « Cliquable » pour un label. Si vous l’utilisez sur une colonne ou une rangé, elle s’applique à tous les composants qu’elle contient.

= Transformation des icones =

À noter qu'une partie des classes de transformation des [https://fontawesome.com Font Awesome] sont disponibles dans let's role :
* <code>fa-rotate-90</code> = rotation de 90° (dans le sens horaire) 
* <code>fa-rotate-180</code> = 	rotation de 180°
* <code>fa-rotate-270</code> = 	rotation de 270°
* <code>fa-flip-horizontal</code> = mirroir horizontal
* <code>fa-flip-vertical</code> = mirroir vertical
* <code>fa-flip-both</code> = mirroir horizontal et vertical
cela permet d'appliquer des transformations aux icones afin que ça corresponde mieux à son idée de mise en forme.

P.I. s'applique aussi aux textes et composants ;)
 
+ cf. [https://fontawesome.com/docs/web/style/styling Styling Font Awesome]


{{ SystemBuilderMenu }}