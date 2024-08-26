Les bindings (liaison en français) permettent aux joueurs de faire référence à un élément de leur feuille de personnage dans le chat. Grâce à cette API, vous avez un contrôle total sur les liens disponibles et la façon dont ils sont affichés.

Un binding est créé avec 4 éléments :
* '''<code>name</code>''', type <code>string</code> : Le nom utilisé dans le chat pour faire référence au binding
* '''<code>componentId</code>''', type <code>string</code> : L’id du composant référencé. Vous pouvez avoir plusieurs binding pour un même componentID, notamment dans le cas des [[repeater|repeaters]].
* '''<code>viewId</code>''', type <code>string</code> : L’id de la [[view]] utilisée pour afficher le binding.
* '''<code>data</code>''', type <code>Function</code> : Une fonction qui retourne l’objet de données transmis à la vue pour le rendu. Ces données seront disponibles dans la vue.

Les bindings sont disponibles via la constante globale <code>Bindings</code>.

= <code>Bindings.add(name, componentId, viewId, dataCallback)</code> =

* '''<code>name</code>''', type <code>string</code> ''<code>requis</code>'' : Le nom utilisé dans le chat.
* '''<code>componentId</code>''', type <code>string</code> ''<code>requis</code>'' : L’id du composant utilisé.
* '''<code>viewId</code>''', type <code>string</code> ''<code>requis</code>'' : L’id de la vue utilisée pour le rendu.
* '''<code>dataCallback</code>''', type <code>Function</code> : Une fonction qui retourne l’objet de données transmis à la vue pour le rendu. L’objet doit être sérialisée en JSON.

= <code>Bindings.send(sheet, name)</code> =

* '''<code>sheet</code>''', type <code>Sheet</code> ''<code>requis</code>'' : La [[fiche]] liée au binding.
* '''<code>name</code>''', type <code>string</code> ''<code>requis</code>'' : Le nom du binding.

Envoie un binding dans le chat. Le binding doit avoir été enregistré avec la fonction <code>Binding.add()</code>.

= <code>Bindings.remove(name)</code> =

* '''<code>name</code>''', type <code>string</code> ''<code>requis</code>'' : Le nom du binding.

Enlève un binding à partir de son nom.

= <code>Bindings.clear(componentId)</code> =

* '''<code>componentId</code>''', type <code>string</code> ''<code>requis</code>'' : L’id du composant.

Enlève tous les bindings liés à un composant.

{{ SystemBuilderMenu }}