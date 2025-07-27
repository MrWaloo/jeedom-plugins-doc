# Changelog MyModbus

## TODO
- Documentation :
  - Documenter les nouvelles fonctionnalités (documentation à jour avec la version V3.0.5)

## Développement en cours dans la branche beta-dev pour la prochaine bêta
- Pas de développement en cours

## Changelog

### V3.0.5

#### 27/07/2025 bêta1

- Utilisation de la dernière version de pymodbus, la version V3.9.2
- Intégration de la bonne licence GPL et non pas AGPL

#### 13/07/2025 bêta

- Correction du problème qui obligeait une seconde sauvegarde de l'équipement pour la prise en compte des modifications des commandes (merci Mips)

### V3.0.4

#### 12/07/2025 stable

- Passage de la version 3.0.4 bêta en stable
- Les 2 branches sont alignées

#### 18/06/2025 bêta

- Correction d'un problème d'affichage de la liste des équipements dont l'interface est utilisable comme interface partagée (merci thomaspascal)

### V3.0.3

#### 10/06/2025 stable

- Passage de la version 3.0.3 bêta1 en stable
- Les 2 branches sont alignées
- Intégration de 2 templates (merci wocha-fr)

#### 07/06/2025 bêta1

- Optimisation de l'utilisation de la mémoire
- Correction d'un message d'erreur

#### 28/05/2025 bêta

- Mise à jour de la configuration du démon en cas de désactivation ou activation d'un équipement par scénario (merci Marp30 et Noyax37)

### V3.0.2

#### 07/05/2025 stable

- Passage de la version 3.0.2 bêta en stable
- Les 2 branches sont alignées

#### 19/04/2025 bêta

- Lancement du démon permis même sans équipement actif pour valider l'installation des dépendances
- Sauvegarde des équipements en cas de mise à jour du plugin

### V3.0.1

#### 13/04/2025 stable

- Passage de la version 3.0.1 bêta6 en stable
- Les 2 branches sont alignées

#### 05/04/2025 bêta6

- Corrections pour la fonction de test

#### 21/03/2025 bêta5

- Correction de la syntaxe pour les valeurs nan (Not A Number)
- Correction de l'écriture des commandes action d'un équipement utilisant l'interface d'un autre équipement

#### 08/03/2025 bêta4

- Utilisation de la dernière version de pymodbus, la version V3.8.6
- Filtrage des valeurs nan (Not A Number) : si une valeur lue est nan alors cette valeur n'est pas remontée vers Jeedom
- [BUGFIX] La fonction de classe sendNewConfig est déclarée comme étant static

#### 14/02/2025 bêta3

- Corrections pour la fonction de test
- Traduction fonctionnelle
- Simplification de la ligne de commande. La configuration n'est plus passée sur la ligne de commande du démon mais est envoyée par la suite.

#### 08/02/2025 bêta2

- Corrections pour la fonction de test
- Ajout de la traduction

#### 06/02/2025 bêta1

- Correction de la mauvaise valeur par défaut de l'équipement de test. Dorénavant, par défaut, l'équipement n'est pas un équipement de test (merci ludoviclt)
- Fonction d'envoi des nouvelles valeurs du démon à Jeedom revue
- Correction de la fonction de nettoyage des anciens fichiers qui effaçait l'icône rtuovertcp à tord

### 02/02/2025 V3.0 stable --> Pas de mise à jour

- Aucune modification, juste un répertoire inutilisé depuis longtemps supprimé du dépôt 

### 01/02/2025 V3.0.1 bêta

- Suppression du lien inutile vers la documentation depuis la configuration des équipements (préparation pour la mise en place de la traduction)
- Utilisation de la dernière version de pymodbus : V3.8.3
- Simplification de la page modale santé
- Il est possible de créer un équipement de test qui va vérifier si les registres dans une certaine plage existent.

### V3.0

#### 23/01/2025 stable

- Passage de la version 3.0 bêta63 en stable
- Suppression du lien invalide vers une vidéo dans la description (24/01/2025)

#### 22/01/2025 bêta63

- Correction d'une erreur de syntaxe PHP qui empêchait le nettoyage des fichiers obsolètes

