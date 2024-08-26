[[Fichier:System-builder-logo.png]]
==Avertissement==
Voici une liste des questions fréquemment posées sur le ''Discord'' de ''Let's Role!'' à propos du ''SystemBuilder''. Les réponses apportées ci-après n'engagent que les utilisateurs qui les ont postées. Elles résultent de leur expérience du ''SystemBuilder''. Elles ne reflètent aucunement les opinions de l'équipe de ''Let's Role!'' et ne peuvent donc être considérées comme officielles — ni même pleinement avérées.

Cette FAQ sera intégrée (sous une forme légèrement différente) dans le futur '''Help Center''' de ''Let's Role!''

==Liens==
===Q) Page web du SystemBuilder===
''Mots clefs : lancer, lien, nouveau, page, système, trouver, web''
 ''Où trouve-t-on la page web du ''SystemBuilder'' ? Je ne vois aucun lien sur le site de ''Let's Role!'' pour y accéder.''

===R) Page web du SystemBuilder===
 Il n'existe pas de lien direct nommé ''SystemBuilder''. Sur le site de ''Let’s Role!'', allez dans ''Bienvenue,''(Votre Nom) > ''Systèmes'' > ''+Créer un nouveau Système''.

*'''P.S.''' : procédez de même pour mettre à jour votre Système en cours de développement, mais en allant, après l'étape ''Systèmes'', dans (Votre Système) > ''Général'' > ''Entrer le System Builder'' (sic).
----

===Q) Développeur débutant===
''Mots clefs : aider, commencer, communauté, débutant, débutante, débuter, développer, développeur, discord, forum, javascript, programmer, programmeur''
 ''Je débute comme développeur sur ''Let's Role!''. Par où commencer ?''

