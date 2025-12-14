# Plugin MyModBus-Server

Le plugin MyModBus-Server permet d'intégrer des serveurs Modbus dans Jeedom. MyModBus-Server est un serveur Modbus
capable de communiquer en :
- Ethernet TCP standard ou RTU
- Ethernet UDP
- Série en mode ASCII ou RTU

> :warning: ***Important***  
> Ce plugin est destiné à des utilisateurs avertis et ayant des notions du protocole Modbus.

A la fin de cette page se trouvent les instructions à respecter pour poser une question sur le
[community de Jeedom](https://community.jeedom.com/).

***

# Configuration de MyModbus-Server

## Le principe

Un équipement correspond à un serveur Modbus qui peut être de trois type :
- Ethernet TCP
- Ethernet UDP
- Série

Pour les types Ethernet TCP ou UDP, il ne peut pas y avoir plusieurs équipements paramétrés sur le même port.  
Pour le type Série, il ne peut pas y avoir plusieurs équipements utilisant la même interface série.

Afin d'éviter les virtuels, il est possible de scinder un équipement en deux (ou plus) :
- un équipement A configuré normalement
- les équipements B et C qui utilisent la configuration de l'équipement A

Ceci peut être pratique pour regrouper les commandes avec un même device ID sans passer par des virtuels.

Dans MyModbus-Server les registres du serveur Modbus sont représentés par les commandes action. Afin d'être en mesure
de visualiser les valeurs courantes des commandes, les valeurs des commandes action sont visualisables dans un onglet
dédié.

