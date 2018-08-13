## Rust  

Instalación de Rust y Cargo

    $ curl -sSf https://static.rust-lang.org/rustup.sh | sh

Nuevo proyecto Rust con Cargo:

    $ cargo new <nombre-proyecto> --bin

Correr aplicación Rust usando Cargo

    $ cargo run
    
### Diesel ORM:

Instalacion

    $ cargo install diesel_cli
    
Agregar 'export PATH=$PATH:/home/pepe/.cargo/bin ' al final del siguiente archivo:

    nano ~/.profile

Refrescar variables:

    $ . ~/.profile

---

Fuentes:

+ http://nickel-org.github.io/getting-started.html
+ http://diesel.rs/guides/getting-started/
+ https://github.com/diesel-rs/diesel/tree/master/examples