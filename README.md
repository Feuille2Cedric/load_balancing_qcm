# load_balancing_qcm
Answer to the load_balancing module QCM

### Corrigé des Réponses Vrai/Faux avec Justifications et Adaptations

1. Le fichier `/etc/systemd/network/brlan.netdev` permet la création de l'interface pont `brlan`.
   - **Vrai**
   - Justification : Le fichier `.netdev` est utilisé pour définir des interfaces réseau virtuelles comme les bridges. Ce fichier est crucial pour la configuration réseau dans les environnements de virtualisation.

2. Le fichier `/etc/resolv.conf` définit les @IP des serveurs DHCP.
   - **Faux**
   - Justification : `/etc/resolv.conf` est utilisé pour configurer les serveurs DNS, pas les serveurs DHCP.

3. La commande `mkinitcpio` permet de générer le chargeur du système de démarrage sous Linux.
   - **Faux**
   - Justification : `mkinitcpio` est utilisé pour générer un initramfs, pas pour créer un chargeur de démarrage. La commande est essentielle pour la configuration correcte du démarrage sur un système Arch Linux.

4. Le fichier XML de configuration d'une VM sous Libvirt permet de définir les @MAC de toutes les interfaces réseau de la VM.
   - **Vrai**
   - Justification : Le fichier XML de Libvirt permet de configurer les adresses MAC des interfaces réseau, ce qui est important pour une configuration réseau statique et stable dans un environnement virtuel.

5. QEMU est un hyperviseur basé sur KVM.
   - **Vrai**
   - Justification : QEMU peut utiliser KVM pour la virtualisation matérielle, permettant une performance proche de celle du matériel natif pour les VMs.

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
    - **Vrai**
    - Justification : En répartition de charge par routage direct, les serveurs doivent accepter les requêtes destinées à l'adresse IP du répartiteur, ce qui est crucial pour la configuration correcte des clusters de serveurs.

12. La commande suivante permet d'ajouter une @IP à l'interface eth0 d'une machine Linux :
    ```bash
    prompt ~ # ip addr add 192.168.0.1/24 dev eth1
    ```
    - **Faux**
    - Justification : La commande devrait se référer à `eth0` au lieu de `eth1`.

13. Libvirt est une surcouche à KVM (ainsi qu'à d'autres hyperviseurs) qui permet de faciliter son utilisation grâce à la commande `virsh`.
    - **Vrai**
    - Justification : Libvirt facilite la gestion des hyperviseurs comme KVM via des commandes comme `virsh`, rendant la gestion des machines virtuelles plus simple et efficace.

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
    - **Vrai**
    - Justification : La commande enregistre la configuration, mais un script supplémentaire est nécessaire pour recharger la configuration après un redémarrage.

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
    - **V