===R) Développeur débutant===
 Suivez [[D%C3%A9buter_comme_d%C3%A9veloppeur|ce lien]] sur ce wiki. Vous pouvez aussi suivre ce tutoriel : [https://www.youtube.com/watch?v=F141URrFVwo https://www.youtube.com/watch?v=F141URrFVwo].
 Vous trouvez facilement en ligne de la documentation ainsi que des cours gratuits sur le langage de développement utilisé dans le ''SystemBuilder'', javascript. Un exemple ? [https://fr.javascript.info/ https://fr.javascript.info/]. Même chose pour Boostrap : [https://getbootstrap.com/docs/4.0/ https://getbootstrap.com/docs/4.0/].
 Ensuite faites-vous aider par une Communauté bienveillante sur le [https://discord.gg/m5cqTwa Discord] (le Forum étant peu fréquenté), en n'hésitant pas à poser toutes sortes de questions. Essayez cependant, avant de poser une question particulière, de vérifier si quelqu'un ne l'aurait pas déjà posée avant vous (et obtenu des réponses), en utilisant la fonction recherche du Discord.
*'''P.S. :''' ''peut-être que certaines réponses à vos questions sont présentes sur la page que vous être en train de lire en ce moment.''

[[File:bonhomme.png|425px|thumb|left|75 - Argh ! Touché à la jambe gauche ! P… ça fait mal… j'peux pas l'croire, p'têt' que c'est juste un bug de ton p… d'Système, non ? — Un joueur anonyme [https://www.deviantart.com/davidberco/art/Bonhomme2-916212559 Creative Commons Attribution 3.0 License]]]

==Dysfonctionnements==
''Mots clefs : changements, commit, compte, modifications, publier, prise'' 
===Q) Modifications non prises en compte===
 ''J'ai apporté des modifications à mon Système dans le ''SystemBuilder'', mais quand je le lance, mes changements ne sont pas pris en compte. Y a-t-il quelque chose que j'ai mal fait ?

===R) Modifications non prises en compte===
 Souvent, enregistrer puis faire un ''Commit'' (''Publier'') de votre Système dans le ''SystemBuilder'' (il sera publié, mais ne sera pas présent dans ''La Boutique de Let's Role!''), dans la foulée, résout bien des problèmes. Vous ne risquez rien à essayer. Vos ''Commit'' successifs seront stockés dans ''Site de Let’s Role!'' > ''Bienvenue,''(Votre Nom) > ''Systèmes'' > (Votre Système) > ''Commits''. Vous pourrez à tout moment restaurer une ancienne version (''Commit'') de votre Système (voir [[FAQ-SystemBuilder#Q.29_Charger_un_Commit|Charger un Commit]]).
----

===Q) Perte de mes dernières modifications===
''Mots clefs : commit, disparues, disparus, données, data, lancer, perte, publier'' 
 ''J'ai enregistré mon Système et/ou fait un ''Commit'' (''Publier'') de mon Système et/ou lancé mon Système dans le SystemBuilder, puis j'ai quitté (éventuellement) le ''SystemBuilder'', mais quand je suis revenu dans le ''SystemBuilder'', toutes mes dernières modifications avaient disparu. Que s'est-il passé ?''

===R) Perte de mes dernières modifications===
 Parfois, lorsque vos modifications contiennent des erreurs, le ''SystemBuilder'' semble « oublier » ou « faire l'impasse » sur toutes ces modifications et réinitialise votre Système à la dernière sauvegarde précédant celles-ci.
----
===Q) Ça ne fonctionne pas===
''Mots clefs : bug, commit, choice, composants, computed, doublon, feuille, ID, lancer, publier, script, sheet, tab, tableau, tableaux''
 ''J'ai voulu enregistrer mon Système et/ou faire un ''Commit'' (''Publier'') de mon Système et/ou lancer mon Système dans le ''SystemBuilder'' ou bien dans une Table hors ''SystemBuilder'', mais ça n'a pas marché. Y a-t-il quelque chose que j'ai mal fait ?

===R) Ça ne fonctionne pas — ID des composants===
 Si vous créez ou mettez à jour une des feuilles (sheet) de votre Système, essayez de voir s'il n'y a pas de doublon(s) dans les intitulés des ID de vos composants. Le ''SystemBuilder'' vous empêche généralement d'utiliser deux fois la même ID pour des composants différents en émettant un message d'erreur et en re-générant une ID aléatoire ; mais voilà, parfois la situation lui échappe, deux composants se retrouvent avec la même ID (vous en êtes à l'origine, trop confiant que vous êtes en la technologie) et cela résulte en un conflit d'ID. Si c'est bien le cas, résoudre ce conflit d'ID est sans aucun doute la solution à votre problème.

*'''P.S.''' : il n'est pas toujours possible de modifier une ID depuis l’''Éditeur graphique'' (par exemple, quand c'est celle d'une vue (view)). Dans ce cas, rendez-vous dans l’''Éditeur de source''. Sélectionnez alors tout le code JSON, copiez-le et collez-le dans la fenêtre d'une application d'éditeur de code présente sur votre ordinateur (comme NotePad sous Windows), puis faites une sauvegarde (Enregistrer) de ce fichier sur votre disque dur. Cela vous servira de backup si les choses tournent mal lors de l'opération suivante. Cherchez ensuite l'ID doublon fautive (en faisant un ctrl-F sur PC ou un command-F sur Mac) dans la fenêtre de l’''Éditeur de source'' du ''SystemBuilder'', puis éditez-la (changez-la en ''xvxvxvxvxvxv'' par exemple). Soyez très précautionneux, ne touchez à rien d'autre dans le code JSON. Essayez alors à nouveau d'enregistrer votre Système. Avec un peu de chance, cela devrait fonctionner. Rappelez-vous : en cas de gros pépin, vous disposez d'un backup.

===R) Ça ne fonctionne pas — Computed===
 Si vous avez inséré une commande dans la zone texte d'un composant pour lequel vous avez coché la case ''Calculé'' (''Computed'') et qu'il y a une ou plusieurs erreurs dans cette commande (du texte de couleur rouge s'affiche en bas à droite de la fenêtre quand vous sélectionnez ce composant), cela peut vous empêcher d'enregistrer votre Système et/ou d'en faire un ''Commit'' (''Publier'') et/ou de le lancer. Si c'est bien le cas, déboguer votre commande (ou décocher temporairement la case ''Calculé'', dans cette optique) est sans aucun doute la solution à votre problème.

===R) Ça ne fonctionne pas — Tableaux===
 Si vous avez créé des tableaux (Tables, à droite de Vues dans le ''SystemBuilder''), pour vos choix (Choice) ou pour vos onglets (Tab) par exemple, essayez d'en vérifier la cohérence. Une ou plusieurs inconsistances dans un ou plusieurs tableaux peuvent vous empêcher d'enregistrer votre Système et/ou d'en faire un ''Commit'' (''Publier'') et/ou de le lancer. Si c'est bien le cas, restaurer cette cohérence est sans aucun doute la solution à votre problème.

===R) Ça ne fonctionne pas — Script===
 Si vous avez associé un script à votre Système, une ou plusieurs erreurs dans ce script peuvent vous empêcher d'enregistrer votre Système et/ou d'en faire un ''Commit'' (''Publier'') et/ou de le lancer. Si c'est bien le cas, déboguer votre script, en vérifiant la syntaxe et en insérant des log() aux points stratégiques par exemple (ou placer temporairement en commentaires toutes les lignes de code fautives, dans cette optique) est sans aucun doute la solution à votre problème.

