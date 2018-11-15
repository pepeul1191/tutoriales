## Yarn

Instlación:

    $ curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
    $ echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
    $ sudo apt-get update && sudo apt-get install yarn
    
Ver la versión instlada:

    $ yarn --version
    
Operaciones:
    
    $ yarn add [package]
    $ yarn add [package]@[version]
    $ yarn add [package]@[tag]
    $ yarn install

---

Fuentes:

+ https://yarnpkg.com/en/docs/install#debian-stable
+ https://yarnpkg.com/en/docs/usage