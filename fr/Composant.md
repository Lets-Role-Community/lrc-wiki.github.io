Représente un composant qui est placé sur une feuille.

= Methods =

== <code>parent()</code> ==

* Retourne : <code>Component|null</code>.

Récupère le composant parent.

== <code>find(id)</code> ==

* '''<code>id</code>''', type <code>string</code> : L’identifiant du composant enfant.
* Retourne : <code>Component|null</code>.

Récupère un élément enfant.

== <code>on(event, callback)</code> ==

== <code>on(event, delegate, callback)</code> ==

* '''<code>event</code>''', type <code>string</code> : Le nom de l’évènement. Valeurs possibles : <code>click</code>, <code>update</code>, <code>mouseenter</code>, <code>mouseleave</code>, <code>keyup</code>.
* '''<code>delegate</code>''', type <code>string</code> : Le composant enfant auquel déléguer l’évènement.
* '''<code>callback</code>''', type <code>Function</code> : La fonction qui sera appelée quand l’évènement surviendra. Le premier argument est l’évènement.
* Retourne : <code>void</code>.

Si l’évènement survient à cause du script, il aura la propriété <code>computed</code> à <code>true</code>. Il est possible de déléguer les évènements à un composant enfant, pratique quand vous utilisez les repeaters. Il n’est possible d’avoir qu’un évènement du même type à la fois pour un même composant.

L’événement '''<code>update</code>''' ne se comporte pas de la même manière sur un '''numberInput''' et sur un '''textInput''' :
* Sur un '''numberInput''', l'update s'effectuera à chaque input dans le champ. Donc si vous taper un nombre à deux chiffres, il s’effectura deux fois.
* Sur un '''textInput''', l'update se lancera lorsque le composant perdra le focus.

== <code>off(event)</code> ==

== <code>off(event, delegate)</code> ==

* '''<code>event</code>''', type <code>string</code> : Le nom de l’évènement. Valeurs possibles : <code>click</code>, <code>update</code>, <code>mouseenter</code>, <code>mouseleave</code>, <code>keyup</code>.
* '''<code>delegate</code>''', type <code>string</code> : Le composant enfant auquel déléguer l’évènement.
* Retourne : <code>void</code>.

Retire un évènement du composant ou de l’un de ses composants enfants délégués.

== <code>hide()</code> ==

* Retourne : <code>void</code>.

Masque le composant.

== <code>show()</code> ==

* Retourne : <code>void</code>.

Affiche le composant si celui-ci est masqué.

== <code>addClass(class)</code> ==

* '''<code>class</code>''', type <code>string</code> : Une classe à ajouter au composant.
* Retourne : <code>void</code>.

== <code>removeClass(class)</code> ==

* '''<code>class</code>''', type <code>string</code> : Une classe à retirer du composant.
* Retourne : <code>void</code>.

== <code>value()</code> ==

== <code>value(newValue)</code> ==

* '''<code>newValue</code>''', type <code>number|string|Object|null</code> : La nouvelle valeur du composant.
* Retourne : <code>null|number|string|Object</code>.

Récupère ou définit la valeur du composant. Si le composant est persistant, la valeur est sauvegardée de façon permanente. Faîtes attention à ne pas utiliser ce setter trop souvent sur des composants persistants, car le serveur a une limite au nombre d’appels possibles. Si le composant a une valeur virtuelle, c’est elle qui est retournée. Utilisez <code>component.rawValue()</code> pour récupérer la valeur de base, la valeur “non-virtuelle”.

<syntaxhighlight lang="javascript">
let hp = sheet.get("hp");  // hp est un composant persistant
log(hp.value());  // 5
hp.value(11);  // met à jour et sauvegarde la nouvelle valeur
</syntaxhighlight>

== <code>rawValue()</code> ==

* Retourne : <code>null|number|string|Object</code>.

Récupère la valeur de base, “non virtualle”, du composant.

<syntaxhighlight lang="javascript">
let hp = sheet.get("hp");
hp.value(17);
log(hp.value());  // 17

hp.virtualValue(20);
log(hp.value());  // 20
log(hp.rawValue());  // 17
</syntaxhighlight>

== <code>virtualValue()</code> ==

== <code>virtualValue(newValue)</code> ==

* '''<code>newValue</code>''', type <code>number|string|Object|null</code> : La nouvelle valeur du composant.
* Retourne : <code>number|string|Object</code>.

Récupère ou définit la valeur virtuelle du composant. Les valeurs virtuelles sont utiles quand vous voulez changer une valeur à partir d’un calcul. Par exemple, vous pourriez avoir une armure qui donne au personnage +2 PV, et définir la valeur virtuelle du composant hp à sa valeur de base + 2. Le composant devrait afficher la valeur virtuelle par défaut, et la valeur de base quand il est survolé.

<syntaxhighlight lang="javascript">
let hp = sheet.get("hp");
hp.virtualValue(hp.rawValue() + 2);
</syntaxhighlight>

== <code>text()</code> ==

== <code>text(replacement)</code> ==

* '''<code>newValue</code>''', type <code>string</code> : Le texte à écrire.
* Retourne : <code>null|string</code>.

Retourne ou définit le texte contenu dans un label. La valeur n’est pas évaluée et le HTML n’est pas autorisé. Utiliser <code>text</code> sur un Label ne modifie pas les data de la sheet (<code>getData</code>). Si on utilise <code>value</code> par contre, le texte du Label sera également changé, mais la sheet aura un nouveau data portant l’identifiant du Label et la valeur entrée. Cette donnée sera alors synchronisée sur tous les clients à la différence d’une utilisation de <code>text</code>.

<syntaxhighlight lang="javascript">
sheet.get("job").text("Warrior");
</syntaxhighlight>

== <code>visible()</code> ==

* Retourne : <code>boolean</code>.

Retourne <code>true</code> si le composant n’est pas masqué.

== <code>sheet()</code> ==

* Retourne : [[system-builder/scripting/sheet|<code>Sheet</code>]].

Retourne la feuille associée à ce composant.

== <code>setChoices(choices)</code> ==

* '''<code>choices</code>''', type <code>Object</code> : Les choix.
* Retourne : <code>void</code>.

Seulement disponible pour les composants Choice, modifie les choix possibles.

<syntaxhighlight lang="javascript">
sheet.get('class').setChoices({
    "tiger": "Big cat",
    "mouse": "Mouse",
    "kitten": "Very small"
});
</syntaxhighlight>

== <code>name()</code> ==

* Retourne : <code>string</code>.

Retourne le nom du composant tel qu’indiqué dans le System Builder.

== <code>id()</code> ==

* Retourne : <code>string</code>.

Retourne l’identifiant du composant tel qu’indiqué dans le System Builder.

== <code>index()</code> ==

* Retourne: <code>string|null</code>

Retourne l’identifiant de l’entrée contenant le composant quand il est contenu dans un répéteur, retourne <code>null</code> si le composant n’est pas dans un répéteur.

{{ SystemBuilderMenu }}