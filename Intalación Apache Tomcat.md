### Instalación de Tomcat

Crear usuario de tomcat:

    $ sudo groupadd tomcat
    $ sudo useradd -s /bin/false -g tomcat -d /opt/tomcat tomcat

Instalar Tomcat:

    $ wget http://apache.mirrors.ionfish.org/tomcat/tomcat-8/v8.0.50/bin/apache-tomcat-8.0.50.tar.gz
    $ sudo mkdir /opt/tomcat
    $ sudo tar xzvf apache-tomcat-8*tar.gz -C /opt/tomcat --strip-components=1

Actualizar permisos:

    $ cd /opt/tomcat
    $ sudo chgrp -R tomcat /opt/tomcat
    $ sudo chmod -R g+r conf
    $ sudo chmod g+x conf
    $ sudo chown -R tomcat webapps/ work/ temp/ logs/

Crear archivo systemd:

El siguiente código nos dirá las alternativas de JDKs instaladas:

    $ sudo update-java-alternatives -l
    >> Output 
    java-8-oracle                  1081       /usr/lib/jvm/java-8-oracle
    $ echo $JAVA_HOME
    >> Output
    /usr/lib/jvm/java-8-oracle

Pegar el siguiente código en el archivo '/etc/systemd/system/tomcat.service', siendo el valor de 'Environment=JAVA_HOME=' el del Output de $JAVA_HOME:

```
[Unit]
Description=Apache Tomcat Web Application Container
After=network.target

[Service]
Type=forking

Environment=JAVA_HOME=/usr/lib/jvm/java-8-oracle/jre
Environment=CATALINA_PID=/opt/tomcat/temp/tomcat.pid
Environment=CATALINA_HOME=/opt/tomcat
Environment=CATALINA_BASE=/opt/tomcat
Environment='CATALINA_OPTS=-Xms512M -Xmx1024M -server -XX:+UseParallelGC'
Environment='JAVA_OPTS=-Djava.awt.headless=true -Djava.security.egd=file:/dev/./urandom'

ExecStart=/opt/tomcat/bin/startup.sh
ExecStop=/opt/tomcat/bin/shutdown.sh

User=tomcat
Group=tomcat
UMask=0007
RestartSec=10
Restart=always

[Install]
WantedBy=multi-user.target
```

Luego de cerrar el archivo reiniciar el servicio:

    $ sudo systemctl daemon-reload
    $ sudo systemctl start tomcat
    $ sudo systemctl status tomcat

Modificar los usuarios del servidor de aplicaciones están en el archivo '/opt/tomcat/conf/tomcat-users.xml':

```
<tomcat-users . . .>
    <user username="admin" password="password" roles="manager-gui,admin-gui"/>
</tomcat-users>
```

Cambiar el puerto por default es haciendo el siguiente cambio en el archivo '/opt/tomcat/conf/server.xml':

```
<Connector connectionTimeout="20000" port="8080" protocol="HTTP/1.1" redirectPort="8443"/>
```

--- 

Fuentes

+ https://www.digitalocean.com/community/tutorials/how-to-install-apache-tomcat-8-on-ubuntu-16-04