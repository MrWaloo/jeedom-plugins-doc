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
- Série
- TCP
- RTU over TCP
- UDP
- Utilisant l'interface d'un autre équipement

Les commandes correspondent aux registres du serveur Modbus.

## La connexion de l'équipement

Il ne peut pas y avoir plusieurs équipements de type TCP ou RTU over TCP paramétrés sur le même port.  
Il ne peut pas y avoir plusieurs équipements de type UDP paramétrés sur le même port. Par contre ils peuvent être
paramétrés sur le même port qu'un équipement TCP ou RTU over TCP.  
Il ne peut pas y avoir plusieurs équipements de type série utilisant la même interface série.

Afin d'éviter les virtuels, il est possible de scinder un équipement en deux (ou plus) :
- un équipement A configuré normalement
- les équipements B et C qui utilisent la configuration d'interface de l'équipement A

Ceci peut être pratique pour regrouper les commandes avec un même device ID sans passer par un virtuel.

## Configuration d'un équipement MyModbus-Server

Les paramètres de base d'un équipement MyModbus-Server sont :
- le protocole de connexion à sélectionner parmis :
  - Série
  - TCP
  - RTU over TCP
  - UDP
  - Utilisant l'interface d'un autre équipement

- l'ID de tous les registres

Si tous les registres du serveur Modbus doivent appartenir au même device-id, vous pouvez renseigner cet ID ici. Si ce
n'est pas le cas, vous pouvez laisser ce champs vide et renseigner l'ID pour chaque commande.

- Ignore les ID inexistants

Afin de ne pas générer d'erreur, si une requête Modbus reçue interroge un ID non configuré, cette requête sera ignorée
si cette option est active.

- Autoriser le broadcast

Dans le protocole Modbus, il est possible d'interroger tous les ID d'un serveur Modbus en utilisant l'ID 0. Certains
appareils utilisent l'ID 0 comme ID par défaut et donc pas comme ID de protocole dédié à une requête broadcast.  
En activant cette option, vous définissez que l'ID 0 est l'ID de broadcast, le serveur Modbus ne prendra donc pas en
compte les registres configurés avec l'ID 0.

***

# En cas de problème

En cas de problème d'utilisation du plugin, vous pouvez poster sur le
[community de Jeedom](https://community.jeedom.com/).