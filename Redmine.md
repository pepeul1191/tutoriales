# Redmine

Redmine is a flexible project management web application written using Ruby on Rails framework.

More details can be found in the doc directory or on the official website http://www.redmine.org

## Requisitos

Instalar ruby > 2.5

## Instalación

1. Descargar Redmine con git:

    $ git clone https://github.com/redmine/redmine.git

2. Crear en MySQL la base de datos 'redmine'.

3. Modificar config/database.yml con la información de la conexión la base de datos.

4. Correr la migración para crear las tablas:

    $ bundle exec rake db:migrate RAILS_ENV=production

5. Crear el archivo config/secrets.yml.

6. Ejecutar el comando para generar el secret:

    $ bundle exec rake secret

7. Copiar el codigo en el archivo 'config/secrets.yml'


```
development:
  secret_key_base:

test:
  secret_key_base:

production:
  secret_key_base: <secret de 6>

```

8. Ejecutar aplicación:

    $ rerun "ruby bin/rails server -e production"

9. Entrar en 'http://localhost:3000', y establecer nueva contraseña (por defecto es admin admin)

## Puma

Crear el archivo 'config/puma.rb'


```
development:
  secret_key_base:

test:
  secret_key_base:

production:
  secret_key_base: <secret de 6>

```

## Backup

+ Base de Datos:

    $ mysqldump -u root -p redmine > db/redmine.sql
    $ mysql -u root -p redmine < db/redmine.sql


+ Archivos:

Está en el contenido de la carpeta files.
