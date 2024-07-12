# load_balancing_qcm
Answer to the load_balancing module QCM

### Corrigé des Réponses Vrai/Faux avec Justifications et Adaptations (Quelques questions non répondues car pas sûr)

Tout commit est le bienvenue si il y a une erreur dans les réponses ***(respectez le template de réponses)***

1. Le fichier `/etc/systemd/network/brlan.netdev` permet la création de l'interface pont `brlan`.
   - **Vrai**
   - Justification : Le fichier `.netdev` est utilisé pour définir des interfaces réseau virtuelles comme les bridges. Ce fichier est crucial pour la configuration réseau dans les environnements de virtualisation.

2. Le fichier `/etc/resolv.conf` définit les @IP des serveurs DHCP.
   - **Faux**
   - Justification : `/etc/resolv.conf` est utilisé pour configurer les serveurs DNS, pas les serveurs DHCP.

3. La commande `mkinitcpio` permet de générer le chargeur du système de démarrage sous Linux.
   - ** JSP **
   - Justification : 

4. Le fichier XML de configuration d'une VM sous Libvirt permet de définir les @MAC de toutes les interfaces réseau de la VM.
   - **Vrai**
   - Justification : Le fichier XML de Libvirt permet de configurer les adresses MAC des interfaces réseau, ce qui est important pour une configuration réseau statique et stable dans un environnement virtuel.

5. QEMU est un hyperviseur basé sur KVM.
   - **Faux**
   - Justification : QEMU n'est pas un hyperviseur basé sur KVM, mais il peut être utilisé conjointement avec KVM pour fournir une solution complète de virtualisation.

6. Keepalive est un service Linux permettant d'avoir 2 répartiteurs de charge en mode MASTER / MASTER.
   - **Faux**
   - Justification : Keepalived utilise le mode MASTER/BACKUP, pas MASTER/MASTER. Ce mode est crucial pour assurer la haute disponibilité en basculant vers un serveur de secours en cas de panne.

7. La commande PHP suivante permet d'afficher l'@IP du serveur dans une page Web :
   ```php
   echo "Response from " . $_SERVER['SERVER_ADDR'];
   ```
   - **Vrai**
   - Justification : La commande affiche l'adresse IP du serveur web, ce qui peut être utile pour des diagnostics ou pour confirmer la configuration réseau.

8. Tout comme Grub, Extlinux est un système de démarrage sous Linux.
   - **Vrai**
   - Justification : Extlinux est un chargeur de démarrage comme Grub, mais basé sur Syslinux, utilisé souvent pour des configurations simples ou des systèmes embarqués.

9. Le fichier `/etc/systemd/network/brlan.netdev` permet la configuration réseau de l'interface pont `brlan`.
   - **Faux**
   - Justification : La configuration réseau spécifique se fait généralement dans un fichier `.network`.

10. La commande `cryptsetup` permet le chiffrement et le déchiffrement d'une partition.
    - **Vrai**
    - Justification : `Cryptsetup` est utilisé pour configurer et gérer le chiffrement de partitions avec LUKS, essentiel pour la sécurité des données sur les disques.

11. Dans le cas de la répartition de charge par routage direct, il faut ajouter l'@IP du répartiteur de charge aux interfaces LAN de chacun des serveurs.
    - **Faux**
    - Justification : Dans le cas de la répartition de charge par routage direct (Direct Routing), il n'est pas nécessaire d'ajouter l'adresse IP du répartiteur de charge (load balancer) aux interfaces LAN de chacun des serveurs. En fait, cela pourrait causer des problèmes de routage et de réseau.

12. La commande suivante permet d'ajouter une @IP à l'interface eth0 d'une machine Linux :
    ```bash
    prompt ~ # ip addr add 192.168.0.1/24 dev eth1
    ```
    - **Faux**
    - Justification : La commande devrait se référer à `eth0` au lieu de `eth1`.

13. Libvirt est une surcouche à KVM (ainsi qu'à d'autres hyperviseurs) qui permet de faciliter son utilisation grâce à la commande `virsh`.
    - **Vrai**
    - Justification : Libvirt est une surcouche logicielle qui simplifie l'utilisation et la gestion des hyperviseurs, y compris KVM, Xen, QEMU, VMware, Hyper-V et d'autres. Libvirt fournit une interface unifiée et des outils pour gérer les machines virtuelles et les réseaux virtualisés. La commande virsh est un utilitaire en ligne de commande fourni par Libvirt qui permet de gérer ces machines virtuelles de manière simplifiée.

