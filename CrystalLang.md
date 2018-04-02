## CrystalLang

Instlación de software:

    $ sudo curl https://dist.crystal-lang.org/apt/setup.sh | sudo bash
    $ sudo apt-key adv --keyserver keys.gnupg.net --recv-keys 09617FD37CC06B54
    $ sudo echo "deb https://dist.crystal-lang.org/apt crystal main" > /etc/apt/sources.list.d/crystal.list
    $ sudo apt-get update
    $ sudo apt-get install crystal
    
Hot reload en con Sentry:

    $ curl -fsSLo- https://raw.githubusercontent.com/samueleaton/sentry/master/install.cr | crystal eval
    
Amber Framework:

    $ sudo apt-get install build-essential libreadline-dev libsqlite3-dev libpq-dev libmysqlclient-dev libssl-dev libyaml-dev
    $ curl -L https://github.com/amberframework/amber/archive/stable.tar.gz | tar xz
    $ cd amber-stable/
    $ shards install
    $ sudo make install

---

Fuentes:

+ https://crystal-lang.org/docs/installation/on_debian_and_ubuntu.html
+ https://hackernoon.com/starting-a-project-with-crystal-and-kemal-90e2647e6c3b
+ https://github.com/samueleaton/sentry
+ https://amberframework.org/guides/getting-started/quickstart/zero-to-deploy.md#zero-to-deploy