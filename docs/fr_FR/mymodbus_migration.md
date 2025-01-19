# Migration du plugin MyModbus version stable

> DISCLAIMER
> Je suis certain que certains utilisateurs n'auront pas lu cette documentation avant de faire la mise à jour de la version stable.
> Si c'est votre cas, je vous conseille de garder votre dernière sauvegarde sur votre ordinateur, vous risquez d'en avoir besoin. Vous
> pouvez faire un fil de discussion sur [community](https://community.jeedom.com/tag/plugin-mymodbus) je ferai mon possible pour vous
> aider, mais si je n'y arrive pas, vous ne pourrez vous en prendre qu'à vous-même.

## Etapes AVANT de faire la mise à jour

### Lire la documentation du plugin

Afin d'en savoir un maximum sur les possibilités du plugin et notemment l'utilisation des plages de registres, lisez
[la documentation](mymodbus_doc.md) au calme.  
Cette étape va vous prendre du temps au moment de la lecture mais ça va vous familiariser avec ce qu'est devenu MyModbus et ses possibilités.

Si vous trouvez que le temps de lecture est long, imaginez le temps de la rédaction...

Par respect pour mon temps, celui de la rédaction de la documentation et celui sur community à résoudre les problèmes qui n'auraient pas été
rencontrés si la documentation et cette page avait été lue, je vous demande de bien tout lire.

### Une sauvegarde Jeedom

Faire une sauvegarde est toujours une bonne idée.  
La copier sur un autre stockage que sur la machine Jeedom est encore mieux.  
La garder jusqu'à ce que vos équipements MyModbus fonctionnent tous parfaitement est la meilleure chose à faire.

### Des captures de la configuration de l'équipement et de TOUTES les commandes

De nombreux outils permettent de faire des captures. Sauvegardez-les avec un nom de fichier que vous comprendrez.

### Stopper le démon

Afin que la désactivation de tous les équipements ne perturbe pas le démon (je ne sais pas comment il réagit) et par sécurité, je recommande
de stopper le démon MyModbus.

Une fois que c'est fait, il faut vérifier qu'aucun ancien process ne tourne encore. Pour cela, connecté avec les droits admin sur Jeedom,
allez dans *réglages / Système / Configuration* puis dans l'onglet *>_ OS/DB*. Là cliquez sur le bouton *>_ Ouvrir* à coté du texte
*>_ Administration Système*.

Sur cette page se trouve tout en haut le texte d'aide suivant : "Cliquez sur une commande à gauche ou tapez une commande personnalisée
ci-dessous".  
Juste en dessous de ce texte se trouve un champ de saisie dans lequel vous pouvez saisir `ps ax | grep mymodbus | grep -v grep` et valider.

Si aucune ligne n'est retournée, c'est que tous les process MyModbus sont arrêtés, vous pouvez passer au chapitre suivant.

Si une ligne de ce type est retournée :  
```
   3906 ?        SNl    0:00 /usr/bin/python3 /var/www/html/plugins/mymodbus/ressources/mymodbus_demond.py --host=192.168.1.20 --port=502 --unid=1 --polling=10 --keepopen=0 --protocol=tcpip --eqid=1 --sign=12321
```

C'est qu'un process MyModbus tourne encore, il va falloir terminer ce process. Il existe un process par ligne retournée, le PID (process ID)
est le premier chiffre de la ligne, ici c'est `3906`.  
Pour terminer un process, il faut lancer la commande :  
```kill -9 [PID]```  
en remplaçant `[PID]` par le PID du process à terminer. Dans notre exemple il faut donc lancer : `kill -9 3906`.

Après avoir terminé tous les process, vous devez vérifier si des process MyModbus tournent toujours et les terminer le cas échéant jusqu'à
ce que plus aucun process MyModbus ne tourne.

### Désactiver les équipements MyModbus

Afin que les équipements ne démarrent pas sans vérification après la mise à jour, il faut désactiver les équipements MyModbus et les sauvegarder.  
Ceci peut être fait une fois les captures réalisées.

***

## Mise à jour du plugin

Comme à votre habitude pour n'importe quel plugin, dans le centre des mises à jour, vous pouvez mettre MyModbus à jour.

***

## Etapes APRÈS avoir fait la mise à jour

Pour chaque équipement, l'un après l'autre :  
1. Vérifiez et corrigez la configuration de l'équipement :
    - d'après ce que vous en savez afin qu'il fonctionne,
    - en la comparant avec la capture.
2. Vérifiez et corrigez les commandes de l'équipement :
    - d'après ce que vous en savez afin qu'elle fonctionne,
    - en la comparant avec la capture,
    - pensez à relier les commandes action à leur commande info si vous en avez une,
3. Sauvegardez l'équipement même si vous n'avez fait aucune modification.

J'ai fait en sorte que la configuration soit reprise, mais il se peut que certains paramètres ne soient pas migrés correctement.

- Une fois tous les équipements vérifiés et sauvegardés, activez-en un et un seul (pensez à sauvegarder).
- Lancez le démon.
- Vérifiez qu'il n'y ait pas de messages d'erreur dans les log.
- Désactivez l'équipement et activer le suivant seulement.
- Vérifiez qu'il n'y ait pas de messages d'erreur dans les log.
- Ainsi de suite pour tous vos équipements.

Bien sûr si vous n'avez qu'un seul équipement, vous n'aurez à faire ceci qu'une seule fois.

Sachez qu'il est possible de scinder un équipement. Ca peut vous permettre d'organiser vos équipement plus simplement et sans passer par des
virtuels. Il vous suffit de créer un nouvel équipement qui utilise l'interface d'un équipement existant et de déplacer les commandes dans ce
nouvel équipement. Tout est réalisable via le plugin.  
C'est expliqué dans la documentation.

- Activez tous vos équipements.

Maintenant tout devrait être bon.

- Faites une sauvegarde.
- Laissez tourner.

## En cas de problème

En cas de problème, consultez les fils de discussion qui traitent de MyModbus, vous y trouverez peut-être la solution à votre problème.
Faites une recherche par mot clé.  
Si un problème similaire est en cours de résolution, attendez la solution.  
Si votre problème n'a pas été solutionné, faites un nouveau fil de discussion en fournissant les captures de l'équipement impacté
(au moins un), les captures de commandes et les log en mode debug. Pour que le niveau de log soit pris en compte, il faut redémarrer
le démon.