==Gestion de mon Système==
===Q) Créer mon premier Système===
''Mots clefs : coder, créer, développeur, javascript, premier, système'' 
 ''Mais je ne sais pas coder en javascript (je ne suis pas développeur) ! Je ne vais pas me lancer dans la création d'un Système sous le ''SystemBuilder'' car ce n'est vraiment pas pour moi ! Il faudrait que je trouve quelqu'un qui le fera à ma place…''

===R) Créer mon premier Système===
 Si vous avez un peu de mal à vous lancer sur le ''SystemBuilder'', commencez d'abord par dessiner les vues (views) de votre fiche sur papier ou sur tout autre support que vous maîtrisez. Identifiez bien les différents types de composants ainsi que leur organisation en rangs et colonnes. Transférez votre fiche seulement ensuite vers le ''SystemBuilder'' : organiser la « mise en page » de la fiche sous ''SystemBuilder'' est plutôt intuitif et amusant (et ludique). Et là, pas besoin de savoir coder en javascript.
 Après, une bonne âme, voyant le superbe résultat que vous aurez obtenu, n'hésitera pas à « programmer » les tirages de dés ; Là encore, pas besoin de savoir coder en javascript. Les tirages de dés s'obtiennent avec quasiment [https://lets-role.com/dice-tester les mêmes formules] que vous utilisez déjà dans le chat pour les jeter.
 Encore après, si quelqu'un souhaite automatiser quelques fonctions, oui, un peu de code javascript sera nécessaire…
 Mais tout cela se fait par étapes. Et c'est plutôt assez simple de trouver des collaborateurs sur un projet qui a déjà un peu avancé que de les réunir à partir de zéro.
----

===Q) Publier mon Système===
''Mots clefs : publier, système''

 ''Comment publier mon Système ? Il y a deux endroits sur ''Let's Role!'' qui mentionnent de publier mon Système ; je n'y comprend plus rien !

===R) Publier mon Système===
 En effet ''Let's Role!'' vous propose de publier votre Système, une première fois dans le ''SystemBuilder'' (bouton « Publier » qui se transforme en bouton « Commit ») et une seconde fois en suivant ''Site de Let’s Role!'' > ''Bienvenue,''(Votre Nom) > ''Systèmes'' > (Votre Système) > ''Général'' > ''Your system is not published.'' > ''Publier ce système''.
 '''1-''' Dans le ''SystemBuilder'', cette option vous permet de créer et/ou mettre à jour votre Système sur Let's Role! (il sera publié, mais ne sera pas présent dans ''La Boutique de Let's Role!''). Vous pourrez alors utiliser et/ou partager votre Système avec qui vous voudrez : [[FAQ-SystemBuilder#Q) Créer une Table hors SystemBuilder pour tester mon Système|Créer une Table hors SystemBuilder pour tester mon Système]].
 '''2-''' Pour ce qui concerne la second mention, cette option vous permet de publier effectivement votre Système dans ''La Boutique de Let's Role!'' : [[FAQ-SystemBuilder#Q) Publier mon Système dans la Boutique|Publier mon Système dans la Boutique]]. Toute la communauté pourra alors utiliser votre Système. NB : vous devez avoir publié aussi votre Système dans le ''SystemBuilder'' pour qu'il soit accessible depuis La Boutique lorsque vous le publierez dans celle-ci.
----

===Q) Charger un Commit===
''Mots clefs : ancienne, anciennes, commit, publier, restaurer, utilisateur, utilisateurs, version, versions'' 
 ''J'ai bien pourri la dernière version de mon Système avec mes modifications hasardeuses et je voudrais juste la mettre à la poubelle. Heureusement que j'avais régulièrement fait des ''Commit'' (''Publier'') ! Comment puis-je restaurer une ancienne version (''Commit'') de mon Système qui était certes moins avancée, mais qui avait l'avantage de fonctionner correctement ?''

===R) Charger un Commit===
 Sur le site de Let’s Role!, allez dans ''Bienvenue,''(Votre Nom) > ''Systèmes'' > (Votre Système) > ''Commits''. Cliquer sur la clef anglaise à droite d'une ancienne version chargera cette version de votre Système dans le ''SystemBuilder'' ; elle remplacera (écrasera) la dernière version de travail dans ce dernier. Cliquer sur l'astérisque à droite d'une ancienne version rendra cette version accessible lors de la création/réouverture d'une Table utilisant votre Système ; tous les utilisateurs utiliseront désormais cette version du Système.
