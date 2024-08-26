== Depuis votre feuille de personnage ==
La plupart des feuilles de personnages intègrent directement les jets de dés. Cliquez simplement sur une ligne de texte ou un bouton et vos dés seront lancés automatiquement !

== Via le chat ==
Vous pouvez aussi lancer des dés en utilisant le chat, en tapant simplement <code>/r formule</code>. La formule est basée sur notre syntaxe de jet, [https://lets-role.com/dice-tester que vous pouvez tester ici].

Quelques exemples :

* <code>/r 3d6</code>
* <code>/r 1D100>55</code>
* <code>/r keeph(2d20)</code>

Il y a plusieurs commandes pour lancer des dés :

* <code>/roll</code> (ou <code>/r</code>) permet de jeter des dés visibles par tous
* <code>/gmroll</code> (ou <code>/gr</code>) permet de jeter des dés visibles par uniquement vous et le GM
* <code>/gmonlyroll</code> (ou <code>/gor</code>) permet de jeter des dés qui seront visibles uniquement par le GM (et même pas par vous)

=== Utiliser les références dans les jets ===
Vous pouvez référencer certains éléments de votre feuille de personnage dans les jets en utilisant un <code>@</code>. Par exemple :

* <code>/r 1d20 + @str_mod</code>