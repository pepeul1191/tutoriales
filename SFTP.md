## SFTP

Gestionar las interfaces de red:

    $ sudo apt-get update
    $ sudo apt-get install vsftpd openssh-server

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
    
Crear el grupo 'ftpaccess'

    $  sudo groupadd ftpaccess
    
Editar el archivo '/etc/ssh/sshd_config' y comentar el siguiente codigo:

    Subsystem sftp /usr/lib/openssh/sftp-server
    
Editar el archivo '/etc/ssh/sshd_config' y agregar el siguiente codigo:

    Subsystem sftp internal-sftp
    Match group ftpaccess
    ChrootDirectory %h
    X11Forwarding no
    AllowTcpForwarding no
    ForceCommand internal-sftp
    
Reiniciar el servicio:

    $ sudo service ssh restart
    
--- 

Fuentes
    
+ http://www.krizna.com/ubuntu/setup-ftp-server-on-ubuntu-14-04-vsftpd/