## FTP

Gestionar las interfaces de red:

    $ sudo apt-get update
    $ sudo apt-get install vsftpd

Editar el archivo '/etc/vsftpd.conf' y descomentar el siguiente codigo:

    write_enable=YES
    local_umask=022 
    chroot_local_user=YES 
    
Editar el archivo '/etc/vsftpd.conf' y agregar el siguiente codigo:

    allow_writeable_chroot=YES
   
    pasv_enable=Yes
    pasv_min_port=40000
    pasv_max_port=40100
    
Reiniciar el servicio:

    $ sudo service vsftpd restart
    
--- 

Fuentes
    
+ http://www.krizna.com/ubuntu/setup-ftp-server-on-ubuntu-14-04-vsftpd/