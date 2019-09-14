# Postgres

### Añadir usuario

    $ sudo adduser pguser
    
Contraseña por defecto recomendada 'pguser123'.

### Crear acceso a usuario

Cambiar a usuario postgres y entrar a postgres:

    $ sudo -u postgres psql

Crear nuevo rol:

    $ sudo -u postgres createuser --interactive
    
    Enter name of role to add: pguser
    Shall the new role be a superuser? (y/n) y

Crear base de datos al nuevo usuario:

    $ sudo -u postgres psql
    postgres=# create database pguser;
    postgres=# create user pguser with encrypted password 'pguser123';
    postgres=# grant all privileges on database pguser to pguser;
    
Acceder a la base de datos con el nuevo usuario:

    $ sudo -u pguser psql

Cambiar contraseña de usuario:

    $ sudo -u postgres psql
    postgres=# ALTER USER pguser WITH PASSWORD 'pguser123';


### Creando usuario, base de datos y acceso con SQL:

    $ sudo -u postgres psql
    postgres=# CREATE DATABASE yourdbname;
    postgres=# CREATE USER youruser WITH ENCRYPTED PASSWORD 'yourpass';
    postgres=# GRANT ALL PRIVILEGES ON DATABASE yourdbname TO youruser;
    

### SQLs

Create table:

```sql
CREATE TABLE carrers (
  id SERIAL PRIMARY KEY,
  name VARCHAR(25) NOT NULL
);


CREATE TABLE teachers (
  id SERIAL PRIMARY KEY,
  names	VARCHAR(40) NOT NULL,
  last_names VARCHAR(40) NOT NULL,
  img	TEXT NOT NULL
);

CREATE TABLE teachers_carrers (
  id SERIAL PRIMARY KEY,
  teacher_id INTEGER REFERENCES teachers(id),
  carrer_id INTEGER REFERENCES carrers(id)
);
```

---

Fuentes:

+ https://www.cyberciti.biz/faq/create-a-user-account-on-ubuntu-linux/
+ https://www.digitalocean.com/community/tutorials/como-instalar-y-utilizar-postgresql-en-ubuntu-16-04-es
+ https://stackoverflow.com/questions/12720967/how-to-change-postgresql-user-password
+ http://www.postgresqltutorial.com/postgresql-foreign-key/
