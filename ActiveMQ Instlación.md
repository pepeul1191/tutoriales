# INSTALACIÓN ActiveMQ

#### 1) Descargar el bin de ActiveMQ

Lo descargamos del siguiente enlace <br>
https://repository.apache.org/content/repositories/snapshots/org/apache/activemq/apache-activemq/5.10-SNAPSHOT/

#### 2) Descomprimir descarga

Descomprimimos la descarga en un directorio por cualquier el método siempre y cuando tenga los permisos ???. Es opcional cambiar el nombre de la carpeta descomprimida.

### 3) Arrancar servicio

$ cd {ruta de la carpeta del paso anterior}
$ cd bin
$ ./activemq console

### 4) Probar sevicio

En la consola nos aparecerá la url donde podemos ver la ubicación del servicio. <br>
Probamos esta url en un explorador web.

### 5) Entrar al panel de administración
Usamos la siguiente url : {url_activemq}/admin/ <br>
El usuario por default es "admin" y la contraseña por default es "admin".

### 6) Crear en Eclipse un proyecto Maven
Entramos a Eclipse 

### 7) Maven Compiler Level

Del siguiente enlace extraemos el código mostrado : <br>
https://maven.apache.org/plugins/maven-compiler-plugin/examples/set-compiler-source-and-target.html <br>
Y lo copiamos el 'build' y lo pegamos en el pom.xml

### 8) Añadimos las dependencias de ActiveMQ en Maven

activemq all

### 9) Añadimos una clase

En src/main/java llamada ActiveMQQueueSender

Fuentes: <br>
http://activemq.apache.org/getting-started.html <br>
http://blog.gigavoice.com/asynchronous-processing-with-php/ <br>