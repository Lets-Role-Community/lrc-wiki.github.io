Une instance de feuille représente une feuille de personnage ou un craft.

= Methodes =

== <code>get(id)</code> ==

* '''<code>id</code>''', type <code>string</code> : L’identifiant de l’élément.
* Retourne : <code>Component|null</code>.

Récupère un élément.

== <code>getVariable(id)</code> ==

* '''<code>id</code>''', type <code>string</code> : L’identifiant de la variable.
* Retourne : <code>number|null</code>.

Récupère la valeur d’une variable.

== <code>setData(data)</code> ==

* '''<code>data</code>''', type <code>Object</code> : Les données à charger.
* Retourne : <code>void</code>.

Définit plusieurs données de la feuille en une seule fois (incluant les valeurs des composants).
Vous ne pouvez définir qu’un maximum de 20 données à la fois.

<syntaxhighlight lang="javascript">
sheet.setData({
    "hp": 30,
    "mp": 12
    //...
});
</syntaxhighlight>

== <code>getData()</code> ==

* Retourne : <code>Object</code>.

Retourne toutes les données de la feuille en une seule fois (incluant les valeurs des composants).

<syntaxhighlight lang="javascript">
let values = sheet.getData();
/* 
values = { 
    avatar: { avatar: "y/x/....png", token: "k/g/....png"},
  hp: 30,
  mp: 12,
  ...
}
*/
</syntaxhighlight>

== <code>prompt(title, view, callback, callbackInit)</code> ==

Voir : [[fr/system-builder/scripting/prompt|API Prompt]]

== <code>id()</code> ==

* Retourne : <code>string</code>.

L’identifiant de la feuille (c’est à dire l’identifiant de la vue principale de la feuille).

== <code>getSheetId()</code> ==

* Retourne : <code>number</code>.

L’identifiant unique de la feuille (c’est à dire un numéro d’ordre de création de la feuille sur Let’s Role). Permet de distinguer une feuille d’une autre feuille du même type.

== <code>name()</code> ==

* Retourne : <code>string</code>.

Le nom de la feuille.

{{ SystemBuilderMenu }}