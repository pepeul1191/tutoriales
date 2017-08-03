# Acceso Remoto a MySQL y MongoDB

Con esto será posible que un host remoto se comunique con una de las bases de datos mencionadas las cuales se deberán encontrar en un servidor Ubuntu 16.04.

#### MySQL

Cambiar bind-address a de 127.0.0.0 a 0.0.0.0

    $ sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
    > bind-address = 127.0.0.1

Reiniciar el servidor MySQL

    $ sudo service mysql restart
    
Entrar por un cliente MySQL al servidor y añadir el host, con su respetivo usuario y contraseña (ip 192.168.1.100 deberá ser reemplazada por la IP del host que solicitará la conexión remota):

    $ mysql -u root -p
    > CREATE USER 'username'@'192.168.1.100' IDENTIFIED BY 'password';
    > GRANT ALL PRIVILEGES ON * . * TO 'username'@'192.168.1.100';

Agregar a las reglas del firewall que permita conecciones del host remoto por el puerto 3306

    $ sudo ufw allow 3306
    
#### MongoDB
    
Agregar en bind-address la IP del servidor

    $ sudo nano /etc/mongod.conf
    > bind_ip = 127.0.0.1,192.168.161.100

Reiniciar el servidor MongoDB

    $ sudo service mongod restart
    
Agregar a las reglas del firewall que permita conecciones del host remoto por el puerto 27017

    $ sudo ufw allow from 192.168.255.255
    $ sudo ufw allow 27017/tcp
    
#### Fuentes

+ http://www.configserverfirewall.com/ubuntu-linux/enable-mysql-remote-access-ubuntu/
+ https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql
+ https://www.mkyong.com/mongodb/mongodb-allow-remote-access/
+ https://www.digitalocean.com/community/tutorials/how-to-setup-a-firewall-with-ufw-on-an-ubuntu-and-debian-cloud-server
+ https://stackoverflow.com/questions/15663001/remote-connections-mysql-ubuntu