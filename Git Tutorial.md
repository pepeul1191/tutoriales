# Tutorial Git

#### Cofinguracion Inicial

Definir de manera global al sistema un usuario y correo.

    $ git config --global user.name "Nombre Apellido"
    $ git config --global user.email "<tucorreo@correo.pe>"
    
Definir el editor de texto por default con el que se editarán los commit

    $ git config --global core.editor "nano"

#### Crear un Repositorio en Git

Hay que inicializar el repositirio en la máquina dentro de un directorio.

    $ git init

Otra alternativa es clonando un repositorio indicando el lugar donde este repositorio se encuentre.

    $ git clone {ruta del repositorio}

#### El Staging Index

Es una área temporal donde se va almacenar los cambio que tenemos de manera local antes de enviarlo en un commit, esto responderá a los archivos que indiquemos que se hayan agreado primero.

    $ git add {archivo}
    
Si queremos añadir todos los cambios sería usando una variante del código anterior:

    $ git add .

Si queremos ver el estado de los archivos previos al commit:

    $ git status

#### Enviando Cambios

Vamos en enviar los cambios que hallamos elaborado en nuestro repositorio.

    $ git commit

Nos aparecerá en un editor de texto el mensaje de lo hace el commit en concreto, eso debe tener en consideración los siguientes aspectos:

+ ¿A qué se debe el cambio elaborado para el cuál usaremos el commit?
+ Explicar que cosas hemos cambiado.
+ ¿Qué ocurrirá o qué efecto tendrá el cambio con el repositorio?

Ahora, en función a estas consideraciones, vamos a elaborar el contido de commit, pero esto debe responder a un formato donde se debe considerar:

+ La línea uno debe tener el resumen del commit usando formas verbales iperativas que tenga menos de 50 carácteres.
+ Luego de la primera línea, la segunda hay que dejarla en blanco.
+ Ya a partir de la tercera línea vendrá la descripción del commit, el cuál deberá responder a las consideraciones a tomar descritas anteriormente.
+ En el contenido del commit, las líneas de los parráfos no deben superar las 72 líneas.

#### Quitar Archivos del Repositorio

Si deseamos quitar un archivo de nuestro repositorio para el siguiente commit, usaremos el siguiente comando:

    $ git rm {nombre del archivo}
    
Para verificar es estado de los archivos a eliminar en el siguiente commit, usamos el siguiente comando:

    $ git status

Para en enviar el commit usaremos el siguiente comando, no olvidando ingresar el mensaje correspondiente al commit.

    $ git commit

Si desea quitar todos los archivos añadidos mediante add, sería el siguiente comando:

    $ git reset

#### Moviendo Archivos

Para esta operación podemos usar el explorador de archivos del sistema operativo o el siguiente comando linux:

    $ mv {nombre del archivo} {nueva ruta del archivo y el nombre del archivo}

Ahora debemos indicar a git que hemos movido el archivo del repositorio, esto será diciendo a git que hemos quitado un archivo y luego que lo hemos agregado a nueva ruta:

    $ git rm {nombre del archivo}
    $ git add {nueva ruta del archivo y el nombre del archivo}

Para verificar es estado de los archivos que hemos cambiado de directorio en el siguiente commit, usamos el siguiente comando:

    $ git status

Para en enviar el commit usaremos el siguiente comando, no olvidando isngresar el mensaje correspondiente al commit.

    $ git commit

#### Deshaciendo Cambios

Si queremos descartar algún cambio elaborado para ser enviado en el siguente commit, primero debemos ver el estado de los commit y ver el archivo que deseamos quitar usando el siguiente comando.

    $ git status

Visulizaremos el estado de los archivos a ser enviados y deberemos identificar el archivo que debemos quitar y escribir el siguiente comando:

    $ git reset HEAD {nombre del archivo a quitar del próximo commit}

Pero en caso que deseemos revertir todos los cambios elaborados al estado inicial de ese archivo, usamos el siguiente comando.

    $ git checkout -- {nombre del archivo}

#### Examinando el Registro

Para visualizar el historial registro de los commit realizados usaremos el siguiente comando:

    $ git log

Pero si deseamos ver menos información de los commit (resumen), usamos el siguiente commit:

    $ git long --oneline

#### Creando Ramas

Para crear una nueva rama de la rama principal (master) usamos el siguiente comando:

    $ git branch {nombre del branch}

Para verificar la rama principal y las que hemos creado usamos el siguiente comando:

    $ git branch

Para cambiar el uso de la rama principal a una rama creada usamos el siguiente comando:

    $ git checkout {nombre de la rama}

Para borrar un rama usamos el siguiente comando:

    $ git branch -d {nombre de la rama}

#### Añadir Remote

Ver o verificar si tenemos enlazado nuestro repositorio a un repositorio remoto:

    $ git remote -v
    
Si no tenemos un destino enlazado, podemos asociar uno usando el siguiente comando: 

    $ git remote add origin {url de repositorio git}
    
Si el repositorio ya cuenta con un destino enlazado, podemos cambiar el destino:

    $ git remote set-url origin {nueva url}
    
#### Otros comandos

Crear repositorio

	$ git init

Crear branch

    $ git checkout -b feature1

Eliminar branch

    $ git branch -d feature1

Listar branchs

	$ git branch

Usar branch

    $ git checkout feature1|master

Crear tag

	$ git tag -a v1.4 -m "my version 1.4"
	$ git push origin v1.0

Mezclar

	// ir a master
	$ git merge branch

Ver cambios

	$ git diff {opcional el nombre del archivo}

Ir a version

	git reset --hard {123123}

---

#### Fuentes : 
 
+ Título : Tutorial de Git en media hora <br>
    Autor (Youtube) : makigas <br>
    Enlace : https://www.youtube.com/watch?v=QGKTdL7GG24 

+ https://stackoverflow.com/questions/2432764/change-the-uri-url-for-a-remote-git-repository
