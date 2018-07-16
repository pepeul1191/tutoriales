 # NODE JS
  ---

1) Agregar repositorio <br>

        $ curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -

2) Instalar NodeJs <br>
    
        $ sudo apt-get install -y nodejs
    
3) (Opcional) Instalar build-essential<br>

        $ sudo apt-get install -y build-essential
    
4) Instalación con NVM

        $ sudo apt-get install build-essential libssl-dev curl
        $ curl -sL https://raw.githubusercontent.com/creationix/nvm/v0.31.0/install.sh -o install_nvm.sh
        $ bash install_nvm.sh
        $ source ~/.profile
        $ nvm install 5.1.1
        $ nvm use 5.1.1
    
5) Instalación de bower

        $ npm install -g bower

 ## Fuentes
 ---

 + https://nodejs.org/en/download/package-manager/
 + https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-16-04
