= Un craft, qu’est-ce que c’est =

Un craft est une modèle de fiche que le créateur du système met à disposition du MJ pour ajouter du contenu à sa partie. Par exemple, des PNJ (Personnage non jouable), des ennemis, des objets, etc.

Un craft peut avoir plusieurs options d’utilisation. - Utilisable en tant que Token sur la carte - Glissable sur une fiche pour l’affecter à un champs de type <code>repeater</code>

= Comment créer un craft =

Pour créer un craft, il faut définir la vue principale. Cela peut être une vue dédié ou alors la vue d’édition d’un repeater.

Une fois cette vue définie, vous devez cocher l’option <code>Craft ?</code>. Cela l’ajoutera à la liste des type disponible dans la bloc <code>Content Crafting</code> de la table virtuelle.

Si votre Craft à pour objectif d’être déposé sur le terrain (un monstre par exemple). Vous devez aussi cocher la case <code>Tokenizable ?</code>

Si votre craft à pour objectif d’être glissé sur une autre fiche afin de l’ajouter à un <code>repeater</code> alors vous devez cocher la case <code>Droppable ?</code>

Enfin, si vous voulez que votre craft ait une image, aussi bien dans la liste des <code>Content Crafting</code> que sur le terrain en mode token; vous devez ajouter un composant <code>Avatar</code> dans la vue et préciser dans le champs d’option <code>Avatar's id</code> du craft l’id du composant que vous venez d’ajouter.

== Exemples de crafts ==

[[Fichier:Craft exemple monster.png]]
Dans l’exemple ci-dessus, nous avons un craft utilisable sur le terrain. Il s’agit d’une fiche de monstre pour le système Dragons.

[[Fichier:Craft exemple weapon.png]]
Dans ce nouvel exemple, il s’agit du craft des armes utilisé dans le système Dragons. Celui-ci est une vue utilisée par le <code>repeater</code> des armes du système Dragons. Le fait d’utiliser la vue du <code>repeater</code> permet d’éviter les duplications de code qu’il faut éviter au maximum lors des developpements.

= Les Drops =

Lorsqu’un craft est de type <code>droppable</code> il faut ajouter un bout de script afin de configurer dans quel <code>repeater</code> la fiche doit être copiée.

Il faut aussi respecter les noms des champs du <code>repeater</code> car les id des champs doivent être identiques. D’où le fait d’utiliser directement la vue d’édition du <code>repeater</code> autant que possible.

== Un peu de code ==

La fonction à utilisé dans le scripting est la fonction Drop, décrite dans la page [[Global]].

La fonction drop fonctionne de la manière suivante : 
* Elle fournit 2 paramètres en entrée 
* '''<code>from</code>''', type <code>Sheet</code> : Fiche d’origine. Le craft. 
* '''<code>to</code>''', <code>Sheet</code> : Fiche de destination. La fiche de personnage par exemple
* Elle attend en retour l’id du repeater de la fiche <code>to</code> qui devra contenir le craft glissé

'''''WARNING''''' Les valeurs des champs dans les fiche <code>from</code> et <code>to</code> ne sont pas retournées correctement actuellement. Ce bug à été signalé sur discord et n’est pas encore corrigé à l’heure actuelle.

Voici un exemple de Drop permettant de gérer deux Crafts, des sorts qui doivent être rangés dans le bon <code>repeater</code> en fonction de la valeur d’un des champs et des armes qui vont directement dans le <code>repeater</code> associé :

<syntaxhighlight lang="javascript">
drop = function(from, to) {
    log("drop de " + from.name() + " vers " + to.name());
    if (from.id() === "fiche_sorts" && to.id() === "main") {
        return "rep_sorts" + from.get("spell_level").value();
    }
    if (from.id() === "attackedit" && to.id() === "main"){
      return "repeteur_armes";
    }
};
</syntaxhighlight>

{{ SystemBuilderMenu }}