14. La répartition de charge par translation d'adresse nécessite d'accepter cette translation en mettant à jour le fichier `ip_forward` comme suit :
    ```bash
    prompt ~ # echo "0" > /proc/sys/net/ipv4/ip_forward
    ```
    - **Faux**
    - Justification : La valeur devrait être 1 pour activer le transfert d'IP, pas 0.

15. La commande suivante définit le mode de répartition de charge avec l'algorithme Round Robin :
    ```bash
    prompt ~ # ipvsadm -A -t 192.168.1.11:80 -s rr
    ```
    - **Vrai**
    - Justification : Cette commande configure la répartition de charge en utilisant l'algorithme Round Robin, un choix courant pour équilibrer la charge de manière égale entre les serveurs.

16. La modification du nom des interfaces réseaux peut se faire grâce à des règles UDEV dans le fichier `/etc/udev/rules.d/10-network.rules`.
    - **Vrai**
    - Justification : Les règles UDEV permettent de renommer les interfaces réseau de manière flexible, essentiel pour une gestion réseau personnalisée et prévisible.

17. Il est possible de faire de la répartition de charge grâce aux serveurs DNS.
    - **Vrai**
    - Justification : Les DNS peuvent distribuer le trafic en répartissant les requêtes sur plusieurs adresses IP, ce qui est utilisé dans les configurations de haute disponibilité et de charge équilibrée.

18. La commande `modprobe` permet de lancer une capture de trame sur le réseau.
    - **Faux**
    - Justification : `Modprobe` est utilisé pour charger et décharger des modules du noyau, pas pour capturer des trames réseau.

19. Grub est un chargeur de système de démarrage sous Linux.
    - **Vrai**
    - Justification : Grub est un chargeur de démarrage couramment utilisé sous Linux.

20. La commande suivante permet de passer le clavier en AZERTY :
    ```bash
    prompt ~ # loadkeys fr-pc
    ```
    - **Vrai**
    - Justification : Cette commande configure le clavier en AZERTY, essentiel pour une utilisation confortable dans des environnements francophones.

21. La commande suivante enregistre la configuration de `ipvsadm` et la recharge automatiquement après un redémarrage de la machine :
    ```bash
    prompt ~ # ipvsadm-save -n > /usr/local/etc/lvs/lvsnat.conf
    ```
    - **Faux**
    - Justification : La commande ipvsadm-save -n > /usr/local/etc/lvs/lvsnat.conf enregistre effectivement la configuration actuelle d'IPVS dans le fichier spécifié (/usr/local/etc/lvs/lvsnat.conf). Cependant, cette commande seule ne garantit pas que la configuration sera rechargée automatiquement après un redémarrage de la machine..

22. La configuration de `ipvsadm` est persistante après un redémarrage de la machine.
    - **Faux**
    - Justification : La configuration n'est pas persistante par défaut sans un script de rechargement.

23. La commande `ipvsadm` permet l'administration de la couche noyau LVS.
    - **Vrai**
    - Justification : `Ipvsadm` est utilisé pour administrer LVS (Linux Virtual Server), crucial pour la gestion de la répartition de charge.

24. Les deux commandes suivantes affichent la configuration des interfaces réseaux :
    ```bash
    prompt ~ # ip addr
    prompt ~ # ifconfig
    ```
    - **Vrai**
    - Justification : Les deux commandes affichent les informations sur les interfaces réseau, bien que `ifconfig` soit plus ancien.

25. L'alias suivant permet de limiter le temps d'essai d'un ping à 1 seconde :
    ```bash
    alias ping='ping -c 1 '
    ```
    - **Faux**
    - Justification : L'alias limite le nombre de paquets envoyés à 1, pas le temps d'essai.

26. Libvirt doit être démarré en tant que service grâce au démon `libvirtd`.
    - **Vrai**
    - Justification : `Libvirtd` est le démon qui doit être démarré pour utiliser les fonctionnalités de Libvirt.

27. La commande suivante permet d'ajouter des points de montages dans le fichier `/etc/fstab` en faisant référence à l'UUID de chaque partition :
    ```bash
    prompt ~ # genfstab -U -p /mnt >> /etc/fstab
    ```
    - **Vrai**
    - Justification : La commande `genfstab` génère les entrées `fstab` en utilisant les UUID des partitions, crucial pour la persistance des montages après redémarrage.

28. Un script bash de gestion d'un service Linux doit au moins pouvoir prendre en paramètre les options start et stop.
    - **Vrai**
    - Justification : Les scripts de service Linux doivent au minimum gérer les commandes start et stop pour un contrôle basique du service.

