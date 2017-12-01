## Ubuntu Server 16.04

Gestionar las interfaces de red:

    $ sudo nano /etc/network/interfaces
    

    # The loopback network interface
    auto lo
    iface lo inet loopback

    # The primary network interface
    # This is an autoconfigured IPv6 interface
    auto enp0s8
    iface enp0s8 inet dhcp

    auto enp0s3
    iface enp0s3 inet dhcp

Apagar las interfaces de red:

    $ sudo /etc/init.d/networking stop
    
Prender las interfaces de red:

    $ sudo /etc/init.d/networking start
    
Mostar las interfaces de red disponibles:
    
    $ ip link show
    
--- 

Fuentes
    
+ https://askubuntu.com/questions/76065/how-do-i-configure-two-network-adapters-in-ubuntu-server
+ https://askubuntu.com/questions/425859/how-to-list-installed-network-cards-in-ubuntu-using-terminal