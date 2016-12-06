# Instalación Apache Tomcat

---

Cambiamos a la carpeta donde tenemos descargado el archivo a instalar.

    $ cd /home/sistemas/Documentos/programas 

Descomprimimos el paquete donde se encuentra el servidor de aplicaciones.

    $ sudo tar xvf apache-tomcat-8.0.24.tar.gz 
    
Movemos los archivos que descomprimimos a la carpeta que creamos.

    $ sudo mv apache-tomcat-8.0.24 /opt/tomcat

Cambiamos a la carpeta donde se encuentra lo desempaquetado.

    $ cd /opt/tomcat

Editamos las variables de entro del Tomcat.

    $ sudo nano ~/.bashrc 
>export JAVA_HOME=/usr/lib/jvm/default-java/
export CATALINA_HOME=/opt/tomcat/

Reiniciamos el bash para que las variables creadas puedan ser usadas en el resto de la instalación.

    $ . ~/.bashrc 

Le otorgamos los permisos de ejecución a la instrucción de inicio del servidor.

    $ sudo chmod +x $CATALINA_HOME/bin/startup.sh 

Le otorgamos los permisos de ejecución a la instrucción de apagado del servidor.

    $ sudo chmod +x $CATALINA_HOME/bin/shutdown.sh 
    
Le otorgamos los permisos de ejecución a catalina.sh.

    $ sudo chmod +x $CATALINA_HOME/bin/catalina.sh 

Configuramos la cuenta de usuario del servidor Tomcat añadiendo lo siguiente al final del documento, pero dentro de las etiquetas tomcat-users

    $ sudo nano $CATALINA_HOME/conf/tomcat-users.xml 

    <role rolename="manager-gui"/>
    <role rolename="manager-script"/>
    <role rolename="manager-jmx"/>
    <role rolename="manager-status"/>
    <role rolename="admin-gui"/>
    <role rolename="admin-script"/>
    <user username="tomcat" password="tomcat" roles="manager-gui,manager-script,manager-jmx,manager-status,admin-gui,admin-script"/>

Otrogamos permisos a los archivos del servidor Tomcat para que cuando usemos este servidor con Netbeans, sea posible leer y usar el archivo de configuración del servidor Tomcat (server.xml).

    $ sudo chmod -R 777 /opt/tomcat/ 
    $ sudo $CATALINA_HOME/bin/shutdown.sh
    $ sudo $CATALINA_HOME/bin/startup.sh Reiniciamos el servidor Tomcat para luego ya poder usarlo.

---

#### Fuente

+ https://www.howtoforge.com/tomcat-on-ubuntu-14.04-install
+ https://www.digitalocean.com/community/tutorials/how-to-install-apache-tomcat-8-on-ubuntu-14-04