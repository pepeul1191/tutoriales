# Yeoman Scaffoling

Común para Angular y Backbone


    $ sudo npm install -g  grunt
    $ sudo npm install -g  grunt-cli
    $ sudo npm install -g  yo
    
AngularJS Generator

    $ npm install -g generator-angular

Backbone Generator

    $ npm install -g generator-backbone

Solución de bug de Backbone Generator

    $  sudo chmod -R 777 /usr/lib/node_modules/generator-backbone/

Solución de bug de Grunt Server

    $ echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p
     
---
Fuentes:
+ https://github.com/yeoman/generator-backbone
+ https://github.com/yeoman/generator-angular
+ https://github.com/yeoman/yeoman/issues/1097