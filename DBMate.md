## DBMate

Instalacion:

    $ curl -fsSL -o dbmate https://github.com/amacneil/dbmate/releases/download/v0.1/dbmate-linux-amd64
    $ chmod +x dbmate
    $ sudo mv dbmate /usr/local/bin
    
Comandos:

    dbmate          # print help
    dbmate new      # generate a new migration file
    dbmate up       # create the database (if it does not already exist) and run any pending migrations
    dbmate create   # create the database
    dbmate drop     # drop the database
    dbmate migrate  # run any pending migrations
    dbmate rollback # roll back the most recent migration
  
Migraciones con DBMATE:

    $ dbmate -d "db/migrations" new <<nombre_de_migracion>>
    $ dbmate -d "ubicaciones/migrations" up
    $  dbmate -d "ubicaciones/migrations" -e "DATABASE_URL2" up
    
Archivo de configuracion '.env' en la raiz del proyecto:

    DATABASE_URL="sqlite:///db/ubicaciones.db"
    DATABASE_URL2="mysql://root:123@127.0.0.1:3306/demo"

  
--

Fuentes:

+ https://dbmate.readthedocs.io/en/latest/
+ https://github.com/amacneil/dbmate