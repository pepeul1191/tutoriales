# TUTORIAL PADRINO

#### 1) Instalar Padrino

    $ gem install padrino

#### 2) Generar un Proyecto Padrino

    $ padrino g project my_project

Si deseamos crear un subproyecto dentro del principal, hacer lo siguiente:

    $ cd my_project
    $ padrino g app gallery

Para crear los controladores usamos lo siguiente:

    $ padrino g controller sample get:index --app gallery

#### 3) Arrancar el Proyecto

    $ padrino start

Gemas adicionales: a colocar en Gemfile

+ gem 'httparty', '~> 0.13.7'
+ gem 'json'
+ gem 'puma'

Fuentes
+ http://padrinorb.com/guides/
