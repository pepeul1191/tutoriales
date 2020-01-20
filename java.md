# Instalar Java en Ubuntu 18.04

## Instalar Java OpenJDK

    $ sudo su
    $ mkdir /opt/jdk
    $ wget https://github.com/AdoptOpenJDK/openjdk8-binaries/releases/download/jdk8u232-b09/OpenJDK8U-jdk_x64_linux_hotspot_8u232b09.tar.gz
    $ tar -zxf OpenJDK8U-jdk_x64_linux_hotspot_8u232b09.tar.gz -C /opt/jdk
    $ ls /opt/jdk
    $ update-alternatives --install /usr/bin/java java /opt/jdk/jdk8u232-b09/bin/java 100
    $ update-alternatives --install /usr/bin/javac javac /opt/jdk/jdk8u232-b09/bin/javac 100
    $ export JAVA_HOME=/opt/jdk/jdk8u232-b09
    $ export PATH=$PATH:$JAVA_HOME/bin

En Atom los plugins a instalar son:

    + ide-java
    + linter-processing-java

## Instalar Maven

En una nueva terminal:

    $ cd /opt/
    $ wget http://www-eu.apache.org/dist/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz
    $ sudo tar -xvzf apache-maven-3.3.9-bin.tar.gz
    $ sudo mv apache-maven-3.3.9 maven

    ```
    export M2_HOME=/opt/maven
    export PATH=${M2_HOME}/bin:${PATH}
    ```

    $ sudo chmod +x /etc/profile.d/mavenenv.sh
    $ sudo source /etc/profile.d/mavenenv.sh

---

Fuentes:

+ https://www.vultr.com/docs/how-to-install-apache-maven-on-ubuntu-16-04
+ https://www.digitalocean.com/community/tutorials/how-to-manually-install-oracle-java-on-a-debian-or-ubuntu-vps
+ https://vitux.com/how-to-setup-java_home-path-in-ubuntu/
