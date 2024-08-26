Les références sont utilisées pour connecter les valeurs des composants entre eux. Par exemple, vous pouvez avoir une composante numérique <code>charisme</code> et une autre <code>persuasion</code>. Si vous voulez que la valeur de <code>persuasion</code> soit égale à 5 + le charisme, définissez simplement la valeur calculée sur <code>5 + @charisma</code>. Lorsque l’utilisateur met à jour la valeur de <code>charisme</code>, la valeur de <code>persuasion</code> se met automatiquement à jour.

Il est possible de lier une référence à une autre référence. Par exemple, <code>charisme</code> pourrait avoir une valeur de <code>7 + @compétence</code> et ainsi de suite.

Il y n’y a qu’une seule restriction : vous ne pouvez pas avoir de références circulaires; comme <code>charisme=5+@beauté</code> et <code>beauté=2+@charisme</code> Si vous faites une référence circulaire, vous aurez une erreur dans la console et la valeur sera <code>0</code>.

{{ SystemBuilderMenu }}