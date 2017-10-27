# Ruby Sequel

### Postgres

Ingresar al cliente mediante la terminal

	$ sudo -u postgres psql

Para salir de la consola:

	postgres=# \q

Para cambiar el la contraseña del superusuario:

	postgres=# \password
    
### Sequel Migrations

Ejecutar migración

	$ sequel -m path/to/migrations postgres://host/database
	$ sequel -m path/to/migrations sqlite://db/accesos.db

Ejecutar el 'down' de las migraciones de la última a la primera:

	$ sequel -m db/migrations -M 0 sqlite://db/accesos.db

Ejecutar el 'up' de las migraciones hasta un versión especifica:

	$ sequel -m db/migrations -M #version sqlite://db/accesos.db

Tipos de Datos de Columnas

	+ :string=>String
	+ :integer=>Integer
	+ :date=>Date
	+ :datetime=>[Time, DateTime].freeze, 
	+ :time=>Sequel::SQLTime, 
	+ :boolean=>[TrueClass, FalseClass].freeze, 
	+ :float=>Float
	+ :decimal=>BigDecimal
	+ :blob=>Sequel::SQL::Blob

### Proyecto Ruby

<b>Gemfile</b>

source 'http://rubygems.org'

```ruby
gem 'sinatra'
gem 'puma'
gem 'mysql2'
gem 'json'
gem 'rerun'
gem 'sqlite3'
gem 'sequel'
```

<b>app.rb</b>

```ruby
require_relative 'config/database'
require 'json'

Dir[File.dirname(__FILE__) + "/models/*.rb"].each do |file| 
  	require file
end

DB[:estado_usuarios].select(:id, :nombre).all.to_a.to_json
puts EstadoUsuario.all.to_a.to_json
for u in EstadoUsuario.all
	puts u.nombre
end
```

<b>config/database.rb</b>

```ruby
require 'sequel'

Sequel::Model.plugin :json_serializer

DB = Sequel.connect('sqlite://db/accesos.db')
DB_BASE = Sequel.connect('sqlite://db/base.db')
```

<b>db/migrations/001_create_usuarios.rb</b>

```ruby
Sequel.migration do
  	up do
	    create_table(:usuarios) do
		      primary_key :id
		      String :usuario, null: false, size: 15
		      String :contrasenia, null: false, size: 30
		      String :correo, null: false, size: 30
	    end
  	end

	down do
		drop_table(:usuarios)
	end
end
```

<b>db/migrations/002_create_estdo_usuarios.rb</b>

```ruby
Sequel.migration do
  	up do
	    create_table(:estado_usuarios) do
		      primary_key :id
		      String :nombre, null: false, size: 30
	    end
  	end

	down do
		drop_table(:estado_usuarios)
	end
end
```

<b>db/migrations/003_relation_usuarios_estado_usuarios.rb</b>

```ruby
Sequel.migration do
  	up do
	    alter_table(:usuarios) do
			#add_column :estado_usuario_id, Integer 
		   add_foreign_key :estado_usuario_id, :estado_usuarios
	    end
	    #create_join_table(estado_usuario_id: :usuarios, id: :estado_usuarios)
  	end

	down do
		drop_column :usuarios, :estado_usuario_id
		#drop_join_table(estado_usuario_id: :usuarios, id: :estado_usuarios)
	end
end
```

<b>db/migrations/004_fill_estado_usuarios.rb</b>

```ruby
Sequel.migration do
  	up do
		DB.transaction do
	  		file = File.new('db/data/estado_usuarios.txt', 'r')

			while (line = file.gets)
				line_array = line.split('::')

				id = line_array[0]
				nombre = line_array[1].strip
				#puts id + " - " + nombre
				DB[:estado_usuarios].insert(id: id, nombre: nombre)
			end
		end
  	end

	down do
		DB[:estado_usuarios].delete
	end
end

```

<b>models/usuario.rb</b>

```ruby

class Usuario < Sequel::Model(DB_BASE)
  	:usuarios
end
```

<b>models/estado_usuario.rb</b>

```ruby
class EstadoUsuario < Sequel::Model(DB)
  	:estado_usuarios
end
```

---

### Fuentes:

+ https://snippets.aktagon.com/snippets/257-how-to-use-activerecord-without-rails
+ https://github.com/jeremyevans/sequel/blob/master/doc/schema_modification.rdoc
+ http://sequel.jeremyevans.net/rdoc/files/doc/migration_rdoc.html
+ http://www.rubydoc.info/gems/sequel/4.38.0/Sequel%2FDatabase%3Aschema
+ http://sequel.jeremyevans.net/rdoc/classes/Sequel/Database.html
+ http://sequel.jeremyevans.net/rdoc/classes/Sequel/Model/ClassMethods.html
+ https://www.digitalocean.com/community/tutorials/como-instalar-y-utilizar-postgresql-en-ubuntu-16-04-es
+ https://www.liquidweb.com/kb/change-a-password-for-postgresql-on-linux-via-command-line/
