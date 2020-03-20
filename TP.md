# TP1 Configuration réseau

## Plan d'adressage :

Interfaces d'administration :
* ESXi1 : 10.X.0.2
* ESXi2 : 10.X.0.3
* ESXi3 (si dispo) : 10.X.0.4
* vCenter : 10.X.0.10


Réseau vMotion
* ESXi1 : 10.X.**1**.2
* ESXi2 : 10.X.**1**.3
* ESXi3 (si dispo) : 10.X.**1**.4


Réseau stockage NFS
* ESXi1 : 10.X.**2**.2
* ESXi2 : 10.X.**2**.3
* ESXi3 (si dispo) : 10.X.**2**.4
* vCenter : 10.X.**2**.10


Réseau VM :
* VM1 : 10.X.**3**.2
* VM2 : 10.X.**3**.3
* VM3 (si 3 ESXi) : 10.X.**3**.3


## Situation de départ

Nous partons de la suiation suivante :
* l'hyperviseur possède 2 cartes réseaux
* la première carte réseau (**uplink**) est connectée au vSwitch0
* il y a un **port group** "VM network" qui est positionné sur le vSwitch0
* il y a un **port group** nommé "Management network"
* il y a un **VMkernel** "vmk0" avec le rôle de "management", qui utilise le **portgroup** "Management Network". Ce VMkernel pour l'IP d'administration de l'ESXi (**rôle** "management") 

## Objectif
* Créer un nouveau **vSwitch** nommé "vSwitch1"
* Rattacher le deuxiéme **uplink** sur ce nouveau **vSwitch**
# TP1 Configuration réseau

## Plan d'adressage :

Interfaces d'administration :
* ESXi1 : 10.X.0.2
* ESXi2 : 10.X.0.3
* ESXi3 (si dispo) : 10.X.0.4
* vCenter : 10.X.0.10


Réseau vMotion
* ESXi1 : 10.X.**1**.2
* ESXi2 : 10.X.**1**.3
* ESXi3 (si dispo) : 10.X.**1**.4


Réseau stockage NFS
* ESXi1 : 10.X.**2**.2
* ESXi2 : 10.X.**2**.3
* ESXi3 (si dispo) : 10.X.**2**.4
* vCenter : 10.X.**2**.10


Réseau VM :
* VM1 : 10.X.**3**.2
* VM2 : 10.X.**3**.3
* VM3 (si 3 ESXi) : 10.X.**3**.3


## Situation de départ

Nous partons de la suiation suivante :
* l'hyperviseur possède 2 cartes réseaux
* la première carte réseau (**uplink**) est connectée au vSwitch0
* il y a un **port group** "VM network" qui est positionné sur le vSwitch0
* il y a un **port group** nommé "Management network"
* il y a un **VMkernel** "vmk0" avec le rôle de "management", qui utilise le **portgroup** "Management Network". Ce VMkernel pour l'IP d'administration de l'ESXi (**rôle** "management") 

## Objectif
* Créer un nouveau **vSwitch** nommé "vSwitch1"
* Rattacher le deuxiéme **uplink** sur ce nouveau **vSwitch**
* Créer un **portgroup** nommé "vMotion" sur le **vSwitch** "vSwitch0
* Créer un **portgroup** nommé "NFS" sur le **vSwitch** "vSwitch0
* Supprimer le **portgroup** sur le "vSwitch0" nommé "VM network"
* Créer un **portgroup** "VM Network" sur le "vSwitch1"
