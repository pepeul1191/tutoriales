# Instalación Eclipse
---
Creamos un directorio llamado eclipse-mars.

    $ sudo mkdir /opt/eclipse-mars 

Creamos un directorio llamado eclipse-mars.

    $ cd /opt/eclipse-mars 

Entramos a la carpeta que hemos creado y descomprimimos el archivo de tar.gz de Eclipse Mars.

    $ sudo tar -zxvf /home/sistemas/Documentos/programas/eclipse-jee-mars-R-linux-gtk-x86_64.tar.gz 

Creamos un acceso directo a la aplicación descomprimida.

    $ sudo nano /usr/share/applications/eclipse-mars.desktop 

>[Desktop Entry]
Name=Eclipse Mars
Type=Application
Exec=/opt/eclipse-mars/eclipse/eclipse
Terminal=false
Icon=/opt/eclipse-mars/eclipse/icon.xpm
Comment=Integrated Development Environment
NoDisplay=false
Categories=Development;IDE;
Name[en]=Eclipse

---

#### Fuente

+ http://ubuntuhandbook.org/index.php/2014/06/install-latest-eclipse-ubuntu-14-04/