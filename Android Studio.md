# INSTALACIÓN Android Studio

#### 1) Descargar android-studio-linux.zip de fuente 1.

#### 2) Instalar los siguientes paquetes

    $ sudo apt-get install lib32z1 lib32ncurses5 lib32bz2-1.0:i386 lib32stdc++6 gradle

#### 3) Descomprimir el archivo android-studio-linux.zip y moverlo a la ruta /usr/local
 
    $ sudo mv android-studio /usr/local

#### 4) Instlar Android Studio 

/usr/local/android-studio/bin$ ./studio.sh 

#### 5) Añadir las varialbles de entrono 

    $ pluma ~/.bashrc
    
    export PATH=${PATH}:/home/pepe/Android/Sdk/tools
    export PATH=${PATH}:/home/pepe/Android/Sdk/platform-tools
    GRADLE_HOME=/opt/android-studio/gradle/gradle-3.2
    export GRADLE_HOME
    
    $ . ~/.bashrc
    $ cd $ANDROID_HOME/tools
    $ mkdir -p templates/gradle/wrapper
    $ cd templates/gradle/wrapper
    $ gradle wrapper   // this installs the needed 'stuff'


---

Fuentes:

+ http://askubuntu.com/questions/634082/how-to-install-android-studio-on-ubuntu
+ https://developer.android.com/studio/index.html?hl=es-419
+ https://developer.android.com/studio/install.html?hl=es-419
+ https://forum.ionicframework.com/t/could-not-find-gradle-wrapper-within-android-sdk-might-need-to-update-your-android-sdk/84453/12
