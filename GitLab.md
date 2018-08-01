# GitLab

#### Instalacion en Ubuntu 16.04

Instalar GitLab:

    $ sudo apt-get install ca-certificates curl openssh-server postfix
    $ cd /tmp
    $ curl -LO https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh
    $ sudo bash /tmp/script.deb.sh
    $ sudo apt-get install gitlab-ce
    
Configurar la reglas del firewall:

    $ sudo ufw allow http
    $ sudo ufw allow https
    $ sudo ufw allow OpenSSH


Quitar el sign-up en el login:

    Gitlab > Admin area > settings > Features > remove the check mark “Signup enabled”
    
 

---

Fuentes:

+ https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-gitlab-on-ubuntu-16-04
+ https://forum.gitlab.com/t/disable-user-creation-on-welcome-page/806