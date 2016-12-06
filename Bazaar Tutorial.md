# Tutorial Bazaar 
---

#### Instalación

Para instalar Bazaar usar el siguiente código.

    $ sudo apt-get install bzr
    
Para comprobar la versión de Bazaar usar el siguiente código:
    
    $ bzr --version

#### Cofinguracion Inicial

Definir de manera global al sistema un usuario y correo.

    $ bzr whoami "José Valdivia <jvaldivia@softweb.pe>"
    
#### Crear un Repositorio en Bazaar

Hay que inicializar el repositirio en la máquina dentro de un directorio.

    $ bzr init
    
#### Añadir archivos al commit

Vamos en añadir todo los cambios que hallamos elaborado en nuestro repositorio.

    $ bzr add
    
Para añadir un archivo en particular al repositorio:

    $ bzr add <nombre + extension del archivo>

#### Enviando Cambios

Vamos en enviar los cambios que hallamos elaborado en nuestro repositorio.

    $ bzr commit

Nos aparecerá en un editor de texto el mensaje de lo hace el commit en concreto, eso debe tener en consideración los siguientes aspectos:

+ ¿A qué se debe el cambio elaborado para el cuál usaremos el commit?
+ Explicar que cosas hemos cambiado.
+ ¿Qué ocurrirá o qué efecto tendrá el cambio con el repositorio?

Ahora, en función a estas consideraciones, vamos a elaborar el contido de commit, pero esto debe responder a un formato donde se debe considerar:

+ La línea uno debe tener el resumen del commit usando formas verbales iperativas que tenga menos de 50 carácteres.
+ Luego de la primera línea, la segunda hay que dejarla en blanco.
+ Ya a partir de la tercera línea vendrá la descripción del commit, el cuál deberá responder a las consideraciones a tomar descritas anteriormente.
+ En el contenido del commit, las líneas de los parráfos no deben superar las 72 líneas.

#### Examinando el Registro

Para visualizar el historial registro de los commit realizados usaremos el siguiente comando:

    $ bzr log
    
#### Ir a un version

Para ir a una versión en especial, usar el siguiente código:

    $ bzr revert -r<número de version>
    
#### Subir al Repositorio Launchopad

Luego de seguir los pasos del tutorial de http://doc.bazaar.canonical.com/bzr.2.6/en/mini-tutorial/index.html#starting-a-new-project, para lo cuál es necesario ver el tutorial http://www.cyberciti.biz/faq/how-to-set-up-ssh-keys-on-linux-unix/ para la creación de los SSH, usar el siguiente comando para enviar los cambios al trunk:

    $  bzr push lp:~jvaldivia/msc.accesos/trunk
    
#### Funcionando Ramas

Nos colamos en la rama donde queremos hacer la función y luego indicamos el lugar donde deberá venir los funcionalidades extras. Hay que tener en cuenta que la rama a incorporar tiene que haber salido de la rama o trunk destino.
    
    $ bzr merge ../dev/estilos
    
Una vez realizado el merge, hay que hacer un commit de los cambios para incorporar la fución al destino.

    $ bzr commit


---

Fuente(s)

+ http://doc.bazaar.canonical.com/bzr.2.6/en/mini-tutorial/index.html#starting-a-new-project
+ http://www.cyberciti.biz/faq/how-to-set-up-ssh-keys-on-linux-unix/