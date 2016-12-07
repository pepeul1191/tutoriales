# SCALA

---

#### Instalación

Instalar Scala y SBT:

    $ echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
    $ sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823
    $ sudo apt-get update
    $ sudo apt-get install scala sbt
    $ curl https://raw.githubusercontent.com/foundweekends/conscript/master/setup.sh | sh
    
Agregar lo siguiente en el PATH

    $ export CONSCRIPT_HOME="$HOME/.conscript"
    $ export CONSCRIPT_OPTS="-XX:MaxPermSize=512M -Dfile.encoding=UTF-8"
    $ export PATH=$CONSCRIPT_HOME/bin:$PATH

Refrescar el PATH

    $ . ~/.bashrc
    
Instalar conscript

    $ cs foundweekends/giter8
        
---

#### Fuente

+ http://www.scala-sbt.org/release/docs/Installing-sbt-on-Linux.html
+ http://www.foundweekends.org/giter8/setup.html