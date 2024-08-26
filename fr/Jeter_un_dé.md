Vous pouvez lier un jet de dés à un label ou une icon, grâce à l’option “Roll on Click”. Ainsi quand un utilisateur cliquera sur le label ou l’icon, les dés seront lancés automatiquement.

L’ API des jet de dés est disponible [https://lets-role.com/dice-tester ici]. La seul différence est que vous pouvez utiliser des références et des variables dans la formule de dés.

Attention : l’'''API de calcul''' ''(computed API)'' est différente de l’'''API de lancer de dés''' (dice API). Ce qui signifie que vous ne pouvez pas utiliser les fonctions disponibles en calcul, comme <code>if</code>, dans le lancer de dés ; et vous ne pouvez pas utiliser de formule de dés comme <code>3d6</code> dans les valeurs calculées.<br />
Notez que cette incompatibilité peut-être contournée grâce aux références et au variables, qui peuvent être utilisées par la ''dice API'' alors qu’elle sont calculées par la ''computed API''.

= Réferences =

A voir : [[Références]].

Vous pouvez faire référence à un autre composant dans un jet de dés en écrivant <code>@id</code>.

Par exemple, si vous avez un ''number input'' dont l’identifiant est <code>dextérité</code> et dont la valeur est 8 ; vous pouvez écrire dans le champ “Roll on click” d’un label la formule <code>1d20 + @dextérité</code>, ce qui lancera <code>1d20 + 8</code>.<br />
Vous pouvez aussi utiliser les références dans la fenêtre de tchat (en écrivant <code>/roll 1d8 + @dextérité</code> par exemple)

= Variables =

A voir : [[Variables]].

Les variables sont comme les références, fonctionnent de la même manière et ont le même usage. Il y a cependant deux différence entre les deux :
* Contrairement à ces dernières, les variables sont contenu dans la '''table “variables”''' et non dans un composant (cette table est disponible par défaut dans le système builder, mais est vide au départ).
* On appelle les variables via <code>$id</code> (et non @).

=== Exemple ===

Voici quelque exemple de formule de dés :<br />
<code>1d20 + @force</code>

<code>(@force)d8 - $faible</code>

<code>1d$force * @avantage</code>

{{ SystemBuilderMenu }}