----

===Q) Inviter des joueuses à la Table créée dans le SystemBuilder===
''Mots clefs : connection, écran, joueur, joueurs, joueuse, joueuses, MJ, noir, table''
 ''J'ai invité mes joueuses à ma Table créée depuis le ''SystemBuilder'', mais quand je m'identifie en tant que MJ depuis le lien ''Mes Tables'' pour accéder à cette Table, ''Let's Role!'' m'affiche un bel écran noir et le Système est inopérant ! Y a-t-il quelque chose que j'ai mal fait ?''

===R) Inviter des joueuses à la Table créée dans le SystemBuilder===
 Cela semble troubler plus d'un créateur de Système. La Table qui a été créée dans le ''SystemBuilder'' (facile à reconnaître, son nom commence par ''[Builder]'' si vous ne l'avez pas édité) l'a été dans un but de tests et de simulation ; elle n'est donc pas opérationnelle en dehors de ce dernier. En conséquence, vous ne devez pas y inviter des joueuses à s'y connecter, car il vous sera impossible de vous y connecter vous-même en tant que MJ depuis ''Le site de Let’s Role!'' > ''Mes Tables''. Cela débouchera inévitablement sur l'affichage d'un écran noir. Préférez cette solution : [[FAQ-SystemBuilder#Q.29_Cr.C3.A9er_une_Table_hors_SystemBuilder_pour_tester_mon_Syst.C3.A8me|Créer une Table hors SystemBuilder pour tester mon Système]] avec mes joueuses.
----

===Q) Inviter un ou des collaborateurs à œuvrer sur mon Système===
''Mots clefs : aide, collaborateur, inviter''
 ''J'ai besoin d'aide pour développer mon Système (ou bien quelqu'un m'a proposé son aide). Comment dois-je procéder pour inviter quelqu'un à venir collaborer sur mon Système ?''

===R) Inviter un ou des collaborateurs à œuvrer sur mon Système===
 Vous devez d'abord contacter votre futur collaborateur afin qu'il vous transmette l'adresse-mail avec laquelle il s'est enregistré sur ''Let's Role!''. Une fois l'adresse en votre possession, sur le site de ''Let's role!'', suivez ''Bienvenue'',(Votre Nom) > ''Systèmes'' > (Votre Système) > ''Collaboration'' > ''Inviter des collaborateurs'' > ''Email de l'utilisateur…'', saisissez l'adresse de votre futur collaborateur puis validez en cliquant ''Send Invitation''. Votre nouveau collaborateur devra suivre ''Bienvenue'',(Son Nom) > ''Systèmes'' > ''Collaborations'', puis valider sa collaboration à votre Système.
----

*'''P.S. :''' ''vous ne pourrez pas travailler tous en même temps sur votre Système. Quand l'un y sera connecté, il faudra qu'il ferme sa session ''SystemBuilder'' pour laisser la place à un/l'autre. Si vous tentez de vous connecter à votre Système sur ''SystemBuilder'' et qu'un de vos collaborateurs est en train de l'éditer, ou a simplement ouvert une session ''SystemBuilder'' avec votre Système, un message d'erreur vous en préviendra.''

===Q) Créer une Table hors SystemBuilder pour tester mon Système===
''Mots clefs : boutique, créer, inviter, joueur, joueurs, joueuse, joueuses, ouvrir, table, test, tests, testeur, testeurs''
 ''Je viens de créer mon Système. Maintenant, je voudrais pouvoir l’utiliser en le sélectionnant dans le menu quand je crée une nouvelle Table, sans pour autant le publier dans ''La Boutique de Let's Role!''. Comment dois-je procéder ?''

===R) Créer une Table hors SystemBuilder pour tester mon Système===
 C'est impossible de cette manière, tant que votre Système n'est pas publié dans ''La Boutique de Let's Role!''. Cependant, vous pouvez procéder autrement : faites un ''Commit'' (''Publier'') de votre Système dans le ''SystemBuilder'' (il sera publié, mais ne sera pas présent dans ''La Boutique de Let's Role!''). Puis, sur le site de ''Let’s Role!'', allez dans ''Bienvenue,''(Votre Nom) > ''Systèmes'' > (Votre Système) > ''Général'' > ''Partager votre système''. Copiez le lien donné, collez-le dans la barre de navigation d’une fenêtre de votre navigateur, ouvrez-le, puis dans la page ouverte cliquez ''+Créer une nouvelle Table''. Ça marche aussi pour que vos joueuses se créent un personnage : ''+Créer nouveau Perso''.

