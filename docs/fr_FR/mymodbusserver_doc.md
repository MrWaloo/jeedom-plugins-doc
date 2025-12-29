# Plugin MyModBus-Server

Le plugin MyModbus-Server permet d'intégrer des serveurs Modbus dans Jeedom. MyModBus-Server est un serveur Modbus
capable de communiquer en :
- Ethernet TCP standard ou RTU
- Ethernet UDP
- Série RTU

> :warning: ***Important***  
> Ce plugin est destiné à des utilisateurs avertis et ayant des notions du protocole Modbus.  
> Avant d'installer ce plugin, soyez certain de vous être documenté correctement sur le Modbus et sur ce plugin et de
> tout avoir parfaitement compris.

A la fin de cette page se trouvent les instructions à respecter pour poser une question sur le
[community de Jeedom](https://community.jeedom.com/).

***

# Configuration de MyModbus-Server

## Les principes du plugin

Un équipement correspond à un serveur Modbus qui peut être de cinq types :
- TCP
- RTU over TCP
- UDP
- Série
- Utilisant l'interface d'un autre équipement

Les commandes correspondent aux registres du serveur Modbus.

### La connexion de l'équipement

Il ne peut pas y avoir plusieurs équipements de type TCP ou RTU over TCP paramétrés sur le même port.  
Il ne peut pas y avoir plusieurs équipements de type UDP paramétrés sur le même port. Par contre ils peuvent être
paramétrés sur le même port qu'un équipement TCP ou RTU over TCP.  
Il ne peut pas y avoir plusieurs équipements de type série utilisant la même interface série.

Afin d'éviter les virtuels, il est possible de scinder un équipement en deux (ou plus) :
- un équipement A configuré normalement
- les équipements B et C qui utilisent la configuration d'interface de l'équipement A

Ceci peut être pratique pour regrouper les commandes avec un même device ID sans passer par un virtuel.

### Les commandes

Dans MyModbus-Server les registres du serveur Modbus sont représentés par les commandes action. Afin d'être en mesure
de visualiser les valeurs courantes des commandes, les valeurs des commandes action sont visualisables dans un onglet
dédié.  
Le fait d'utiliser des commandes action et non pas des commandes info permet de déclencher une mise à jour du registre
du serveur Modbus au moment d'un changement de valeur.  
L'onglet dédié qui fourni la valeur courante des registres affiche des commandes info qui sont l'image des commandes
action. Ces commandes ne sont pas configurables puisque potentiellement supprimées et recréées lors de la sauvegarde de
l'équipement.


***

# En cas de problème

En cas de problème d'utilisation du plugin, vous pouvez poster sur le
[community de Jeedom](https://community.jeedom.com/).