#### 03/01/2025 bêta62

- Petite modification pratique et purement esthétique : l'ID de l'équipement est affiché dans l'onglet

#### 19/12/2024 bêta61

- Un test d'égalité ou de différence avec une valeur (ou une chaine de caractères) est maintenant possible pour une commande info de sous-type binaire qui lit un registre (merci ludoviclt)

#### 07/12/2024 bêta60

- Correction d'une erreur qui empêchait l'import des commandes de lecture de plage de registres lors de l'utilisation d'un template (merci ludoviclt)

#### 09/11/2024 bêta59

- Vérification que la plage de registres source soit définie (merci ludoviclt)
- Vérification de la version des modules installés

### 07/11/2024 versions stable et bêta sans modification de version

- Mise à jour du lien vers la documentation

Explications : [https://community.jeedom.com/t/evolutions-du-plugin-mymodbus-version-stable/133443](https://community.jeedom.com/t/evolutions-du-plugin-mymodbus-version-stable/133443)

### V3.0 bêta

#### 05/11/2024 bêta58

- Cas particulier d'extraction d'un bit de registre dans une plage de registres (merci Doud)

#### 03/11/2024 bêta57

- Outil de déplacement des commandes d'un équipement à un autre afin de garder les commandes lors d'un split d'équipement en
cas d'utilisation de la même interface

#### 30/10/2024 bêta56

- Correction sur les fonctions d'écriture

#### 25/10/2024 bêta55

> :warning: ***Important***  
> Une réinstallation des dépendances doit être faite sans quoi le démon MyModbus ne fonctionnera pas.  
> Elle est lancée automatiquement après la mise à jour du plugin.

- Utilisation de pymodbus V3.7.4

#### 24/10/2024 bêta54

- Forçage de la version de pymodbus à 3.7.3

#### 16/10/2024 bêta53

- Mise à jour de jeedomdaemon (il faut relancer l'installation des dépendances)

#### 07/10/2024 bêta52

- Nouveauté : inversion des doubles-mots possible
- Nouveauté : affichage de la configuration d'inversion en fonction du type de donnée

#### 05/10/2024 bêta51

- Nouveauté : utilisation de la même interface pour plusieurs équipements
- Nouveauté : ajout d'une commande info 'Polling' qui contient le temps de polling recalculé actuel (si la commande n'existe pas,
sauvegardez l'équipement)
- Correction : la commande "Cycle OK" est mise à 0 dès qu'une erreur se produit et est mise à 1 dès qu'un cycle complet (lecture
de toutes les commandes info) s'est déroulé sans erreur
- Correction du mode "Sur événement" qui pouvait ne pas réagir à la commande "Rafraîchir"
- Correction du mode "Sur événement" qui rajoutait une boucle de lecture à chaque rafraîchissement
- En mode "Sur événement", suppression des tâches run_loop "done"
- Amélioration de la gestion de la connexion
- Amélioration de la gestion d'une nouvelle configuration
- Structure du démon : la classe MyModbusConfig est écrite dans un fichier dédié
- [ESSAI] Suppression effective de l'ancien répertoire 'ressources' (avec 2 S) qui n'est plus utilisé

#### 26/09/2024 bêta50

- Si les valeurs saisies dans la configuration commencent ou se terminent par des espaces, ceux-ci sont ignorés
- Le polling n'est plus recalculé en cas d'erreur durant le cycle

#### 25/09/2024 bêta49

- Correction de l'erreur de syntaxe qui bloquait les écritures (merci wocha-fr)

#### 24/09/2024 bêta48

- Correction de la fonction eqLogic.getDeamonLaunchable (merci wocha-fr)
- Correction du type d'un index de dictionnaire (merci wocha-fr)
- Corrections de syntaxe (merci thomaspascal, Droopy et lperenna)
- [ESSAI] Gestion correcte d'un temps d'attente après erreur plus long (quelques minutes)

#### 23/09/2024 bêta47

> :warning: ***Important***  
> A partir de cette version, l'inversion des mots ne sera plus nécessaire si l'architecture du CPU est identique entre
l'appareil et votre machine Jeedom. La logique a été inversée dans le module pymodbus, alors j'ai fait des fonctions à ma sauce.
Cela affecte les commandes info et action sur des variables d'au moins 32 bits.
> Veillez à bien vérifier votre configuration avant et à faire les adaptations nécessaires.

- Gestion interne du boutisme (endianess) et non plus via pymodbus
- Suppression du double log en cas d'erreur de lecture

#### 22/09/2024 bêta46

- Vérification que la commande existe bien lorsqu'un changement de valeur est reçu pour éviter une erreur (merci thomaspascal)
- Affichage du bouton "Supprimer" dans le viewer de template (merci thomaspascal)
- Corrections pour les connexions série (merci wocha-fr)

#### 20/09/2024 bêta45

- Correction du problème avec les templates
- Correction du problème avec l'ordre des mots d'une valeurs sur plus de 32 bits dans une plage de registres lorsque l'offset
dans la plage de registres est impaire
- Correction de la prise en charge du paramètre "port" pour les liaisons série

#### 19/09/2024 bêta44

- Prise en compte de la configuration d'inversion des octets et des mots pour les valeurs lues depuis une plage de registres
(merci thomaspascal)

#### 18/09/2024 bêta43

- Optimisation du verrou qui permet les requêtes afin que les écritures puissent être faites plus rapidement
- Vérification de l'état de la connexion avant chaque requête
- Le polling peut être configuré à 0.01s minimum
- Reprise de l'ancienne configuration du format de données pour les commandes action également
- Le démon n'est pas "launchable" si le venv n'est pas présent
- Suppression de l'ancien répertoire mal orthographié "ressources" (avec 2 S)

#### 17/09/2024 bêta42

> :warning: ***Important***  
> 1. Avant de faire cette mise à jour, désactivez les équipements MyModbus. Faites une capture de la configuration des équipements
et des commandes. Après la mise à jour, **sauvegardez les équipements sans les activer**. Vérifiez bien la configuration des
commandes.
> 2. Si des commandes dont l'adresse d'esclave vaut 0 ne fonctionnent plus après la mise à jour, il faut passer cette valeur à 1.
Il s'agit de la valeur par défaut depuis pymodbus v3.7.0. Si les erreurs persistent, recherchez quelle est la valeur à renseigner
dans la documentation constructeur.

- Réécriture complète du démon :
  - Utilisation de bibliothèques de dev tiers pour Jeedom (jeedomdaemon, dependance.lib, pyenv.lib) (merci Mips, nebz et TiTiDom)
  - Utilisation de pymodbus V3.7.2 (à ce jour)
  - Abandon de la dépendance avec pyenv4Jeedom
  - Abandon de BinaryPayloadBuilder et BinaryPayloadDecoder appelés à disparaître du module pymodbus (dès 3.8.0 pas encore sortie)
  - Ajout des paramètres d'équipement :
    - Timeout pour la connexion
    - Nombre de tentatives en cas d'erreur de lecture
    - Temps d'attente après une erreur de lecture pour éviter d'enchainer les erreurs pour la même raison
  - Structure des appels des sous-classes pymodbus.ModbusRequest inspirée de l'intégration Modbus de Home-Assistant
  - Ajout de la commande info `Cycle OK` qui est mise à 1 si le dernier cycle de lecture s'est déroulé sans erreur, sinon 0. Cette
  commande peut être surveillée. Si elle passe à 0, c'est qu'il y a eu un problème durant le dernier cycle de lecture
  - Il n'est plus possible de modifier le niveau de log à la volée, il faut redémarrer le démon
- Page de configuration de l'équipement :
  - Plus rapide : sans appels ajax à des pages php locales
  - Le bouton 'Ajouter une commande' est flottant (merci noodom), le bouton en bas de page est supprimé
- Suppression du format bit inversé qui ne fonctionnait pas et qui est facile à mettre en place (`1 - #value#`)
- Suppression des formats int8, seuls les formats uint8 sont gardés
- Suppression du format float16
- Prise en compte de l'inversion des octets et des mots pour les chaînes de caractères

#### 17/06/2024 bêta41

- Correction d'une erreur de syntaxe (merci m.georgein)
- Lors de l'exécution d'une commande action, il faut vérifier si l'équipement est actif avant d'envoyer la commande au démon

#### 03/05/2024 bêta40

- Correction de syntaxe sur des messages de log du démon (merci à Jean-Baptiste)

#### 15/04/2024 bêta39

- Correction de l'utilisation de la fonction `strtolower` (merci à Jean-Baptiste)

#### 14/03/2024 bêta38

- Logs un peu plus détaillés en mode debug

#### 11/03/2024 bêta37

- Amélioration de l'interaction avec pyenv

#### 08/03/2024 bêta36

- Amélioration de l'interaction avec pyenv

#### 06/03/2024 bêta35

- Initialisation de pyenv

#### 04/03/2024 bêta34

- Externalisation de pyenv dans un plugin dédié
- Suppression du bouton dans la configuration du plugin pour supprimer le répertoire ressources/_pyenv

#### 21/02/2024 bêta33

- Ajout d'un bouton dans la configuration du plugin pour supprimer le répertoire ressources/_pyenv
- Affichage de toute la config dans le visualisateur de template
- Possibilité d'utiliser #value# dans le champ valeur d'une commande action pour faire référence à la valeur de la commande info liée

#### 17/02/2024 bêta32

- Correction pour que '0' puisse être écrit (merci à Doud)

#### 16/02/2024 bêta31

- Suppression du mode bi-maître qui ne fonctionne pas
- Lors de la sauvegarde, si rien n'est précisé dans le champ valeur, définir avec `#slider#`, `#select#` ou `#color#` en fonction du cas, sinon invalider la config
- Lors de la sauvegarde si `#slider#`, `#select#` ou `#color#`, en fonction du cas, n'est pas dans le champ valeur, avertir avec une erreur.
- Invalider l'exécution d'une commande action si la valeur à écrire est vide

#### 14/02/2024 bêta30 (mise à jour de la St Valentin)

- Le champ valeur est sauvegardé correctement

#### 12/02/2024 bêta29

- Ajout de la gestion de templates (documentation à mettre à jour)  
Cette fonctionnalité est basée sur ce qui existe dans jMQTT
- Révision du bandeau de menu de la configuration du plugin (page d'ajout des équipements)
- Corrections de syntaxe

#### 09/01/2024 bêta28

- Correction du script post-install.sh pour mettre à jour pyenv même après la restauration d'un backup de Jeedom (merci à m.georgein)

#### 03/12/2023 bêta27

- Correction du script post-install.sh pour mettre à jour pyenv correctement avant d'installer python V3.11.6

#### 28/11/2023 bêta26

- Correction du script post-install.sh pour mettre à jour pyenv avant d'installer python V3.11.6 (merci ngm47)

#### 26/11/2023 bêta25

- Liste des paquets à installer réduite au minimum
- Passage à python V3.11.6 sous pyenv. L'étape de réinstallation des dépendances va durer plusieurs dizaines de minutes.
- Retour arrière sur une modification de la version bêta24 : le fait que le démon soit "launchable" si plusieurs équipements utilisent le même port série
- Mise à jour de la documentation
- Ajout de la possibilité de personnaliser les interfaces série (idée de jmcaous trouvée sur le Community)

#### 08/11/2023 bêta24

- Correction erreur 500 à la sauvegarde d'un nouvel équipement (merci ksin)
- Le démon est "launchable" si plusieurs équipements utilisent le même port série. Dans ce cas, c'est à l'utilisateur de configurer le plugin correctement (merci indirectement à ksin)
- Petites corrections

#### 02/08/2023 bêta23

- Les listes sont gérées pour les binaires également
- Les couleurs sont prises en compte

#### 14/07/2023 bêta22

- Le bouton d'ajout de commande en bas du tableau des commandes fonctionne dorénavant comme attendu
- Les retours NaN sont correctement gérés

#### 06/06/2023 bêta21

- Forçage de la version pymodbus 3.2.2 pour éviter des erreurs avant de trouver une meilleure solution

#### 10/05/2023 bêta20

- Correction des logs des écritures en mode bi-maître
- Ajout de la commande info liée aux commandes action
- Ajout du bouton de création de commande en fin de tableau

#### 06/05/2023 bêta19

- Deuxième tentative du mode bi-maître spécifique aux chaudières De Dietrich Diematic (merci à loustic03 de m'avoir laissé autant de temps pour tester chez lui)

#### 05/05/2023 bêta18

- Prise en charge des commandes action avec une liste
- Première tentative du mode bi-maître spécifique aux chaudières De Dietrich Diematic
- Affichage de la configuration de l'endianess pour les commandes actions (merci à thomaspascal)
- Indentation du code de tout le plugin avec 2 espaces au lieu de 4

#### 13/04/2023 bêta17

- Pour les commandes binaires depuis une plage de registres, les plages numériques en source sont possibles mais un filtre doit être spécifié (merci à Noyax37)

#### 10/04/2023 bêta16

- Petite correction sur le log lors de l'exécution d'une commande action

#### 09/04/2023 bêta15

- Amélioration de la saisie des commandes an désélectionnant les options invisibles (merci à Noyax37)
- Remontée de la valeur lue vers Jeedom par le démon si la commande est configurée avec "Répéter les valeurs identiques" à "Oui" (merci Bison pour l'astuce)
- Meilleure gestion des exceptions
- Ajout du nom de l'équipement dans les logs du démon (là où c'est possible)

#### 07/04/2023 bêta14

- Les reconnexions automatiques de pymodbus sont désactivées. Les (re)connexions sont gérées par le démon (merci à thomaspascal)
- En cas de sauvegarde de la configuration, le démon se déconnecte avant de prendre la nouvelle configuration en compte (merci à thomaspascal)
- Maintien de l'ordre des commandes lors de la sauvegarde qui rajoute les commandes spéciales (merci à thomaspascal)
- Correction de l'erreur lors de la duplication d'un équipement (merci à Noyax37)
- Suppression des paramètres de configuration utilisés dans l'ancienne version (et donc le retour en version stable est rendu impossible sans restaurer un backup ou resaisir les configurations)

#### 05/04/2023 bêta13

- Contournement de l'erreur d'affichage des paramètres d'équipement (Solution en cours)
- Correction de l'erreur lors de la duplication d'un équipement (merci à Noyax37)
- Démon : si la lecture retourne 'nan', la valeur n'est pas remontée vers Jeedom et une erreur est générée (merci à ced2001)

#### 04/04/2023 bêta12

- Ajout du mode cyclique
- Ajout du mode lecture sur événement
- Le temps de polling minimum est maintenant de 1 seconde
- Mise en place des paramètres d'équipement par défaut
- Migration de la configuration de l'équipement en cas de migration depuis l'ancienne version de MyModbus
- Remontée de la valeur lue vers Jeedom par le démon uniquement en cas de changement de valeur
- Diverses optimisations

#### 29/03/2023 bêta11

- Correction de l'affichage du paramètre "adresse esclave" des commandes action (merci à Noyax37 et à pilou226)

#### 28/03/2023 (0:08) bêta10

- Correction de l'erreur lors de l'écriture d'un binaire (merci à ngm47)
- La pause suite à une commande action est cumulable avec l'écriture de la valeur d'une expression

#### 27/03/2023 (8:57) bêta9

- Passer le niveau de log à la volée en cas de changement sans redémarrer le démon
- Passer les modifications de configuration à la volée lors de la sauvegarde sans redémarrer le démon
- Meilleure gestion de la communication entre le démon et les process PyModbusClient
- Meilleure gestion des arrêts des process
- La valeur des commandes action peut être configurée comme dans le plugin Virtuel
- Seuls les équipements utilisant le protocole de connexion "serial" ne peuvent pas utiliser la même interface.  
Les équipements en TCP ou UDP **peuvent** communiquer avec la même adresse IP, ça ne veut pas dire qu'ils le doivent.

#### 24/03/2023 bêta8

- Correction de la fonction de validation des adresses d'une plage de registres
- Optimisation du temps de traitement des valeurs remontées par le démon
- Gestion de la reconnexion en cas de déconnexion
- Heartbeat entre le démon et Jeedom : un signal envoyé par le démon à Jeedom, si pas de réponse le démon se termine (pour éviter les zombis)
- Permettre un temps d'attente avant la première requête (compatibilité avec Huawei SUN2000)
- Validation de la configuration de sorte que deux équipements ne puissent pas utiliser la même connexion

#### 23/03/2023 bêta7

- Correction d'une erreur lors de la vérification des plages

#### 23/03/2023 bêta6

- Liste déroulante pour le choix de la plage de registres (documentation ok)

#### 21/03/2023 bêta5

- Lecture d'une plage d'adresses en une fois et assignation indirecte des commandes info :
Version avec une configuration permettant une meilleure compatibilité

#### 19/03/2023 bêta4

- Lecture d'une plage d'adresses en une fois et assignation indirecte des commandes info (à documenter)

#### 17/03/2023 bêta3

- Correction du bug qui supprimait toutes les commandes au moment de sauvegarder la configuration d'un équipement

#### 16/03/2023 bêta2

- Correction de l'installation des dépendances
- Logging au niveau paramétré dans Jeedom, même pour le démon
- Ajout de l'ID dans les commandes
- Ecriture au moment où la commande est lancée dans Jeedom et plus à la fin du cycle (polling)
- Possibilité de rajouter un temps d'attente après l'écriture d'une valeur fixe
- Plus d'informations sont loggées en cas d'exception lors des lectures et écritures

#### 10/03/2023 bêta1

- Réécriture complète du plugin afin de gérer un maximum de modes et de formats de données

### V2.3

Toutes les versions antérieures à la version V3.0 ont été développées par Bebel27.

#### 08/03/2023 stable

- Passage de la version beta en stable, il faudra impérativement relancer les dépendances !
- Par sécurité avant de faire la mise à jour, vous pouvez faire un backup de votre installation. 

#### 17/03/2021 V2.2.3 bêta

- ajout options dans la page de configuration pour redémarrer les démons si Nok 

#### 06/03/2021 V2.2.2 bêta

- ajout gestion du rtu (test) 

#### 07/02/2021 V2.2.0 bêta

- ajout gestion des démons 

#### 04/01/2021 V2.1.2 bêta

- ajout écriture multiples registers fonction 16 

#### 28/12/2020 V2.1.1 bêta

- Mise à jour du script d'écriture pour python 3 (version beta)

#### 22/06/2020 V2.1 bêta

- Ajout d'un mode pour la lecture des inputs_registers des compteurs de puissances Eastrom (version beta)

#### 01/06/2020 V2.0 bêta

- Passage en python3 nécessite une mise à jour des dépendances
- Possibilité de filtrer directement des bits dans le plugin, sans passer par des virtuels
- Ajout de la lecture de float et de int en holding register 

### V1.4

#### 09/04/2020 V1.4.stable

- Mise à jour Logo ..... Merci alois.myard pour cette création 

#### 23/03/2020 V1.4.4

- mise à jour page configuration, ajout des équipements en paramètre.

#### 23/03/2020 V1.4.4

- Ajout page santé

#### 21/03/2020 V1.4.3

- Ajout configuration pour automate Wago 

#### 15/03/2020 V1.4.2

- Mise à jour du script des dépendances V1.3

#### 05/03/2020 V1.4.1

- Mise à jour du logo au standard officiel.

#### 23/02/2020 V1.4.0

- Ajout compatibilité Jeedom en V3.3 (suite test fais en V3.3)

### V1.3 et avant

#### 09/02/2020 V1.3.2

- Ajout Python PIP dans le script d'installation des dépendances. (Suite problème remonté sur Community par @hitaki)

#### 03/02/2020 V1.3.1

- Suppression du time out sur la gestion du port de com, car il entrainait des erreurs de lecture

#### 22/01/2020 V1.3

- Résolution du bug sur le retour des valeurs des équipements à IP commune.

#### 18/01/2020 V1.2 bêta

- Découverte d'un bug sur la lecture d'une même ip avec un unit différent. En cours de résolution 
- correction du script d'écriture (ajour de l'unit id) essais sur un automate wago ok  

#### 28/12/2019 V1.1 stable

- passage en stable (demande en cours) 

#### 14/01/2020 V1.2 bêta

- Correction bug sur sauvegarde
- Mise à jour visuel commandes
- Mise en service du NTP pour crouzet à 00h30 si activé