29. La répartition de charge par translation d'adresse sollicite moins le répartiteur que la répartition de charge par routage direct.
    - **Faux**
    - Justification : La translation d'adresse peut solliciter davantage le répartiteur à cause de la surcharge de la translation.

30. La couche du noyau Linux qui gère la répartition de charge s'appelle LVS (Linux Virtual Server).
    - **Vrai**
    - Justification : La commande suivante permet de démarrer automatiquement, au démarrage du système, le service de gestion des interfaces réseaux :
    - ```bash
      prompt ~ # systemctl enable systemd-networkd
      ```

31. La commande suivante formate l'image disque myVM.raw avec un système de fichier Windows :
    ```bash
      prompt ~ # mkfs.ext4 -F myVM.raw
    ```
    - **Faux**
    - Justification : La commande mkfs.ext4 formate le disque avec un système de fichiers ext4, qui est un système de fichiers Linux, et non Windows.

32. Keepalive est un service Linux qui peut, entre autre, ajouter une @IP virtuelle au répartiteur de charge.
    - **Faux**
    - Justification : Keepalived est un service Linux utilisé pour la haute disponibilité et la répartition de charge. Il peut gérer des adresses IP virtuelles et est souvent utilisé en conjonction avec des solutions de répartition de charge comme LVS (Linux Virtual Server) pour assurer la haute disponibilité..

33. Le fichier XML de configuration d'une VM sous Libvirt permet de définir les @IP de toutes les interfaces réseau de la VM.
    - **Faux**
    - Justification : Le fichier XML de configuration d'une VM sous Libvirt définit la configuration de la VM, mais ne spécifie pas directement les adresses IP des interfaces réseau. Celles-ci sont généralement configurées au niveau du système d'exploitation invité.

34. La commande fdisk permet, entre autre, de modifier le type d'une partition.
    - **Vrai**
    - Justification : La commande fdisk permet de créer, supprimer, modifier et gérer les partitions sur un disque, y compris le type de partition.

35. La commande suivante diminue l'image disque myVM.raw de 4Go :
    ```bash
    prompt ~ # fallocate -l 4G myVM.raw
    ```
    - **Faux**
    - Justification : La commande fdisk permet de créer, supprimer, modifier et gérer les partitions sur un disque, y compris le type de partition.

36. Keepalive monitore l'état des serveurs grâce à l'envoi d'un ping qui sert de battement de cœur.
    - **Faux**
    - Justification : Keepalived est un logiciel utilisé pour la haute disponibilité et la répartition de charge, souvent en conjonction avec LVS (Linux Virtual Server). Bien que Keepalived utilise le protocole VRRP (Virtual Router Redundancy Protocol) pour la gestion des adresses IP virtuelles et le basculement, il ne se contente pas d'envoyer des pings comme mécanisme de battement de cœur (heartbeat) pour surveiller l'état des serveurs..

37. Le fichier /etc/systemd/network/brlan.network permet le configuration réseau de l'interface pont brlan.
    - **Vrai**
    - Justification : Le fichier /etc/systemd/network/brlan.network est utilisé pour configurer les interfaces réseau lorsqu'on utilise systemd-networkd pour gérer le réseau sous Linux.

38. La commande suivante permet la création d'une machine virtuelle de manière persistante dans Libvirt (elle sera toujours visible après son extinction) :
    ```bash
    prompt ~ # virsh create myVM.xml
    ```
    - **Faux**
    - Justification : La commande virsh create myVM.xml crée et démarre une machine virtuelle à partir du fichier de configuration, mais elle n'est pas persistante (elle disparaît après l'arrêt). Pour créer une VM de manière persistante, il faut utiliser virsh define myVM.xml.

39. La commande suivante permet de lister toutes les machines virtuelles, même celles qui ne sont pas démarrées :
    ```bash
    prompt ~ # virsh list
    ```
    - **Faux**
    - Justification : La commande virsh list sans options ne liste que les machines virtuelles en cours d'exécution. Pour lister toutes les machines, même celles qui sont arrêtées, il faut utiliser virsh list --all.

40. La commande suivante permet de démarrer automatiquement, au démarrage du système, le service de gestion des interfaces réseaux :
    ```bash
    prompt ~ # systemctl enable systemd-networkd
    ```
    - **Vrai**
    - Justification : Cette commande crée des liens symboliques dans les répertoires d'activation des services au démarrage, assurant ainsi que systemd-networkd soit démarré automatiquement lors du boot du système.
