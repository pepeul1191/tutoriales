# Instalación de RUBY

---

#### Instalación de Ruby

    $ sudo apt-get update
    $ sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev libmysqlclient-dev

#### Instalación de Ruby Virtual Enviroment

    $ cd 
    $ git clone git://github.com/sstephenson/rbenv.git .rbenv 
    $ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc 
    $ echo 'eval "$(rbenv init -)"' >> ~/.bashrc 
    $ exec $SHELL
 
    $ git clone git://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build 
    $ echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc 
    $ exec $SHELL 

    $ git clone https://github.com/sstephenson/rbenv-gem-rehash.git ~/.rbenv/plugins/rbenv-gem-rehash 

#### Instalación de una Versión Específica de Ruby Usnado Ruby Virtual Enviroment

    $ rbenv install 2.2.3 
    $ rbenv global 2.2.3 
    $ ruby -v 

Now we tell Rubygems not to install the documentation for each package locally and then install Bundler <br>

    $ echo "gem: --no-ri --no-rdoc" > ~/.gemrc 
    $ sudo gem install bundler 

#### Pendientes

Servidor Puma -> http://puma.io/ <br>
Rails con Puma -> https://www.digitalocean.com/community/tutorials/how-to-deploy-a-rails-app-with-puma-and-nginx-on-ubuntu-14-04 <br>

#### Fuentes

+ https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-14-04
+ https://gorails.com/setup/ubuntu/13.10 - Instlación
+ http://stackoverflow.com/questions/3608287/error-installing-mysql2-failed-to-build-gem-native-extension