*'''P.S.''' : vous pouvez aussi inclure ce lien privé dans un e-mail ou un sms, que vous expédierez à vos joueuses.
*'''P.S. 2''' : n’oubliez pas, ensuite, de les inviter à votre Table.
*'''P.S. 3''' : vous souhaiterez peut-être aussi partager ce lien avec un ou plusieurs testeurs qui créeront eux aussi une Table utilisant votre Système.
*'''P.S. 4''' : vous pouvez à tout moment générer un nouveau lien privé ; l'ancien sera alors invalidé.
----

===Q) Publier mon Système dans la Boutique===
''Mots clefs : boutique, publier, communauté, partager, système''
 ''Ça y est, mon Système est au point et opérationnel, je l'ai testé en tant que MJ avec mes joueuses – hors du ''SystemBuilder'' – sur une Table que j'ai créée à cette occasion (voir [[FAQ-SystemBuilder#Q.29_Cr.C3.A9er_une_Table_hors_SystemBuilder_pour_tester_mon_Syst.C3.A8me|Créer une Table hors SystemBuilder pour tester mon Système]]) ; la partie s'est bien déroulée et tout a fonctionné à merveille. Je souhaite donc publier mon Système dans ''La Boutique de Let's Role!'' pour le partager avec la Communauté. Comment dois-je procéder ?''

===R) Publier mon Système dans la Boutique===
 Faites un ''Commit'' (''Publier'') de votre Système dans le ''SystemBuilder'' (il sera publié, mais ne sera pas présent dans ''La Boutique de Let's Role!'' pour le moment). Puis, sur le site de ''Let’s Role!'', allez dans ''Bienvenue,''(Votre Nom) > ''Systèmes'' > (Votre Système) > ''Général'' > ''Your System is not published''. Changez simplement l'état du bouton associé.

*'''P.S.''' : pensez à en informer la Communauté en inscrivant votre Système sur la [[Liste_des_systèmes|liste des Systèmes du wiki]] 🇫🇷 et aussi éventuellement sur la [https://lets-role.wiki/System_list liste des Systèmes du wiki] 🇬🇧.
*'''P.S. 2''' : vous pourrez aussi l'annoncer sur le [https://discord.gg/m5cqTwa Discord] où un modérateur épinglera votre post.

===Q) Traduire mon Système dans une autre langue===
 ''Je voudrais traduire l'interface de mon Système dans une autre langue (ou bien quelqu'un m'a proposé de m'aider à le faire). Comment dois-je procéder ?''

===R) Traduire mon Système dans une autre langue===
 À venir
----

===Q) Proposer ma collaboration pour traduire un Système===
 ''J'ai repéré un Système dont je pourrais sans doute traduire l'interface (dans ma propre langue ou dans une autre que je maîtrise) si seulement je pouvais contacter son auteur. Comment dois-je procéder pour le contacter et lui proposer mon aide ?''

===R) Proposer ma collaboration pour traduire un Système===
 À venir

==Versions du SystemBuilder==
===Q) Nouveau SystemBuilder===
''Mots clefs : ancien, ancienne, développer, nouveau, nouvelle, système, version
 ''J'ai entendu parler de l'arrivée d'une nouvelle version du ''SystemBuilder''.''
 '''1-''' ''Pourrai-je continuer à développer mon ancien Système sous l'ancienne version du ''SystemBuilder'' ou devrai-je mettre ce Système à niveau après le déploiement de la nouvelle version ?''
 '''2-''' ''Pourrai-je choisir la version du ''SystemBuilder'' que je veux utiliser pour développer mes futurs Systèmes après le déploiement de la nouvelle version ?''

===R) Nouveau SystemBuilder===
 '''1-''' Oui, il sera possible de rester en ''SystemBuilder v1'' ou bien de convertir son ancien Système pour le ''SystemBuilder v2'', ce qui demandera de modifier un peu son script, même si l'API sera similaire.
 '''2-''' Non, les Systèmes créés après le déploiement du nouveau ''SystemBuilder'' ne pourront être développés que sous cette nouvelle version.